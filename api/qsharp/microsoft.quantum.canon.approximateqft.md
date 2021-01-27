---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850321"
---
# <a name="approximateqft-operation"></a><span data-ttu-id="336b0-102">ApproximateQFT, operacja</span><span class="sxs-lookup"><span data-stu-id="336b0-102">ApproximateQFT operation</span></span>

<span data-ttu-id="336b0-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="336b0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="336b0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="336b0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="336b0-105">Zastosuj przybliżoną transformację Quantum Fouriera (AQFT) do rejestru Quantum.</span><span class="sxs-lookup"><span data-stu-id="336b0-105">Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.</span></span>

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="336b0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="336b0-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="336b0-107">Odp.: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="336b0-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="336b0-108">Przybliżony parametr, który określa, na którym poziomie kontrolowane są obroty Z osi Z, które występują w obwodzie QFT.</span><span class="sxs-lookup"><span data-stu-id="336b0-108">approximation parameter which determines at which level the controlled Z-rotations that occur in the QFT circuit are pruned.</span></span>

<span data-ttu-id="336b0-109">Parametr przybliżenia a określa poziom oczyszczania obrotów Z, czyli ∈ {0.. n} i wszystkie rotacje Z 2π/2K, gdzie k>a są usuwane z obwodu QFT.</span><span class="sxs-lookup"><span data-stu-id="336b0-109">The approximation parameter a determines the pruning level of the Z-rotations, i.e., a ∈ {0..n} and all Z-rotations 2π/2ᵏ where k>a are removed from the QFT circuit.</span></span> <span data-ttu-id="336b0-110">Wiadomo, że w przypadku k >= log ₂ (n) + log ₂ (1/ε) + 3 jeden może być powiązany | | QFT-AQFT | |<ε.</span><span class="sxs-lookup"><span data-stu-id="336b0-110">It is known that for k >= log₂(n)+log₂(1/ε)+3 one can bound ||QFT-AQFT||<ε.</span></span>


### <a name="qs--bigendian"></a><span data-ttu-id="336b0-111">QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="336b0-111">qs : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="336b0-112">Rejestr Quantum o n qubits, do którego jest stosowana Przybliżona transformacja Quantum Fouriera.</span><span class="sxs-lookup"><span data-stu-id="336b0-112">quantum register of n qubits to which the Approximate Quantum Fourier Transform is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="336b0-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="336b0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="336b0-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="336b0-114">Remarks</span></span>

<span data-ttu-id="336b0-115">AQFT wymaga bram do rotacji z 2π/2K i Hadamard.</span><span class="sxs-lookup"><span data-stu-id="336b0-115">AQFT requires Z-rotation gates of the form 2π/2ᵏ and Hadamard gates.</span></span>

<span data-ttu-id="336b0-116">Założono, że dane wejściowe i wyjściowe są kodowane w kodowaniu big endian.</span><span class="sxs-lookup"><span data-stu-id="336b0-116">The input and output are assumed to be encoded in big endian encoding.</span></span>

## <a name="references"></a><span data-ttu-id="336b0-117">Odwołania</span><span class="sxs-lookup"><span data-stu-id="336b0-117">References</span></span>

- [<span data-ttu-id="336b0-118">*M. Roetteler, th. Beth*, Zastosuj. algebry aparatu. gmin. Comput. 19 (3): 177-193 (2008)</span><span class="sxs-lookup"><span data-stu-id="336b0-118"> *M. Roetteler, Th. Beth*, Appl. Algebra Eng. Commun. Comput. 19(3): 177-193 (2008) </span></span>](http://doi.org/10.1007/s00200-008-0072-2)
- [<span data-ttu-id="336b0-119">*D. Coppersmith* ArXiv: Quant-pH/0201067v1</span><span class="sxs-lookup"><span data-stu-id="336b0-119"> *D. Coppersmith* arXiv:quant-ph/0201067v1 </span></span>](https://arxiv.org/abs/quant-ph/0201067)