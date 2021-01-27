---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855322"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="91939-102">SizeAdjustedTruthTable, funkcja</span><span class="sxs-lookup"><span data-stu-id="91939-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="91939-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="91939-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="91939-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91939-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91939-105">Dostosowuje tabelę prawdy z tablicy wartości logicznych zgodnie z liczbą zmiennych</span><span class="sxs-lookup"><span data-stu-id="91939-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="91939-106">Zwracana jest nowa tablica o długości `2^numVars` , która może wymagać poszerzenia `table` rozmiaru z `false` wpisami lub obcinanie go do `2^numVars` elementów.</span><span class="sxs-lookup"><span data-stu-id="91939-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="91939-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="91939-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="91939-108">Tabela: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="91939-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="91939-109">Tabela prawdy jako tablica wartości prawdy</span><span class="sxs-lookup"><span data-stu-id="91939-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="91939-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="91939-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="91939-111">Liczba zmiennych</span><span class="sxs-lookup"><span data-stu-id="91939-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="91939-112">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="91939-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="91939-113">Dostosowana wielkość korekty w tabeli prawdy</span><span class="sxs-lookup"><span data-stu-id="91939-113">Size adjusted truth table</span></span>