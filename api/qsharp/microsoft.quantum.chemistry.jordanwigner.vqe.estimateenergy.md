---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: EstimateEnergy, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: fb59071ed05234d4a19cd97598bf479489b9985c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214419"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="a03fe-102">EstimateEnergy, operacja</span><span class="sxs-lookup"><span data-stu-id="a03fe-102">EstimateEnergy operation</span></span>

<span data-ttu-id="a03fe-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="a03fe-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="a03fe-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a03fe-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="a03fe-105">Szacuje energię cząsteczki przez zsumowanie zużycia energii przez poszczególne Jordan-Wigner warunki.</span><span class="sxs-lookup"><span data-stu-id="a03fe-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="a03fe-106">Opis</span><span class="sxs-lookup"><span data-stu-id="a03fe-106">Description</span></span>

<span data-ttu-id="a03fe-107">Ta operacja jest niejawnie oparta na Konwencji indeksowania w górę i w dół.</span><span class="sxs-lookup"><span data-stu-id="a03fe-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="a03fe-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a03fe-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="a03fe-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="a03fe-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="a03fe-110">Jordan-Wigner hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="a03fe-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="a03fe-111">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a03fe-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a03fe-112">Liczba próbek do oszacowania warunków oczekiwania.</span><span class="sxs-lookup"><span data-stu-id="a03fe-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="a03fe-113">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a03fe-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a03fe-114">Szacowana energia cząsteczki</span><span class="sxs-lookup"><span data-stu-id="a03fe-114">The estimated energy of the molecule</span></span>