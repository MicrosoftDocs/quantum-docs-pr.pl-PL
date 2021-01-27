---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: ed70d9f24af06f8918083307c98a5f6c4671f1c3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852945"
---
# <a name="inputencoder-function"></a><span data-ttu-id="31b1c-102">InputEncoder, funkcja</span><span class="sxs-lookup"><span data-stu-id="31b1c-102">InputEncoder function</span></span>

<span data-ttu-id="31b1c-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="31b1c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="31b1c-104">Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="31b1c-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="31b1c-105">Biorąc pod sobą zestaw współczynników i tolerancję, zwraca operację przygotowania stanu, która przygotowuje każdy współczynnik jako odpowiadającą amplitudę podstawy obliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="31b1c-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="31b1c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="31b1c-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="31b1c-107">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="31b1c-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="31b1c-108">Współczynniki do zakodowania w stanie wejściowym.</span><span class="sxs-lookup"><span data-stu-id="31b1c-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="31b1c-109">Wynik: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="31b1c-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="31b1c-110">Operacja przygotowania stanu, która przygotowuje dane współczynniki jako stan wejścia dla danego rejestru.</span><span class="sxs-lookup"><span data-stu-id="31b1c-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>