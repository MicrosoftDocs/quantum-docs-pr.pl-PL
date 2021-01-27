---
uid: Microsoft.Quantum.Intrinsic.Message
title: Message — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Message
qsharp.summary: Logs a message.
ms.openlocfilehash: 652e33de69ffb725f117db3beeffa66558776f49
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849376"
---
# <a name="message-function"></a><span data-ttu-id="cfa53-102">Message — funkcja</span><span class="sxs-lookup"><span data-stu-id="cfa53-102">Message function</span></span>

<span data-ttu-id="cfa53-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cfa53-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cfa53-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cfa53-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cfa53-105">Rejestruje komunikat.</span><span class="sxs-lookup"><span data-stu-id="cfa53-105">Logs a message.</span></span>

```qsharp
function Message (msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="cfa53-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cfa53-106">Input</span></span>

### <a name="msg--string"></a><span data-ttu-id="cfa53-107">msg: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cfa53-107">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cfa53-108">Komunikat, który ma zostać zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="cfa53-108">The message to be reported.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cfa53-109">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfa53-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cfa53-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cfa53-110">Remarks</span></span>

<span data-ttu-id="cfa53-111">Określone zachowanie tej funkcji jest zależne od symulatora, ale w większości przypadków dany komunikat zostanie zapisany w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="cfa53-111">The specific behavior of this function is simulator-dependent, but in most cases the given message will be written to the console.</span></span>