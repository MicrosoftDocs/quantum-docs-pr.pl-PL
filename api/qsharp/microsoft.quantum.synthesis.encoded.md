---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Funkcja zakodowana
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 6b9d21969ee90f3928b65a1c97a5b0f15157e381
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725204"
---
# <a name="encoded-function"></a><span data-ttu-id="afea7-102">Funkcja zakodowana</span><span class="sxs-lookup"><span data-stu-id="afea7-102">Encoded function</span></span>

<span data-ttu-id="afea7-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="afea7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="afea7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afea7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afea7-105">Koduj tabelę prawdy w {1,-1} kodowaniu</span><span class="sxs-lookup"><span data-stu-id="afea7-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="afea7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="afea7-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="afea7-107">Tabela: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="afea7-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="afea7-108">Tabela prawdy jako tablica wartości prawdy</span><span class="sxs-lookup"><span data-stu-id="afea7-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="afea7-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="afea7-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="afea7-110">Tabela prawdy jako tablica {1,-1} liczb całkowitych</span><span class="sxs-lookup"><span data-stu-id="afea7-110">Truth table as array of {1,-1} integers</span></span>