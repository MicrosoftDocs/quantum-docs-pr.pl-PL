---
title: Jordania-Wigner reprezentacja | Microsoft Docs
description: Jordania — dokumentacja koncepcji reprezentacji Wigner
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: f34233bc17ff68a9e04256959f8d79be2682c34f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184053"
---
# <a name="jordan-wigner-representation"></a>Jordania — reprezentacja Wigner

Podczas gdy druga Quantized Hamiltonians jest wygodnie reprezentowana w $a ^ \dagger $ (Tworzenie) i $a $ (Annihilation), te operacje nie są podstawowymi operacjami na komputerach Quantum.
W związku z tym, Jeśli wolimy wdrożyć je na komputerze z systemem Quantum, musimy zmapować operatory na macierze jednostkowe, które można zaimplementować na komputerze Quantum.
Reprezentacja Jordania – Wigner daje jedną taką mapę.
Jednak inne, takie jak Bravyi — reprezentacja Kitaev istnieje również i mają własne względne zalety i wady.
Główną zaletą reprezentacji Jordania-Wigner jest prostota.

Reprezentacja Jordania-Wigner jest prosta do przesłania do.
Należy odwołać się, że stan $ \ket{0}_j $ oznacza, że wartość obracająca się $j $ jest pusta i $ \ket{1}_j $ oznacza, że jest zajęta.
Oznacza to, że qubits może w naturalny sposób przechowywać zawód danego kręgu.
Następnie będziemy $a ^ \dagger_j \ket{0}_j = \ket{1}_j $ i $a ^ \dagger_j \ket{1}_j = $0.
Można łatwo sprawdzić, czy \begin{align} ^ \dagger_j & = \begin{bmatrix}0 & 1 \\\ 0 & 0 \end{bmatrix} = \frac{X_j + iY_j}{2}, \nonumber\\\\ a_j & = \begin{bmatrix}0 & 0 \\\ 1 & 0 \end{ bmatrix} = \frac{X_j-iY_j}{2}, \end{align}, gdzie $X _j $ i $Y _j $ są operatorami Pauli-$X $ i-$Y $ działającymi na qubit $j $.
Pokazuje to, że w przypadku pojedynczego kręgu można łatwo reprezentować operatory tworzenia i Annihilation w odniesieniu do macierzy jednostkowych, które są rozpoznawane przez komputery Quantum.
Należy pamiętać, że chociaż $X $ i $Y $ są jednostkowymi $a ^ \dagger $, a $a $ nie są.
Zobaczymy później, że to nie stanowi wyzwania dla symulacji.

Jeden z problemów, który pozostanie, że chociaż powyższa konstrukcja działa w przypadku pojedynczego kręgu, kończy się niepowodzeniem w przypadku systemów z co najmniej dwoma orbitals.
Ponieważ Fermions są antisymmetic, wiemy, że $a ^ \dagger_j a ^ \dagger_k =-a ^ \dagger_k a ^ \dagger_j $ dla dowolnego $j $ i $k $.
Jednak $ $ \left (\frac{X_j-iY_j}{2}\right) \left (\frac{X_k-iY_k}{2}\right) = \left (\frac{X_k-iY_k}{2}\right) \left (\frac{X_j-iY_j}{2}\right).
$ $ Innymi słowy, dwa operatory tworzenia nie przełączają się zgodnie z potrzebami.
Można to rozwiązać przy użyciu prostego, w przypadku nieeleganckiego sposobu.
Poprawka ma zwrócić uwagę, że operatorzy Pauli naturalnie nie współdziałają.
W szczególności $XZ =-ZX $ i $YZ =-ZY $.
W tym celu przeplatanie operatorów $Z $ do konstrukcji operatora pozwala na emulowanie poprawnej ochrony.
Pełna konstrukcja jest następująca: 

\begin{align} ^ \dagger_1 & = \left (\frac{X-iY}{2}\right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a ^ \dagger_2 & = Z\otimes\left (\frac{X-iY}{2}\right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1 ,\\\\ ^ \dagger_3 & = Z\otimes Z\otimes \left (\frac{X-iY}{2}\right) \otimes 1 \otimes \cdots \otimes 1,\\\\ & \vdots\\\\ \dagger_N & = Z\otimes Z\otimes Z\otimes Z \otimes \cdots Z\otimes \left (\frac{X-iY}{2}\right). \label{eq:JW} \end{align}

Warto również przedstawić Operatory liczbowe, $n _j $, w warunkach operatorów Pauli.
Thankfully, ciągi $Z $ operatory (nazywane ciągami Jordania-Wigner) anulują po wykonaniu tej podstawienia.
Po przeprowadzeniu tego wywołania (i odwołując się do $X _jY_j = iZ_j $) mamy{2}\begin{Equation} n_j = a ^ \dagger_j a_j = \frac{(1-Z_j)}.
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Konstruowanie Hamiltonians w Jordanii-Wigner reprezentacji

Po wywołaniu reprezentacji Jordania-Wigner przetłumaczenia hamiltonian na sumę operatorów Pauli jest prosta do przodu.
Po prostu należy zamienić wszystkie operatory $a ^ \dagger $ i $a $ w Fermionic hamiltonian na ciągi Pauli-operatory określone powyżej.
Gdy jedna z nich wykonuje tę podstawienie, istnieje tylko pięć klas warunków w hamiltonian.
Te pięć klas odpowiada różnym sposobom, w których można wybrać $p, q $ i $p, q, r, s $ w jednoczęściowej i dwóch terminologii w hamiltonian.
Te pięć klas, w przypadku $p > q > r > s $ i rzeczywista orbitals, są

\begin{align} H_ {PP} a_p ^ \dagger a_p & = \sum_p \frac{H_{PP}}{2}(1-Z_p)\\\\ H_ {pq} (a_p ^ \dagger a_q + a ^ \dagger_q a_p) & = \frac{H_{pq}}{2}\left (\prod_{j = q + 1} ^ {p-1} Z_j \right) \ Left (X_pX_q + Y_pY_q\right)\\\\ H_ {pqqp} n_p n_q & = \frac{H_{pqqp}}{4}\left (1-Z_p-Z_q + Z_pZ_q \right)\\\\ H_ {pqqr} & = \frac{H_{pqqr}}{2}\left (\prod_{j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r\right) \left (\frac{1-Z_q}{2}\right)\\\\ H_ {pqrs} & = \frac{H_{pqrs}}{8}\prod_{j = s + 1} ^ {r-1} Z_j\prod_ {k = q + 1} ^ {p-1} Z_k \Big (XXXX-XXYY + XYXY\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber\\\\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

Chociaż generowanie takich Hamiltonians jest wymagane tylko wtedy, gdy wymagają zastosowania tych reguł zamiennych, to nie byłoby możliwe w przypadku dużych cząsteczek, które mogą składać się z milionów Hamiltonianych warunków.
Alternatywnie możemy automatycznie skonstruować `JordanWignerEncoding`, uwzględniając `FermionHamiltonian` reprezentację hamiltonian.

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
