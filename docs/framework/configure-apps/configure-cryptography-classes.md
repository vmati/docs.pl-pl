---
title: Konfigurowanie klasy kryptografii
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 79eb9f9ef95dae24dd38fa93b137c9303815143b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="0bfbe-102">Konfigurowanie klasy kryptografii</span><span class="sxs-lookup"><span data-stu-id="0bfbe-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="0bfbe-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] Pozwala administratorom komputera do konfigurowania domyślne algorytmów kryptograficznych i algorytm implementacji, korzystających z programu .NET Framework i odpowiednio napisanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0bfbe-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="0bfbe-104">Na przykład przedsiębiorstwo, które ma własną implementację algorytmu kryptograficznego ułatwia tę implementację domyślnego zamiast implementacji w [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bfbe-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="0bfbe-105">Mimo że zarządzanych aplikacji, które używają kryptografii zawsze można wybrać jawnie powiązać konkretnej implementacji, zaleca się ich tworzenie obiektów kryptograficzne przy użyciu systemu konfiguracji usług kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="0bfbe-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0bfbe-106">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="0bfbe-106">In This Section</span></span>  
 [<span data-ttu-id="0bfbe-107">Mapowanie nazw algorytmów na klasy kryptografii</span><span class="sxs-lookup"><span data-stu-id="0bfbe-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="0bfbe-108">Opisuje sposób mapowania nazwy algorytmu klasy kryptografii.</span><span class="sxs-lookup"><span data-stu-id="0bfbe-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="0bfbe-109">Mapowanie identyfikatorów obiektów na algorytmy kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="0bfbe-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="0bfbe-110">Opisuje sposób odwzorowywania identyfikator obiektu algorytmu kryptograficznego.</span><span class="sxs-lookup"><span data-stu-id="0bfbe-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0bfbe-111">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="0bfbe-111">Related Sections</span></span>  
 [<span data-ttu-id="0bfbe-112">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="0bfbe-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="0bfbe-113">Zawiera omówienie usług kryptograficznych programu [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bfbe-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="0bfbe-114">Schemat ustawień kryptografii</span><span class="sxs-lookup"><span data-stu-id="0bfbe-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="0bfbe-115">W tym artykule opisano elementy, które mapują algorytm przyjaznej nazwy klasy, które implementują algorytmów kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="0bfbe-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>