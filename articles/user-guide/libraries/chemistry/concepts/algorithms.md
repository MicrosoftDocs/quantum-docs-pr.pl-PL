---
title: Symulowanie hamiltonian Dynamics
description: Dowiedz się, jak używać formuł Trotter-Suzuki i qubitization do pracy z symulacjami hamiltonian.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: 299eb1484a697ad9d1577aabb44ccb61e908bae3
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834010"
---
# <a name="simulating-hamiltonian-dynamics"></a>Symulowanie hamiltonian Dynamics

Gdy hamiltonian jest wyrażona jako suma operatorów elementarnych, można następnie kompilować do podstawowych operacji bram przy użyciu hosta dobrze znanych technik.
Trzy efektywne podejścia obejmują: Trotter — Suzukie formuły, liniowe kombinacje unitaries i qubitization.
Wyjaśniono te trzy podejścia poniżej i przedstawiono konkretne Q# Przykłady sposobu wdrażania tych metod przy użyciu biblioteki symulacji hamiltonian.


## <a name="trottersuzuki-formulas"></a>Trotter — formuły Suzuki
Pomysłem za Trotter — formuły Suzuki są proste: wyrażenie hamiltonian jako sumę łatwego do symulowania Hamiltonians, a następnie przybliżenie całkowitego rozwoju jako sekwencji tych prostszych ewolucji.
W szczególności Let $H = \ sum_ {j = 1} ^ m H_j $ to hamiltonian.
Następnie $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, co oznacza, że jeśli $t \ll $1, błąd w tym przybliżeniu będzie nieznaczny.
Należy pamiętać, że jeśli $e ^ {-i H t} $ były zwykłą wartością wykładniczą, błąd w tym przybliżeniu nie będzie $O (m ^ 2 t ^ 2) $: wartość będzie równa zero.
Ten błąd występuje, ponieważ $e ^ {-iHt} $ jest operatorem wykładniczym i w związku z tym występuje błąd podczas korzystania z tej formuły ze względu na fakt, że $H _j $ warunki nie współpracownicy (*tj.*$H _j H_k \ne H_k H_j $).

Jeśli $t $ jest duże, Trotter — formuły Suzuki mogą być używane w celu dokładnego symulowania dynamiki przez podzielenie go na sekwencję krótkich etapów czasu.
Niech $r $ to liczba kroków podejmowanych w trakcie rozwoju czasu, więc każdy krok czasu jest wykonywany dla czasu $t/r $. Następnie mamy $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m ^ {-iH_j t/r} \ Right) ^ r + O (m ^ 2 t ^ 2/r), $ $, co oznacza, że jeśli $r $ skaluje jako $m ^ 2 t ^ 2/1/Epsilon $, błąd można wykonać z najwyżej $ \epsilon $ dla dowolnego $ \epsilon>$0.

Dokładniejsze przybliżenia mogą być kompilowane przez konstruowanie sekwencji wykładniczych operatorów w taki sposób, że warunki błędu anulują się.
Najprostsza taka formuła, druga Order Trotter-Suzuki Formula, przyjmuje postać $ $ U_2 (t) = \left (\ prod_ {j = 1} ^ {m} e ^ {-iH_j t/2R} \ prod_ {j = m} ^ 1 e ^ {-iH_j t/2R} \ Right) ^ r = e ^ {-iHt} + O (m ^ 3 t ^ 3/r ^ 2), $ $ błąd, który można wprowadzić poniżej $ \epsilon $ dla dowolnego $ \epsilon>$0, wybierając $r $ do skalowania jako $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.

Nawet formuły wyższego rzędu, w tym ($ 2K $) kolejność jednokierunkowa dla $k>$0, można utworzyć rekursywnie: $ $ U_ {2K} (t) = [U_ {2K-2} (s_k \~ t)] ^ 2 U_ {2K-2} ([1-4s_k] t) [U_ {2K-2} (s_k \~ t)] ^ 2 = e ^ {-iHt} + O ((m t) ^ {2K + 1}/r ^ {2K}), $ $ where $s _k = (4-4 ^ {1/(2K-1)}) ^ {-1} $.

Najprostszą jest następująca czwarta kolejność ($k = $2), pierwotnie wprowadzona przez Suzuki: $ $ U_4 (t) = [U_2 (s_2 \~ t)] ^ 2 U_2 ([1-4s_2] t) [U_2 (s_2 \~ t)] ^ 2 = e ^ {-iHt} + O (m ^ 5t ^ 5/r ^ 4), $ $, gdzie $s _2 = (4-4 ^ {1/3}) ^ {-1} $.
Ogólnie rzecz biorąc, szybkie i wysoce uporządkowane formuły mogą być w podobny sposób skonstruowane. jednak koszty wynikające z używania bardziej złożonych integratorów często są większe niż w czwartej kolejności w przypadku większości praktycznych problemów.

