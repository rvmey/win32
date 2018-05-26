---
Description: Creates a CMC request object from an inner nested PKCS \#10 request.
ms.assetid: 8a0dc078-22ca-4bff-9cc0-46823912d3da
title: createCNGCustomCMC
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# createCNGCustomCMC

The createCNGCustomCMC sample creates a CMC request object from an inner nested PKCS \#10 request. The inner request is created by using an asymmetric [*private key*](https://msdn.microsoft.com/library/windows/desktop/ms721603#-security-private-key-gly). The private key is created by using the Cryptography API: Next Generation (CNG) cryptographic provider and the algorithm specified on the command line. Custom options such as export policy and key protection level are also set on the private key.

## Location

When you install the Microsoft Windows Software Development Kit (SDK), the sample is installed, by default, in the *%ProgramFiles%*\\Microsoft SDKs\\Windows\\v7.0\\Samples\\Security\\X509 Certificate Enrollment\\VC\\createCNGCustomCMC folder.

## Discussion

The createCNGCustomCMC sample:

1.  Processes the following command line arguments:
    -   The name of a CNG [*cryptographic service provider*](https://msdn.microsoft.com/library/windows/desktop/ms721572#-security-cryptographic-service-provider-gly) (CSP).
    -   The name of the algorithm used to generate an asymmetric private key.
    -   The name of the algorithm used to [*hash*](https://msdn.microsoft.com/library/windows/desktop/ms721586#-security-hash-gly) the [*certificate request*](https://msdn.microsoft.com/library/windows/desktop/ms721572#-security-certificate-request-gly).
    -   An output file in which to save the certificate request.
    -   An optional string (AlternateSignature) which, if present, specifies that a discrete rather than a combined signature algorithm be used. For more information, see the [**AlternateSignatureAlgorithm**](/windows/win32/CertEnroll/nf-certenroll-ix509certificaterequest-get_alternatesignaturealgorithm?branch=master) property.
2.  Creates an [**IX509PrivateKey**](/windows/win32/CertEnroll/nn-certenroll-ix509privatekey?branch=master) object and sets the following properties:
    -   [**LegacyCsp**](/windows/win32/CertEnroll/nf-certenroll-ix509privatekey-get_legacycsp?branch=master)
    -   [**ProviderName**](/windows/win32/CertEnroll/nf-certenroll-ix509privatekey-get_providername?branch=master)
    -   [**Algorithm**](/windows/win32/CertEnroll/nf-certenroll-ix509privatekey-get_algorithm?branch=master)
    -   [**KeyProtection**](/windows/win32/CertEnroll/nf-certenroll-ix509privatekey-get_keyprotection?branch=master)
    -   [**ExportPolicy**](/windows/win32/CertEnroll/nf-certenroll-ix509privatekey-get_exportpolicy?branch=master)
3.  Creates an asymmetric private key.
4.  Creates an [**IX509CertificateRequestPkcs10**](/windows/win32/CertEnroll/nn-certenroll-ix509certificaterequestpkcs10?branch=master) object and initializes it by using the private key.
5.  Creates an [**IX509CertificateRequestCmc**](/windows/win32/CertEnroll/nn-certenroll-ix509certificaterequestcmc?branch=master) object and initializes it by using the PKCS \#10 request object created in step 4.
6.  Sets the alternate signature algorithm flag to **VARIANT\_TRUE** or **VARIANT\_FALSE** depending on whether an alternate signature string is specified on the command line. For more information, see [**AlternateSignatureAlgorithm**](/windows/win32/CertEnroll/nf-certenroll-ix509certificaterequest-get_alternatesignaturealgorithm?branch=master).
7.  Creates a [*hashing algorithm*](https://msdn.microsoft.com/library/windows/desktop/ms721586#-security-hashing-algorithm-gly) [*object identifier*](https://msdn.microsoft.com/library/windows/desktop/ms721599#-security-object-identifier-gly) (OID) from the algorithm name specified on the command line and sets the OID on the CMC request object.
8.  Signs the certificate request and encodes it by using [*Distinguished Encoding Rules*](https://msdn.microsoft.com/library/windows/desktop/ms721573#-security-distinguished-encoding-rules-gly) (DER).
9.  Retrieves a string that contains the encoded CMC certificate request and saves it to a file. The EncodeToFileW function is defined in EnrollCommon.cpp.

## Related topics

<dl> <dt>

[CMC Request](cmc-request.md)
</dt> <dt>

[PKCS \#10 Request](pkcs--10-request.md)
</dt> <dt>

[Using the Included Samples](using-the-included-samples.md)
</dt> <dt>

[**IX509PrivateKey**](/windows/win32/CertEnroll/nn-certenroll-ix509privatekey?branch=master)
</dt> </dl>

 

 


