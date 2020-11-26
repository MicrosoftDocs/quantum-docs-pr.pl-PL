---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 53131a755571ad1ac0a8a984bf229b16f67dbe51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195362"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="90776-102">IsCoprimeI, funkcja</span><span class="sxs-lookup"><span data-stu-id="90776-102">IsCoprimeI function</span></span>

<span data-ttu-id="90776-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="90776-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="90776-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90776-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90776-105">Zwraca wartość true, jeśli $a $ i $b $ są współi w przeciwnym razie false.</span><span class="sxs-lookup"><span data-stu-id="90776-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="90776-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="90776-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="90776-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90776-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90776-108">Pierwsza liczba, które są testowane co primality</span><span class="sxs-lookup"><span data-stu-id="90776-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="90776-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90776-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90776-110">Druga liczba, z której jest testowana primality</span><span class="sxs-lookup"><span data-stu-id="90776-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="90776-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="90776-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="90776-112">Prawda, jeśli $a $ i $b $ są współdzielone (np. ich największy wspólny dzielnik to 1) i w przeciwnym razie ma wartość false</span><span class="sxs-lookup"><span data-stu-id="90776-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>