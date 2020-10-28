---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725134"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="18e38-102">RequiresCapability typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="18e38-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="18e38-103">Przestrzeń nazw: [Microsoft. Quantum. określania wartości docelowej](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="18e38-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="18e38-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18e38-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18e38-105">Atrybut rozpoznany przez kompilator używany do oznaczania możliwego do uruchomienia możliwości środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="18e38-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="18e38-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="18e38-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="18e38-107">Poziom: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="18e38-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="18e38-108">Nazwa poziomu możliwości środowiska uruchomieniowego wymaganego przez wywoływany.</span><span class="sxs-lookup"><span data-stu-id="18e38-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="18e38-109">Przyczyna: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="18e38-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="18e38-110">Opis przyczyny, dla którego możliwe jest wykonanie tej możliwości środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="18e38-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="18e38-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="18e38-111">Remarks</span></span>

<span data-ttu-id="18e38-112">Ten atrybut jest automatycznie dodawany do żądanych przez kompilator, chyba że wystąpienie tego atrybutu już istnieje w możliwym do przeniesieniu.</span><span class="sxs-lookup"><span data-stu-id="18e38-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="18e38-113">Nie powinno być używane z wyjątkiem rzadkich przypadków, w których kompilator nie wystawia prawidłowo wymaganej funkcji.</span><span class="sxs-lookup"><span data-stu-id="18e38-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="18e38-114">Poniżej znajduje się lista nazw poziomów możliwości w kolejności rosnących możliwości lub zmniejszających się ograniczeń:</span><span class="sxs-lookup"><span data-stu-id="18e38-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="18e38-115">Nie można porównać wyników pomiaru dla równości.</span><span class="sxs-lookup"><span data-stu-id="18e38-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="18e38-116">Wyniki pomiarów można porównać pod kątem równości tylko w wyrażeniach warunkowych if-Statement w operacjach.</span><span class="sxs-lookup"><span data-stu-id="18e38-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="18e38-117">Blok instrukcji if-Statement, który zależy od wyniku nie może zawierać instrukcji Set dla zmiennych modyfikowalnych zadeklarowanych poza blokiem lub instrukcji return.</span><span class="sxs-lookup"><span data-stu-id="18e38-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="18e38-118">Brak ograniczeń środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="18e38-118">No runtime restrictions.</span></span> <span data-ttu-id="18e38-119">Można wykonać dowolny program Q #.</span><span class="sxs-lookup"><span data-stu-id="18e38-119">Any Q# program can be executed.</span></span>