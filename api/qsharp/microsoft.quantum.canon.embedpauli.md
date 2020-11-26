---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207041"
---
# <a name="embedpauli-function"></a><span data-ttu-id="229d6-102">EmbedPauli, funkcja</span><span class="sxs-lookup"><span data-stu-id="229d6-102">EmbedPauli function</span></span>

<span data-ttu-id="229d6-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="229d6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="229d6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="229d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="229d6-105">Za pomocą pojedynczego operatora Pauli qubit i indeksu qubit, zwraca wieloqubity operator Pauli z danym operatorem Single-qubit w tym indeksie i `PauliI` w każdym innym indeksie.</span><span class="sxs-lookup"><span data-stu-id="229d6-105">Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.</span></span>

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="229d6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="229d6-106">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="229d6-107">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="229d6-107">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="229d6-108">Qubit operator Pauli, który ma zostać umieszczony w danej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="229d6-108">A single-qubit Pauli operator to be placed at the given location.</span></span>


### <a name="location--int"></a><span data-ttu-id="229d6-109">Lokalizacja: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="229d6-109">location : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="229d6-110">Indeks taki `output[location] == pauli` , gdzie `output` jest danymi wyjściowymi tej funkcji.</span><span class="sxs-lookup"><span data-stu-id="229d6-110">An index such that `output[location] == pauli`, where `output` is the output of this function.</span></span>


### <a name="n--int"></a><span data-ttu-id="229d6-111">n: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="229d6-111">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="229d6-112">Długość tablicy, która ma zostać zwrócona.</span><span class="sxs-lookup"><span data-stu-id="229d6-112">Length of the array to be returned.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="229d6-113">Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="229d6-113">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

