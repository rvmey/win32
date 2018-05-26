---
Description: Applications determine whether to grant access to securable objects by calling the AuthzAccessCheck function.
ms.assetid: dad0a102-08ed-4cd2-bef5-87bc48fc7fc2
title: Checking Access with Authz API
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Checking Access with Authz API

Applications determine whether to grant access to securable objects by calling the [**AuthzAccessCheck**](/windows/win32/Authz/nf-authz-authzaccesscheck?branch=master) function.

The [**AuthzAccessCheck**](/windows/win32/Authz/nf-authz-authzaccesscheck?branch=master) function takes both [**AUTHZ\_ACCESS\_REQUEST**](/windows/win32/Authz/ns-authz-_authz_access_request?branch=master) and [**SECURITY\_DESCRIPTOR**](/windows/win32/Winnt/ns-winnt-_security_descriptor?branch=master) structures as parameters. The **AUTHZ\_ACCESS\_REQUEST** structure specifies a level of access requested. The **AuthzAccessCheck** function evaluates the requested access against the specified **SECURITY\_DESCRIPTOR** for a specified client context. For information about how a security descriptor controls access to an object, see [How DACLs Control Access to an Object](how-dacls-control-access-to-an-object.md).

Attribute variables must be in the form of an expression when used with logical operators; otherwise, they are evaluated as unknown.

## Callback Function

If the [*discretionary access control list*](https://msdn.microsoft.com/library/windows/desktop/ms721573#-security-discretionary-access-control-list-gly) (DACL) of the [**SECURITY\_DESCRIPTOR**](/windows/win32/Winnt/ns-winnt-_security_descriptor?branch=master) of the object to be checked contains any callback [*access control entries*](https://msdn.microsoft.com/library/windows/desktop/ms721532#-security-access-control-entry-gly) (ACEs), [**AuthzAccessCheck**](/windows/win32/Authz/nf-authz-authzaccesscheck?branch=master) calls the [**AuthzAccessCheckCallback**](authzaccesscheckcallback.md) function for each callback ACE contained in the DACL. A callback ACE is any ACE structure whose ACE type contains the word "callback." The **AuthzAccessCheckCallback** function is an application-defined function that must be registered when the resource manager is initialized by calling the [**AuthzInitializeResourceManager**](/windows/win32/Authz/nf-authz-authzinitializeresourcemanager?branch=master) function.

A callback function allows an application to define business logic to be evaluated at runtime. When the [**AuthzAccessCheckCallback**](authzaccesscheckcallback.md) function is called, the callback ACE that caused the call is passed to the callback function for evaluation. If the application-defined logic evaluates as **TRUE**, then the callback ACE is included in the access check. Otherwise, it is ignored.

## Caching Access Results

The results of an access check can be cached and used in future calls to the [**AuthzCachedAccessCheck**](/windows/win32/Authz/nf-authz-authzcachedaccesscheck?branch=master) function. For more information about caching access checks, including an example, see [Caching Access Checks](caching-access-checks.md).

## Example

The following example creates a [**SECURITY\_DESCRIPTOR**](/windows/win32/Winnt/ns-winnt-_security_descriptor?branch=master) that allows **READ\_CONTROL** access to built-in administrators. It uses that security descriptor to check access for the client specified by the client context created in the example in [Initializing a Client Context](initializing-a-client-context.md).


```C++
BOOL CheckAccess(AUTHZ_CLIENT_CONTEXT_HANDLE hClientContext)
{
    #define MY_MAX 4096


    PSECURITY_DESCRIPTOR    pSecurityDescriptor = NULL;
    ULONG                    cbSecurityDescriptorSize = 0;
    AUTHZ_ACCESS_REQUEST    Request;
    CHAR                    ReplyBuffer[MY_MAX];
    PAUTHZ_ACCESS_REPLY        pReply = (PAUTHZ_ACCESS_REPLY)ReplyBuffer;
    DWORD                    AuthzError =0;

    //Allocate memory for the access request structure.
    RtlZeroMemory(&amp;Request, sizeof(AUTHZ_ACCESS_REQUEST));

    //Set up the access request structure.
    Request.DesiredAccess = READ_CONTROL;
    
    //Allocate memory for the access reply structure.
    RtlZeroMemory(ReplyBuffer, MY_MAX);

    //Set up the access reply structure.
    pReply->ResultListLength = 1;
    pReply->Error = (PDWORD) ((PCHAR) pReply + sizeof(AUTHZ_ACCESS_REPLY));
    pReply->GrantedAccessMask = (PACCESS_MASK) (pReply->Error + pReply->ResultListLength);
    pReply->SaclEvaluationResults = NULL;

    //Create security descriptor.
    if(!ConvertStringSecurityDescriptorToSecurityDescriptor(
        L"O:LAG:BAD:(A;;RC;;;BA)",
        SDDL_REVISION_1,
        &amp;pSecurityDescriptor,
        NULL))
    {
        printf_s("ConvertStringSecurityDescriptorToSecurityDescriptor failed with %d\n", GetLastError()); 
        return FALSE;
    }

    //Call AuthzAccessCheck.
    if(!AuthzAccessCheck(
        0,
        hClientContext,
        &amp;Request,
        NULL,
        pSecurityDescriptor,
        NULL,
        0,
        pReply,
        NULL))
    {
        printf_s("AuthzAccessCheck failed with %d\n", GetLastError());
        
    LocalFree(pSecurityDescriptor);
    
        return FALSE;
    }


    //Print results.
    if(*pReply->GrantedAccessMask & READ_CONTROL)
    {
        printf_s("Access granted.\n");
    }
    else
    {
        printf_s("Access denied.\n");
    }

  LocalFree(pSecurityDescriptor);
    return TRUE;

}
```



## Related topics

<dl> <dt>

[Adding SIDs to a Client Context](adding-sids-to-a-client-context.md)
</dt> <dt>

[Caching Access Checks](caching-access-checks.md)
</dt> <dt>

[Initializing a Client Context](initializing-a-client-context.md)
</dt> <dt>

[Querying a Client Context](querying-a-client-context.md)
</dt> </dl>

 

 


