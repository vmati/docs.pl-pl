---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6e1eccbaae35a16fe4fb133296698d347c190e94
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="28d1a-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="28d1a-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="28d1a-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="28d1a-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d1a-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="28d1a-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="28d1a-105">Metody</span><span class="sxs-lookup"><span data-stu-id="28d1a-105">Methods</span></span>  
 <span data-ttu-id="28d1a-106">Klasa TextMessageEncodingBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="28d1a-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="28d1a-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="28d1a-107">Properties</span></span>  
 <span data-ttu-id="28d1a-108">Klasa TextMessageEncodingBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="28d1a-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="28d1a-109">Kodowanie</span><span class="sxs-lookup"><span data-stu-id="28d1a-109">Encoding</span></span>  
 <span data-ttu-id="28d1a-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="28d1a-110">Data type: string</span></span>  
  
 <span data-ttu-id="28d1a-111">Dostęp typu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="28d1a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="28d1a-112">Zestaw znaków kodowania używanego w celu emisji komunikatów w powiązaniu.</span><span class="sxs-lookup"><span data-stu-id="28d1a-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="28d1a-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="28d1a-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="28d1a-114">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="28d1a-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="28d1a-115">Dostęp typu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="28d1a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="28d1a-116">Liczba całkowita definiująca, ile komunikatów można jednocześnie odczytać bez przydziału nowych czytników.</span><span class="sxs-lookup"><span data-stu-id="28d1a-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="28d1a-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="28d1a-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="28d1a-118">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="28d1a-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="28d1a-119">Dostęp typu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="28d1a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="28d1a-120">Liczba całkowita definiująca, ile komunikatów można jednocześnie wysłać bez przydziału nowych modułów zapisujących.</span><span class="sxs-lookup"><span data-stu-id="28d1a-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="28d1a-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="28d1a-121">ReaderQuotas</span></span>  
 <span data-ttu-id="28d1a-122">Typ danych: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="28d1a-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="28d1a-123">Dostęp typu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="28d1a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="28d1a-124">Przydziały czytników.</span><span class="sxs-lookup"><span data-stu-id="28d1a-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28d1a-125">Wymagania</span><span class="sxs-lookup"><span data-stu-id="28d1a-125">Requirements</span></span>  
  
|<span data-ttu-id="28d1a-126">MOF</span><span class="sxs-lookup"><span data-stu-id="28d1a-126">MOF</span></span>|<span data-ttu-id="28d1a-127">Zadeklarowany w Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="28d1a-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="28d1a-128">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="28d1a-128">Namespace</span></span>|<span data-ttu-id="28d1a-129">Zdefiniowany w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="28d1a-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28d1a-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="28d1a-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>