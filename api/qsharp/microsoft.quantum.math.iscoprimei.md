---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851366"
---
# <a name="iscoprimei-function"></a><span data-ttu-id="c975a-102">IsCoprimeI, funkcja</span><span class="sxs-lookup"><span data-stu-id="c975a-102">IsCoprimeI function</span></span>

<span data-ttu-id="c975a-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c975a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c975a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c975a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c975a-105">Zwraca wartość true, jeśli $a $ i $b $ są współi w przeciwnym razie false.</span><span class="sxs-lookup"><span data-stu-id="c975a-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="c975a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c975a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="c975a-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c975a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c975a-108">Pierwsza liczba, które są testowane co primality</span><span class="sxs-lookup"><span data-stu-id="c975a-108">the first number of which co-primality is being tested</span></span>


### <a name="b--int"></a><span data-ttu-id="c975a-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c975a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c975a-110">Druga liczba, z której jest testowana primality</span><span class="sxs-lookup"><span data-stu-id="c975a-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="c975a-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c975a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c975a-112">Prawda, jeśli $a $ i $b $ są współdzielone (np. ich największy wspólny dzielnik to 1) i w przeciwnym razie ma wartość false</span><span class="sxs-lookup"><span data-stu-id="c975a-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>