---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712838"
---
# <a name="dumpregister-function"></a><span data-ttu-id="0e395-102">DumpRegister, funkcja</span><span class="sxs-lookup"><span data-stu-id="0e395-102">DumpRegister function</span></span>

<span data-ttu-id="0e395-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0e395-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0e395-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e395-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e395-105">Zrzuca stan bieżącej maszyny docelowej skojarzony z danym qubits.</span><span class="sxs-lookup"><span data-stu-id="0e395-105">Dumps the current target machine's status associated with the given qubits.</span></span>

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0e395-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0e395-106">Input</span></span>

### <a name="location--t"></a><span data-ttu-id="0e395-107">Lokalizacja: 'T</span><span class="sxs-lookup"><span data-stu-id="0e395-107">location : 'T</span></span>

<span data-ttu-id="0e395-108">Zawiera informacje o tym, gdzie wygenerować zrzut stanu.</span><span class="sxs-lookup"><span data-stu-id="0e395-108">Provides information on where to generate the state's dump.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="0e395-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0e395-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0e395-110">Lista qubits do raportowania.</span><span class="sxs-lookup"><span data-stu-id="0e395-110">The list of qubits to report.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e395-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e395-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="0e395-112">Brak.</span><span class="sxs-lookup"><span data-stu-id="0e395-112">None.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0e395-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0e395-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e395-114">'C</span><span class="sxs-lookup"><span data-stu-id="0e395-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="0e395-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0e395-115">Remarks</span></span>

<span data-ttu-id="0e395-116">Ta metoda umożliwia zrzut informacji skojarzonych ze stanem danego qubits do pliku lub innej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="0e395-116">This method allows you to dump the information associated with the state of the given qubits into a file or some other location.</span></span>
<span data-ttu-id="0e395-117">Rzeczywiste wygenerowane informacje i semantyka `location` są specyficzne dla każdej maszyny docelowej.</span><span class="sxs-lookup"><span data-stu-id="0e395-117">The actual information generated and the semantics of `location` are specific to each target machine.</span></span> <span data-ttu-id="0e395-118">Jednak podanie pustej krotki jako lokalizacji ( `()` ) zazwyczaj oznacza wygenerowanie danych wyjściowych w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="0e395-118">However, providing an empty tuple as a location (`()`) typically means to generate the output to the console.</span></span>

<span data-ttu-id="0e395-119">W przypadku lokalnego symulatora pełnego stanu dystrybuowanego w ramach zestawu Quantum Development Kit ta metoda oczekuje ciągu z ścieżką do pliku, w którym będzie zapisywać stan danego qubits (tj. funkcja Wave odpowiedniego podsystemu) jako Jednowymiarowa tablica liczb zespolonych, w których każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru odpowiedniego stanu.</span><span class="sxs-lookup"><span data-stu-id="0e395-119">For the local full state simulator distributed as part of the Quantum Development Kit, this method  expects a string with the path to a file in which it will write the state of the given qubits (i.e. the wave function of the corresponding  subsystem) as a one-dimensional array of complex numbers, in which each element represents the amplitudes of the probability of measuring the corresponding state.</span></span>
<span data-ttu-id="0e395-120">Jeśli dany qubits są Entangled z innymi qubit i ich stan nie może zostać oddzielony, tylko zgłasza, że qubits są Entangled.</span><span class="sxs-lookup"><span data-stu-id="0e395-120">If the given qubits are entangled with some other qubit and their state can't be separated, it just reports that the qubits are entangled.</span></span>