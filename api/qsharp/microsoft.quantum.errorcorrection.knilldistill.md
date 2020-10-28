---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712278"
---
# <a name="knilldistill-operation"></a><span data-ttu-id="5f66e-102">KnillDistill, operacja</span><span class="sxs-lookup"><span data-stu-id="5f66e-102">KnillDistill operation</span></span>

<span data-ttu-id="5f66e-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="5f66e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="5f66e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5f66e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5f66e-105">Implementuje algorytm Knillowania stanu Magic.</span><span class="sxs-lookup"><span data-stu-id="5f66e-105">Implements the Knill magic state distillation algorithm.</span></span>

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a><span data-ttu-id="5f66e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5f66e-106">Description</span></span>

<span data-ttu-id="5f66e-107">Podajesz 15 przybliżonych kopii stanu Magic $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket {8} {1} \end{align}, $ $ zapewnia jedną kopię w wyższej jakości.</span><span class="sxs-lookup"><span data-stu-id="5f66e-107">Given 15 approximate copies of a magic state $$ \begin{align} \cos\frac{\pi}{8} \ket{0} + \sin \frac{\pi}{8} \ket{1} \end{align}, $$ yields one higher-quality copy.</span></span>

## <a name="input"></a><span data-ttu-id="5f66e-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5f66e-108">Input</span></span>

### <a name="roughmagic--qubit"></a><span data-ttu-id="5f66e-109">roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5f66e-109">roughMagic : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5f66e-110">Rejestr piętnastu qubits zawierający przybliżone kopie stanu Magic.</span><span class="sxs-lookup"><span data-stu-id="5f66e-110">A register of fifteen qubits containing approximate copies of a magic state.</span></span> <span data-ttu-id="5f66e-111">Po zastosowaniu tej procedury dalszej `roughMagic[0]` kontroli będzie zawierać jeden wyższy poziom kopii, a reszta rejestru zostanie zresetowana do stanu $ \ket{00\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="5f66e-111">Following application of this distillation procedure, `roughMagic[0]` will contain one higher-quality copy, and the rest of the register will be reset to the $\ket{00\cdots 0}$ state.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5f66e-112">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5f66e-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5f66e-113">Jeśli `true` , wówczas procedura zakończyła się pomyślnie i zostanie zaakceptowana kopia wyższej jakości.</span><span class="sxs-lookup"><span data-stu-id="5f66e-113">If `true`, then the procedure succeeded and the higher-quality copy should be accepted.</span></span> <span data-ttu-id="5f66e-114">Jeśli `false` procedura zakończyła się niepowodzeniem, a stan rejestru powinien być traktowany jako niezdefiniowany.</span><span class="sxs-lookup"><span data-stu-id="5f66e-114">If `false`, the procedure failed, and the state of the register should be considered undefined.</span></span>

## <a name="remarks"></a><span data-ttu-id="5f66e-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5f66e-115">Remarks</span></span>

<span data-ttu-id="5f66e-116">Przestrzegamy algorytmu Knill.</span><span class="sxs-lookup"><span data-stu-id="5f66e-116">We follow the algorithm of Knill.</span></span>
<span data-ttu-id="5f66e-117">Jednak Obecna implementacja jest daleko przed optymalną, ponieważ używa zbyt wielu qubits.</span><span class="sxs-lookup"><span data-stu-id="5f66e-117">However, the present implementation is far from being optimal, as it uses too many qubits.</span></span>
<span data-ttu-id="5f66e-118">Stany Magic są wstrzykiwane w tej procedurze, w tym przypadku są to lepsze protokoły.</span><span class="sxs-lookup"><span data-stu-id="5f66e-118">The magic states are injected in this routine, in which case there are better protocols.</span></span>

## <a name="references"></a><span data-ttu-id="5f66e-119">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="5f66e-119">References</span></span>

- [<span data-ttu-id="5f66e-120">Knill</span><span class="sxs-lookup"><span data-stu-id="5f66e-120">Knill</span></span>](https://arxiv.org/abs/quant-ph/0402171)