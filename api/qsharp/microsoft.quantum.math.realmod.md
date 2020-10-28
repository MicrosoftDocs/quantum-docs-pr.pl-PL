---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720405"
---
# <a name="realmod-function"></a><span data-ttu-id="de65b-102">RealMod, funkcja</span><span class="sxs-lookup"><span data-stu-id="de65b-102">RealMod function</span></span>

<span data-ttu-id="de65b-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="de65b-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="de65b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de65b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de65b-105">Oblicza moduł między dwoma liczbami rzeczywistymi.</span><span class="sxs-lookup"><span data-stu-id="de65b-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="de65b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="de65b-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="de65b-107">wartość: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de65b-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="de65b-108">Liczba rzeczywista $x $, aby pobrać moduł.</span><span class="sxs-lookup"><span data-stu-id="de65b-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="de65b-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de65b-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="de65b-110">Liczba rzeczywista, która przyjmuje moduł $x $ w odniesieniu do.</span><span class="sxs-lookup"><span data-stu-id="de65b-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="de65b-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de65b-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="de65b-112">Najmniejsza wartość, która ma zostać zwrócona przez tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="de65b-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="de65b-113">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="de65b-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="de65b-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="de65b-114">Remarks</span></span>

<span data-ttu-id="de65b-115">Ta funkcja oblicza moduł rzeczywisty, zawijając linię rzeczywistą wokół okręgu jednostki, a następnie wyszukując kąt w okręgu jednostki odpowiadającym danym wejściowym.</span><span class="sxs-lookup"><span data-stu-id="de65b-115">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="de65b-116">`minValue`Następnie dane wejściowe określają, gdzie należy wyciąć okrąg jednostkowy.</span><span class="sxs-lookup"><span data-stu-id="de65b-116">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>