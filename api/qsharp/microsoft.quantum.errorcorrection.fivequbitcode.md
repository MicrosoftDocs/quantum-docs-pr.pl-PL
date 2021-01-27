---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853141"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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