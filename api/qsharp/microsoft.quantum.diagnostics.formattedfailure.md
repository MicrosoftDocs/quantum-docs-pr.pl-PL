---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712679"
---
# <a name="formattedfailure-function"></a><span data-ttu-id="d93aa-102">FormattedFailure, funkcja</span><span class="sxs-lookup"><span data-stu-id="d93aa-102">FormattedFailure function</span></span>

<span data-ttu-id="d93aa-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d93aa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d93aa-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d93aa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d93aa-105">Funkcja wewnętrzna używana do niepowodzenia z znaczącymi komunikatami o błędach.</span><span class="sxs-lookup"><span data-stu-id="d93aa-105">Internal function used to fail with meaningful error messages.</span></span>

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d93aa-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d93aa-106">Input</span></span>

### <a name="actual--t"></a><span data-ttu-id="d93aa-107">rzeczywista: 'T</span><span class="sxs-lookup"><span data-stu-id="d93aa-107">actual : 'T</span></span>




### <a name="expected--t"></a><span data-ttu-id="d93aa-108">Oczekiwano: 'T</span><span class="sxs-lookup"><span data-stu-id="d93aa-108">expected : 'T</span></span>




### <a name="message--string"></a><span data-ttu-id="d93aa-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d93aa-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>





## <a name="output--unit"></a><span data-ttu-id="d93aa-110">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d93aa-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d93aa-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d93aa-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d93aa-112">'C</span><span class="sxs-lookup"><span data-stu-id="d93aa-112">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d93aa-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d93aa-113">Remarks</span></span>

<span data-ttu-id="d93aa-114">Ta funkcja jest przeznaczona do emulowania przez środowiska uruchomieniowe symulacji, dlatego w celu umożliwienia przesyłania dalej sformatowanych sprzeczności.</span><span class="sxs-lookup"><span data-stu-id="d93aa-114">This function is intended to be emulated by simulation runtimes, so as to allow forwarding formatted contradictions.</span></span>