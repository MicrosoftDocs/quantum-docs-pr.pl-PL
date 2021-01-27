---
uid: Microsoft.Quantum.Math.ModL
title: ModL, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: f044ae16d93d31d0f28f5fcf076cff2bfef62eb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846841"
---
# <a name="modl-function"></a><span data-ttu-id="22536-102">ModL, funkcja</span><span class="sxs-lookup"><span data-stu-id="22536-102">ModL function</span></span>

<span data-ttu-id="22536-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="22536-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="22536-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="22536-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="22536-105">Zwraca moduł liczby w odniesieniu do innej liczby.</span><span class="sxs-lookup"><span data-stu-id="22536-105">Returns the modulus of a number with respect to another number.</span></span>

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="22536-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="22536-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="22536-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22536-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="22536-108">Dane wejściowe $a $, których moduł ma zostać zwrócony.</span><span class="sxs-lookup"><span data-stu-id="22536-108">The input $a$ whose modulus is to be returned.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="22536-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22536-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="22536-110">Liczba, względem której ma zostać zwrócony moduł $a $.</span><span class="sxs-lookup"><span data-stu-id="22536-110">The number with respect to which the modulus of $a$ is to be returned.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="22536-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="22536-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="22536-112">Moduł $a \bmod b $.</span><span class="sxs-lookup"><span data-stu-id="22536-112">The modulus $a \bmod b$.</span></span>