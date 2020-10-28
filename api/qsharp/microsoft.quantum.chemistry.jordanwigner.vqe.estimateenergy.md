---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: EstimateEnergy, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: 52e527a68818c80f93bc177d3563064fd0f2aea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713748"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="392f9-102">EstimateEnergy, operacja</span><span class="sxs-lookup"><span data-stu-id="392f9-102">EstimateEnergy operation</span></span>

<span data-ttu-id="392f9-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="392f9-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="392f9-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="392f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="392f9-105">Szacuje energię cząsteczki przez zsumowanie zużycia energii przez poszczególne Jordan-Wigner warunki.</span><span class="sxs-lookup"><span data-stu-id="392f9-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="392f9-106">Opis</span><span class="sxs-lookup"><span data-stu-id="392f9-106">Description</span></span>

<span data-ttu-id="392f9-107">Ta operacja jest niejawnie oparta na Konwencji indeksowania w górę i w dół.</span><span class="sxs-lookup"><span data-stu-id="392f9-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="392f9-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="392f9-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="392f9-109">jwHamiltonian: [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="392f9-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="392f9-110">Jordan-Wigner hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="392f9-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="392f9-111">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="392f9-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="392f9-112">Liczba próbek do oszacowania warunków oczekiwania.</span><span class="sxs-lookup"><span data-stu-id="392f9-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="392f9-113">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="392f9-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="392f9-114">Szacowana energia cząsteczki</span><span class="sxs-lookup"><span data-stu-id="392f9-114">The estimated energy of the molecule</span></span>