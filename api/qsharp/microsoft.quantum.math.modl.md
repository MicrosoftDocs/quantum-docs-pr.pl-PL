---
uid: Microsoft.Quantum.Math.ModL
title: ModL, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227798"
---
# <a name="modl-function"></a><span data-ttu-id="0be7d-102">ModL, funkcja</span><span class="sxs-lookup"><span data-stu-id="0be7d-102">ModL function</span></span>

<span data-ttu-id="0be7d-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0be7d-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0be7d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0be7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0be7d-105">Zwraca moduł liczby w odniesieniu do innej liczby.</span><span class="sxs-lookup"><span data-stu-id="0be7d-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="0be7d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0be7d-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="0be7d-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0be7d-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0be7d-108">Dane wejściowe $a $, których moduł ma zostać zwrócony.</span><span class="sxs-lookup"><span data-stu-id="0be7d-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="0be7d-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0be7d-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0be7d-110">Liczba, względem której ma zostać zwrócony moduł $a $.</span><span class="sxs-lookup"><span data-stu-id="0be7d-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="0be7d-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0be7d-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="0be7d-112">Moduł $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="0be7d-112">The modulus $a \bmod b$.</span></span>