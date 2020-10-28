---
uid: Microsoft.Quantum.ErrorCorrection.BitFlipRecoveryFn
title: BitFlipRecoveryFn, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: BitFlipRecoveryFn
qsharp.summary: Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.
ms.openlocfilehash: dad90475b2506187282825e143b11adc5120f453
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712497"
---
# <a name="bitfliprecoveryfn-function"></a><span data-ttu-id="72921-102">BitFlipRecoveryFn, funkcja</span><span class="sxs-lookup"><span data-stu-id="72921-102">BitFlipRecoveryFn function</span></span>

<span data-ttu-id="72921-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="72921-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="72921-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72921-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72921-105">Funkcja dla operacji odzyskiwania Pauli dla danego pomiaru Syndrome przez wyszukiwanie w tabeli dla kodu przewrócenia ⟦ 3, 1, 1 ⟧.</span><span class="sxs-lookup"><span data-stu-id="72921-105">Function for recovery Pauli operations for given syndrome measurement by table lookup for the ⟦3, 1, 1⟧ bit flip code.</span></span>

```qsharp
function BitFlipRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="72921-106">Wynik: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="72921-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="72921-107">Funkcja typu `RecoveryFn` , która przyjmuje pomiar Syndrome `Result[]` i zwraca `Pauli[]` operacje, które korygują wykryty błąd.</span><span class="sxs-lookup"><span data-stu-id="72921-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operations that corrects the detected error.</span></span>

## <a name="see-also"></a><span data-ttu-id="72921-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="72921-108">See Also</span></span>

- [<span data-ttu-id="72921-109">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="72921-109">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)