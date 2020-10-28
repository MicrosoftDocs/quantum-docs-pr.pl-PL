---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712180"
---
# <a name="steanecode-function"></a>SteaneCode, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Zwraca wartość CSS reprezentującą ⟦ 7, 1, 3 ⟧ Steane Code Encoder i dekodera z pomiarem Syndrome w miejscu.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Dane wyjściowe: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Obiekt typu CSS, który gromadzi wszystkie istotne dane w celu kodowania i korekcji błędów dla kodu ⟦ 7, 1, 3 ⟧ Steane.

## <a name="remarks"></a>Uwagi

Ten kod został znaleziony w następującym dokumencie:

- A. Steane, "wiele zakłóceń cząsteczek i Korekcja błędów Quantum", proc. Roy. SOC. Lond. A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.