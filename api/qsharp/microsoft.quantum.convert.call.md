---
uid: Microsoft.Quantum.Convert.Call
title: Operacja wywołania
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 92c159cef878fb587b0ed514fd6660dd19527cab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214215"
---
# <a name="call-operation"></a><span data-ttu-id="464df-102">Operacja wywołania</span><span class="sxs-lookup"><span data-stu-id="464df-102">Call operation</span></span>

<span data-ttu-id="464df-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="464df-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="464df-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="464df-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="464df-105">Wywołuje funkcję z danymi wejściowymi.</span><span class="sxs-lookup"><span data-stu-id="464df-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="464df-106">Opis</span><span class="sxs-lookup"><span data-stu-id="464df-106">Description</span></span>

<span data-ttu-id="464df-107">Dana funkcja i dane wejściowe do tej funkcji, wywołuje funkcję i zwraca dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="464df-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="464df-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="464df-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="464df-109">fn: dane wyjściowe "Input->"</span><span class="sxs-lookup"><span data-stu-id="464df-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="464df-110">Funkcja, która ma zostać wywołana.</span><span class="sxs-lookup"><span data-stu-id="464df-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="464df-111">dane wejściowe: "wejście</span><span class="sxs-lookup"><span data-stu-id="464df-111">input : 'Input</span></span>

<span data-ttu-id="464df-112">Dane wejściowe do przesłania do funkcji.</span><span class="sxs-lookup"><span data-stu-id="464df-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="464df-113">Dane wyjściowe: "output"</span><span class="sxs-lookup"><span data-stu-id="464df-113">Output : 'Output</span></span>

<span data-ttu-id="464df-114">Wynik wywołania `fn` .</span><span class="sxs-lookup"><span data-stu-id="464df-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="464df-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="464df-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="464df-116">"Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="464df-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="464df-117">"Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="464df-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="464df-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="464df-118">Remarks</span></span>

<span data-ttu-id="464df-119">Ta operacja jest szczególnie przydatna w przypadku wymuszania wywołania funkcji w konkretnym miejscu w ramach operacji lub do wywołania funkcji, w której oczekiwana jest operacja.</span><span class="sxs-lookup"><span data-stu-id="464df-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>