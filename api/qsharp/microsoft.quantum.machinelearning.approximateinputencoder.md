---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 035c353c34362aa3486a7df9e7bb1bc95a6f63be
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856176"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="2680a-102">ApproximateInputEncoder, funkcja</span><span class="sxs-lookup"><span data-stu-id="2680a-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="2680a-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2680a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2680a-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2680a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2680a-105">Mając na względzie zestaw współczynników i tolerancję, zwraca operację przygotowania stanu, która przygotowuje każdy współczynnik jako odpowiadającą amplitudę podstawy obliczeniowej, aż do podanej tolerancji.</span><span class="sxs-lookup"><span data-stu-id="2680a-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="2680a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2680a-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="2680a-107">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2680a-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2680a-108">Tolerancja przybliżona, która ma być używana w kodowaniu danego współczynników do stanu wejściowego.</span><span class="sxs-lookup"><span data-stu-id="2680a-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="2680a-109">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2680a-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2680a-110">Współczynniki do zakodowania w stanie wejściowym.</span><span class="sxs-lookup"><span data-stu-id="2680a-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="2680a-111">Wynik: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="2680a-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="2680a-112">Operacja przygotowania stanu, która przygotowuje dane współczynniki jako stan wejścia dla danego rejestru.</span><span class="sxs-lookup"><span data-stu-id="2680a-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>