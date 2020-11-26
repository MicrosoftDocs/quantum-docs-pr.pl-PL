---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Funkcja zakodowana
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 803f35b9e7af547bc34f21de74684fba885bfda9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203182"
---
# <a name="encoded-function"></a><span data-ttu-id="077e6-102">Funkcja zakodowana</span><span class="sxs-lookup"><span data-stu-id="077e6-102">Encoded function</span></span>

<span data-ttu-id="077e6-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="077e6-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="077e6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="077e6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="077e6-105">Koduj tabelę prawdy w {1,-1} kodowaniu</span><span class="sxs-lookup"><span data-stu-id="077e6-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="077e6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="077e6-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="077e6-107">Tabela: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="077e6-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="077e6-108">Tabela prawdy jako tablica wartości prawdy</span><span class="sxs-lookup"><span data-stu-id="077e6-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="077e6-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="077e6-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="077e6-110">Tabela prawdy jako tablica {1,-1} liczb całkowitych</span><span class="sxs-lookup"><span data-stu-id="077e6-110">Truth table as array of {1,-1} integers</span></span>