---
title: "DataContract — surogat"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77eee3172b24bc0252ecb18d9ce6b283ba6e5c93
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="datacontract-surrogate"></a><span data-ttu-id="8b05b-102">DataContract — surogat</span><span class="sxs-lookup"><span data-stu-id="8b05b-102">DataContract Surrogate</span></span>
<span data-ttu-id="8b05b-103">W przykładzie pokazano, jak procesy, takie jak serializacji, deserializacji schematu eksportowania i importowania schematu można dostosować za pomocą kontraktu danych dwuskładnikowy klasy.</span><span class="sxs-lookup"><span data-stu-id="8b05b-103">This sample demonstrates how processes like serialization, deserialization, schema export, and schema import can be customized using a data contract surrogate class.</span></span> <span data-ttu-id="8b05b-104">Ten przykład przedstawia sposób użycia surogatu w przypadku scenariusza klienta i serwera, gdy dane są serializowane i przesyłane między [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] klienta i usługi.</span><span class="sxs-lookup"><span data-stu-id="8b05b-104">This sample shows how to use a surrogate in a client and server scenario where data is serialized and transmitted between a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b05b-105">Procedury i kompilacji instrukcje dotyczące instalacji dla tego przykładu znajdują się na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="8b05b-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8b05b-106">W przykładzie użyto następujących kontraktu usługi:</span><span class="sxs-lookup"><span data-stu-id="8b05b-106">The sample uses the following service contract:</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[AllowNonSerializableTypes]  
public interface IPersonnelDataService  
{  
    [OperationContract]  
    void AddEmployee(Employee employee);  
  
