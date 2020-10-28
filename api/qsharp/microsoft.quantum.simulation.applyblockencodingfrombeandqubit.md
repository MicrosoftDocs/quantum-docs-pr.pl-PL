---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingFromBEandQubit
title: ApplyBlockEncodingFromBEandQubit, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingFromBEandQubit
qsharp.summary: Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding
ms.openlocfilehash: d11c5bd8a33fc5dfc9ed3aa374c9c53afe286e24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722105"
---
# <a name="applyblockencodingfrombeandqubit-operation"></a><span data-ttu-id="e1d71-102">ApplyBlockEncodingFromBEandQubit, operacja</span><span class="sxs-lookup"><span data-stu-id="e1d71-102">ApplyBlockEncodingFromBEandQubit operation</span></span>

<span data-ttu-id="e1d71-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e1d71-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e1d71-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1d71-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e1d71-105">Konwersja ((LittleEndian, qubit []) => () jest korektą + CTL) do BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="e1d71-105">Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding</span></span>

```qsharp
operation ApplyBlockEncodingFromBEandQubit (op : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl), auxiliary : Qubit[], system : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="e1d71-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e1d71-106">Input</span></span>

### <a name="op--littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="e1d71-107">op: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="e1d71-107">op : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="e1d71-108">pomocniczy: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e1d71-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="system--qubit"></a><span data-ttu-id="e1d71-109">System: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e1d71-109">system : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="e1d71-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1d71-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

