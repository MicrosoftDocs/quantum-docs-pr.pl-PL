---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 73b031f1082d0a12975abad074b07184dcbabdbe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230025"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState, funkcja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca operację, która przygotowuje oczyszczanie danego stanu mieszanego.
"Oczyszczony stan mieszany" odnosi się do Stanów formularza | ψ ⟩ = Σi √ pi | i ⟩ | garbagei ⟩ określony przez wektor współczynników {pi}. Stany tego formularza można zmniejszyć do Stanów mieszanych ρ ≔ pi | i ⟩ ⟨ i | przez śledzenie w rejestrze "garbage" (oznacza to, że stan mieszany, który jest przekątną w oparciu o obliczenia).

Zobacz, https://arxiv.org/pdf/1805.03662.pdf?page=15 Aby uzyskać więcej dyskusji.

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Opis

Używa techniki Quantum ROM do reprezentowania danej macierzy gęstości, zwracając tę reprezentację jako operację przygotowania stanu.

W szczególności, podanej na liście $N $ współczynniki $ \ alpha_j $, ta funkcja zwraca operację, która używa techniki pamięci podręcznej Quantum w celu przygotowania przybliżenia $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ \begin{align}: \ sum_ {{j = 0} ^ {N-1} \ \rho {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $, gdzie każda $p _j $ jest przybliżeniem danego współczynnika $ \ alpha_j $, tak że $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ for each $j $.

Gdy przeszedł rejestr indeksów i rejestr qubits elementów bezużytecznych, we wstępnym stanie $ \ket {0} \ket{00\cdots 0} zwrócona operacja przygotowuje oba rejestry do oczyszczenia $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _j}, \end{align} $ $, takie jak resetowanie i cofanie przydziału rejestru elementów bezużytecznych, umożliwia przeprowadzenie żądanego przygotowania do poziomu błędu docelowego $ \epsilon

## <a name="input"></a>Dane wejściowe

### <a name="targeterror--double"></a>targetError: [Double](xref:microsoft.quantum.lang-ref.double)

Błąd elementu docelowego $ \epsilon $.


### <a name="coefficients--double"></a>współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]

Tablica współczynników $N $, określająca prawdopodobieństwo Stanów bazowych.
Liczby ujemne $-\ alpha_j $ będą traktowane jako dodatnie $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Wynik: [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Operacja, która przygotowuje $ \tilde \rho $ jako oczyszczanie do wspólnych indeksów i rejestrów elementów bezużytecznych.

## <a name="remarks"></a>Uwagi

Współczynniki przekazane do tej operacji są znormalizowane zgodnie z 1 normą, w taki sposób, że współczynniki są zawsze traktowane do opisywania prawidłowego rozkładu prawdopodobieństwa kategorii.

## <a name="references"></a>Odwołania

- Kodowanie elektronicznego spektrum w obwodach Quantum przy użyciu liniowej o złożoności T Babbush, Craig Gidney, Dominic W. Jagods, Nathana Wiebe, Jarrod McClean, Alexandru, Austin Fowlera, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. przygotowaniu. PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)