    [OperationContract]  
    Employee GetEmployee(string name);  
}  
```  
  
 <span data-ttu-id="8b05b-107">`AddEmployee` Operacji umożliwia użytkownikom dodanie danych dotyczących nowych pracowników i `GetEmployee` operacja obsługuje wyszukiwania dla pracowników na podstawie nazwy.</span><span class="sxs-lookup"><span data-stu-id="8b05b-107">The `AddEmployee` operation allows users to add data about new employees and the `GetEmployee` operation supports search for employees based on name.</span></span>  
  
 <span data-ttu-id="8b05b-108">Te operacje przy użyciu następującego typu danych:</span><span class="sxs-lookup"><span data-stu-id="8b05b-108">These operations use the following data type:</span></span>  
  
```  
[DataContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
class Employee  
{  
    [DataMember]  
    public DateTime dateHired;  
  
    [DataMember]  
    public Decimal salary;  
  
    [DataMember]  
    public Person person;  
}  
```  
  
 <span data-ttu-id="8b05b-109">W `Employee` typu `Person` klasy (wyświetlone czcionką następujący przykładowy kod) nie może być serializowany przez <xref:System.Runtime.Serialization.DataContractSerializer> , ponieważ nie jest klasą kontraktu prawidłowe dane.</span><span class="sxs-lookup"><span data-stu-id="8b05b-109">In the `Employee` type, the `Person` class (shown in the following sample code) cannot be serialized by the <xref:System.Runtime.Serialization.DataContractSerializer> because it is not a valid data contract class.</span></span>  
  
```  
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 <span data-ttu-id="8b05b-110">Możesz zastosować `DataContract` atrybutu `Person` klasy, ale nie zawsze jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="8b05b-110">You can apply the `DataContract` attribute to the `Person` class, but this is not always possible.</span></span> <span data-ttu-id="8b05b-111">Na przykład `Person` w osobny zestaw, w którym masz kontrolka nie można zdefiniować klasy.</span><span class="sxs-lookup"><span data-stu-id="8b05b-111">For example, the `Person` class can be defined in a separate assembly over which you have no control.</span></span>  
  
 <span data-ttu-id="8b05b-112">Podane to ograniczenie, aby serializować `Person` klasa ma zastąpić go z innej klasy, która jest oznaczony atrybutem `DataContractAttribute` i skopiuj przez dane niezbędne do nowej klasy.</span><span class="sxs-lookup"><span data-stu-id="8b05b-112">Given this restriction, one way to serialize the `Person` class is to substitute it with another class that is marked with `DataContractAttribute` and copy over necessary data to the new class.</span></span> <span data-ttu-id="8b05b-113">Celem jest zapewnienie `Person` klasy są wyświetlane jako DataContract do <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8b05b-113">The objective is to make the `Person` class appear as a DataContract to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="8b05b-114">Należy pamiętać, że jest jednym ze sposobów serializować klasy kontraktu bez danych.</span><span class="sxs-lookup"><span data-stu-id="8b05b-114">Note that this is one way to serialize non-data contract classes.</span></span>  
  
 <span data-ttu-id="8b05b-115">Przykład logicznie zastępuje `Person` klasy z inną klasę o nazwie `PersonSurrogated`.</span><span class="sxs-lookup"><span data-stu-id="8b05b-115">The sample logically replaces the `Person` class with a different class named `PersonSurrogated`.</span></span>  
  
```  
[DataContract(Name="Person", Namespace = "http://Microsoft.ServiceModel.Samples")]  
public class PersonSurrogated  
{  
    [DataMember]  
    public string FirstName;  
  
    [DataMember]  
    public string LastName;  
  
    [DataMember]  
    public int Age;  
}  
```  
  
 <span data-ttu-id="8b05b-116">Surogatu kontraktu danych służy do osiągnięcia tego zastąpienia.</span><span class="sxs-lookup"><span data-stu-id="8b05b-116">The data contract surrogate is used to achieve this replacement.</span></span> <span data-ttu-id="8b05b-117">Zastępcza Umowa danych jest klasa, która implementuje <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span><span class="sxs-lookup"><span data-stu-id="8b05b-117">A data contract surrogate is a class that implements <xref:System.Runtime.Serialization.IDataContractSurrogate>.</span></span> <span data-ttu-id="8b05b-118">W tym przykładzie `AllowNonSerializableTypesSurrogate` klasa implementuje ten interfejs.</span><span class="sxs-lookup"><span data-stu-id="8b05b-118">In this sample, the `AllowNonSerializableTypesSurrogate` class implements this interface.</span></span>  
  
 <span data-ttu-id="8b05b-119">W implementacji interfejsu pierwszego zadania jest ustanowienie mapowanie typu `Person` do `PersonSurrogated`.</span><span class="sxs-lookup"><span data-stu-id="8b05b-119">In the interface implementation, the first task is to establish a type mapping from `Person` to `PersonSurrogated`.</span></span> <span data-ttu-id="8b05b-120">To jest używany zarówno w czasie serializacji, jak i w czasie eksportowania schematu.</span><span class="sxs-lookup"><span data-stu-id="8b05b-120">This is used both at serialization time as well as at schema export time.</span></span> <span data-ttu-id="8b05b-121">Zaimplementowanie odbywa się to mapowanie <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> metody.</span><span class="sxs-lookup"><span data-stu-id="8b05b-121">This mapping is achieved by implementing the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29> method.</span></span>  
  
```  
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 <span data-ttu-id="8b05b-122"><xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> Mapy metody `Person` wystąpienie do `PersonSurrogated` wystąpienie podczas serializacji, jak pokazano w poniższym kodzie próbki.</span><span class="sxs-lookup"><span data-stu-id="8b05b-122">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29> method maps a `Person` instance to a `PersonSurrogated` instance during serialization, as shown in the following sample code.</span></span>  
  
```  
public object GetObjectToSerialize(object obj, Type targetType)  
{  
    if (obj is Person)  
    {  
        Person person = (Person)obj;  
        PersonSurrogated personSurrogated = new PersonSurrogated();  
        personSurrogated.FirstName = person.firstName;  
        personSurrogated.LastName = person.lastName;  
        personSurrogated.Age = person.age;  
        return personSurrogated;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="8b05b-123"><xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> Metoda zapewnia wstecznego mapowania do deserializacji, jak pokazano w poniższym kodzie próbki.</span><span class="sxs-lookup"><span data-stu-id="8b05b-123">The <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29> method provides the reverse mapping for deserialization, as shown in the following sample code.</span></span>  
  
```  
public object GetDeserializedObject(object obj,   
Type targetType)  
{  
    if (obj is PersonSurrogated)  
    {  
        PersonSurrogated personSurrogated = (PersonSurrogated)obj;  
        Person person = new Person();  
        person.firstName = personSurrogated.FirstName;  
        person.lastName = personSurrogated.LastName;  
        person.age = personSurrogated.Age;  
        return person;  
    }  
    return obj;  
}  
```  
  
 <span data-ttu-id="8b05b-124">Do mapowania `PersonSurrogated` kontraktu danych do istniejącej `Person` klasy podczas importowania schematu, implementuje próbki <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> metody, jak pokazano w poniższym kodzie próbki.</span><span class="sxs-lookup"><span data-stu-id="8b05b-124">To map the `PersonSurrogated` data contract to the existing `Person` class during schema import, the sample implements the <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29> method, as shown in the following sample code.</span></span>  
  
```  
public Type GetReferencedTypeOnImport(string typeName,   
               string typeNamespace, object customData)  
{  
if (  
typeNamespace.Equals("http://schemas.datacontract.org/2004/07/DCSurrogateSample")  
)  
    {  
         if (typeName.Equals("PersonSurrogated"))  
        {  
             return typeof(Person);  
        }  
     }  
     return null;  
}  
```  
  
 <span data-ttu-id="8b05b-125">Następujący przykładowy kod zakończeniu realizacji <xref:System.Runtime.Serialization.IDataContractSurrogate> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="8b05b-125">The following sample code completes the implementation of the <xref:System.Runtime.Serialization.IDataContractSurrogate> interface.</span></span>  
  
```  
public System.CodeDom.CodeTypeDeclaration ProcessImportedType(  
          System.CodeDom.CodeTypeDeclaration typeDeclaration,   
          System.CodeDom.CodeCompileUnit compileUnit)  
{  
    return typeDeclaration;  
}  
public object GetCustomDataToExport(Type clrType,   
                               Type dataContractType)  
{  
    return null;  
}  
  
public object GetCustomDataToExport(  
System.Reflection.MemberInfo memberInfo, Type dataContractType)  
{  
    return null;  
}  
public void GetKnownCustomDataTypes(  
        KnownTypeCollection customDataTypes)  
{  
    // It does not matter what we do here.  
    throw new NotImplementedException();  
}  
```  
  
 <span data-ttu-id="8b05b-126">W tym przykładzie surogatu jest włączone w modelu ServiceModel przez atrybut o nazwie `AllowNonSerializableTypesAttribute`.</span><span class="sxs-lookup"><span data-stu-id="8b05b-126">In this sample, the surrogate is enabled in ServiceModel by an attribute called `AllowNonSerializableTypesAttribute`.</span></span> <span data-ttu-id="8b05b-127">Deweloperzy należy zastosować ten atrybut na ich kontraktu usługi, jak pokazano na `IPersonnelDataService` powyżej kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="8b05b-127">Developers would need to apply this attribute on their service contract as shown on the `IPersonnelDataService` service contract above.</span></span> <span data-ttu-id="8b05b-128">Ten atrybut implementuje `IContractBehavior` i konfiguruje surogatu na operacje w jego `ApplyClientBehavior` i `ApplyDispatchBehavior` metody.</span><span class="sxs-lookup"><span data-stu-id="8b05b-128">This attribute implements `IContractBehavior` and sets up the surrogate on operations in its `ApplyClientBehavior` and `ApplyDispatchBehavior` methods.</span></span>  
  
 <span data-ttu-id="8b05b-129">Ten atrybut nie jest konieczne w takim przypadku — służy do celów demonstracyjnych, w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8b05b-129">The attribute is not necessary in this case - it is used for demonstration purposes in this sample.</span></span> <span data-ttu-id="8b05b-130">Użytkownicy mogą również włączyć surogatu przez ręczne dodanie podobne `IContractBehavior`, `IEndpointBehavior` lub `IOperationBehavior` przy użyciu kodu lub konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="8b05b-130">Users can alternatively enable a surrogate by manually adding a similar `IContractBehavior`, `IEndpointBehavior` or `IOperationBehavior` using code or using configuration.</span></span>  
  
 <span data-ttu-id="8b05b-131">`IContractBehavior` Wygląda implementację dla operacji korzystających z DataContract przez sprawdzenie, czy mają one `DataContractSerializerOperationBehavior` zarejestrowany.</span><span class="sxs-lookup"><span data-stu-id="8b05b-131">The `IContractBehavior` implementation looks for operations that use DataContract by checking if they have a `DataContractSerializerOperationBehavior` registered.</span></span> <span data-ttu-id="8b05b-132">Jeśli nie, ustawia `DataContractSurrogate` właściwości tego zachowania.</span><span class="sxs-lookup"><span data-stu-id="8b05b-132">If they do, it sets the `DataContractSurrogate` property on that behavior.</span></span> <span data-ttu-id="8b05b-133">Następujący przykładowy kod pokazuje, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="8b05b-133">The following sample code shows how this is done.</span></span> <span data-ttu-id="8b05b-134">Ustawienie to zachowanie operacji surogatu włączy ją do serializacji i deserializacji.</span><span class="sxs-lookup"><span data-stu-id="8b05b-134">Setting the surrogate on this operation behavior enables it for serialization and deserialization.</span></span>  
  
```  
public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime proxy)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatch)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
private static void ApplyDataContractSurrogate(OperationDescription description)  
{  
    DataContractSerializerOperationBehavior dcsOperationBehavior = description.Behaviors.Find<DataContractSerializerOperationBehavior>();  
    if (dcsOperationBehavior != null)  
    {  
        if (dcsOperationBehavior.DataContractSurrogate == null)  
            dcsOperationBehavior.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
    }  
}  
```  
  
 <span data-ttu-id="8b05b-135">Dodatkowe kroki należy podjąć w celu podłączenia surogatu do użycia podczas generowania metadanych.</span><span class="sxs-lookup"><span data-stu-id="8b05b-135">Additional steps need to be taken to plug in the surrogate for use during metadata generation.</span></span> <span data-ttu-id="8b05b-136">Jeden mechanizm w tym celu jest zapewnienie `IWsdlExportExtension` czyli przykładzie pokazano.</span><span class="sxs-lookup"><span data-stu-id="8b05b-136">One mechanism to do this is to provide an `IWsdlExportExtension` which is what this sample demonstrates.</span></span> <span data-ttu-id="8b05b-137">Innym sposobem jest zmodyfikowanie `WsdlExporter` bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="8b05b-137">Another way is to modify the `WsdlExporter` directly.</span></span>  
  
 <span data-ttu-id="8b05b-138">`AllowNonSerializableTypesAttribute` Atrybutu implementuje `IWsdlExportExtension` i `IContractBehavior`.</span><span class="sxs-lookup"><span data-stu-id="8b05b-138">The `AllowNonSerializableTypesAttribute` attribute implements `IWsdlExportExtension` and `IContractBehavior`.</span></span> <span data-ttu-id="8b05b-139">Rozszerzenia mogą być `IContractBehavior` lub `IEndpointBehavior` w takim przypadku.</span><span class="sxs-lookup"><span data-stu-id="8b05b-139">The extension can be either an `IContractBehavior` or `IEndpointBehavior` in this case.</span></span> <span data-ttu-id="8b05b-140">Jego `IWsdlExportExtension.ExportContract` implementacji metody umożliwia surogatu, dodając ją do `XsdDataContractExporter` używane podczas generowania schematu DataContract.</span><span class="sxs-lookup"><span data-stu-id="8b05b-140">Its `IWsdlExportExtension.ExportContract` method implementation enables the surrogate by adding it to the `XsdDataContractExporter` used during schema generation for DataContract.</span></span> <span data-ttu-id="8b05b-141">Poniższy fragment kodu pokazano, jak to zrobić.</span><span class="sxs-lookup"><span data-stu-id="8b05b-141">The following code snippet shows how to do this.</span></span>  
  
```  
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
    if (exporter == null)  
        throw new ArgumentNullException("exporter");  
  
    object dataContractExporter;  
    XsdDataContractExporter xsdDCExporter;  
    if (!exporter.State.TryGetValue(typeof(XsdDataContractExporter), out dataContractExporter))  
    {  
        xsdDCExporter = new XsdDataContractExporter(exporter.GeneratedXmlSchemas);  
        exporter.State.Add(typeof(XsdDataContractExporter), xsdDCExporter);  
    }  
    else  
    {  
        xsdDCExporter = (XsdDataContractExporter)dataContractExporter;  
    }  
    if (xsdDCExporter.Options == null)  
        xsdDCExporter.Options = new ExportOptions();  
  
    if (xsdDCExporter.Options.DataContractSurrogate == null)  
        xsdDCExporter.Options.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
}  
```  
  
 <span data-ttu-id="8b05b-142">Po uruchomieniu próbki, gdy klient wywołuje AddEmployee następuje wywołanie GetEmployee w celu sprawdzenia, jeśli pierwsze wywołanie zakończyło się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="8b05b-142">When you run the sample, the client calls AddEmployee followed by a GetEmployee call to check if the first call was successful.</span></span> <span data-ttu-id="8b05b-143">Wynik żądania operacji GetEmployee jest wyświetlany w oknie konsoli klienta.</span><span class="sxs-lookup"><span data-stu-id="8b05b-143">The result of the GetEmployee operation request is displayed in the client console window.</span></span> <span data-ttu-id="8b05b-144">Operacja GetEmployee musi pomyślnie w znajdowaniu pracownik i wydrukować "znaleziono".</span><span class="sxs-lookup"><span data-stu-id="8b05b-144">The GetEmployee operation must succeed in finding the employee and print "found".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b05b-145">W tym przykładzie pokazano, jak dołączyć surogatu serializacja, deserializacji a Generowanie metadanych.</span><span class="sxs-lookup"><span data-stu-id="8b05b-145">This sample shows how to plug in a surrogate for serialize, deserialize and metadata generation.</span></span> <span data-ttu-id="8b05b-146">Jak dołączyć surogatu dla generowanie kodu na podstawie metadanych nie są wyświetlane.</span><span class="sxs-lookup"><span data-stu-id="8b05b-146">It does not show how to plug in a surrogate for code generation from metadata.</span></span> <span data-ttu-id="8b05b-147">Aby zapoznać się przykładem sposobu surogatu może służyć do generowania kodu klienta, zobacz [niestandardowa publikacja WSDL](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) próbki.</span><span class="sxs-lookup"><span data-stu-id="8b05b-147">To see a sample of how a surrogate can be used to plug into client code generation, see the [Custom WSDL Publication](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md) sample.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8b05b-148">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="8b05b-148">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8b05b-149">Upewnij się, że wykonano procedurę [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8b05b-149">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8b05b-150">Aby utworzyć edition C# rozwiązania, postępuj zgodnie z instrukcjami w [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8b05b-150">To build the C# edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8b05b-151">Aby uruchomić przykładowy w konfiguracji pojedynczej lub między komputerami, postępuj zgodnie z instrukcjami w [uruchamiania przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8b05b-151">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b05b-152">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="8b05b-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8b05b-153">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="8b05b-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8b05b-154">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="8b05b-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8b05b-155">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="8b05b-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
  
## <a name="see-also"></a><span data-ttu-id="8b05b-156">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8b05b-156">See Also</span></span>