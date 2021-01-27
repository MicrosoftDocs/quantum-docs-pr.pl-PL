---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: MultiplyByModularInteger, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846492"
---
# <a name="multiplybymodularinteger-operation"></a><span data-ttu-id="27621-102">MultiplyByModularInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="27621-102">MultiplyByModularInteger operation</span></span>

<span data-ttu-id="27621-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="27621-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="27621-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27621-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27621-105">Wykonuje mnożenie modularne przez stałą całkowitą w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="27621-105">Performs modular multiplication by an integer constant on a qubit register.</span></span>

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="27621-106">Opis</span><span class="sxs-lookup"><span data-stu-id="27621-106">Description</span></span>

<span data-ttu-id="27621-107">Poinformuj nas `modulus` o $N $ i `constMultiplier` $a $.</span><span class="sxs-lookup"><span data-stu-id="27621-107">Let us denote `modulus` by $N$ and `constMultiplier` by $a$.</span></span>
<span data-ttu-id="27621-108">Następnie ta operacja implementuje operacje jednostkowe zdefiniowane przez następującą mapę w oparciu o obliczenia: $ $ \begin{align} \ket{y} \mapsto \ket{(\cdot y) \operatorname{mod} N} \end{align} $ $ dla wszystkich $y $ między $0 $ i $N – $1.</span><span class="sxs-lookup"><span data-stu-id="27621-108">Then this operation implements a unitary operation defined by the following map on the computational basis: $$ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $$ for all $y$ between $0$ and $N - 1$.</span></span>

## <a name="input"></a><span data-ttu-id="27621-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="27621-109">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="27621-110">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27621-110">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27621-111">Stała, przez którą mnożnik jest mnożony.</span><span class="sxs-lookup"><span data-stu-id="27621-111">Constant by which multiplier is being multiplied.</span></span> <span data-ttu-id="27621-112">Musi być współdzielone z modułem.</span><span class="sxs-lookup"><span data-stu-id="27621-112">Must be co-prime to modulus.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="27621-113">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="27621-113">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="27621-114">Operacja mnożenia jest wykonywana modulo `modulus` .</span><span class="sxs-lookup"><span data-stu-id="27621-114">The multiplication operation is performed modulo `modulus`.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="27621-115">mnożnik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="27621-115">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="27621-116">Liczba pomnożona przez stałą.</span><span class="sxs-lookup"><span data-stu-id="27621-116">The number being multiplied by a constant.</span></span>
<span data-ttu-id="27621-117">Jest to tablica qubits kodowania liczby całkowitej w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="27621-117">This is an array of qubits encoding an integer in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27621-118">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27621-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="27621-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="27621-119">Remarks</span></span>

- <span data-ttu-id="27621-120">Aby zapoznać się ze schematem obwodu i wyjaśnieniem, zobacz rysunek 7 na [stronie 8 ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span><span class="sxs-lookup"><span data-stu-id="27621-120">For the circuit diagram and explanation see Figure 7 on [Page 8 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)</span></span>
- <span data-ttu-id="27621-121">Ta operacja odnosi się do p ₐ w [ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="27621-121">This operation corresponds to Uₐ in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>