---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713510"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="53ed0-102">FunctionAsOperation, funkcja</span><span class="sxs-lookup"><span data-stu-id="53ed0-102">FunctionAsOperation function</span></span>

<span data-ttu-id="53ed0-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="53ed0-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="53ed0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53ed0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53ed0-105">Konwertuje funkcje na operacje.</span><span class="sxs-lookup"><span data-stu-id="53ed0-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="53ed0-106">Opis</span><span class="sxs-lookup"><span data-stu-id="53ed0-106">Description</span></span>

<span data-ttu-id="53ed0-107">Dana funkcja zwraca operację, która wywołuje tę funkcję, i która nic nie robi.</span><span class="sxs-lookup"><span data-stu-id="53ed0-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="53ed0-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="53ed0-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="53ed0-109">fn: dane wyjściowe "Input->"</span><span class="sxs-lookup"><span data-stu-id="53ed0-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="53ed0-110">Funkcja, która ma zostać przekonwertowana na operację.</span><span class="sxs-lookup"><span data-stu-id="53ed0-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="53ed0-111">Wyjście: dane wyjściowe "Input =>"</span><span class="sxs-lookup"><span data-stu-id="53ed0-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="53ed0-112">Operacja `op` , która `op(input)` jest taka sama jak `fn(input)` dla wszystkich `input` .</span><span class="sxs-lookup"><span data-stu-id="53ed0-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="53ed0-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="53ed0-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="53ed0-114">"Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="53ed0-114">'Input</span></span>

<span data-ttu-id="53ed0-115">Typ danych wejściowych funkcji do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="53ed0-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="53ed0-116">"Dane wyjściowe</span><span class="sxs-lookup"><span data-stu-id="53ed0-116">'Output</span></span>

<span data-ttu-id="53ed0-117">Typ danych wyjściowych funkcji do przekonwertowania.</span><span class="sxs-lookup"><span data-stu-id="53ed0-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="53ed0-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="53ed0-118">Remarks</span></span>

<span data-ttu-id="53ed0-119">Jest to przydatne głównie do przekazywania funkcji do funkcji lub operacji, które oczekują operacji jako dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="53ed0-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>