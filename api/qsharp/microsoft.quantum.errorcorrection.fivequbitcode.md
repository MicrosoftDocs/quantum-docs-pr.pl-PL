---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712343"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Zwraca wartość QECC reprezentującą ⟦ 5, 1, 3 ⟧ kodu kodera i dekodera z pomiarem Syndrome w miejscu.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Wynik: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Zwraca implementację kodu korekty błędu Quantum przez określenie `QECC` typu.

## <a name="remarks"></a>Uwagi

Ten kod został znaleziony niezależnie w następujących dwóch dokumentach:

- C. C. Bennett, D. DiVincenzo, J. A. Smolin i W. K. Wootters, "mieszane Stany Entanglement i Korekcja błędów Quantum," fizyczny. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 i
- ®. Laflamme, C. Miquel, J. P. Paz i W. H. Zurek, "doskonały kod korekcji błędów Quantum", "fizyczny. Rev. Lett. 77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019