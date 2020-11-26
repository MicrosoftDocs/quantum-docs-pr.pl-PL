---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: FiveQubitCodeRecoveryFn, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 47e8a74d3631be2209537679ec9786a8dab63c58
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200785"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="7073e-102">FiveQubitCodeRecoveryFn, funkcja</span><span class="sxs-lookup"><span data-stu-id="7073e-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="7073e-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7073e-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7073e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7073e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7073e-105">Zwraca funkcję, która mapuje Syndrome błędów do odpowiednich operatorów Pauliych w celu poprawienia błędów przez wyszukiwanie w tabeli dla kodu ⟦ 5, 1, 3 ⟧.</span><span class="sxs-lookup"><span data-stu-id="7073e-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="7073e-106">Wynik: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="7073e-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="7073e-107">Funkcja typu `RecoveryFn` , która przyjmuje pomiar Syndrome `Result[]` i zwraca `Pauli[]` operatory, które korygują wykryty błąd.</span><span class="sxs-lookup"><span data-stu-id="7073e-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="7073e-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7073e-108">Remarks</span></span>

<span data-ttu-id="7073e-109">Przez iterację wszystkich błędów wag $1 $ uzyskamy łącznie $3 \ Times 5 = 15 $ możliwe nieuproszczony Syndromes.</span><span class="sxs-lookup"><span data-stu-id="7073e-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="7073e-110">Wraz z tożsamością, tabela błędu i odpowiadające Syndrome są kompilowane.</span><span class="sxs-lookup"><span data-stu-id="7073e-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="7073e-111">Dla kodu 5 qubit ta tabela jest podawana: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0, 0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0, 0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ z $Y _i $ uzyskane przez dodanie $X _i $ i $Z _i $ Syndromes.</span><span class="sxs-lookup"><span data-stu-id="7073e-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="7073e-112">Należy zauważyć, że kolejność w odnośniku wyszukiwania tabeli jest wyrażana przez konwersję bitvectors na liczby całkowite (przy użyciu little endian).</span><span class="sxs-lookup"><span data-stu-id="7073e-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="7073e-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7073e-113">See Also</span></span>

- [<span data-ttu-id="7073e-114">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="7073e-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)