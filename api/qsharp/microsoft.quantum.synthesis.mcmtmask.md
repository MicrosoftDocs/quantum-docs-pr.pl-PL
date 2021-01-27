---
uid: Microsoft.Quantum.Synthesis.MCMTMask
title: MCMTMask typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: MCMTMask
qsharp.summary: >-
  A type to represent a multiple-controlled multiple-target Toffoli gate.

  The first integer is a bit mask for control lines.  Bit indexes which are set correspond to control line indexes.

  The second integer is a bit mask for target lines.  Bit indexes which are set correspond to target line indexes.

  The bit indexes of both integers must be disjoint.
ms.openlocfilehash: 50bec0f9aca95afab83491db6b742d1f0323371f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855378"
---
# <a name="mcmtmask-user-defined-type"></a>MCMTMask typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Typ reprezentujący wielokierunkową bramę Toffoli z wieloma lokalizacjami.

Pierwsza liczba całkowita jest maską bitową dla linii kontrolnych.  Ustawione indeksy bitowe odpowiadają indeksom wierszy sterowania.

Druga liczba całkowita jest maską bitową dla wierszy docelowych.  Ustawione indeksy bitowe odpowiadają indeksom wierszy docelowych.

Indeksy bitowe obu liczb całkowitych muszą być rozłączone.

```qsharp

newtype MCMTMask = (ControlMask : Int, TargetMask : Int);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="controlmask--int"></a>ControlMask: [int](xref:microsoft.quantum.lang-ref.int)


### <a name="targetmask--int"></a>TargetMask: [int](xref:microsoft.quantum.lang-ref.int)

