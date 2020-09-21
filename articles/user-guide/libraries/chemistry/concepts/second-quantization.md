---
title: Drugie podziału
description: Dowiedz się więcej na temat drugiego podejścia podziału do modelowania struktur elektronicznych w programowaniu Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835812"
---
# <a name="second-quantization"></a>Drugie podziału

Drugie podziału analizuje problem struktury elektronicznej przy użyciu innego obiektywu.
Zamiast przypisywania poszczególnych $Nów _e $ Electrons do określonego stanu (lub orbity), druga podziału śledzi każdą wartość rzutu i przechowuje informacje o tym, czy w każdym z nich jest obecny numer elektronów, i w tym samym czasie automatycznie zapewnia właściwości symetrii odpowiedniej funkcji Wave.
Jest to ważne, ponieważ umożliwia określenie modeli chemii Quantum bez konieczności symmetrizing stanu danych wejściowych (jak jest to wymagane dla fermions), a także, ponieważ druga podziału umożliwia symulowanie takich modeli przy użyciu małych komputerów Quantum.

Przykładem drugiego podziału w działaniu Przypuśćmy, że $ \ psi_0 \cdots \ psi_ {N-1} $ to orthonormal zestaw orbitals przestrzennych.
Te orbitals są wybrane do reprezentowania systemu tak dokładnie, jak to możliwe w ramach ograniczonego zestawu.
Typowym przykładem takich orbitals są niepodzielne orbitals, które tworzą eigenbasis dla atomów wodoru.
Ponieważ Electrons mają dwa stany pokrętła, dwa Electrons mogą być Crammed do każdego z nich.
Oznacza to, że poprawne Stany podstawowe mają postać $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ WHERE $ \uparrow $ i $ \downarrow $ są etykietami, które określają dwa eigenstates stopnia swobody.
Ten połączony indeks $ (j, \sigma) $ dla $ \sigma \In \{ \uparrow, \downarrow \} $ jest nazywany kręgiem, ponieważ przechowuje zarówno przestrzenne, jak i kąt obrotu.
W bibliotece chemii polecenie "orbitals" jest przechowywane w `SpinOrbital` strukturze danych i tworzone w następujący sposób.

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

Oznacza to, że możemy formalnie myśleć o podstawie dla elementu "obrót" i "przestrzenny" funkcji Wave jako $ \ psi_ {0} \cdots \ psi_ {2n-1} $, gdzie każdy indeks jest teraz wyliczeniem $ (j, \sigma) $.
Jedną z możliwych wyliczeniem jest $g (j, \sigma) = j + N\sigma ' $.
Kolejną możliwym wyliczeniem jest $h (j, \sigma) = 2 * j + \sigma $.
Biblioteka chemii Quantum może korzystać z tych konwencji, a w tym celu można utworzyć wystąpienie orbitals z takimi samymi kodowaniem.

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

W przypadku systemów fermionic zasada wykluczenia Pauli zapobiega obecności więcej niż jednego elementu elektronu w jednym punkcie obrotu w tym samym czasie.
Oznacza to, że możemy napisać dwa stany prawne dla $ \ psi_1 $ as \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket {0} _1 & \Text{if $ \ psi_1 $ nie jest zajmowana} \\\
\ket {1} _1 & \Text{if $ \ psi_1 $ jest zajęta.} \end{Cases} \end{Equation} to rozwiązanie jest doskonałe dla komputerów z systemem Quantum, ponieważ oznacza to, że firma Microsoft może przechowywać zawód elektroniczny jako pojedynczy bit Quantum.

Stany zawodności dla elementu $2N $ orbitals mogą być w podobny sposób przechowywane w $2N $ qubits.
Przykładowo, jeśli $N = $2, wówczas stan $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $

będzie odpowiadać za zajmowany przez pozostałe elementy orbitals $1 $ i $2 $.
Analogicznie, stan $ $ \ket {0} \equiv \ket {0} _ {0} \cdots \ket {0} _{N-1}, $ $

nie ma Electrons i jest znany jako "stan próżniowy".

Atrakcyjny efekt uboczny drugiego podziałuu polega na tym, że nie jest już konieczne jawne śledzenie przeciwsymetrii stanu Quantum.
Wynika to z faktu, że w miarę jak zobaczymy, że antysymetria stanu reprezentuje zamiast nich reguły ochrony przed współdziałaniem operatorów, które tworzą i niszczą działania elektroniczne z kręgu.

## <a name="fermionic-operators"></a>Operatory Fermionic

Dwa podstawowe operatory, które działają na podstawie wektorów drugiej Quantized są znane jako operatory tworzenia i Annihilation.
Te operatory wstawiają lub niszczą Electrons w określonej lokalizacji.
Są one oznaczone $a ^ \ dagger_j $ i $a _j $.

