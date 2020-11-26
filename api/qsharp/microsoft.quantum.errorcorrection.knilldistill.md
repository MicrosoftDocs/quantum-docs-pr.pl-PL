---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: KnillDistill, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: df00c7572d909a67ec658bc8dccaf0e338afe5c5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200751"
---
# <a name="knilldistill-operation"></a>KnillDistill, operacja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="references"></a>Odwołania

- [Knill](https://arxiv.org/abs/quant-ph/0402171)