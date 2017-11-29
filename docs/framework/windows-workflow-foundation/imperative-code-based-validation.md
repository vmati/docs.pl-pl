---
title: Weryfikacja opartej na kodzie imperatywne
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5b9919c2919bf670396dc4af7d17d7087f9b4908
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="imperative-code-based-validation"></a><span data-ttu-id="b9cb4-102">Weryfikacja opartej na kodzie imperatywne</span><span class="sxs-lookup"><span data-stu-id="b9cb4-102">Imperative Code-Based Validation</span></span>
<span data-ttu-id="b9cb4-103">Konieczne weryfikacji opartych na kodzie zapewnia prosty sposób działania w celu udostępnienia weryfikacji o sobie samym i jest dostępny dla działań, które pochodzą z <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, i <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-103">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and is available for activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="b9cb4-104">Sprawdzanie poprawności kodu, który określa wszelkie błędy lub ostrzeżenia walidacji jest dodawany do działania.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-104">Validation code that determines any validation errors or warnings is added to the activity.</span></span>  
  
## <a name="using-code-based-validation"></a><span data-ttu-id="b9cb4-105">Za pomocą opartej na kodzie sprawdzania poprawności</span><span class="sxs-lookup"><span data-stu-id="b9cb4-105">Using Code-Based Validation</span></span>  
 <span data-ttu-id="b9cb4-106">Oparte na kodzie sprawdzania poprawności jest obsługiwana przez działania, które pochodzą z <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, i <xref:System.Activities.NativeActivity>.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-106">Code-based validation is supported by activities that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, and <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="b9cb4-107">Sprawdzanie poprawności kodu można umieścić w <xref:System.Activities.CodeActivity.CacheMetadata%2A> zastąpienie, a błędy lub ostrzeżenia walidacji mogą być dodawane do argumentu metadanych.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-107">Validation code can be placed in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override, and validation errors or warnings can be added to the metadata argument.</span></span> <span data-ttu-id="b9cb4-108">W poniższym przykładzie pobierana z [podstawowe sprawdzanie poprawności](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) przykładowe, jeśli `Cost` jest większa niż `Price`, błąd sprawdzania poprawności jest dodawany do metadanych.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-108">In the following example, taken from the [Basic Validation](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md) sample, if the `Cost` is greater than the `Price`, a validation error is added to the metadata.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9cb4-109">Należy pamiętać, że `Cost` i `Price` nie są argumenty do działania, ale nie ma właściwości, które są ustawione w czasie projektowania.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-109">Note that `Cost` and `Price` are not arguments to the activity, but are properties that are set at design time.</span></span> <span data-ttu-id="b9cb4-110">Oznacza to dlaczego ich wartości można zweryfikować w <xref:System.Activities.CodeActivity.CacheMetadata%2A> zastąpienia.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-110">That is why their values can be validated in the <xref:System.Activities.CodeActivity.CacheMetadata%2A> override.</span></span> <span data-ttu-id="b9cb4-111">Nie można zweryfikować wartości danych przepływających przez argument w czasie projektowania, ponieważ nie przepływ danych do czasu wykonywania, ale argumentów działania mogą być sprawdzone, aby upewnić się, że są one związane przy użyciu `RequiredArgument` atrybutu i przeciążenia grup.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-111">The value of the data flowing through an argument cannot be validated at design time because the data does not flow until run time, but activity arguments can be validated to ensure that they are bound by using the `RequiredArgument` attribute and overload groups.</span></span> <span data-ttu-id="b9cb4-112">Ten przykładowy kod widzi `RequiredArgument` atrybutu dla `Description` argumentu i jeśli nie jest powiązany, zostanie wygenerowany błąd sprawdzania poprawności.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-112">This example code sees the `RequiredArgument` attribute for the `Description` argument, and if it is not bound then a validation error is generated.</span></span> <span data-ttu-id="b9cb4-113">Wymagane argumenty zostały omówione w [wymaganych argumentów i grup przeciążenia](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b9cb4-113">Required arguments are covered in [Required Arguments and Overload Groups](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md).</span></span>  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error   
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 <span data-ttu-id="b9cb4-114">Domyślnie błąd sprawdzania poprawności jest dodawany do metadanych podczas <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-114">By default, a validation error is added to the metadata when <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> is called.</span></span> <span data-ttu-id="b9cb4-115">Aby dodać ostrzeżenie walidacji, użyj <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> przeciążenia, które przyjmuje <xref:System.Activities.Validation.ValidationError>i określić, że <xref:System.Activities.Validation.ValidationError> reprezentuje ostrzeżenie przez ustawienie <xref:System.Activities.Validation.ValidationError.IsWarning%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-115">To add a validation warning, use the <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> overload that takes a <xref:System.Activities.Validation.ValidationError>, and specify that the <xref:System.Activities.Validation.ValidationError> represents a warning by setting the <xref:System.Activities.Validation.ValidationError.IsWarning%2A> property.</span></span>  
  
 <span data-ttu-id="b9cb4-116">Sprawdzanie poprawności występuje, gdy przepływ pracy zostanie zmodyfikowany w Projektancie przepływów pracy i wszelkie błędy sprawdzania poprawności zostaną wyświetlone w Projektancie przepływów pracy.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-116">Validation occurs when a workflow is modified in the workflow designer and any validation errors or warnings are displayed in the workflow designer.</span></span> <span data-ttu-id="b9cb4-117">Sprawdzanie poprawności występuje także w czasie wykonywania po wywołaniu przepływu pracy i, jeśli wystąpią jakieś błędy sprawdzania poprawności, <xref:System.Activities.InvalidWorkflowException> jest generowany przez logikę sprawdzania poprawności domyślnej.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-117">Validation also occurs at run time when a workflow is invoked and if any validation errors occur, an <xref:System.Activities.InvalidWorkflowException> is thrown by the default validation logic.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="b9cb4-118">wywoływanie sprawdzania poprawności i uzyskiwania dostępu do sprawdzania poprawności ostrzeżeń i błędów, zobacz [wywoływania sprawdzania poprawności działania](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="b9cb4-118"> invoking validation and accessing any validation warnings or errors, see [Invoking Activity Validation](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md).</span></span>  
  
 <span data-ttu-id="b9cb4-119">Wszelkie wyjątki, które są generowane z <xref:System.Activities.CodeActivity.CacheMetadata%2A> nie są traktowane jako błędy sprawdzania poprawności.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-119">Any exceptions that are thrown from <xref:System.Activities.CodeActivity.CacheMetadata%2A> are not treated as validation errors.</span></span> <span data-ttu-id="b9cb4-120">Te wyjątki zostaną wyjścia z wywołania <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> i muszą być obsługiwane przez obiekt wywołujący.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-120">These exceptions will escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span>  
  
 <span data-ttu-id="b9cb4-121">Oparte na kodzie sprawdzania poprawności jest przydatna do sprawdzania poprawności działania, który zawiera kod, ale nie ma wgląd w innych działań w przepływie pracy.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-121">Code-based validation is useful for validating the activity that contains the code, but it does not have visibility into the other activities in the workflow.</span></span> <span data-ttu-id="b9cb4-122">Sprawdzanie poprawności ograniczenia deklaratywne pozwala, aby sprawdzić poprawność relacje między działania i innych działań w przepływie pracy i znajdują się w [deklaratywne ograniczenia](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md) tematu.</span><span class="sxs-lookup"><span data-stu-id="b9cb4-122">Declarative constraints validation provides the ability to validate the relationships between an activity and other activities in the workflow, and is covered in the [Declarative Constraints](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md) topic.</span></span>