Aby powyższe strategie działały, musimy mieć metodę symulowania szerokiej klasy $e ^ {-iH_j t} $.
Najprostszą rodziną Hamiltonians i raczej najbardziej przydatną w tym miejscu może być operator Pauli.
Operatory Pauli można łatwo symulować, ponieważ mogą być ukośne przy użyciu operacji Clifford (które są bramami standardowymi w ramach przetwarzania Quantum).
Po przeprowadzeniu przekątnej ich eigenvalues można znaleźć, obliczając parzystość qubits, na której działają.

Na przykład $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ WHERE $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 \\\
        0 & e ^ {i t} & 0 & 0 \\\
        0 & 0 & e ^ {IT} & 0 \\\
        0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.
$ $ Tutaj, $e ^ {-iHt} \ket {00} = e ^ {IT} \ket {00} $ i $e ^ {-iHt} \ket {01} = e ^ {-IT} \ket {01} $, które mogą być widoczne bezpośrednio jako konsekwencja, że parzystość $0 $ jest $0 $, podczas gdy parzystość ciągu bitowego $1 $ to $1 $.

Wykładnicze operatory Pauli można zaimplementować bezpośrednio Q# przy użyciu <xref:microsoft.quantum.intrinsic.exp> operacji:
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

W przypadku Fermionic Hamiltonians, w której [dekompozycja Jordanii – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) , wygodnie mapuje hamiltonian na sumę operatorów Pauli.
Oznacza to, że powyższe podejście można łatwo dostosować do symulowania chemii.
Zamiast ręcznego zapętlenia wszystkich Paulich w reprezentacji Jordania-Wigner, poniżej przedstawiono prosty przykład sposobu działania takiej symulacji w ramach chemii.
Naszym punktem początkowym jest [kodowanie Jordania – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) Fermionic hamiltonian, wyrażone w kodzie jako wystąpienie `JordanWignerEncoding` klasy.

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

Ten format reprezentacji Wigner do Q# użycia przez algorytmy symulacji jest typem zdefiniowanym przez użytkownika `JordanWignerEncodingData` .
W programie Q# ten format jest przesyłany do wygodnej funkcji `TrotterStepOracle` , która zwraca operator zbliżający się czas i ewolucji przy użyciu Trotter — Integrator Suzuki, a także innych parametrów wymaganych do jego uruchomienia.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Ponadto ta implementacja stosuje pewne optymalizacje omówione w [symulacji struktury elektronicznej Hamiltonians przy użyciu komputerów Quantum](https://arxiv.org/abs/1001.3855) i [ulepszanie algorytmów Quantum dla chemii Quantum](https://arxiv.org/abs/1403.1539) w celu zminimalizowania liczby wymaganych rotacji z pojedynczej qubit, a także zmniejszenia błędów symulacji.

## <a name="qubitization"></a>Qubitization

Qubitization jest alternatywnym podejściem do symulacji, która używa koncepcji z przechodzenia Quantum do symulowania jednostek Quantum Dynamics.
Chociaż qubitization wymaga więcej qubits niż Trotter formuł, Metoda niesie obietnice zwiększenia optymalne skalowanie z czasem ewolucji i odporność na błędy.
Z tego względu jest to preferowana metoda symulowania hamiltonian Dynamics w ogólności i rozwiązywania problemu ze strukturą elektroniczną.

Na wysokim poziomie qubitization wykonuje się w następujący sposób.
Najpierw pozwól $H = \ sum_j h_j H_j $ dla jednostek jednostkowych i hermitian $H _j $ i $h _j \ge $0.
Wykonując parę odbicia, qubitization implementuje operator, który jest odpowiednikiem $ $W = e ^ {\Pm i \cos ^ {-1} (h/| h | _1)}, $ $ WHERE $ | H | _1 = \ sum_j | h_j | $.
Następny krok polega na przekroczeniu wartości eigenvalues operatora "from" z $e ^ {i\pm \cos ^ {-1} (E_k/| h | _1)} $, gdzie $E _k $ to eigenvalues $H $, $e ^ {-iE_k t} $.
Można to osiągnąć przy użyciu różnych metod przekształcania wartości pojedynczej klasy Quantum, w tym [przetwarzania sygnałów Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).

Alternatywnie, jeśli pożądane są tylko ilości statyczne (na przykład energia stanu ziemi hamiltonian), wystarcza do zastosowania [szacowania fazy](xref:microsoft.quantum.libraries.characterization) bezpośrednio do $W $, aby oszacować energię stanu ziemi z wyniku, przyjmując cosinus wyniku.
Jest to istotne, ponieważ umożliwia przekształcenie widma klasycznego, a nie użycie metody transformacji pojedynczej wartości.