Na przykład \begin{align} a ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \quad a ^ \ dagger_1 \ket {1} _1 = 0, \quad A_1 \ket {0} _1 = 0, \quad A_1 \ket {1} _1 = \ket {0} _1.
\end{align} Pamiętaj, że w tym miejscu $a ^ \ dagger_1 \ket {1} _1 = 0 $ i $a _1 \ket _1 {0} $ Yield zero-Vector not $ \ket {0} _1 $.
W związku z tym operatory te nie hermitian ani nie są jednostkowe.
Reprezentujemy ogólne operatory tworzenia i Annihilation przy użyciu <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> typu.
Na przykład pojedynczy operator tworzenia jest reprezentowany jako poniżej.

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

Również przy użyciu takich operatorów możemy wyrazić $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}.
$ $ Tę sekwencję operatorów można utworzyć w bibliotece symulacji hamiltonian przy użyciu kodu C#, który jest podobny do wielkości dwukierunkowego obrotu w jednym miejscu, jak powyżej:
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

W przypadku systemu $k $ Fermions, w drugim podziału akcja operatora tworzenia $a ^ \ dagger_i $ jest określona przez $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ i $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $, gdzie $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ mierzy łączną liczbę Fermions, które są w stanie pojedynczej cząsteczek i mają indeks $j < i $.

Trzeci operator jest również często używany w drugim reprezentacje Quantized.
Ten operator jest znany jako operator Number i jest zdefiniowany przez \begin{Equation} n_i = a ^ \ dagger_i a_i.
\end{Equation} ten operator zlicza zawód danego kręgu, który ma na celu wypowiedzenie \begin{align} n_i \ket {0} _i &= 0 \ nonumber\\\
n_i \ket {1} _i &= \ket {1} _i.
\end{align} podobne do powyższych `FermionTerm` przykładów, ten operator liczby jest zbudowany w następujący sposób.
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

Subtlety powoduje, że w przypadku korzystania z operatorów tworzenia lub Annihilation w systemach fermionic.
Wymagane jest, aby wszystkie prawidłowe Stany Quantum były symetryczne w ramach wymiany etykiet.
Oznacza to, że $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 ^ \ dagger_2 \ket {0} .
$ $ Takie operatory są określane jako "leki" i ogólnie w odniesieniu do jakichkolwiek $i, j $ \begin{align} a ^ \ dagger_i ^ \ dagger_j =-(1-\ delta_ {i, j}) ^ \ dagger_j a ^ \ dagger_i, \quad ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.
\end{align} w ten sposób następujące dwa <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> wystąpienia są uznawane za nierównoważne
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

Wymaganie, aby każdy z operatorów tworzenia nie pozostały w przypadku, gdy przy użyciu drugiej reprezentacji quantizedu nie nastąpiły wyzwania w związku z Fermions.
Zamiast tego wyzwanie zostanie ponowione w naszej definicji operatorów tworzenia. 

Przy użyciu reguł antypoślizg niektóre `LadderSequence` wystąpienia rzeczywiście odpowiadają tej samej sekwencji operatorów fermionic, czasami do znaku minus.
Na przykład rozważmy hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.
W tym celu należy zdefiniować porządkowanie kanoniczne dla każdego z nich `FermionTerm` .
Wszystkie `FermionTerm` są automatycznie umieszczane w porządku kanonicznym w następujący sposób.
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a>Second-Quantized Fermionic hamiltonian

Być może unsurprising, że hamiltonian w [modelach Quantum dla systemów elektronicznych](xref:microsoft.quantum.chemistry.concepts.quantummodels) można napisać pod warunkiem tworzenia i operatorów Annihilation.
W szczególności, jeśli $ \psi \_ j $ to orbitals kręgosłupa, które tworzą podstawę

\begin{Equation} \hat{H} = \sum \_ {pq} h { \_ pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} h \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ RA \_ s + h \_ {\textrm}, NUC: \label{EQ} totalHam, gdzie $h \_ {\end{Equation} \textrm} $ to energia jądrowa (jest to stała w ramach przybliżania ponoszonego przez NUC) i

\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3 \_ , \end{align}

gdzie $V (x) $ jest potencjalną wartość pola i

\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x 2) \psi \_ \_ \_ \_ \_ . \ Label {EQ: całeks} \mathrm{d}

Warunki $h \_ {pq} $ są określane jako całki jednokolorowe, ponieważ wszystkie te warunki obejmują tylko jedną electronsę i podobnie $h \_ {pqrs} $ są całkowitymi częściami dwuskładnikowymi.
Są one nazywane całkami, ponieważ przetwarzanie wartości tych współczynników wymaga całkowitej liczby.
Te warunki elektronów opisują energię kinetyczną poszczególnych Electrons i ich interakcje z polami elektrycznymi jądra.
Całkowite całki elektronów z drugiej strony opisują interakcje między Electrons.

