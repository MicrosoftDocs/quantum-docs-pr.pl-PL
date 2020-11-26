---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 4eb55dd4fd8d78e4b5a9bb289dacfbdb3aa4beb8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199016"
---
# <a name="message-function"></a><span data-ttu-id="bff7e-102">Message — funkcja</span><span class="sxs-lookup"><span data-stu-id="bff7e-102">Message function</span></span>

<span data-ttu-id="bff7e-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="bff7e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="bff7e-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bff7e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bff7e-105">Rejestruje komunikat.</span><span class="sxs-lookup"><span data-stu-id="bff7e-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bff7e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bff7e-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="bff7e-107">msg: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bff7e-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bff7e-108">Komunikat, który ma zostać zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="bff7e-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bff7e-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bff7e-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bff7e-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bff7e-110">Remarks</span></span>

<span data-ttu-id="bff7e-111">Określone zachowanie tej funkcji jest zależne od symulatora, ale w większości przypadków dany komunikat zostanie zapisany w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="bff7e-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>