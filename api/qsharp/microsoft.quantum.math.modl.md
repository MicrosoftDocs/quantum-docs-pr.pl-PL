---
uid: Microsoft.Quantum.Math.ModL
title: ModL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 15b11a59d189aa881da9fb514cf0fe3bc9f20201
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723104"
---
# <a name="modl-function"></a><span data-ttu-id="1ff35-102">ModL, funkcja</span><span class="sxs-lookup"><span data-stu-id="1ff35-102">ModL function</span></span>

<span data-ttu-id="1ff35-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="1ff35-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="1ff35-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1ff35-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1ff35-105">Zwraca moduł liczby w odniesieniu do innej liczby.</span><span class="sxs-lookup"><span data-stu-id="1ff35-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="1ff35-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1ff35-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="1ff35-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1ff35-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1ff35-108">Dane wejściowe $a $, których moduł ma zostać zwrócony.</span><span class="sxs-lookup"><span data-stu-id="1ff35-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="1ff35-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1ff35-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1ff35-110">Liczba, względem której ma zostać zwrócony moduł $a $.</span><span class="sxs-lookup"><span data-stu-id="1ff35-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="1ff35-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="1ff35-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="1ff35-112">Moduł $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="1ff35-112">The modulus $a \bmod b$.</span></span>