---
uid: Microsoft.Quantum.Canon.Snd
title: SND — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c05053b45d24c3398526d1269b90bb40d1e0ef27
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715451"
---
# <a name="snd-function"></a><span data-ttu-id="b6981-102">SND — funkcja</span><span class="sxs-lookup"><span data-stu-id="b6981-102">Snd function</span></span>

<span data-ttu-id="b6981-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b6981-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b6981-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6981-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6981-105">Dana para zwraca jego drugi element.</span><span class="sxs-lookup"><span data-stu-id="b6981-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="b6981-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b6981-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="b6981-107">para: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="b6981-107">pair : ('T,'U)</span></span>

<span data-ttu-id="b6981-108">Krotka z dwoma elementami.</span><span class="sxs-lookup"><span data-stu-id="b6981-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="b6981-109">Wynik: ' U</span><span class="sxs-lookup"><span data-stu-id="b6981-109">Output : 'U</span></span>

<span data-ttu-id="b6981-110">Drugi element `pair` .</span><span class="sxs-lookup"><span data-stu-id="b6981-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b6981-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b6981-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b6981-112">'C</span><span class="sxs-lookup"><span data-stu-id="b6981-112">'T</span></span>

<span data-ttu-id="b6981-113">Typ pierwszego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="b6981-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="b6981-114">' U</span><span class="sxs-lookup"><span data-stu-id="b6981-114">'U</span></span>

<span data-ttu-id="b6981-115">Typ drugiego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="b6981-115">The type of the pair's second member.</span></span>