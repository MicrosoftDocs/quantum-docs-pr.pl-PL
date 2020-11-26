---
uid: Microsoft.Quantum.Simulation.ApplyBlockEncodingFromBEandQubit
title: ApplyBlockEncodingFromBEandQubit, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: ApplyBlockEncodingFromBEandQubit
qsharp.summary: Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding
ms.openlocfilehash: 16d54a982b020f4d4ded5901ec07de44a2d09726
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229617"
---
# <a name="applyblockencodingfrombeandqubit-operation"></a><span data-ttu-id="7f72a-102">ApplyBlockEncodingFromBEandQubit, operacja</span><span class="sxs-lookup"><span data-stu-id="7f72a-102">ApplyBlockEncodingFromBEandQubit operation</span></span>

<span data-ttu-id="7f72a-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7f72a-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7f72a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f72a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f72a-105">Konwersja ((LittleEndian, qubit []) => () jest korektą + CTL) do BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="7f72a-105">Conversion of ((LittleEndian, Qubit[]) => () is Adj + Ctl) to BlockEncoding</span></span>

```qsharp
operation ApplyBlockEncodingFromBEandQubit (op : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl), auxiliary : Qubit[], system : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7f72a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7f72a-106">Input</span></span>

### <a name="op--littleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="7f72a-107">op: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="7f72a-107">op : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="7f72a-108">pomocniczy: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7f72a-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="system--qubit"></a><span data-ttu-id="7f72a-109">System: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="7f72a-109">system : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="7f72a-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7f72a-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

