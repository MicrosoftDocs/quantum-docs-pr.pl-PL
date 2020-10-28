---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722306"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="c901d-102">IsCoprimeL, funkcja</span><span class="sxs-lookup"><span data-stu-id="c901d-102">IsCoprimeL function</span></span>

<span data-ttu-id="c901d-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c901d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c901d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c901d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c901d-105">Zwraca wartość true, jeśli $a $ i $b $ są współi w przeciwnym razie false.</span><span class="sxs-lookup"><span data-stu-id="c901d-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="c901d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c901d-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="c901d-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c901d-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c901d-108">Pierwsza liczba, które są testowane co primality</span><span class="sxs-lookup"><span data-stu-id="c901d-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="c901d-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c901d-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c901d-110">Druga liczba, z której jest testowana primality</span><span class="sxs-lookup"><span data-stu-id="c901d-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="c901d-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c901d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c901d-112">Prawda, jeśli $a $ i $b $ są współdzielone (np. ich największy wspólny dzielnik to 1) i w przeciwnym razie ma wartość false</span><span class="sxs-lookup"><span data-stu-id="c901d-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>