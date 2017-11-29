---
title: "Jak: utworzyć dostawcę tokenu zabezpieczającego niestandardowych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0bf616b1af46c62166b0430c1b67b3a97f0613ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-security-token-provider"></a><span data-ttu-id="c304e-102">Jak: utworzyć dostawcę tokenu zabezpieczającego niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c304e-102">How to: Create a Custom Security Token Provider</span></span>
<span data-ttu-id="c304e-103">W tym temacie przedstawiono sposób tworzenia nowych typów tokenu z dostawcę tokenu zabezpieczającego niestandardowych i sposobu integracji dostawcy z Menedżer tokenów zabezpieczających niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="c304e-103">This topic shows how to create new token types with a custom security token provider and how to integrate the provider with a custom security token manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c304e-104">Utworzyć niestandardowego dostawcę tokenów, jeśli dostarczane przez system tokenów w <xref:System.IdentityModel.Tokens> przestrzeni nazw nie są zgodne z wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="c304e-104">Create a custom token provider if the system-provided tokens found in the <xref:System.IdentityModel.Tokens> namespace do not match your requirements.</span></span>  
  
 <span data-ttu-id="c304e-105">Dostawcy tokenów zabezpieczających tworzy reprezentację tokenu zabezpieczeń na podstawie informacji w poświadczeniach klienta lub usługi.</span><span class="sxs-lookup"><span data-stu-id="c304e-105">The security token provider creates a security token representation based on information in the client or service credentials.</span></span> <span data-ttu-id="c304e-106">Aby użyć niestandardowego dostawcy tokenów zabezpieczających w [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zabezpieczeń, należy utworzyć niestandardowe poświadczenia i implementacje Menedżer tokenów zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c304e-106">To use the custom security token provider in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security, you must create custom credentials and security token manager implementations.</span></span>  
  
 <span data-ttu-id="c304e-107">Aby uzyskać więcej informacji o niestandardowych poświadczeń i Menedżer tokenów zabezpieczających zobacz [wskazówki: Tworzenie niestandardowego klienta i poświadczeń usługi](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="c304e-107">For more information about custom credentials and security token manager see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="c304e-108">Aby uzyskać więcej informacji o poświadczeniach zabezpieczeń tokenu Menedżera dostawcy klas i uwierzytelniania, zobacz [Architektura zabezpieczeń](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f).</span><span class="sxs-lookup"><span data-stu-id="c304e-108">For more information about credentials, security token manager, provider and authenticator classes, see the [Security Architecture](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f).</span></span>  
  
### <a name="to-create-a-custom-security-token-provider"></a><span data-ttu-id="c304e-109">Aby utworzyć dostawcę tokenu zabezpieczającego niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c304e-109">To create a custom security token provider</span></span>  
  
1.  <span data-ttu-id="c304e-110">Zdefiniuj nową klasę pochodną <xref:System.IdentityModel.Selectors.SecurityTokenProvider> klasy.</span><span class="sxs-lookup"><span data-stu-id="c304e-110">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class.</span></span>  
  
2.  <span data-ttu-id="c304e-111">Implementowanie <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> metody.</span><span class="sxs-lookup"><span data-stu-id="c304e-111">Implement the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="c304e-112">Metoda jest odpowiedzialna za tworzenie i zwracanie wystąpienie tokenu zabezpieczającego.</span><span class="sxs-lookup"><span data-stu-id="c304e-112">The method is responsible for creating and returning an instance of the security token.</span></span> <span data-ttu-id="c304e-113">Poniższy przykład tworzy klasę o nazwie `MySecurityTokenProvider`i zastępuje <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> sposób zwrócenia wystąpienia klasy <xref:System.IdentityModel.Tokens.X509SecurityToken> klasy.</span><span class="sxs-lookup"><span data-stu-id="c304e-113">The following example creates a class named `MySecurityTokenProvider`, and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method to return an instance of the <xref:System.IdentityModel.Tokens.X509SecurityToken> class.</span></span> <span data-ttu-id="c304e-114">Konstruktor klasy wymaga wystąpienia <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> klasy.</span><span class="sxs-lookup"><span data-stu-id="c304e-114">The class constructor requires an instance of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class.</span></span>  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a><span data-ttu-id="c304e-115">Aby zintegrować dostawcę tokenu zabezpieczającego niestandardowych z Menedżer tokenów zabezpieczających niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c304e-115">To integrate a custom security token provider with a custom security token manager</span></span>  
  
1.  <span data-ttu-id="c304e-116">Zdefiniuj nową klasę pochodną <xref:System.IdentityModel.Selectors.SecurityTokenManager> klasy.</span><span class="sxs-lookup"><span data-stu-id="c304e-116">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span> <span data-ttu-id="c304e-117">(Poniższy przykład pochodzi z <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> klasy, która jest pochodną <xref:System.IdentityModel.Selectors.SecurityTokenManager> klasy.)</span><span class="sxs-lookup"><span data-stu-id="c304e-117">(The example below derives from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class, which derives from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.)</span></span>  
  
2.  <span data-ttu-id="c304e-118">Zastąpienie <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> metodę, jeśli jeszcze nie jest przeciążona.</span><span class="sxs-lookup"><span data-stu-id="c304e-118">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if is not already overridden.</span></span>  
  
     <span data-ttu-id="c304e-119"><xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> Metoda jest odpowiedzialna za zwracanie wystąpienia <xref:System.IdentityModel.Selectors.SecurityTokenProvider> klasy należy <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parametr przekazany do metody [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] strukturę zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c304e-119">The <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method is responsible for returning an instance of the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class appropriate to the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter passed to the method by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework.</span></span> <span data-ttu-id="c304e-120">Zmodyfikuj metodę, aby zwrócić implementacji dostawcy tokenów zabezpieczeń niestandardowe (utworzonego w poprzedniej procedurze) gdy metoda jest wywoływana z parametrem tokenu odpowiednich ustawień zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="c304e-120">Modify the method to return the custom security token provider implementation (created in the previous procedure) when the method is called with an appropriate security token parameter.</span></span> <span data-ttu-id="c304e-121">Aby uzyskać więcej informacji na temat Menedżer tokenów zabezpieczających, zobacz [wskazówki: Tworzenie niestandardowego klienta i poświadczeń usługi](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="c304e-121">For more information about the security token manager, see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
3.  <span data-ttu-id="c304e-122">Dodanie logiki niestandardowej metody do zwrócić dostawcy tokenu zabezpieczeń niestandardowe na podstawie <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parametru.</span><span class="sxs-lookup"><span data-stu-id="c304e-122">Add custom logic to the method to enable it to return your custom security token provider based on the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter.</span></span> <span data-ttu-id="c304e-123">Poniższy przykład zwraca dostawcę tokenów zabezpieczających niestandardowych, jeśli spełnione są wymagania tokenu.</span><span class="sxs-lookup"><span data-stu-id="c304e-123">The following sample returns the custom security token provider if the token requirements are met.</span></span> <span data-ttu-id="c304e-124">Wymagania obejmują tokenu zabezpieczającego X.509 i kierunek wiadomości (czy jest używany dla danych wyjściowych komunikat).</span><span class="sxs-lookup"><span data-stu-id="c304e-124">The requirements include an X.509 security token and the message direction (that the token is used for message output).</span></span> <span data-ttu-id="c304e-125">We wszystkich innych przypadkach kod wywołuje klasa podstawowa do obsługi innych wymagań dotyczących zabezpieczeń tokenu zachowanie dostarczane przez system.</span><span class="sxs-lookup"><span data-stu-id="c304e-125">For all other cases, the code calls the base class to maintain the system-provided behavior for other security token requirements.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="c304e-126">Przykład</span><span class="sxs-lookup"><span data-stu-id="c304e-126">Example</span></span>  
 <span data-ttu-id="c304e-127">Poniżej pokazano pełnego <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementacji wraz z odpowiednią <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementacji.</span><span class="sxs-lookup"><span data-stu-id="c304e-127">The following shows a complete <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation along with a corresponding <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementation.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="c304e-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c304e-128">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [<span data-ttu-id="c304e-129">Wskazówki: Tworzenie niestandardowego klienta i poświadczeń usługi</span><span class="sxs-lookup"><span data-stu-id="c304e-129">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [<span data-ttu-id="c304e-130">Porady: tworzenie wystawcy uwierzytelnienia tokenu zabezpieczeń niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c304e-130">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [<span data-ttu-id="c304e-131">Architektura zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="c304e-131">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)