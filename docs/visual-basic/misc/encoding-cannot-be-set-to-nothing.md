---
title: "Kodowanie nie można ustawić na wartość Nothing"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 42baef6e0634849004290dce3db32e47f103282d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="encoding-cannot-be-set-to-nothing"></a>Kodowanie nie można ustawić na wartość Nothing
Próba odczytu lub zapisu w pliku nie powiodło się, ponieważ parametr `encoding` została ustawiona jako `Nothing` , ale wymaga prawidłowej wartości.  
  
 <xref:System.Text.Encoding>Służy do określania, jakie szyfrowanie do użycia podczas zapisywania do pliku. Wartość domyślna to UTF-8.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Podaj prawidłową wartość dla `encoding` parametru.  
  
## <a name="see-also"></a>Zobacz też  
 [Kodowanie pliku](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 [Odczyt z plików](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [Zapisywanie w plikach](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 [My.Computer.FileSystem.ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)  
 [My.Computer.FileSystem.WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
