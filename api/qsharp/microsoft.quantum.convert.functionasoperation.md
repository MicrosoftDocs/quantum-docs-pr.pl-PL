---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833837"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="2083f-102">FunctionAsOperation, funkcja</span><span class="sxs-lookup"><span data-stu-id="2083f-102">FunctionAsOperation function</span></span>

<span data-ttu-id="2083f-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="2083f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="2083f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2083f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2083f-105">Konwertuje funkcje na operacje.</span><span class="sxs-lookup"><span data-stu-id="2083f-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="2083f-106">Opis</span><span class="sxs-lookup"><span data-stu-id="2083f-106">Description</span></span>

<span data-ttu-id="2083f-107">Dana funkcja zwraca operację, która wywołuje tę funkcję, i która nic nie robi.</span><span class="sxs-lookup"><span data-stu-id="2083f-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="2083f-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2083f-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="2083f-109">fn: dane wyjściowe "Input->"</span><span class="sxs-lookup"><span data-stu-id="2083f-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="2083f-110">Funkcja, która ma zostać przekonwertowana na operację.</span><span class="sxs-lookup"><span data-stu-id="2083f-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="2083f-111">Wyjście: dane wyjściowe "Input =>"</span><span class="sxs-lookup"><span data-stu-id="2083f-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="2083f-112">Operacja `op` , która `op(input)` jest taka sama jak `fn(input)` dla wszystkich `input` .</span><span class="sxs-lookup"><span data-stu-id="2083f-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2083f-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2083f-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="2083f-114">"Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2083f-114">'Input</span></span>

<span data-ttu-id="2083f-115">Typ danych wejściowych funkcji do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="2083f-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="2083f-116">"Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="2083f-116">'Output</span></span>

<span data-ttu-id="2083f-117">Typ danych wyjściowych funkcji do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="2083f-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="2083f-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2083f-118">Remarks</span></span>

<span data-ttu-id="2083f-119">Jest to przydatne głównie do przekazywania funkcji do funkcji lub operacji, które oczekują operacji jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="2083f-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>