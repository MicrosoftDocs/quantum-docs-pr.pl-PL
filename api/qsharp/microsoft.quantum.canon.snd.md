---
uid: Microsoft.Quantum.Canon.Snd
title: SND — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205324"
---
# <a name="snd-function"></a><span data-ttu-id="d4706-102">SND — funkcja</span><span class="sxs-lookup"><span data-stu-id="d4706-102">Snd function</span></span>

<span data-ttu-id="d4706-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d4706-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d4706-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4706-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4706-105">Dana para zwraca jego drugi element.</span><span class="sxs-lookup"><span data-stu-id="d4706-105">Given a pair, returns its second element.</span></span>

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a><span data-ttu-id="d4706-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d4706-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="d4706-107">para: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="d4706-107">pair : ('T,'U)</span></span>

<span data-ttu-id="d4706-108">Krotka z dwoma elementami.</span><span class="sxs-lookup"><span data-stu-id="d4706-108">A tuple with two elements.</span></span>



## <a name="output--u"></a><span data-ttu-id="d4706-109">Wynik: ' U</span><span class="sxs-lookup"><span data-stu-id="d4706-109">Output : 'U</span></span>

<span data-ttu-id="d4706-110">Drugi element `pair` .</span><span class="sxs-lookup"><span data-stu-id="d4706-110">The second element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d4706-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d4706-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4706-112">'C</span><span class="sxs-lookup"><span data-stu-id="d4706-112">'T</span></span>

<span data-ttu-id="d4706-113">Typ pierwszego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="d4706-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="d4706-114">' U</span><span class="sxs-lookup"><span data-stu-id="d4706-114">'U</span></span>

<span data-ttu-id="d4706-115">Typ drugiego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="d4706-115">The type of the pair's second member.</span></span>