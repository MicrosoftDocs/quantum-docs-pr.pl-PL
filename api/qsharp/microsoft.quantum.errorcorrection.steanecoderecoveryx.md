---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: c90eac291ebe718d10377399184ad705bb51673e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824693"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX, funkcja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="references"></a>Odwołania

- D. Gottesman, "kody stabilizujące i Korekcja błędów Quantum", "Ph.D., Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)