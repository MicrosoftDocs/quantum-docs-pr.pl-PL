---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828273"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="d9038-102">FormattedFailure, funkcja</span><span class="sxs-lookup"><span data-stu-id="d9038-102">FormattedFailure function</span></span>

<span data-ttu-id="d9038-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d9038-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d9038-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9038-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9038-105">Funkcja wewnętrzna używana do niepowodzenia z znaczącymi komunikatami o błędach.</span><span class="sxs-lookup"><span data-stu-id="d9038-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d9038-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d9038-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="d9038-107">rzeczywista: 'T</span><span class="sxs-lookup"><span data-stu-id="d9038-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="d9038-108">Oczekiwano: 'T</span><span class="sxs-lookup"><span data-stu-id="d9038-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="d9038-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d9038-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="d9038-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9038-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d9038-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d9038-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9038-112">'C</span><span class="sxs-lookup"><span data-stu-id="d9038-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d9038-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d9038-113">Remarks</span></span>

<span data-ttu-id="d9038-114">Ta funkcja jest przeznaczona do emulowania przez środowiska uruchomieniowe symulacji, dlatego w celu umożliwienia przesyłania dalej sformatowanych sprzeczności.</span><span class="sxs-lookup"><span data-stu-id="d9038-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>