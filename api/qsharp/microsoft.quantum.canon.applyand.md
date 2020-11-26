---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: ApplyAnd, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: b749013584c89273375da002ac36b3575085b7f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219298"
---
# <a name="applyand-operation"></a>ApplyAnd, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Odwraca daną wartość docelową qubit, jeśli i tylko wtedy, gdy oba kontrolki qubits znajdują się w stanie 1, przy użyciu miary do wykonania sąsiedniej operacji.

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Odwraca, `target` czy i tylko wtedy, gdy obie kontrolki są 1, ale zakłada, że `target` jest w stanie 0.  Operacja ma wartość T-Count 4, T-Głębokość 2 i nie wymaga pomocnika qubit. w związku z tym może być preferowana operacja CCNOT, jeśli `target` jest ona znana jako 0.  Sąsiadująco z tą operacją jest oparte na pomiarach i nie wymaga żadnych bram T.

Kontrolowana aplikacja tej operacji nie wymaga pomocnika qubit, `2^c` `Rz` bram i nie jest zoptymalizowana pod kątem głębokości, gdzie `c` jest liczbą ogólnych formantów qubits, łącznie z dwoma kontrolkami z `ApplyAnd` operacji.  Aplikacja z możliwością `2^c - 1` `Rz` współdziałania wymaga bram (o kącie o podwójnym rozmiarze niesąsiadującej operacji), nie qubit pomocnika i nie jest zoptymalizowana pod kątem głębokości.

## <a name="input"></a>Dane wejściowe

### <a name="control1--qubit"></a>Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pierwszy formant qubit


### <a name="control2--qubit"></a>Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druga kontrolka qubit


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Docelowa qubit pomocnicza; musi być w stanie 0



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Odwołania

- Cody Nowak: "Nowa konstrukcja dla bramy Toffoli odpornej na uszkodzenia", biorev. obr. A 87, 022328, 2013 [ArXiv: 1212.5069](https://arxiv.org/abs/1212.5069) DOI: 10.1103/PhysRevA. 87.022328
- Craig Gidney: "Halving kosztów dodawania jednostek Quantum 2, strona 74, 2018 [ArXiv: 1709.06648](https://arxiv.org/abs/1709.06648) DOI: 10.1103/PhysRevA. 85.044302
- Mathias Soeken: "usługi Quantum Oracle obwodów i wzorzec dla Boże Narodzenie", [artykuł w blogu z 19 grudnia 2019](https://msoeken.github.io/blog_qac.html) (Uwaga: wyjaśnienie dotyczące wielu kontrolowanej konstrukcji)