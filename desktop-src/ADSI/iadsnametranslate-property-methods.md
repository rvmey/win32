---
title: IADsNameTranslate Property Methods
description: Sets the ChaseReferral property.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 7c44fe9b-16a5-4bd5-a80b-8f3dcfec20cc
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
keywords:
- IADsNameTranslate Property Methods ADSI
topic_type:
- apiref
api_name:
- IADsNameTranslate Property Methods
- IADsNameTranslate.ChaseReferral
- IADsNameTranslate.put_ChaseReferral
api_location:
- Activeds.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# IADsNameTranslate Property Methods

The property method of the [**IADsNameTranslate**](/windows/win32/Iads/nn-iads-iadsnametranslate?branch=master) interface sets the **ChaseReferral** property. For more information, see [Interface Property Methods](interface-property-methods.md).

## Properties

<dl> <dt>

**ChaseReferral**
</dt> <dd> <dl>

Options of referral chasing as defined in [**ADS\_CHASE\_REFERRALS\_ENUM**](/windows/win32/Iads/ne-iads-__midl___midl_itf_ads_0000_0000_0024?branch=master). When referral chasing is set, the name translation is performed on objects that do not belong to this directory and are the referrals returned from referral chasing.

<dt>

Access type: Write-only
</dt> <dt>

Scripting data type: **LONG**
</dt> <dt>



``` syntax
// C++ method syntax
HRESULT put_ChaseReferral(
  [in] LONG lnChaseReferral
);
```


</dt> </dl> </dd> </dl>

 

## Remarks

The referral chasing options apply only when you use [**IADsNameTranslate::Set**](/windows/win32/Iads/nf-iads-iadsnametranslate-set?branch=master) and [**IADsNameTranslate::Get**](/windows/win32/Iads/nf-iads-iadsnametranslate-get?branch=master). The feature is not available with [**IADsNameTranslate::SetEx**](/windows/win32/Iads/nf-iads-iadsnametranslate-setex?branch=master) or [**IADsNameTranslate::GetEx**](/windows/win32/Iads/nf-iads-iadsnametranslate-getex?branch=master).

The [**IADsNameTranslate**](/windows/win32/Iads/nn-iads-iadsnametranslate?branch=master) interface has a partial implementation of [**ADS\_CHASE\_REFERRALS\_ENUM**](/windows/win32/Iads/ne-iads-__midl___midl_itf_ads_0000_0000_0024?branch=master) through the **ChaseReferral** property. If the **ChaseReferral** property is set to zero (0), it is the same as specifying **ADS\_CHASE\_REFERRALS\_NEVER** (0). If a nonzero value is used, it is the same as specifying **ADS\_CHASE\_REFERRALS\_ALWAYS** (0x60). **IADsNameTranslate** does not implement the **ADS\_CHASE\_REFERRALS\_SUBORDINATE** (0x20) or **ADS\_CHASE\_REFERRALS\_EXTERNAL** (0x40) options.

The default setting for referral chasing is enabled (**ADS\_CHASE\_REFERRALS\_ALWAYS**). Without referral chasing, you can have name translation performed on those objects residing on the connected directory server only. If you are uncertain whether the object of interest is on the specified server, you should set this property to be **ADS\_CHASE\_REFERRALS\_ALWAYS**.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Header<br/>                   | <dl> <dt>Iads.h</dt> </dl>       |
| DLL<br/>                      | <dl> <dt>Activeds.dll</dt> </dl> |
| IID<br/>                      | IID\_IADsNameTranslate is defined as B1B272A3-3625-11D1-A3A4-00C04FB950DC<br/>    |



## See also

<dl> <dt>

[**ADS\_CHASE\_REFERRALS\_ENUM**](/windows/win32/Iads/ne-iads-__midl___midl_itf_ads_0000_0000_0024?branch=master)
</dt> <dt>

[**IADsNameTranslate**](/windows/win32/Iads/nn-iads-iadsnametranslate?branch=master)
</dt> <dt>

[**IADsNameTranslate::Get**](/windows/win32/Iads/nf-iads-iadsnametranslate-get?branch=master)
</dt> <dt>

[**IADsNameTranslate::GetEx**](/windows/win32/Iads/nf-iads-iadsnametranslate-getex?branch=master)
</dt> <dt>

[**IADsNameTranslate::Set**](/windows/win32/Iads/nf-iads-iadsnametranslate-set?branch=master)
</dt> <dt>

[**IADsNameTranslate::SetEx**](/windows/win32/Iads/nf-iads-iadsnametranslate-setex?branch=master)
</dt> <dt>

[Interface Property Methods](interface-property-methods.md)
</dt> </dl>

 

 




