---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: e7eb2dfce060b61e27deae31e3c1fc6dc3d7655c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202111"
---
# <a name="dumpmachine-function"></a><span data-ttu-id="16a93-102">DumpMachine, funkcja</span><span class="sxs-lookup"><span data-stu-id="16a93-102">DumpMachine function</span></span>

<span data-ttu-id="16a93-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="16a93-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="16a93-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="16a93-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="16a93-105">Zrzuca stan bieżącej maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="16a93-105">Dumps the current target machine's status.</span></span>

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="16a93-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="16a93-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="16a93-107">Lokalizacja: 'T</span><span class="sxs-lookup"><span data-stu-id="16a93-107">location : 'T</span></span>

<span data-ttu-id="16a93-108">Zawiera informacje o tym, gdzie wygenerować zrzut maszyny.</span><span class="sxs-lookup"><span data-stu-id="16a93-108">Provides information on where to generate the machine's dump.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16a93-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16a93-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="16a93-110">Brak.</span><span class="sxs-lookup"><span data-stu-id="16a93-110">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="16a93-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="16a93-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16a93-112">'C</span><span class="sxs-lookup"><span data-stu-id="16a93-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="16a93-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="16a93-113">Remarks</span></span>

<span data-ttu-id="16a93-114">Ta metoda umożliwia zrzut informacji o bieżącym stanie maszyny docelowej do pliku lub innej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="16a93-114">This method allows you to dump information about the current status of the target machine into a file or some other location.</span></span>
<span data-ttu-id="16a93-115">Rzeczywiste wygenerowane informacje i semantyka `location` są specyficzne dla każdej maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="16a93-115">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="16a93-116">Jednak podanie pustej krotki jako lokalizacji ( `()` ) lub po prostu pominięcie `location` parametru zazwyczaj oznacza wygenerowanie danych wyjściowych w konsoli.</span><span class="sxs-lookup"><span data-stu-id="16a93-116">However, providing an empty tuple as a location (`()`) or just omitting the `location` parameter typically means to generate the output to the console.</span></span>

<span data-ttu-id="16a93-117">W przypadku lokalnego symulatora pełnego stanu dystrybuowanego w ramach zestawu Quantum Development Kit ta metoda oczekuje ciągu z ścieżką do pliku, w którym pisze funkcję Wave jako jednowymiarową tablicę liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru odpowiedniego stanu.</span><span class="sxs-lookup"><span data-stu-id="16a93-117">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the wave function as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>