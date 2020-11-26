---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 217ce4cd113ecbc6a06ed83c6c1dcb7baa46387d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195379"
---
# <a name="inversemodi-function"></a><span data-ttu-id="b2ea5-102">InverseModI, funkcja</span><span class="sxs-lookup"><span data-stu-id="b2ea5-102">InverseModI function</span></span>

<span data-ttu-id="b2ea5-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b2ea5-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b2ea5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2ea5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2ea5-105">Zwraca $b $, które $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="b2ea5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b2ea5-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b2ea5-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2ea5-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b2ea5-108">Odwrócona liczba</span><span class="sxs-lookup"><span data-stu-id="b2ea5-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="b2ea5-109">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2ea5-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b2ea5-110">Moduł, zgodnie z którym liczby są odwrócone</span><span class="sxs-lookup"><span data-stu-id="b2ea5-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="b2ea5-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2ea5-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b2ea5-112">Liczba całkowita $b $, taka jak $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="b2ea5-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>