---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723356"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="70729-102">IsCoprimeI, funkcja</span><span class="sxs-lookup"><span data-stu-id="70729-102">IsCoprimeI function</span></span>

<span data-ttu-id="70729-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="70729-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="70729-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="70729-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="70729-105">Zwraca wartość true, jeśli $a $ i $b $ są współi w przeciwnym razie false.</span><span class="sxs-lookup"><span data-stu-id="70729-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="70729-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="70729-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="70729-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="70729-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="70729-108">Pierwsza liczba, które są testowane co primality</span><span class="sxs-lookup"><span data-stu-id="70729-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="70729-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="70729-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="70729-110">Druga liczba, z której jest testowana primality</span><span class="sxs-lookup"><span data-stu-id="70729-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="70729-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="70729-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="70729-112">Prawda, jeśli $a $ i $b $ są współdzielone (np. ich największy wspólny dzielnik to 1) i w przeciwnym razie ma wartość false</span><span class="sxs-lookup"><span data-stu-id="70729-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>