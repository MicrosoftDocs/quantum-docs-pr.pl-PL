---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712278"
---
# <a name="knilldistill-operation"></a>KnillDistill, operacja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Implementuje algorytm Knillowania stanu Magic.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Opis

Podajesz 15 przybliżonych kopii stanu Magic $ $ \begin{align} \cos\frac{\pi} {8} \ket {0} + \sin \frac{\pi} \ket {8} {1} \end{align}, $ $ zapewnia jedną kopię w wyższej jakości.

## <a name="input"></a>Dane wejściowe

### <a name="roughmagic--qubit"></a>roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr piętnastu qubits zawierający przybliżone kopie stanu Magic. Po zastosowaniu tej procedury dalszej `roughMagic[0]` kontroli będzie zawierać jeden wyższy poziom kopii, a reszta rejestru zostanie zresetowana do stanu $ \ket{00\cdots 0} $.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

Jeśli `true` , wówczas procedura zakończyła się pomyślnie i zostanie zaakceptowana kopia wyższej jakości. Jeśli `false` procedura zakończyła się niepowodzeniem, a stan rejestru powinien być traktowany jako niezdefiniowany.

## <a name="remarks"></a>Uwagi

Przestrzegamy algorytmu Knill.
Jednak Obecna implementacja jest daleko przed optymalną, ponieważ używa zbyt wielu qubits.
Stany Magic są wstrzykiwane w tej procedurze, w tym przypadku są to lepsze protokoły.

## <a name="references"></a>Dokumentacja

- [Knill](https://arxiv.org/abs/quant-ph/0402171)