---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853051"
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