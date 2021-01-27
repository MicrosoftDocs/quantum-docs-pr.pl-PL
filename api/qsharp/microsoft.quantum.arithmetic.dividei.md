---
uid: Microsoft.Quantum.Arithmetic.DivideI
title: DivideI, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: DivideI
qsharp.summary: Divides two quantum integers.
ms.openlocfilehash: 73c4e394ca38b8089b2990f8a8b6a3ee50f644d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846681"
---
# <a name="dividei-operation"></a><span data-ttu-id="d998a-102">DivideI, operacja</span><span class="sxs-lookup"><span data-stu-id="d998a-102">DivideI operation</span></span>

<span data-ttu-id="d998a-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d998a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d998a-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d998a-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d998a-105">Dzieli dwie liczby całkowite jednostek Quantum.</span><span class="sxs-lookup"><span data-stu-id="d998a-105">Divides two quantum integers.</span></span>

```qsharp
operation DivideI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d998a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d998a-106">Description</span></span>

<span data-ttu-id="d998a-107">`xs` pozostanie resztę `xs - floor(xs/ys) * ys` i `result` zostanie wstrzymane `floor(xs/ys)` .</span><span class="sxs-lookup"><span data-stu-id="d998a-107">`xs` will hold the remainder `xs - floor(xs/ys) * ys` and `result` will hold `floor(xs/ys)`.</span></span>

## <a name="input"></a><span data-ttu-id="d998a-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d998a-108">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="d998a-109">XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d998a-109">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d998a-110">$na dywidenda $-bitowa zostanie zastąpiona resztą.</span><span class="sxs-lookup"><span data-stu-id="d998a-110">$n$-bit dividend, will be replaced by the remainder.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="d998a-111">YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d998a-111">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d998a-112">$n dzielnika $-bitowego</span><span class="sxs-lookup"><span data-stu-id="d998a-112">$n$-bit divisor</span></span>


### <a name="result--littleendian"></a><span data-ttu-id="d998a-113">wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d998a-113">result : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d998a-114">wyniki $n $-bit muszą być w stanie $ \ket {0} $ początkowo i zostaną zastąpione przez wynik dzielenia liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="d998a-114">$n$-bit result, must be in state $\ket{0}$ initially and will be replaced by the result of the integer division.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d998a-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d998a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d998a-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d998a-116">Remarks</span></span>

<span data-ttu-id="d998a-117">Stosuje standardowe podejście Shift-and-odejmowanie do wdrożenia dzielenia.</span><span class="sxs-lookup"><span data-stu-id="d998a-117">Uses a standard shift-and-subtract approach to implement the division.</span></span>
<span data-ttu-id="d998a-118">Kontrolowana wersja jest wyspecjalizowana, co oznacza, że odejmowanie nie wymaga dodatkowych kontroli.</span><span class="sxs-lookup"><span data-stu-id="d998a-118">The controlled version is specialized such the subtraction does not require additional controls.</span></span>