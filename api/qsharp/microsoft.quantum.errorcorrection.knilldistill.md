---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853116"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="6ab8d-102">KnillDistill, operacja</span><span class="sxs-lookup"><span data-stu-id="6ab8d-102">KnillDistill operation</span></span>

<span data-ttu-id="6ab8d-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="6ab8d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="6ab8d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ab8d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ab8d-105">Implementuje algorytm Knillowania stanu Magic.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="6ab8d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6ab8d-106">Description</span></span>

<span data-ttu-id="6ab8d-107">Podajesz 15 przybliżonych kopii stanu Magic $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket {8} {1} \end{align}, $ $ zapewnia jedną kopię w wyższej jakości.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="6ab8d-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6ab8d-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="6ab8d-109">roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6ab8d-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6ab8d-110">Rejestr piętnastu qubits zawierający przybliżone kopie stanu Magic.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="6ab8d-111">Po zastosowaniu tej procedury dalszej `roughMagic[0]` kontroli będzie zawierać jeden wyższy poziom kopii, a reszta rejestru zostanie zresetowana do stanu $ \ket{00\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6ab8d-112">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6ab8d-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ab8d-113">Jeśli `true` , wówczas procedura zakończyła się pomyślnie i zostanie zaakceptowana kopia wyższej jakości.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="6ab8d-114">Jeśli `false` procedura zakończyła się niepowodzeniem, a stan rejestru powinien być traktowany jako niezdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ab8d-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6ab8d-115">Remarks</span></span>

<span data-ttu-id="6ab8d-116">Przestrzegamy algorytmu Knill.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="6ab8d-117">Jednak Obecna implementacja jest daleko przed optymalną, ponieważ używa zbyt wielu qubits.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="6ab8d-118">Stany Magic są wstrzykiwane w tej procedurze, w tym przypadku są to lepsze protokoły.</span><span class="sxs-lookup"><span data-stu-id="6ab8d-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="6ab8d-119">Odwołania</span><span class="sxs-lookup"><span data-stu-id="6ab8d-119">References</span></span>

- [<span data-ttu-id="6ab8d-120">Knill</span><span class="sxs-lookup"><span data-stu-id="6ab8d-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)