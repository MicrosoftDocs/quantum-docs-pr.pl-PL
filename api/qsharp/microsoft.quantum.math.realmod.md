---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 56da313fabb20655ec358120b8d9b435e4971159
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848343"
---
# <a name="realmod-function"></a><span data-ttu-id="e3c8f-102">RealMod, funkcja</span><span class="sxs-lookup"><span data-stu-id="e3c8f-102">RealMod function</span></span>

<span data-ttu-id="e3c8f-103">Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="e3c8f-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="e3c8f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e3c8f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e3c8f-105">Oblicza moduł między dwoma liczbami rzeczywistymi.</span><span class="sxs-lookup"><span data-stu-id="e3c8f-105">Computes the modulus between two real numbers.</span></span>

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a><span data-ttu-id="e3c8f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e3c8f-106">Input</span></span>

### <a name="value--double"></a><span data-ttu-id="e3c8f-107">wartość: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3c8f-107">value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e3c8f-108">Liczba rzeczywista $x $, aby pobrać moduł.</span><span class="sxs-lookup"><span data-stu-id="e3c8f-108">A real number $x$ to take the modulus of.</span></span>


### <a name="modulo--double"></a><span data-ttu-id="e3c8f-109">modulo: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3c8f-109">modulo : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e3c8f-110">Liczba rzeczywista, która przyjmuje moduł $x $ w odniesieniu do.</span><span class="sxs-lookup"><span data-stu-id="e3c8f-110">A real number to take the modulus of $x$ with respect to.</span></span>


### <a name="minvalue--double"></a><span data-ttu-id="e3c8f-111">minValue: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3c8f-111">minValue : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e3c8f-112">Najmniejsza wartość, która ma zostać zwrócona przez tę funkcję.</span><span class="sxs-lookup"><span data-stu-id="e3c8f-112">The smallest value to be returned by this function.</span></span>



## <a name="output--double"></a><span data-ttu-id="e3c8f-113">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e3c8f-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="example"></a><span data-ttu-id="e3c8f-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="e3c8f-114">Example</span></span>

```qsharp
    // Returns 3 π / 2.
    let y = RealMod(5.5 * PI(), 2.0 * PI(), 0.0);
    // Returns -1.2, since +3.6 and -1.2 are 4.8 apart on the real line,
    // which is a multiple of 2.4.
    let z = RealMod(3.6, 2.4, -1.2);
```

## <a name="remarks"></a><span data-ttu-id="e3c8f-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e3c8f-115">Remarks</span></span>

<span data-ttu-id="e3c8f-116">Ta funkcja oblicza moduł rzeczywisty, zawijając linię rzeczywistą wokół okręgu jednostki, a następnie wyszukując kąt w okręgu jednostki odpowiadającym danym wejściowym.</span><span class="sxs-lookup"><span data-stu-id="e3c8f-116">This function computes the real modulus by wrapping the real line about the unit circle, then finding the angle on the unit circle corresponding to the input.</span></span>
<span data-ttu-id="e3c8f-117">`minValue`Następnie dane wejściowe określają, gdzie należy wyciąć okrąg jednostkowy.</span><span class="sxs-lookup"><span data-stu-id="e3c8f-117">The `minValue` input then effectively specifies where to cut the unit circle.</span></span>