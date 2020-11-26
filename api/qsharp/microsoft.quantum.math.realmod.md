---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 20916d8462288395384aa875bfae4f042ba6b6ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228257"
---
# <a name="realmod-function"></a><span data-ttu-id="4441a-102">RealMod, funkcja</span><span class="sxs-lookup"><span data-stu-id="4441a-102">RealMod function</span></span>

<span data-ttu-id="4441a-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="4441a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="4441a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4441a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4441a-105">Oblicza moduł między dwoma liczbami rzeczywistymi.</span><span class="sxs-lookup"><span data-stu-id="4441a-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="4441a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4441a-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="4441a-107">wartość: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4441a-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4441a-108">Liczba rzeczywista $x $, aby pobrać moduł.</span><span class="sxs-lookup"><span data-stu-id="4441a-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="4441a-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4441a-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4441a-110">Liczba rzeczywista, która przyjmuje moduł $x $ w odniesieniu do.</span><span class="sxs-lookup"><span data-stu-id="4441a-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="4441a-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4441a-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4441a-112">Najmniejsza wartość, która ma zostać zwrócona przez tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="4441a-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="4441a-113">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4441a-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="4441a-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4441a-114">Remarks</span></span>

<span data-ttu-id="4441a-115">Ta funkcja oblicza moduł rzeczywisty, zawijając linię rzeczywistą wokół okręgu jednostki, a następnie wyszukując kąt w okręgu jednostki odpowiadającym danym wejściowym.</span><span class="sxs-lookup"><span data-stu-id="4441a-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="4441a-116">`minValue`Następnie dane wejściowe określają, gdzie należy wyciąć okrąg jednostkowy.</span><span class="sxs-lookup"><span data-stu-id="4441a-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>