---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712133"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Dekoder dla X części grupy stabilizatorów ⟦ 7, 1, 3 ⟧ Steane w kodzie Quantum.

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>Dane wejściowe

### <a name="syndrome--syndrome"></a>Syndrome: [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

Tablica Syndrome uzyskana z mierzenia częściowej klasy stabilizującej.



## <a name="output--pauli"></a>Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tablica operacji Pauli, która w przypadku zastosowania do zakodowanego systemu Quantum, koryguje błąd odpowiadający `syndrome` .

## <a name="remarks"></a>Uwagi

Wybrany dekoder używa właściwości CSS kodu ⟦ 7, 1, 3 ⟧ Steane Code, tj. poprawia liczbę błędów X i Z. Właściwość kodu jest, że lokalizacja X, odpowiednio, korekta z, ma zostać zastosowana, jest kodowaniem 3-bitowym X, odpowiednio, Z Syndrome, gdy jest traktowana jako liczba całkowita.

## <a name="references"></a>Dokumentacja

- D. Gottesman, "kody stabilizujące i Korekcja błędów Quantum", "Ph.D., Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)