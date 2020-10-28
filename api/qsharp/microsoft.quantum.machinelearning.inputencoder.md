---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709753"
---
# <a name="inputencoder-function"></a><span data-ttu-id="66780-102">InputEncoder, funkcja</span><span class="sxs-lookup"><span data-stu-id="66780-102">InputEncoder function</span></span>

<span data-ttu-id="66780-103">Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="66780-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="66780-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="66780-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="66780-105">Biorąc pod sobą zestaw współczynników i tolerancję, zwraca operację przygotowania stanu, która przygotowuje każdy współczynnik jako odpowiadającą amplitudę podstawy obliczeniowej.</span><span class="sxs-lookup"><span data-stu-id="66780-105">Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.</span></span>

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a><span data-ttu-id="66780-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="66780-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="66780-107">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="66780-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="66780-108">Współczynniki do zakodowania w stanie wejściowym.</span><span class="sxs-lookup"><span data-stu-id="66780-108">The coefficients to be encoded into an input state.</span></span>



## <a name="output--stategenerator"></a><span data-ttu-id="66780-109">Wynik: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="66780-109">Output : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="66780-110">Operacja przygotowania stanu, która przygotowuje dane współczynniki jako stan wejścia dla danego rejestru.</span><span class="sxs-lookup"><span data-stu-id="66780-110">A state preparation operation that prepares the given coefficients as an input state on a given register.</span></span>