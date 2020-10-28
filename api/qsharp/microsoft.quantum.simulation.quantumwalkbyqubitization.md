---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725577"
---
# <a name="quantumwalkbyqubitization-function"></a><span data-ttu-id="7e973-102">QuantumWalkByQubitization, funkcja</span><span class="sxs-lookup"><span data-stu-id="7e973-102">QuantumWalkByQubitization function</span></span>

<span data-ttu-id="7e973-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="7e973-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="7e973-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e973-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e973-105">Konwertuje odbicie w kodowaniu bloku w przeszukiwaniu Quantum.</span><span class="sxs-lookup"><span data-stu-id="7e973-105">Converts a block-encoding reflection into a quantum walk.</span></span>

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a><span data-ttu-id="7e973-106">Opis</span><span class="sxs-lookup"><span data-stu-id="7e973-106">Description</span></span>

<span data-ttu-id="7e973-107">W `BlockEncodingReflection` odniesieniu do jednostki $U $, która koduje część operatora $H $ Interest, konwertuje ją na przeszukiwanie quantum $W $ zawierający spektrum $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="7e973-107">Given a `BlockEncodingReflection` represented by a unitary $U$ that encodes some operator $H$ of interest, converts it into a quantum walk $W$ containing the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="input"></a><span data-ttu-id="7e973-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7e973-108">Input</span></span>

### <a name="blockencoding--blockencodingreflection"></a><span data-ttu-id="7e973-109">blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span><span class="sxs-lookup"><span data-stu-id="7e973-109">blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)</span></span>

<span data-ttu-id="7e973-110">`BlockEncodingReflection`$U jednostkowe $ mają być konwertowane do przeszukiwania Quantum.</span><span class="sxs-lookup"><span data-stu-id="7e973-110">A `BlockEncodingReflection` unitary $U$ to be converted into a Quantum walk.</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="7e973-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="7e973-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="7e973-112">Proces Quantum przeprowadzi $W $ wspólnie z rejestrami `a` i `s` ten blok kodu $H $ i zawiera zakres $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.</span><span class="sxs-lookup"><span data-stu-id="7e973-112">A quantum walk $W$ acting jointly on registers `a` and `s` that block- encodes $H$, and contains the spectrum of $\pm e^{\pm i\sin^{-1}(H)}$.</span></span>

## <a name="references"></a><span data-ttu-id="7e973-113">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="7e973-113">References</span></span>

- <span data-ttu-id="7e973-114">Symulacja hamiltonian przez Qubitization Guang przerywają Hao Low, Tomasz L. Czuang https://arxiv.org/abs/1610.06546</span><span class="sxs-lookup"><span data-stu-id="7e973-114">Hamiltonian Simulation by Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546</span></span>

## <a name="see-also"></a><span data-ttu-id="7e973-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7e973-115">See Also</span></span>

- [<span data-ttu-id="7e973-116">Microsoft. Quantum. Symulacja. BlockEncoding</span><span class="sxs-lookup"><span data-stu-id="7e973-116">Microsoft.Quantum.Simulation.BlockEncoding</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [<span data-ttu-id="7e973-117">Microsoft. Quantum. Symulacja. BlockEncodingReflection</span><span class="sxs-lookup"><span data-stu-id="7e973-117">Microsoft.Quantum.Simulation.BlockEncodingReflection</span></span>](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)