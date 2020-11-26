---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ccef1bbf400e01800053777d0010acb7addaef53
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192489"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="6b906-102">QuantumWalkByQubitization, funkcja</span><span class="sxs-lookup"><span data-stu-id="6b906-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="6b906-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="6b906-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="6b906-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b906-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b906-105">Konwertuje odbicie w kodowaniu bloku w przeszukiwaniu Quantum.</span><span class="sxs-lookup"><span data-stu-id="6b906-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="6b906-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6b906-106">Description</span></span>

<span data-ttu-id="6b906-107">W `BlockEncodingReflection` odniesieniu do jednostki $U $, która koduje część operatora $H $ Interest, konwertuje ją na przeszukiwanie quantum $W $ zawierający spektrum $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="6b906-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="6b906-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6b906-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="6b906-109">blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="6b906-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="6b906-110">`BlockEncodingReflection`$U jednostkowe $ mają być konwertowane do przeszukiwania Quantum.</span><span class="sxs-lookup"><span data-stu-id="6b906-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="6b906-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="6b906-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="6b906-112">Proces Quantum przeprowadzi $W $ wspólnie z rejestrami `a` i `s` ten blok kodu $H $ i zawiera zakres $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="6b906-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="6b906-113">Odwołania</span><span class="sxs-lookup"><span data-stu-id="6b906-113">References</span></span>

- <span data-ttu-id="6b906-114">Symulacja hamiltonian przez Qubitization Guang przerywają Hao Low, Tomasz L. Czuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="6b906-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="6b906-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6b906-115">See Also</span></span>

- [<span data-ttu-id="6b906-116">Microsoft. Quantum. Symulacja. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="6b906-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="6b906-117">Microsoft. Quantum. Symulacja. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="6b906-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)