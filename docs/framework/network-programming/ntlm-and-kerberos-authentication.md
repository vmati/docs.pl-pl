---
title: Uwierzytelnianie NTLM i uwierzytelnianie Kerberos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 36e88b163ab857180a02278828dba7dcec457736
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="35e6b-102">Uwierzytelnianie NTLM i uwierzytelnianie Kerberos</span><span class="sxs-lookup"><span data-stu-id="35e6b-102">NTLM and Kerberos Authentication</span></span>
<span data-ttu-id="35e6b-103">Domyślne uwierzytelnianie NTLM i uwierzytelnianie Kerberos korzystanie z poświadczeń użytkownika systemu Microsoft Windows NT, skojarzone z aplikacji wywołującej prób uwierzytelniania z serwerem.</span><span class="sxs-lookup"><span data-stu-id="35e6b-103">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="35e6b-104">Podczas korzystania z uwierzytelniania NTLM innych niż domyślne, aplikacja ustawia typ uwierzytelniania NTLM i używa <xref:System.Net.NetworkCredential> obiektu w celu przekazania nazwę użytkownika, hasło i domenę do hosta, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="35e6b-104">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =   
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 <span data-ttu-id="35e6b-105">Aplikacje, które muszą łączyć się przy użyciu poświadczeń użytkownika aplikacji usług Internet zrobić za pomocą poświadczeń domyślnych użytkownika, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="35e6b-105">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 <span data-ttu-id="35e6b-106">Moduł uwierzytelniania negotiate Określa, czy serwer zdalny jest przy użyciu protokołu NTLM lub Kerberos i wysyła właściwą odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="35e6b-106">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35e6b-107">Uwierzytelnianie NTLM nie działa za pośrednictwem serwera proxy.</span><span class="sxs-lookup"><span data-stu-id="35e6b-107">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e6b-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="35e6b-108">See Also</span></span>  
 [<span data-ttu-id="35e6b-109">Podstawowe oraz uwierzytelnianie szyfrowane</span><span class="sxs-lookup"><span data-stu-id="35e6b-109">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [<span data-ttu-id="35e6b-110">Uwierzytelnianie Internet</span><span class="sxs-lookup"><span data-stu-id="35e6b-110">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)