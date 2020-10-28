---
uid: Microsoft.Quantum.ErrorCorrection.RecoverCSS
title: RecoverCSS, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoverCSS
qsharp.summary: Performs a single round of error correction by a quantum code described by a `CSS` type.
ms.openlocfilehash: 48d3cd3d5f6aea265fac2f50b913ab855a31accf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712203"
---
# <a name="recovercss-operation"></a><span data-ttu-id="8650a-102">RecoverCSS, operacja</span><span class="sxs-lookup"><span data-stu-id="8650a-102">RecoverCSS operation</span></span>

<span data-ttu-id="8650a-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="8650a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="8650a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8650a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8650a-105">Wykonuje pojedynczą rundę korekcji błędów przez kod Quantum opisany przez `CSS` Typ.</span><span class="sxs-lookup"><span data-stu-id="8650a-105">Performs a single round of error correction by a quantum code described by a `CSS` type.</span></span>

```qsharp
operation RecoverCSS (code : Microsoft.Quantum.ErrorCorrection.CSS, fnX : Microsoft.Quantum.ErrorCorrection.RecoveryFn, fnZ : Microsoft.Quantum.ErrorCorrection.RecoveryFn, logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : Unit
```


## <a name="input"></a><span data-ttu-id="8650a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8650a-106">Input</span></span>

### <a name="code--css"></a><span data-ttu-id="8650a-107">kod: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span><span class="sxs-lookup"><span data-stu-id="8650a-107">code : [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)</span></span>

<span data-ttu-id="8650a-108">Błąd w formacie CSS Quantum — poprawianie kodu w pakiecie jako `CSS` Typ opisuje kodowanie i dekodowanie danych Quantum oraz sposób mierzenia błędu Syndromes.</span><span class="sxs-lookup"><span data-stu-id="8650a-108">A quantum CSS error-correcting code packaged as a `CSS` type describes the encoding and decoding of quantum data, and how error syndromes are to be measured.</span></span>


### <a name="fnx--recoveryfn"></a><span data-ttu-id="8650a-109">fnX: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="8650a-109">fnX : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="8650a-110">A `RecoveryFn` , który mapuje każdy $X $ Error Syndrome do `Pauli[]` operacji, które korygują wykryty błąd.</span><span class="sxs-lookup"><span data-stu-id="8650a-110">A `RecoveryFn` that maps each $X$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="fnz--recoveryfn"></a><span data-ttu-id="8650a-111">fnZ: [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="8650a-111">fnZ : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="8650a-112">A `RecoveryFn` , który mapuje każdy $Z $ Error Syndrome do `Pauli[]` operacji, które korygują wykryty błąd.</span><span class="sxs-lookup"><span data-stu-id="8650a-112">A `RecoveryFn` that maps each $Z$ error syndrome to the `Pauli[]` operations that correct the detected error.</span></span>


### <a name="logicalregister--logicalregister"></a><span data-ttu-id="8650a-113">logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="8650a-113">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="8650a-114">Tablica qubits, w której jest zdefiniowany kod stabilizatorów.</span><span class="sxs-lookup"><span data-stu-id="8650a-114">An array of qubits where the stabilizer code is defined.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8650a-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8650a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="8650a-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8650a-116">See Also</span></span>

- [<span data-ttu-id="8650a-117">Microsoft. Quantum. ErrorCorrection. CSS</span><span class="sxs-lookup"><span data-stu-id="8650a-117">Microsoft.Quantum.ErrorCorrection.CSS</span></span>](xref:Microsoft.Quantum.ErrorCorrection.CSS)
- [<span data-ttu-id="8650a-118">Microsoft. Quantum. ErrorCorrection. RecoveryFn</span><span class="sxs-lookup"><span data-stu-id="8650a-118">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)
- [<span data-ttu-id="8650a-119">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="8650a-119">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)