---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 36336f9e47e5f360cf5e19ffb6e15b4af88b2580
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850048"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="f3550-102">SyndromeMeasOp typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="f3550-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="f3550-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f3550-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f3550-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3550-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3550-105">Reprezentuje operację, która jest używana do mierzenia Syndrome w bloku kodu z korekcją błędów.</span><span class="sxs-lookup"><span data-stu-id="f3550-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="example"></a><span data-ttu-id="f3550-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="f3550-106">Example</span></span>

<span data-ttu-id="f3550-107">Zmierz Syndromes dla kodu bitowego $S = \langle ZZI, izz \rangle $ przy użyciu wartości "Scratch qubits" w sposób odporny na uszkodzenia:</span><span class="sxs-lookup"><span data-stu-id="f3550-107">Measure syndromes for the bit-flip code $S = \langle ZZI, IZZ \rangle$ using scratch qubits in a non–fault tolerant manner:</span></span>

```qsharp
    let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
            [PauliZ, PauliZ, PauliI],
            [PauliI, PauliZ, PauliZ]
        ], _, MeasureWithScratch));
```

## <a name="remarks"></a><span data-ttu-id="f3550-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f3550-108">Remarks</span></span>

<span data-ttu-id="f3550-109">Sygnatura `(LogicalRegister => Syndrome)` reprezentuje operację, która działa wspólnie na qubits w `LogicalRegister` i niektórych qubits pomocniczych, a następnie obejmuje pomiary qubits pomocniczych w celu wyodrębnienia `Syndrome` wartości reprezentującej `Result[]` te pomiary.</span><span class="sxs-lookup"><span data-stu-id="f3550-109">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3550-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f3550-110">See Also</span></span>

- [<span data-ttu-id="f3550-111">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="f3550-111">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="f3550-112">Microsoft. Quantum. ErrorCorrection. Syndrome</span><span class="sxs-lookup"><span data-stu-id="f3550-112">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)