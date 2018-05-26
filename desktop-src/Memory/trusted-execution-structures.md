---
Description: The following structures are used when working with enclaves that are used to create trusted execution environments
ms.assetid: 61F99132-E947-4EA4-86A0-914CE316B53A
title: Trusted Execution Structures
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Trusted Execution Structures

The following structures are used when working with enclaves that are used to create trusted execution environments:

## In this section



| Topic                                                                                         | Description                                                                                                                                                                                                                             |
|-----------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**ENCLAVE\_CREATE\_INFO\_SGX**](/windows/win32/winnt/ns-winnt-_enclave_create_info_sgx?branch=master)<br/>                      | Contains architecture-specific information to use to create an enclave when the enclave type is **ENCLAVE\_TYPE\_SGX**, which specifies an enclave for the Intel Software Guard Extensions (SGX) architecture extension.<br/>     |
| [**ENCLAVE\_CREATE\_INFO\_VBS**](/windows/win32/winnt/ns-winnt-_enclave_create_info_vbs?branch=master)<br/>                      | Contains architecture-specific information to use to create an enclave when the enclave type is **ENCLAVE\_TYPE\_VBS**, which specifies a virtualization-based security (VBS) enclave.<br/>                                       |
| [**ENCLAVE\_IDENTITY**](/windows/win32/ntenclv/ns-ntenclv-enclave_identity?branch=master)<br/>                                      | Describes the identity of the primary module of an enclave. <br/>                                                                                                                                                                 |
| [**ENCLAVE\_INFORMATION**](/windows/win32/ntenclv/ns-ntenclv-enclave_information?branch=master)<br/>                                | Contains information about the currently executing enclave.<br/>                                                                                                                                                                  |
| [**ENCLAVE\_INIT\_INFO\_SGX**](/windows/win32/winnt/ns-winnt-_enclave_init_info_sgx?branch=master)<br/>                          | Contains architecture-specific information to use to initialize an enclave when the enclave type is **ENCLAVE\_TYPE\_SGX**, which specifies an enclave for the Intel Software Guard Extensions (SGX) architecture extension.<br/> |
| [**ENCLAVE\_INIT\_INFO\_VBS**](/windows/win32/winnt/ns-winnt-_enclave_init_info_vbs?branch=master)<br/>                          | Contains architecture-specific information to use to initialize an enclave when the enclave type is **ENCLAVE\_TYPE\_VBS**, which specifies a virtualization-based security (VBS) enclave.<br/>                                   |
| [**IMAGE\_ENCLAVE\_CONFIG32**](/windows/win32/winnt/ns-winnt-_image_enclave_config32?branch=master)<br/>                         | Defines the format of the enclave configuration for systems running 32-bit Windows.<br/>                                                                                                                                          |
| [**IMAGE\_ENCLAVE\_CONFIG64**](/windows/win32/winnt/?branch=master)<br/>                         | Defines the format of the enclave configuration for systems running 64-bit Windows.<br/>                                                                                                                                          |
| [**IMAGE\_ENCLAVE\_IMPORT**](/windows/win32/winnt/ns-winnt-_image_enclave_import?branch=master)<br/>                             | Defines a entry in the array of images that an enclave can import.<br/>                                                                                                                                                           |
| [**VBS\_ENCLAVE\_REPORT**](/windows/win32/ntenclv/ns-ntenclv-vbs_enclave_report?branch=master)<br/>                                 | Describes the format of the signed statement contained in a report generated by calling the [**EnclaveGetAttestationReport**](/windows/win32/winenclaveapi/nf-winenclaveapi-enclavegetattestationreport?branch=master) function.<br/>                                                     |
| [**VBS\_ENCLAVE\_REPORT\_MODULE**](/windows/win32/ntenclv/ns-ntenclv-vbs_enclave_report_module?branch=master)<br/>                  | Describes a module loaded for the enclave.<br/>                                                                                                                                                                                   |
| [**VBS\_ENCLAVE\_REPORT\_PKG\_HEADER**](/windows/win32/ntenclv/ns-ntenclv-vbs_enclave_report_pkg_header?branch=master)<br/>         | Describes the contents of a report generated by calling the [**EnclaveGetAttestationReport**](/windows/win32/winenclaveapi/nf-winenclaveapi-enclavegetattestationreport?branch=master) function.<br/>                                                                                     |
| [**VBS\_ENCLAVE\_REPORT\_VARDATA\_HEADER**](/windows/win32/ntenclv/ns-ntenclv-vbs_enclave_report_vardata_header?branch=master)<br/> | Describes the format of a variable data block contained in a report that the [**EnclaveGetAttestationReport**](/windows/win32/winenclaveapi/nf-winenclaveapi-enclavegetattestationreport?branch=master) function generates.<br/>                                                          |



 

 

 



