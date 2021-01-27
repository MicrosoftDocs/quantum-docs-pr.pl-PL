---
uid: Microsoft.Quantum.Canon.ArrangedQubits
title: ArrangedQubits, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ArrangedQubits
qsharp.summary: Arrange control, target, and helper qubits according to an index
ms.openlocfilehash: 07a4ed5fe99dedb333246f7161d157dcd01a01da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841074"
---
# <a name="arrangedqubits-function"></a><span data-ttu-id="330a2-102">ArrangedQubits, funkcja</span><span class="sxs-lookup"><span data-stu-id="330a2-102">ArrangedQubits function</span></span>

<span data-ttu-id="330a2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="330a2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="330a2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="330a2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="330a2-105">Rozmieszczanie formantów, obiektów docelowych i qubits pomocnika zgodnie z indeksem</span><span class="sxs-lookup"><span data-stu-id="330a2-105">Arrange control, target, and helper qubits according to an index</span></span>

```qsharp
function ArrangedQubits (controls : Qubit[], target : Qubit, helper : Qubit[]) : Qubit[]
```


## <a name="description"></a><span data-ttu-id="330a2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="330a2-106">Description</span></span>

<span data-ttu-id="330a2-107">Zwraca tablicę qubit z elementem docelowym przy indeksie 0 i kontrolujem indeks 2 ^ i.</span><span class="sxs-lookup"><span data-stu-id="330a2-107">Returns a Qubit array with target at index 0, and control i at index 2^i.</span></span>  <span data-ttu-id="330a2-108">Qubits pomocnika są wstawiane do wszystkich innych pozycji w tablicy.</span><span class="sxs-lookup"><span data-stu-id="330a2-108">The helper qubits are inserted to all other positions in the array.</span></span>

## <a name="input"></a><span data-ttu-id="330a2-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="330a2-109">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="330a2-110">kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="330a2-110">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="330a2-111">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="330a2-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>




### <a name="helper--qubit"></a><span data-ttu-id="330a2-112">pomocnik: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="330a2-112">helper : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--qubit"></a><span data-ttu-id="330a2-113">Wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="330a2-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

