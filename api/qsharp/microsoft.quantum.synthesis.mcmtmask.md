---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 0d3ca12d55fa4b5e8332d50939954de29e39b715
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725498"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="82381-102">MCMTMask typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="82381-102">MCMTMask user defined type</span></span>

<span data-ttu-id="82381-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="82381-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="82381-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82381-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82381-105">Typ reprezentujący wielokierunkową bramę Toffoli z wieloma lokalizacjami.</span><span class="sxs-lookup"><span data-stu-id="82381-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="82381-106">Pierwsza liczba całkowita jest maską bitową dla linii kontrolnych.</span><span class="sxs-lookup"><span data-stu-id="82381-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="82381-107">Ustawione indeksy bitowe odpowiadają indeksom wierszy sterowania.</span><span class="sxs-lookup"><span data-stu-id="82381-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="82381-108">Druga liczba całkowita jest maską bitową dla wierszy docelowych.</span><span class="sxs-lookup"><span data-stu-id="82381-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="82381-109">Ustawione indeksy bitowe odpowiadają indeksom wierszy docelowych.</span><span class="sxs-lookup"><span data-stu-id="82381-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="82381-110">Indeksy bitowe obu liczb całkowitych muszą być rozłączone.</span><span class="sxs-lookup"><span data-stu-id="82381-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="82381-111">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="82381-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="82381-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82381-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="82381-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82381-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

