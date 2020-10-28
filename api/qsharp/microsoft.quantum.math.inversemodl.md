---
uid: Microsoft.Quantum.Math.InverseModL
title: InverseModL, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModL
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: e7cb9e98cb0635c50162611f6a52c56027d4a5eb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723631"
---
# <a name="inversemodl-function"></a><span data-ttu-id="73852-102">InverseModL, funkcja</span><span class="sxs-lookup"><span data-stu-id="73852-102">InverseModL function</span></span>

<span data-ttu-id="73852-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="73852-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="73852-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="73852-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="73852-105">Zwraca $b $, które $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="73852-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModL (a : BigInt, modulus : BigInt) : BigInt
```


## <a name="input"></a><span data-ttu-id="73852-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="73852-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="73852-107">Odp.: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="73852-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="73852-108">Odwrócona liczba</span><span class="sxs-lookup"><span data-stu-id="73852-108">The number being inverted</span></span>


### <a name="modulus--bigint"></a><span data-ttu-id="73852-109">Moduł: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="73852-109">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="73852-110">Moduł, zgodnie z którym liczby są odwrócone</span><span class="sxs-lookup"><span data-stu-id="73852-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--bigint"></a><span data-ttu-id="73852-111">Dane wyjściowe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="73852-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="73852-112">Liczba całkowita $b $, taka jak $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="73852-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>