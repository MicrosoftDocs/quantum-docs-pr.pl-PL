---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855150"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="97d84-102">RequiresCapability typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="97d84-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="97d84-103">Przestrzeń nazw: [Microsoft. Quantum. określania wartości docelowej](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="97d84-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="97d84-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="97d84-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="97d84-105">Atrybut rozpoznany przez kompilator używany do oznaczania możliwego do uruchomienia możliwości środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="97d84-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="97d84-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="97d84-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="97d84-107">Poziom: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="97d84-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="97d84-108">Nazwa poziomu możliwości środowiska uruchomieniowego wymaganego przez wywoływany.</span><span class="sxs-lookup"><span data-stu-id="97d84-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="97d84-109">Przyczyna: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="97d84-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="97d84-110">Opis przyczyny, dla którego możliwe jest wykonanie tej możliwości środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="97d84-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="97d84-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="97d84-111">Remarks</span></span>

<span data-ttu-id="97d84-112">Ten atrybut jest automatycznie dodawany do żądanych przez kompilator, chyba że wystąpienie tego atrybutu już istnieje w możliwym do przeniesieniu.</span><span class="sxs-lookup"><span data-stu-id="97d84-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="97d84-113">Nie powinno być używane z wyjątkiem rzadkich przypadków, w których kompilator nie wystawia prawidłowo wymaganej funkcji.</span><span class="sxs-lookup"><span data-stu-id="97d84-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="97d84-114">Poniżej znajduje się lista nazw poziomów możliwości w kolejności rosnących możliwości lub zmniejszających się ograniczeń:</span><span class="sxs-lookup"><span data-stu-id="97d84-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="97d84-115">Nie można porównać wyników pomiaru dla równości.</span><span class="sxs-lookup"><span data-stu-id="97d84-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="97d84-116">Wyniki pomiarów można porównać pod kątem równości tylko w wyrażeniach warunkowych if-Statement w operacjach.</span><span class="sxs-lookup"><span data-stu-id="97d84-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="97d84-117">Blok instrukcji if-Statement, który zależy od wyniku nie może zawierać instrukcji Set dla zmiennych modyfikowalnych zadeklarowanych poza blokiem lub instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="97d84-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="97d84-118">Brak ograniczeń środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="97d84-118">No runtime restrictions.</span></span> <span data-ttu-id="97d84-119">Można wykonać dowolny program Q #.</span><span class="sxs-lookup"><span data-stu-id="97d84-119">Any Q# program can be executed.</span></span>