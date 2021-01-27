---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 18adf28b4e99c825f14e9271791ded069e687901
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837691"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>JordanWignerInputState typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format danych przesłanych od języka C# do Q # w celu reprezentowania przygotowania stanu początkowego znaczenie danych reprezentowane przez algorytm, który go otrzymuje.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