Intuition, co oznacza, że te warunki mogą być wydobyć od operatorów tworzenia i Annihilation, które składają się z każdego z nich.
Na przykład $h _ {pq} a ^ \ dagger_p a_q $ zawiera opis elektronów przeskoku od kręgu "$q" i "obracającą się $p $".
Podobnie termin $h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (dla różnych $p, q, r $ $) opisuje dwie Electrons w orbitals $r $ i $s $, a następnie kończy się w orbitalsu $p $ i $q $.
Jeśli $r = q $ i $p = s $ następnie $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ zapewnia karę energii skojarzoną z dwoma electronsami, ale nie opisują procesu dynamicznego.

Firma Microsoft może reprezentować takie Hamiltonians za pomocą `FermionHamiltonian` klasy, która jest zasadniczo listą zawierającą wszystkie żądane `FermionTerm` wystąpienia.
Ponieważ Hamiltonians są hermitian według definicji, indeksuje terminy przy użyciu bardziej wyspecjalizowanego typu, `HermitianFermionTerm` który również używa hermitian symetrii podczas sprawdzania, czy warunki są równoważne.

Pozwól nam skonstruować kilka przykładów przykładowych.
Rozważmy hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
Firma Microsoft może uprościć tę konstrukcję przy użyciu faktu, że operatory hamiltonian są operatorami hermitian.
W przypadku dodawania warunków do hamiltonian przy użyciu `Add` , każdy termin nieHermitian, taki jak, `fermionTerm0` przyjmuje się, że jest sparowany z jego sprzężeniem hermitian.
W ten sposób Poniższy fragment kodu reprezentuje również ten sam hamiltonian:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Korzystając z reguł antypoślizg, niektóre `FermionTerm` wystąpienia w hamiltonian rzeczywiście odpowiadają tej samej sekwencji operatorów fermionic, czasami do znaku minus.
Na przykład rozważmy hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, który jest sumą warunków zbudowanych powyżej.
Być może nie zawsze jest jasne, że użytkownik ma równoważne warunki i dlatego mogą być dodawane do hamiltonian oddzielnie.
Alternatywnie można chcieć zmodyfikować już istniejące warunki w hamiltonian.
W takich przypadkach firma Microsoft może łączyć równoważne warunki w następujący sposób.
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
Łącząc współczynniki równoważnego terminu, zmniejszamy łączną liczbę warunków w hamiltonian.
Później, zmniejsza to liczbę bram Quantum wymaganych do symulowania hamiltonian.

### <a name="internal-representation"></a>Reprezentacja wewnętrzna

Fermionic hamiltonian z jednym i dwoma interakcjami jest reprezentowana w notacji drugiej-Quantized jako

$ $ \begin{align} H = \sum \_ {pq} h \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s}.
\end{align} $ $

W tej notacji istnieje maksymalnie $N ^ 2 + N ^ 4 $.
Jednak wiele z tych współczynników może być zebranych w zależności od tego samego operatora.
Na przykład w przypadku, gdy $p, q, r, s $ są oddzielnymi indeksami, firma Microsoft może używać zasad ochrony antyszpiegowskiej, aby pokazać, że: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger {p} a { \_ \_ r} a { \_ s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} \_ = \_ % \dagger {q} a {\dagger \_ {p} a {s} \_ a { \_ r}.
$$

Ponadto, jako $H $ jest hermitian, każdy $h operator fermionic hermitian \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $, ma hermitian koniugat, który znajduje się również w $H $. W celu jednoznacznego indeksowania grup warunków scharakteryzowanych przez te symmetries definiujemy porządkowanie kanoniczne na indeksach $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) $ dowolnej sekwencji $n + m $ fermionic operatory $a ^ \dagger \_ {i \_ 1} \cdots \_ : ^ \dagger {i n \_ } a { \_ j 1 \_ } \cdots $AS \_ \_
-   Wszystkie operatory tworzenia $a ^ \dagger \_ {i \_ \cdot} $ są umieszczane przed wszystkimi operatorami Annihilation $a \_ {j \_ \cdot} $.
-   Wszystkie indeksy operatora tworzenia są sortowane w kolejności rosnącej, czyli $i \_ 1< i \_ 2< \cdots < i \_ n $.
-   Wszystkie indeksy operatora Annihilation są sortowane w kolejności malejącej, czyli $j \_ 1> j \_ 2 \cdots > j \_ m $.
-   Indeks z lewej strony jest mniejszy niż lub równy indeksowi najwyższego poziomu, który jest $i \_ 1 \ Le j \_ m $.

Daj nam zidentyfikować ten zestaw indeksów uporządkowanych w formie kanonicznej jako $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \In S \_ {n, m}.
\end{align} $ $

W tym porządku kanonicznym fermionic hamiltonian może być wyrażony jako $ $ \begin{align} H = \sum \_ {(p, q) \In S \_ {1,1} } H " \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \In s \_ {2,2} } godz." \_ {pqrs} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} + a ^ \dagger \_ {s} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $ z odpowiednio przystosowanymi $h " \_ {pq} $ i $h" \_ {pqrs} $ ".

