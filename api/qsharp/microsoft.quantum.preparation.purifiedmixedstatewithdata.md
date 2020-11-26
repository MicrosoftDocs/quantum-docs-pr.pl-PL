---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229957"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData, funkcja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca operację, która przygotowuje oczyszczanie danego stanu mieszanego, Entangled z rejestrem reprezentującym daną kolekcję danych.
"Oczyszczony stan mieszany z danymi" odnosi się do stanu formularza Σi √ pi | i ⟩ | XI ⟩ | garbagei ⟩, gdzie każda XI to bitstring kodowanie dodatkowych danych skojarzonych z rejestrem | i ⟩.

Zobacz, https://arxiv.org/pdf/1805.03662.pdf?page=15 Aby uzyskać więcej dyskusji.

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Opis

Używa techniki Quantum ROM do reprezentowania danej macierzy gęstości, zwracając tę reprezentację jako operację przygotowania stanu.

W szczególności, uwzględniając listę $N $ współwydajne $ \ alpha_j $ oraz bitstring $ \vec{x}_j $ skojarzone z każdym czynnikiem, ta funkcja zwraca operację wykorzystującą technikę pamięci podręcznej Quantum do przygotowania przybliżenia $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x}_j} \end{align} $ $ stanu mieszanego $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ Frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $, gdzie każda $p _j $ to przybliżenie do danego współczynnika $ \ alpha_j $ tak, że $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.

Gdy przeszedł rejestr indeksów i rejestr elementów bezużytecznych qubits, początkowo w stanie $ \ket {0} \ket{00\cdots 0}, zwrócona operacja przygotowuje oba rejestry do oczyszczenia $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _j} \ket{\text{garbage} _j}, \end{align} $ $, takich jak resetowanie i cofanie przydziału rejestru elementów bezużytecznych powoduje, że w przypadku błędu docelowego $ \epsilon $.

## <a name="input"></a>Dane wejściowe

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Błąd elementu docelowego $ \epsilon $.


### <a name="coefficients--doublebool"></a>współczynniki: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []

Tablica $N współczynników, określająca prawdopodobieństwo Stanów bazowych, wraz z bitstring $ \vec{x} _j $ skojarzonymi z każdym czynnikiem.
Liczby ujemne $-\ alpha_j $ będą traktowane jako dodatnie $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Wynik: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Operacja, która przygotowuje $ \tilde \rho $ jako oczyszczanie do wspólnych indeksów i rejestrów elementów bezużytecznych.

## <a name="remarks"></a>Uwagi

Współczynniki przekazane do tej operacji są znormalizowane zgodnie z 1 normą, w taki sposób, że współczynniki są zawsze traktowane do opisywania prawidłowego rozkładu prawdopodobieństwa kategorii.

## <a name="references"></a>Odwołania

- Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. przygotowaniu. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)