Na bardziej szczegółowym poziomie implementacja qubitization wymaga dwóch podprocedur, które udostępniają interfejsy dla hamiltonian.
W przeciwieństwie do metod Trotter – Suzuki, te podprocedury są nie klasyczne, a ich implementacja będzie wymagała użycia logarithmically więcej qubits niż jest to wymagane dla symulacji opartej na Trotter.

Pierwsza podprocedura Quantum wykorzystywana przez qubitization jest nazywana $ \operatorname{Select} $ i jest zastosowana do uzyskania \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation}, gdzie każda $H _j $ jest przyjęta jako hermitian i jednostkowa.
Chociaż może to być restrykcyjne, należy odwołać, że operatory Pauli są hermitian i jednostkowe, a więc aplikacje, takie jak symulowanie chemii Quantum, naturalnie są w tej strukturze.
Operacja $ \operatorname{Select} $, prawdopodobnie Surprisingly, jest w rzeczywistości operacją odbicia.
Może to być widoczne z faktu, że $ \operatorname{Select} ^ 2 \ KET {j} \ket{\psi} = \ket{j} \ket{\psi} $, ponieważ każda $H _j $ jest jednostką i hermitian, a tym samym eigenvalues $ \Pm $1.

Druga podprocedura jest nazywana $ \operatorname{Prepare} $.
Podczas gdy operacja Select zapewnia spójny dostęp do każdego z hamiltonian warunków $H _j $ procedura Prepare zapewnia metodę uzyskiwania dostępu do współczynników $h _j $, \begin{Equation} \operatorname{Prepare}\ket {0} = \ sum_j \sqrt{\frac{h_j} {| H | _1}} \ket{j}.
\end{Equation} następnie przy użyciu wielokrotnie kontrolowanej bramy fazy, zobaczymy, że $ $ \Lambda\ket {0} ^ {\otimes n} = \begin{Cases} \- \ket{x} & \Text{if} x = 0 \\\
        \ket{x} & \Text{Otherwise} \end{cases}.
$$

Operacja $ \operatorname{Prepare} $ nie jest używana bezpośrednio w qubitization, ale raczej służy do implementowania odbicia o stanie, który $ \operatorname{Prepare} $ tworzy $ $ \begin{align} R &amp; = 1-2 \ operatorname {Prepare} \ket {0} \bra {0} \operatorname{Prepare} ^ {-1} \\ \\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^ {-1} .
\end{align} $ $

Operator przeszukiwania, $W $, może być wyrażony w postaci $ \operatorname{Select} $ i $R $ operacji as $ $ W = \operatorname{Select} R, $ $, który ponownie można zobaczyć, aby zaimplementować operatora, który jest równoważny (do isometry), aby $e ^ {\Pm i \cos ^ {-1} (h/| H | _1)} $.

Te podprocedury można łatwo skonfigurować w programie Q# .
Przykładowo Rozważmy proste qubit poprzecznie Ising hamiltonian, gdzie $H = X_1 + X_2 + Z_1 Z_2 $.
W takim przypadku kod implementujący Q# operację $ \operatorname{SELECT} $ jest wywoływany przez <xref:microsoft.quantum.canon.multiplexoperations> , podczas gdy operacja $ \operatorname{Prepare} $ może zostać zaimplementowana przy użyciu <xref:microsoft.quantum.preparation.preparearbitrarystate> .
Przykład, który obejmuje symulowanie modelu Hubbard, można znaleźć jako [ Q# przykład](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).

Ręczne określenie tych kroków dla dowolnego problemu chemicznego będzie wymagało dużej nakładu pracy, które można uniknąć przy użyciu biblioteki chemicznej.
Podobnie jak w przypadku algorytmu symulacji Trotter – Suzuki powyżej, `JordanWignerEncodingData` jest ona przenoszona do funkcji wygodnej, `QubitizationOracle` która zwraca operator Instruktaż, oprócz innych parametrów wymaganych do uruchomienia.

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

Co ważne, implementacja <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> ma zastosowanie do dowolnego Hamiltoniansu określonego jako liniowa kombinacja ciągów Pauli.
Wersja zoptymalizowana pod kątem symulacji chemicznej jest wywoływana przy użyciu <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle> .
Ta wersja jest zoptymalizowana pod kątem zminimalizowania liczby bram T wykorzystujących techniki omówione w temacie [kodowanie elektronicznych widm w obwodach Quantum przy użyciu liniowej złożoności T](https://arxiv.org/abs/1805.03662).
