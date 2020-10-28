---
uid: Microsoft.Quantum.Math.InverseModI
title: InverseModI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: InverseModI
qsharp.summary: Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.
ms.openlocfilehash: 6efc9da5f5ebb64065a90e749daa629dc2dce9cf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723636"
---
# <a name="inversemodi-function"></a><span data-ttu-id="f4820-102">InverseModI, funkcja</span><span class="sxs-lookup"><span data-stu-id="f4820-102">InverseModI function</span></span>

<span data-ttu-id="f4820-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="f4820-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="f4820-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4820-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4820-105">Zwraca $b $, które $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="f4820-105">Returns $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>

```qsharp
function InverseModI (a : Int, modulus : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f4820-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f4820-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="f4820-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4820-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4820-108">Odwrócona liczba</span><span class="sxs-lookup"><span data-stu-id="f4820-108">The number being inverted</span></span>


### <a name="modulus--int"></a><span data-ttu-id="f4820-109">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4820-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4820-110">Moduł, zgodnie z którym liczby są odwrócone</span><span class="sxs-lookup"><span data-stu-id="f4820-110">The modulus according to which the numbers are inverted</span></span>



## <a name="output--int"></a><span data-ttu-id="f4820-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4820-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4820-112">Liczba całkowita $b $, taka jak $a \cdot b = 1 (\operatorname{mod} \texttt{Modulus}) $.</span><span class="sxs-lookup"><span data-stu-id="f4820-112">Integer $b$ such that $a \cdot b = 1 (\operatorname{mod} \texttt{modulus})$.</span></span>