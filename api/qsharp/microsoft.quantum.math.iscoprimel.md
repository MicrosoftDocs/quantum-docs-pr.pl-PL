---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851344"
---
# <a name="iscoprimel-function"></a><span data-ttu-id="fe59b-102">IsCoprimeL, funkcja</span><span class="sxs-lookup"><span data-stu-id="fe59b-102">IsCoprimeL function</span></span>

<span data-ttu-id="fe59b-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fe59b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fe59b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe59b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe59b-105">Zwraca wartość true, jeśli $a $ i $b $ są współi w przeciwnym razie false.</span><span class="sxs-lookup"><span data-stu-id="fe59b-105">Returns true if $a$ and $b$ are co-prime and false otherwise.</span></span>

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="fe59b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fe59b-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="fe59b-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe59b-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fe59b-108">Pierwsza liczba, które są testowane co primality</span><span class="sxs-lookup"><span data-stu-id="fe59b-108">the first number of which co-primality is being tested</span></span>


### <a name="b--bigint"></a><span data-ttu-id="fe59b-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fe59b-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fe59b-110">Druga liczba, z której jest testowana primality</span><span class="sxs-lookup"><span data-stu-id="fe59b-110">the second number of which co-primality is being tested</span></span>



## <a name="output--bool"></a><span data-ttu-id="fe59b-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe59b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe59b-112">Prawda, jeśli $a $ i $b $ są współdzielone (np. ich największy wspólny dzielnik to 1) i w przeciwnym razie ma wartość false</span><span class="sxs-lookup"><span data-stu-id="fe59b-112">True, if $a$ and $b$ are co-prime (e.g. their greatest common divisor is 1 ), and false otherwise</span></span>