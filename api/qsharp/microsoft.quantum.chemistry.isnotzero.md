---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839602"
---
# <a name="isnotzero-function"></a><span data-ttu-id="e9826-102">IsNotZero, funkcja</span><span class="sxs-lookup"><span data-stu-id="e9826-102">IsNotZero function</span></span>

<span data-ttu-id="e9826-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e9826-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="e9826-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e9826-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="e9826-105">Sprawdza, czy `Double` liczba nie jest w przybliżeniu równa zero.</span><span class="sxs-lookup"><span data-stu-id="e9826-105">Checks whether a `Double` number is not approximately zero.</span></span>

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="e9826-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e9826-106">Input</span></span>

### <a name="number--double"></a><span data-ttu-id="e9826-107">Liczba: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e9826-107">number : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e9826-108">Liczba do sprawdzenia</span><span class="sxs-lookup"><span data-stu-id="e9826-108">Number to be checked</span></span>



## <a name="output--bool"></a><span data-ttu-id="e9826-109">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e9826-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e9826-110">Zwraca wartość true, jeśli `number` ma wartość bezwzględną większą niż `1e-15` .</span><span class="sxs-lookup"><span data-stu-id="e9826-110">Returns true if `number` has an absolute value greater than `1e-15`.</span></span>