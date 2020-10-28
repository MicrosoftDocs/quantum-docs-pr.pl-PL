---
uid: Microsoft.Quantum.ErrorCorrection.ApplyBitFlipEncoder
title: ApplyBitFlipEncoder, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: ApplyBitFlipEncoder
qsharp.summary: >-
  Private operation used to implement both the bit flip encoder and decoder.

  Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`. In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.
ms.openlocfilehash: 4d78cbb5892aabc600321185641bbf217bd4d745
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712516"
---
# <a name="applybitflipencoder-operation"></a><span data-ttu-id="141fa-102">ApplyBitFlipEncoder, operacja</span><span class="sxs-lookup"><span data-stu-id="141fa-102">ApplyBitFlipEncoder operation</span></span>

<span data-ttu-id="141fa-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="141fa-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="141fa-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="141fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="141fa-105">Operacja prywatna używana do implementowania zarówno kodera przerzucania bitowego, jak i dekodera.</span><span class="sxs-lookup"><span data-stu-id="141fa-105">Private operation used to implement both the bit flip encoder and decoder.</span></span>

<span data-ttu-id="141fa-106">Należy zauważyć, że ten koder może korzystać ze spójnego odzyskiwania w miejscu, w którym to przypadku będzie "przyczyną" błędu opisanego w stanie początkowym `auxQubits` .</span><span class="sxs-lookup"><span data-stu-id="141fa-106">Note that this encoder can make use of in-place coherent recovery, in which case it will "cause" the error described by the initial state of `auxQubits`.</span></span>
<span data-ttu-id="141fa-107">W szczególności, jeśli `auxQubits` są początkowo w stanie $ \ket {10} $, spowoduje to wystąpienie błędu $X _1 $ na zakodowanym qubit.</span><span class="sxs-lookup"><span data-stu-id="141fa-107">In particular, if `auxQubits` are initially in the state $\ket{10}$, this will cause an $X_1$ error on the encoded qubit.</span></span>

```qsharp
operation ApplyBitFlipEncoder (coherentRecovery : Bool, data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="141fa-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="141fa-108">Input</span></span>

### <a name="coherentrecovery--bool"></a><span data-ttu-id="141fa-109">coherentRecovery: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="141fa-109">coherentRecovery : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="data--qubit"></a><span data-ttu-id="141fa-110">dane: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="141fa-110">data : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="scratch--qubit"></a><span data-ttu-id="141fa-111">Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="141fa-111">scratch : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>





## <a name="output--unit"></a><span data-ttu-id="141fa-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="141fa-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="141fa-113">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="141fa-113">References</span></span>

- <span data-ttu-id="141fa-114">doi:10.1103/PhysRevA.85.044302</span><span class="sxs-lookup"><span data-stu-id="141fa-114">doi:10.1103/PhysRevA.85.044302</span></span>