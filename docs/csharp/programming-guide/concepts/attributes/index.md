---
title: Atrybuty (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f148f13f-a0d5-4f22-9c87-4b73d5dde270
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f9fc23cf7afbd28f0c9ae438cbce298cbf362fbd
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/09/2017
---
# <a name="attributes-c"></a>Atrybuty (C#)
Atrybuty udostępnia zaawansowane metody kojarzenia metadanych lub deklaratywne informacji z kodu (zestawy, typy metod, właściwości i tak dalej). Po atrybutu jest skojarzony z jednostką program, ten atrybut można tworzyć zapytania w czasie wykonywania przy użyciu techniki o nazwie *odbicia*. Aby uzyskać więcej informacji, zobacz [odbicia (C#)](../../../../csharp/programming-guide/concepts/reflection.md).  
  
 Atrybuty mieć następujące właściwości:  
  
-   Atrybuty dodawać metadane do programu. *Metadane* znajdują się informacje o typy zdefiniowane w programie. Wszystkie zestawy .NET zawierają określony zestaw metadanych, które opisują typy i elementy członkowskie typu zdefiniowany w zestawie. Można dodawać atrybuty niestandardowe, aby określić dodatkowe informacje, które jest wymagane. Aby uzyskać więcej informacji zobacz, [tworzenie niestandardowe atrybuty (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).  
  
-   Co najmniej jeden atrybut można stosować do całego zestawy, moduły lub mniejsze elementy programu, takich jak klasy i właściwości.  
  
-   Atrybuty mogą akceptować argumenty w taki sam sposób jak metody i właściwości.  
  
-   Program można sprawdzić jego własnej ani metadanych w programach przy użyciu odbicia. Aby uzyskać więcej informacji, zobacz [podczas uzyskiwania dostępu do atrybutów przy użyciu odbicia (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).  
  
## <a name="using-attributes"></a>Przy użyciu atrybutów  
 Atrybuty można umieścić w praktycznie dowolnej deklaracji, chociaż określony atrybut mogą ograniczać typów deklaracje, na których jest ona prawidłowa. W C# należy określić atrybut przez umieszczenie nazwę atrybutu, ujęta w nawiasy kwadratowe ([]), powyżej deklaracji jednostki, której dotyczy.  
  
 W tym przykładzie <xref:System.SerializableAttribute> atrybut służy do stosowania określonej właściwości do klasy:  
  
```csharp  
[System.Serializable]  
public class SampleClass  
{  
    // Objects of this type can be serialized.  
}  
```  
  
 Metody z atrybutem <xref:System.Runtime.InteropServices.DllImportAttribute> jest zadeklarowany w następujący sposób:  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
[System.Runtime.InteropServices.DllImport("user32.dll")]  
extern static void SampleMethod();  
```  
  
 Więcej niż jeden atrybut można umieścić w deklaracji:  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
void MethodA([In][Out] ref double x) { }  
void MethodB([Out][In] ref double x) { }  
void MethodC([In, Out] ref double x) { }  
```  
  
 Niektóre atrybuty można określić więcej niż raz dla danej jednostki. Na przykład multiuse atrybutu <xref:System.Diagnostics.ConditionalAttribute>:  
  
```csharp  
[Conditional("DEBUG"), Conditional("TEST1")]  
void TraceMethod()  
{  
    // ...  
}  
```  
  
> [!NOTE]
>  Według Konwencji wszystkich nazw atrybutów kończyć się wyrazem "Atrybutu", aby odróżnić je od innych elementów w programie .NET Framework. Nie trzeba jednak określić sufiks atrybutu przy użyciu atrybutów w kodzie. Na przykład `[DllImport]` jest odpowiednikiem `[DllImportAttribute]`, ale `DllImportAttribute` jest rzeczywistą nazwą atrybutu w programie .NET Framework.  
  
### <a name="attribute-parameters"></a>Parametry atrybutów  
 Wiele atrybutów ma parametry, które mogą być pozycyjnych, bez nazwy lub nazwane. Parametry pozycyjne musi być podana w odpowiedniej kolejności i nie może zostać pominięta; nazwane parametry są opcjonalne i może zostać określony w dowolnej kolejności. Parametry pozycyjne są określony jako pierwszy. Na przykład te trzy atrybuty są równoważne:  
  
```csharp  
[DllImport("user32.dll")]  
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]  
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]  
```  
  
 Pierwszy parametr Nazwa biblioteki DLL jest pozycyjnych i zawsze zostanie osiągnięty jako pierwszy; inne o nazwie. W takim przypadku nazwanych parametrów domyślna wartość to false, więc można pominąć. Zajrzyj do dokumentacji poszczególne atrybuty, aby uzyskać informacje dotyczące domyślne wartości parametrów.  
  
### <a name="attribute-targets"></a>Docelowe atrybuty  
 *Docelowej* atrybutu jest jednostki, której dotyczy ten atrybut. Na przykład atrybut mogą stosować do klasy, konkretnej metody lub całego zestawu. Domyślnie atrybut dotyczy poprzedza element. Ale można również jawnie określić, na przykład, czy atrybut jest stosowany do metody, lub jej parametr albo jego wartości zwracanej.  
  
 Aby jawnie określić obiekt docelowy atrybutu, należy użyć następującej składni:  
  
```csharp  
[target : attribute-list]  
```  
  
 Lista możliwości `target` w poniższej tabeli przedstawiono wartości.  
  
|Wartość docelowa|Informacje zawarte w tym artykule dotyczą|  
|------------------|----------------|  
|`assembly`|Całego zestawu|  
|`module`|Bieżący modułu zestawu|  
|`field`|Pole w klasie lub strukturze|  
|`event`|Zdarzenie|  
|`method`|Metoda lub `get` i `set` metod dostępu do właściwości|  
|`param`|Parametry metody lub `set` parametry metody dostępu właściwości|  
|`property`|Właściwość|  
|`return`|Zwraca wartość metody, właściwości indeksatora lub `get` metody dostępu właściwości|  
|`type`|Struktury, klasy, interface, enum lub delegate|  
  
 Poniższy przykład pokazuje, jak można zastosować atrybutów do zestawów i modułów. Aby uzyskać więcej informacji, zobacz [takie same atrybuty wspólne (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).  
  
```csharp  
using System;  
using System.Reflection;  
[assembly: AssemblyTitleAttribute("Production assembly 4")]  
[module: CLSCompliant(true)]  
```  
  
 Poniższy przykład przedstawia sposób zastosować atrybutów do metod, parametrów metod i metody zwracają wartości w języku C#.  
  
```csharp  
// default: applies to method  
[SomeAttr]  
int Method1() { return 0; }  
  
// applies to method  
[method: SomeAttr]  
int Method2() { return 0; }  
  
// applies to return value  
[return: SomeAttr]  
int Method3() { return 0; }  
```  
  
> [!NOTE]
>  Niezależnie od celów, na którym `SomeAttr` zdefiniowano był prawidłowy, `return` docelowy musi być określony, nawet jeśli `SomeAttr` zostały zdefiniowane do stosowania tylko dla wartości zwracane. Innymi słowy, kompilator nie będzie używać `AttributeUsage` informacje umożliwiające rozwiązanie docelowe atrybuty niejednoznaczne. Aby uzyskać więcej informacji, zobacz [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).  
  
## <a name="common-uses-for-attributes"></a>Najczęstsze zastosowania dla atrybutów  
 Poniższa lista zawiera kilka typowych zastosowań atrybutów w kodzie:  
  
-   Oznaczanie za pomocą metody `WebMethod` atrybutów w usługach sieci Web, aby wskazać, że metoda powinna być wywoływana za pośrednictwem protokołu SOAP. Aby uzyskać więcej informacji, zobacz <xref:System.Web.Services.WebMethodAttribute>.  
  
-   Zawierająca opis sposobu zorganizowania parametrów metody podczas współpracy z kodu macierzystego. Aby uzyskać więcej informacji, zobacz <xref:System.Runtime.InteropServices.MarshalAsAttribute>.  
  
-   Opisujących właściwości modelu COM dla klas, metod i interfejsów.  
  
-   Wywoływanie niezarządzanych w kodzie za pomocą <xref:System.Runtime.InteropServices.DllImportAttribute> klasy.  
  
-   Opisujące używanemu zestawowi pod względem tytułu, wersji, opis lub znakiem towarowym.  
  
-   Opisujące członków klasy do serializacji trwałości.  
  
-   Opisujących sposób mapowania między elementami członkowskimi klas i węzłów XML do serializacji XML.  
  
-   Opisujących wymagania dotyczące zabezpieczeń dla metod.  
  
-   Określanie właściwości używanych do wymuszania zabezpieczeń.  
  
-   Kontrolowanie optymalizacji przez kompilator just-in-time (JIT), kod jest łatwy do debugowania.  
  
-   Uzyskiwanie informacji o elemencie wywołującym metodę.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 Aby uzyskać więcej informacji, zobacz:  
  
-   [Tworzenie atrybutów niestandardowych (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   [Uzyskiwanie dostępu do atrybutów przy użyciu odbicia (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
-   [Porady: tworzenie złożenia C/C++ za pomocą atrybutów (C#)](../../../../csharp/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [Atrybuty wspólne (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
  
-   [Informacje o wywołującym (C#)](../../../../csharp/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a>Zobacz też  
 [Przewodnik programowania w języku C#](../../../../csharp/programming-guide/index.md)  
 [Odbicie (C#)](../../../../csharp/programming-guide/concepts/reflection.md)  
 [Atrybuty](../../../../../docs/standard/attributes/index.md)
