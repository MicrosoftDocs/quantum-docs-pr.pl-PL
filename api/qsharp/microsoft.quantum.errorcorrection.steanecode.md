---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200479"
---
# <a name="steanecode-function"></a>SteaneCode, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wartość CSS reprezentującą ⟦ 7, 1, 3 ⟧ Steane Code Encoder i dekodera z pomiarem Syndrome w miejscu.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Dane wyjściowe: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Obiekt typu CSS, który gromadzi wszystkie istotne dane w celu kodowania i korekcji błędów dla kodu ⟦ 7, 1, 3 ⟧ Steane.

## <a name="remarks"></a>Uwagi

Ten kod został znaleziony w następującym dokumencie:

- A. Steane, "wiele zakłóceń cząsteczek i Korekcja błędów Quantum", proc. Roy. SOC. Lond. A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.