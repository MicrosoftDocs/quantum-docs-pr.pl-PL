---
uid: Microsoft.Quantum.Synthesis.Extended
title: Funkcja rozszerzona
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855470"
---
# <a name="extended-function"></a><span data-ttu-id="ed861-102">Funkcja rozszerzona</span><span class="sxs-lookup"><span data-stu-id="ed861-102">Extended function</span></span>

<span data-ttu-id="ed861-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="ed861-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="ed861-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed861-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed861-105">Rozszerza spektrum przez odwrócone współczynniki</span><span class="sxs-lookup"><span data-stu-id="ed861-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="ed861-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ed861-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="ed861-107">spektrum: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ed861-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ed861-108">Współczynniki widma</span><span class="sxs-lookup"><span data-stu-id="ed861-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="ed861-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ed861-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ed861-110">Współczynniki, po których następuje odwrócona kopia</span><span class="sxs-lookup"><span data-stu-id="ed861-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="ed861-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="ed861-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```