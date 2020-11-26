---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 3c2debbb1f2019c7188dcb00f8ac09154fd4fd4f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203025"
---
# <a name="mcmtmask-user-defined-type"></a><span data-ttu-id="5912b-102">MCMTMask typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="5912b-102">MCMTMask user defined type</span></span>

<span data-ttu-id="5912b-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5912b-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5912b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5912b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5912b-105">Typ reprezentujący wielokierunkową bramę Toffoli z wieloma lokalizacjami.</span><span class="sxs-lookup"><span data-stu-id="5912b-105">A type to represent a multiple-controlled multiple-target Toffoli gate.</span></span>

<span data-ttu-id="5912b-106">Pierwsza liczba całkowita jest maską bitową dla linii kontrolnych.</span><span class="sxs-lookup"><span data-stu-id="5912b-106">The first integer is a bit mask for control lines.</span></span>  <span data-ttu-id="5912b-107">Ustawione indeksy bitowe odpowiadają indeksom wierszy sterowania.</span><span class="sxs-lookup"><span data-stu-id="5912b-107">Bit indexes which are set correspond to control line indexes.</span></span>

<span data-ttu-id="5912b-108">Druga liczba całkowita jest maską bitową dla wierszy docelowych.</span><span class="sxs-lookup"><span data-stu-id="5912b-108">The second integer is a bit mask for target lines.</span></span>  <span data-ttu-id="5912b-109">Ustawione indeksy bitowe odpowiadają indeksom wierszy docelowych.</span><span class="sxs-lookup"><span data-stu-id="5912b-109">Bit indexes which are set correspond to target line indexes.</span></span>

<span data-ttu-id="5912b-110">Indeksy bitowe obu liczb całkowitych muszą być rozłączone.</span><span class="sxs-lookup"><span data-stu-id="5912b-110">The bit indexes of both integers must be disjoint.</span></span>

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a><span data-ttu-id="5912b-111">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="5912b-111">Named Items</span></span>

### <a name="controlmask--int"></a><span data-ttu-id="5912b-112">ControlMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5912b-112">ControlMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>


### <a name="targetmask--int"></a><span data-ttu-id="5912b-113">TargetMask: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5912b-113">TargetMask : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

