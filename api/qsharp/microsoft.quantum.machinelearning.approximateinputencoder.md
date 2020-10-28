---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 67ef7a47a2e036f0953d946b4ace0e6673b173bd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720537"
---
# <a name="approximateinputencoder-function"></a><span data-ttu-id="19966-102">ApproximateInputEncoder, funkcja</span><span class="sxs-lookup"><span data-stu-id="19966-102">ApproximateInputEncoder function</span></span>

<span data-ttu-id="19966-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="19966-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="19966-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="19966-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="19966-105">Mając na względzie zestaw współczynników i tolerancję, zwraca operację przygotowania stanu, która przygotowuje każdy współczynnik jako odpowiadającą amplitudę podstawy obliczeniowej, aż do podanej tolerancji.</span><span class="sxs-lookup"><span data-stu-id="19966-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.</span></span>

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="19966-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="19966-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="19966-107">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="19966-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="19966-108">Tolerancja przybliżona, która ma być używana w kodowaniu danego współczynników do stanu wejściowego.</span><span class="sxs-lookup"><span data-stu-id="19966-108">The approximation tolerance to be used in encoding the given coefficients into an input state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="19966-109">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="19966-109">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="19966-110">Współczynniki do zakodowania w stanie wejściowym.</span><span class="sxs-lookup"><span data-stu-id="19966-110">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="19966-111">Wynik: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="19966-111">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="19966-112">Operacja przygotowania stanu, która przygotowuje dane współczynniki jako stan wejścia dla danego rejestru.</span><span class="sxs-lookup"><span data-stu-id="19966-112">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>