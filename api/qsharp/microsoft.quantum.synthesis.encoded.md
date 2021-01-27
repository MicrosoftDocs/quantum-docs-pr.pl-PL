---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Funkcja zakodowana
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855498"
---
# <a name="encoded-function"></a><span data-ttu-id="2ea2e-102">Funkcja zakodowana</span><span class="sxs-lookup"><span data-stu-id="2ea2e-102">Encoded function</span></span>

<span data-ttu-id="2ea2e-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2ea2e-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2ea2e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ea2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ea2e-105">Koduj tabelę prawdy w {1,-1} kodowaniu</span><span class="sxs-lookup"><span data-stu-id="2ea2e-105">Encode truth table in {1,-1} coding</span></span>

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="2ea2e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2ea2e-106">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="2ea2e-107">Tabela: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2ea2e-107">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2ea2e-108">Tabela prawdy jako tablica wartości prawdy</span><span class="sxs-lookup"><span data-stu-id="2ea2e-108">Truth table as array of truth values</span></span>



## <a name="output--int"></a><span data-ttu-id="2ea2e-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2ea2e-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2ea2e-110">Tabela prawdy jako tablica {1,-1} liczb całkowitych</span><span class="sxs-lookup"><span data-stu-id="2ea2e-110">Truth table as array of {1,-1} integers</span></span>

## <a name="example"></a><span data-ttu-id="2ea2e-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="2ea2e-111">Example</span></span>

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```