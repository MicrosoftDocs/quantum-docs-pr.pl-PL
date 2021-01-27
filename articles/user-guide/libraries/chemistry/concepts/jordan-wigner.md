---
title: Reprezentacja Jordan-Wigner
description: Dowiedz się więcej na temat reprezentacji Jordan-Wigner, która mapuje operatory hamiltonian na macierze jednostkowe, które można łatwiej zaimplementować na komputerze Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 738c8262ea66b8a02ea7541e402953237dc2ea48
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844135"
---
# <a name="jordan-wigner-representation"></a>Reprezentacja Jordan-Wigner

Podczas gdy druga Quantized Hamiltonians jest wygodnie reprezentowana w $a ^ \dagger $ (Tworzenie) i $a $ (Annihilation), te operacje nie są podstawowymi operacjami na komputerach Quantum.
W związku z tym, Jeśli wolimy wdrożyć je na komputerze z systemem Quantum, musimy zmapować operatory na macierze jednostkowe, które można zaimplementować na komputerze Quantum.
Reprezentacja Jordania – Wigner daje jedną taką mapę.
Jednak inne, takie jak Bravyi — reprezentacja Kitaev istnieje również i mają własne względne zalety i wady.
Główną zaletą reprezentacji Jordan-Wigner jest prostota.

Reprezentacja Jordan-Wigner jest prosta do przesłania do.
Należy odwołać się, że stan $ \ket {0} _j $ oznacza, że $j "$" jest puste, a $ _j \ket $ {1} oznacza, że jest zajęta.
Oznacza to, że qubits może w naturalny sposób przechowywać zawód danego kręgu.
Następnie będziemy $a ^ \ dagger_j \ket {0} _j = \ket {1} _j $ i $a ^ \ dagger_j \ket {1} _j = $0.
Można łatwo sprawdzić, czy \begin{align} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} , \nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} , \end{align}, gdzie $X _j $ i $Y _j $ to operatory Pauli-$X $ i-$Y $ działające na qubit $j $.

>[!NOTE]
> W Q# stanie $ \ket {0} $ reprezentuje wartość + 1 eigenstate operatora $Z $. W niektórych obszarach fizyki $ \ket {0} $ reprezentuje stan ziemi niskiego zużycia energii, a w rezultacie-1 eigenstate operatora $Z $. W związku z tym niektóre formuły mogą różnić się od popularnej literatury.

W bibliotece chemii używamy $ \ket {0} $ do reprezentowania niezajętego kręgu.
Pokazuje to, że w przypadku pojedynczego kręgu można łatwo reprezentować operatory tworzenia i Annihilation w odniesieniu do macierzy jednostkowych, które są rozpoznawane przez komputery Quantum.
Należy pamiętać, że chociaż $X $ i $Y $ są jednostkowymi $a ^ \dagger $, a $a $ nie są.
Zobaczymy później, że to nie stanowi wyzwania dla symulacji.

Jeden z problemów, który pozostanie, że chociaż powyższa konstrukcja działa w przypadku pojedynczego kręgu, kończy się niepowodzeniem w przypadku systemów z co najmniej dwoma orbitals.
Ponieważ Fermions są antisymmetic, wiemy, że $a ^ \ dagger_j ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $ dla dowolnego $j $ i $k $.
Jednak $ $ \left (\frac{X_j-iY_j} {2} \right) \left (\frac{X_k-iY_k} {2} \right) = \left (\frac{X_k-iY_k} {2} \right) \left (\frac{X_j-iY_j} {2} \right).
$ $ Innymi słowy, dwa operatory tworzenia nie przełączają się zgodnie z potrzebami.
Można to rozwiązać przy użyciu prostego, w przypadku nieeleganckiego sposobu.
Poprawka ma zwrócić uwagę, że operatorzy Pauli naturalnie nie współdziałają.
W szczególności $XZ =-ZX $ i $YZ =-ZY $.
W tym celu przeplatanie operatorów $Z $ do konstrukcji operatora pozwala na emulowanie poprawnej ochrony.
Pełna konstrukcja jest następująca: 

\begin{align} a ^ \ dagger_1 &= \left (\frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1, { \\ \\ \ dagger_2 &= Z\otimes\left (\frac{X-iy} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_3 &= Z\otimes Z\otimes \left (\frac{X-iy} {2} \right) \otimes 1 \otimes \cdots \otimes 1, \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left (\frac{X-iy} \right {2} ). \label{eq:JW} \end{align}

Warto również przedstawić Operatory liczbowe, $n _j $, w odniesieniu do operatorów Pauli.
Thankfully, ciągi $Z $ operatory (znane jako ciągi Jordan-Wigner) anulują po wykonaniu tej podstawie.
Po przeprowadzeniu tego wywołania (i odwołujący się do $X _jY_j = iZ_j $) mamy \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} .
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Konstruowanie Hamiltonians w reprezentacji Jordan-Wigner

Po wywołaniu Jordan-Wigner reprezentację tłumaczenia hamiltonian na sumę operatorów Pauli jest prosta do przodu.
Po prostu należy zamienić wszystkie operatory $a ^ \dagger $ i $a $ w Fermionic hamiltonian na ciągi Pauli-operatory określone powyżej.
Gdy jedna z nich wykonuje tę podstawienie, istnieje tylko pięć klas warunków w hamiltonian.
Te pięć klas odpowiada różnym sposobom, w których można wybrać $p, q $ i $p, q, r, s $ w jednoczęściowej i dwóch terminologii w hamiltonian.
Te pięć klas, w przypadku $p>q>r>s $ i rzeczywista orbitals, są

\begin{align} H_ {PP} a_p ^ \dagger a_p &= \ sum_p \frac{H_ {PP}} {2} (1-Z_p) \\ \\ H_ {pq} (a_p ^ \dagger a_q + a ^ \ dagger_q a_p) &= \frac{H_ {pq}} {2} \left (\ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left (X_pX_q + Y_pY_q \right) \\ \\ H_ {pqqp} n_p n_q &= \frac{H_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{H_ {pqqr}} {2} \left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q} {2} \right) \\ \\ H_ {pqrs} &= \frac{H_ {pqrs}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (xxxx-XXYY + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

Chociaż generowanie takich Hamiltonians jest wymagane tylko wtedy, gdy wymagają zastosowania tych reguł zamiennych, to nie byłoby możliwe w przypadku dużych cząsteczek, które mogą składać się z milionów Hamiltonianych warunków.
Alternatywnie możemy automatycznie skonstruować `JordanWignerEncoding` podaną `FermionHamiltonian` reprezentację hamiltonian.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Po zbudowaniu Hamiltonians w tym formularzu możemy użyć hosta algorytmów symulacji Quantum do skompilowania dynamiki wygenerowanej przez $e ^ {-iHt} $ do sekwencji bram elementarnych (w przypadku niektórych użytkowników z możliwością zdefiniowania tolerancji błędów).
Omawiamy dwie najpopularniejsze metody dotyczące symulacji Quantum, qubitization i Trotter — formuł Suzuki, w dokumentacji dotyczącej algorytmów. Udostępniamy implementacje obu metod w bibliotece symulacji hamiltonian.
