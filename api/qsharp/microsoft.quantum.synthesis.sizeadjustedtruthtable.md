---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725470"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="a45b6-102">SizeAdjustedTruthTable, funkcja</span><span class="sxs-lookup"><span data-stu-id="a45b6-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="a45b6-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a45b6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a45b6-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a45b6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a45b6-105">Dostosowuje tabelę prawdy z tablicy wartości logicznych zgodnie z liczbą zmiennych</span><span class="sxs-lookup"><span data-stu-id="a45b6-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="a45b6-106">Zwracana jest nowa tablica o długości `2^numVars` , która może wymagać poszerzenia `table` rozmiaru z `false` wpisami lub obcinanie go do `2^numVars` elementów.</span><span class="sxs-lookup"><span data-stu-id="a45b6-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="a45b6-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a45b6-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="a45b6-108">Tabela: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a45b6-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a45b6-109">Tabela prawdy jako tablica wartości prawdy</span><span class="sxs-lookup"><span data-stu-id="a45b6-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="a45b6-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a45b6-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a45b6-111">Liczba zmiennych</span><span class="sxs-lookup"><span data-stu-id="a45b6-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="a45b6-112">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="a45b6-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="a45b6-113">Dostosowana wielkość korekty w tabeli prawdy</span><span class="sxs-lookup"><span data-stu-id="a45b6-113">Size adjusted truth table</span></span>