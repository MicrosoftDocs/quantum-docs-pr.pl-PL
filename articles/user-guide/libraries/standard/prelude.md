---
title: Wewnętrzne operacje i funkcje w QDK
description: Dowiedz się więcej na temat wewnętrznych operacji i funkcji w QDK, w tym funkcji klasycznych, operacji związanych z jednostką, rotacją i pomiarem.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.prelude
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6ed5b1677a204b9425f229a3ea0855bb789f3f75
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857185"
---
# <a name="the-prelude"></a>Preludium #

Q#Kompilator i maszyny docelowe dołączone do zestawu Quantum Development Kit zapewniają zestaw funkcji wewnętrznych i operacji, które mogą być używane podczas pisania programów Quantum w systemie Q# .

## <a name="intrinsic-operations-and-functions"></a>Operacje i funkcje wewnętrzne ##

Operacje wewnętrzne zdefiniowane w bibliotece standardowej w przybliżeniu należą do jednej z kilku kategorii:

- Najważniejsze funkcje klasyczne, zebrane w <xref:Microsoft.Quantum.Core> przestrzeni nazw.
- Operacje reprezentujące unitaries złożone z [Clifford i $T $ bramy](xref:microsoft.quantum.concepts.qubit).
- Operacje reprezentujące rotacje różnych operatorów.
- Operacje implementujące pomiary.

Ze względu na to, że zestaw bram Clifford + $T $ jest [uniwersalny](xref:microsoft.quantum.concepts.multiple-qubits) dla przetwarzania Quantum, te operacje wystarczą do około wdrożenia dowolnego algorytmu Quantum w ramach niewielkiego błędu.
Dostarczając również rotacje, Q# pozwala programistie na działanie w ramach jednej biblioteki bramy qubit i CNOT. Ta biblioteka jest znacznie łatwiejsza, ponieważ nie wymaga od programisty bezpośredniego wyrażenia Clifford + $T $ dekompozycji i ponieważ istnieją wysoce wydajne metody kompilowania jednego qubit unitaries do Clifford i $T $ (zobacz [tutaj](xref:microsoft.quantum.more-information) , aby uzyskać więcej informacji).

Tam, gdzie to możliwe, operacje zdefiniowane w Preludium, które działają na qubits zezwala na stosowanie `Controlled` wariantu, w taki sposób, że maszyna docelowa wykona odpowiednią dekompozycję.

Wiele funkcji i operacji zdefiniowanych w tej części Preludium znajdują się w @"microsoft.quantum.intrinsic" przestrzeni nazw, w taki sposób, że większość Q# plików źródłowych będzie miała `open Microsoft.Quantum.Intrinsic;` dyrektywę natychmiast po wstępnej deklaracji przestrzeni nazw.
<xref:Microsoft.Quantum.Core>Przestrzeń nazw jest automatycznie otwierana, dzięki czemu funkcje takie jak <xref:Microsoft.Quantum.Core.Length> mogą być używane bez `open` instrukcji.

### <a name="common-single-qubit-unitary-operations"></a>Typowe operacje jednostkowe Single-Qubit ###

Preludium definiuje także wiele typowych [operacji pojedynczych qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).
Wszystkie te operacje umożliwiają zarówno `Controlled` funktory, jak i `Adjoint` .

#### <a name="pauli-operators"></a>Operatory Pauli ####

<xref:Microsoft.Quantum.Intrinsic.X>Operacja implementuje operator Pauli $X $.
Jest to czasami nazywane `NOT` bramą.
Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` .
Odnosi się do jednostki pojedynczej qubit:

\begin{Equation} \begin{bmatrix} 0 & 1 \\ \\ % fixme: obecnie używa ona hakera quadwhack.
1 & 0 \end{bmatrix} \end{Equation}

<xref:Microsoft.Quantum.Intrinsic.Y>Operacja implementuje operator Pauli $Y $.
Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` .
Odnosi się do jednostki pojedynczej qubit:

\begin{Equation} \begin{bmatrix} 0 &-i \\ \\ % fixme: obecnie korzysta to z hakerów quadwhack.
i & 0 \end{bmatrix} \end{Equation}

<xref:Microsoft.Quantum.Intrinsic.Z>Operacja implementuje operator Pauli $Z $.
Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` .
Odnosi się do jednostki pojedynczej qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: obecnie używa to hakera quadwhack.
0 &-1 \end{bmatrix} \end{Equation}

Zobaczymy, że te przekształcenia są zamapowane na [Bloch sfery](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (oś obrotu w każdym przypadku jest wyróżniona czerwony):

![Operacje Pauli zamapowane na sferę Bloch](~/media/prelude_pauliBloch.png)

Należy pamiętać, że zastosowanie tej samej bramy Pauli dwa razy do tego samego qubit powoduje anulowanie operacji (ponieważ teraz wykonano pełny obrót 2π (360 °) przez powierzchnię do kuli Bloch, a tym samym dociera do punktu początkowego. Pozwala to na poniższą tożsamość:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Może to być visualised w sferze Bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Inne Single-Qubit Cliffords ####

<xref:Microsoft.Quantum.Intrinsic.H>Operacja implementuje bramę Hadamard.
Ta zmiana polega na tym, że Pauli $X $ i $Z $ osi docelowej qubit, takich jak $H \ket {0} = \ket{+} \mathrel{: =} (\ket {0} + \ket {1} )/\sqrt {2} $ i $H \ket{+} = \ket {0} $.
Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` i odpowiada jednemu qubitemu jednostkom:

\begin{Equation} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ % fixme: obecnie jest to funkcja, która używa quadwhack.
1 &-1 \end{bmatrix} \end{Equation}

Brama Hadamard jest szczególnie ważna, ponieważ może służyć do tworzenia nadpozycji {0} Stanów $ \ket $ i $ \ket {1} $. W reprezentacji w sferze Bloch, najłatwiej jest traktować ją jako rotacja $ \ket{\psi} $ wokół osi x przez $ \pi $ RADIANS ($ 180 ^ \circ $), po której następuje rotacja (w prawo) wokół osi y przez $ \ pi/2 $ RADIANS ($ 90 ^ \circ $):

![Operacja Hadamard zamapowana na sferę Bloch](~/media/prelude_hadamardBloch.png)

<xref:Microsoft.Quantum.Intrinsic.S>Operacja implementuje bramę fazy $S $.
To jest pierwiastek kwadratowy macierzy Pauli $Z $ operacji.
Oznacza to, że $S ^ 2 = Z $.
Ma sygnaturę `(Qubit => Unit is Adj + Ctl)` i odpowiada jednemu qubitemu jednostkom:

\begin{Equation} \begin{bmatrix} 1 & 0 \\ \\ % fixme: obecnie używa to hakera quadwhack.
0 & i \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Rotacje ####

Oprócz operacji Pauli i Clifford powyżej, Q# Preludium oferuje różne sposoby wyrażania rotacji.
Zgodnie z opisem w [operacjach pojedynczego qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), możliwość rotacji jest niezwykle ważna dla algorytmów Quantum.

Zaczynamy od tego, że możemy wyrazić jakąkolwiek operację qubit za pomocą bram $H $ i $T $, gdzie $H $ jest operacją Hadamard, a gdzie \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ % fixme: obecnie korzysta z platformy Quad back/Swagger/docs/v1..
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} to jest pierwiastek kwadratowy <xref:Microsoft.Quantum.Intrinsic.S> operacji, na przykład $T ^ 2 = S $.
Brama $T $ jest zaimplementowana przez <xref:Microsoft.Quantum.Intrinsic.T> operację i ma sygnaturę `(Qubit => Unit is Adj + Ctl)` wskazującą, że jest operacją jednostkową na jednym qubit.

Mimo że jest to w zasadzie wystarczającej do opisywania dowolnej operacji pojedynczej qubit, różne maszyny docelowe mogą być bardziej wydajnymi reprezentacjami dla rotacji z operatorami Pauli, tak że Preludium zawiera różne sposoby convienentlynia takich rotacji.
Najbardziej podstawowe są <xref:Microsoft.Quantum.Intrinsic.R> operacje, które implementują obrót wokół określonej osi Pauli, \Begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} gdzie $ \sigma $ jest operatorem Pauli, $ \phi $ to kąt i gdzie $ \exp $ reprezentuje tablicę wykładniczą.
Ma sygnaturę `((Pauli, Double, Qubit) => Unit is Adj + Ctl)` , gdzie pierwsze dwie części danych wejściowych reprezentują klasyczne argumenty $ \sigma $ i $ \phi $, które są niezbędne do określenia operatora jednostkowego $R (\sigma, \phi) $.
Firma Microsoft może częściowo zastosować $ \sigma $ i $ \phi $, aby uzyskać operację, której typem jest moduł jednostki pojedynczej qubit.
Na przykład `R(PauliZ, PI() / 4, _)` ma typ `(Qubit => Unit is Adj + Ctl)` .

> [!NOTE]
> <xref:Microsoft.Quantum.Intrinsic.R>Operacja dzieli kąt wejścia na 2 i mnoży ją przez-1.
> W przypadku $Z $ rotacji oznacza to, że $ \ket {0} $ eigenstate jest obrócona o $-\phi/$2, a $ \ket {1} $ eigenstate jest obrócona o $ \phi/$2, tak aby $ \ket {1} $ eigenstate został obrócony przez $ \phi $ względem elementu $ \ket {0} $ eigenstate.
>
> W szczególności oznacza to, że `T` `R(PauliZ, PI() / 8, _)` różnią się tylko nieistotną [fazą globalną](xref:microsoft.quantum.glossary#global-phase).
> Z tego powodu $T $ jest czasami znane jako brama $ \frac{\pi} {8} $.
>
> Należy również pamiętać, że obracanie wokół siebie `PauliI` powoduje zastosowanie globalnej fazy $ \phi/$2. Chociaż takie fazy nie mają znaczenia, jak zostało to zatwierdzono w [dokumentach koncepcyjnych](xref:microsoft.quantum.concepts.qubit), są one istotne dla kontrolowanych `PauliI` rotacji.

W ramach algorytmów Quantum często warto wyrazić rotację jako ułamki dyadic, takie jak $ \phi = \pi k/2 ^ n $ dla niektórych $k \In \mathbb{Z} $ i $n \In \mathbb{N} $.
<xref:Microsoft.Quantum.Intrinsic.RFrac>Operacja implementuje obrót wokół określonej osi Pauli przy użyciu tej Konwencji.
Różni się od <xref:Microsoft.Quantum.Intrinsic.R> , że kąt obrotu jest określony jako dwa dane wejściowe typu `Int` interpretowane jako ułamek dyadic.
W tym celu `RFrac` ma sygnaturę `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)` .
Implementuje qubit jednostki $ \exp (\pi k \sigma/2 ^ n) $, gdzie $ \sigma $ jest matrycą Pauli odpowiadającą pierwszemu argumentowi, $k $ jest drugim argumentem, a $n $ to trzeci argument.
`RFrac(_,k,n,_)` jest taka sama jak `R(_,-πk/2^n,_)` ; należy zauważyć, że kąt jest *wartością ujemną* części ułamkowej.

<xref:Microsoft.Quantum.Intrinsic.Rx>Operacja implementuje obrót wokół osi Pauli $X $.
Ma sygnaturę `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rx(_, _)` jest taka sama jak `R(PauliX, _, _)` .

<xref:Microsoft.Quantum.Intrinsic.Ry>Operacja implementuje obrót wokół osi Pauli $Y $.
Ma sygnaturę `((Double, Qubit) => Unit is Adj + Ctl)` .
`Ry(_, _)` jest taka sama jak `R(PauliY,_ , _)` .

<xref:Microsoft.Quantum.Intrinsic.Rz>Operacja implementuje obrót wokół osi Pauli $Z $.
Ma sygnaturę `((Double, Qubit) => Unit is Adj + Ctl)` .
`Rz(_, _)` jest taka sama jak `R(PauliZ, _, _)` .

<xref:Microsoft.Quantum.Intrinsic.R1>Operacja implementuje obrót o podaną ilość około $ \ket {1} $, eigenstate $-$1 z $Z $.
Ma sygnaturę `((Double, Qubit) => Unit is Adj + Ctl)` .
`R1(phi,_)` jest taka sama, jak `R(PauliZ,phi,_)` i `R(PauliI,-phi,_)` .

<xref:Microsoft.Quantum.Intrinsic.R1Frac>Operacja implementuje rotację ułamkową o podaną ilość wokół elementu Z = 1 eigenstate.
Ma sygnaturę `((Int,Int, Qubit) => Unit is Adj + Ctl)` .
`R1Frac(k,n,_)` jest taka sama, jak `RFrac(PauliZ,-k.n+1,_)` i `RFrac(PauliI,k,n+1,_)` .

Poniżej przedstawiono przykład operacji obrotu (wokół osi Pauli $Z $, w tym wystąpieniu) zamapowanej na sferę Bloch:

![Operacja obrotu zamapowana na Bloch sferę](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operacje wykonywane przez wiele qubit ####

Oprócz operacji pojedynczych qubit, Preludium także definiuje kilka operacji qubit.

Po pierwsze, <xref:Microsoft.Quantum.Intrinsic.CNOT> operacja wykonuje standardowe kontrolowane `NOT` bramy, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 0 & \\ \\ 0 & 1 & 0 \end{bmatrix}.
\end{Equation} ma sygnaturę `((Qubit, Qubit) => Unit is Adj + Ctl)` reprezentującą, że $ \operatorname{CNOT} $ działa unitarily na dwóch indywidualnych qubits.
`CNOT(q1, q2)` jest taka sama jak `(Controlled X)([q1], q2)` .
Ponieważ `Controlled` Funktor umożliwia kontrolę nad rejestrem, używamy literału tablicowego, `[q1]` Aby wskazać, że chcemy tylko jedną kontrolkę.

<xref:Microsoft.Quantum.Intrinsic.CCNOT>Operacja wykonuje podwójnie sterowaną bramą, a także znaną jako bramę Toffoli.
Ma sygnaturę `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)` .
`CCNOT(q1, q2, q3)` jest taka sama jak `(Controlled X)([q1, q2], q3)` .

<xref:Microsoft.Quantum.Intrinsic.SWAP>Operacja zamienia Stany Quantum z dwóch qubitsów.
Oznacza to, że implementuje macierz jednostkową \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 & & 1 \\ \\ & 0 & 0 \\ \\ 0 & 0 & 0 1 \end{bmatrix}.
\end{Equation} ma sygnaturę `((Qubit, Qubit) => Unit is Adj + Ctl)` .
`SWAP(q1,q2)` jest odpowiednikiem `CNOT(q1, q2)` `CNOT(q2, q1)` , a następnie `CNOT(q1, q2)` .

> [!NOTE]
> Brama wymiany *nie* jest taka sama jak zmiana rozmieszczenia elementów zmiennej typu `Qubit[]` .
> Zastosowanie `SWAP(q1, q2)` powoduje zmianę stanu qubits, do którego odwołuje się `q1` i, i `q2` `let swappedRegister = [q2, q1];` tylko ma wpływ na sposób odwoływania się do tych qubits.
> Ponadto program `(Controlled SWAP)([q0], (q1, q2))` pozwala na `SWAP` spełnienie stanu qubit trzeciego, który nie może reprezentować przez ponowne rozmieszczenie elementów.
> Brama przełączenia kontrolowanego, znana także jako brama Fredkin, jest wystarczająco wydajna, aby obejmowała wszystkie klasyczne obliczenia.

Na koniec Preludium zawiera dwie operacje do reprezentowania wykładniczych operatorów wieloqubitowych Pauli.
<xref:Microsoft.Quantum.Intrinsic.Exp>Operacja wykonuje rotację na podstawie iloczynu Pauli macierzy. reprezentowane przez wieloqubitne \Begin{Equation} \operatorname{EXP} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} WHERE $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ jest sekwencją operatorów pojedyncze-qubit Pauli i gdzie $ \phi $ jest kątem.
`Exp`Obrót reprezentuje element $ \vec{\sigma} $ jako tablicę `Pauli` elementów, tak że ma on sygnaturę `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)` .

<xref:Microsoft.Quantum.Intrinsic.ExpFrac>Operacja wykonuje ten sam obrót przy użyciu notacji dyadic ułamek opisanej powyżej.
Ma sygnaturę `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)` .

> [!WARNING]
> Wartość wykładnicza iloczynu dwuczęściowego w operatorach Pauli nie jest taka sama jak iloczynów dwuczęściowych operatorów Pauli.
> Oznacza to, że $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Miary ###

Podczas mierzenia, wartość + 1 eigenvalue operatora jest mierzona jako `Zero` wynik i-1 eigenvalue do `One` wyniku.

> [!NOTE]
> Chociaż ta konwencja może wydawać się nieparzysta, ma dwie zalety.
> Najpierw poszanowanie wyniku $ \ket {0} $ jest reprezentowane przez `Result` wartość `Zero` , natomiast przestrzeganie $ \ket {1} $ odpowiada `One` .
> Następnie możemy napisać, że eigenvalue $ \lambda $ odpowiadający wynikowi $r $ to $ \lambda = (-1) ^ r $.

Operacje pomiarów nie obsługują ani `Adjoint` `Controlled` Funktor.

<xref:Microsoft.Quantum.Intrinsic.Measure>Operacja wykonuje wspólne pomiary co najmniej jednego qubits w określonym produkcie operatorów Pauli.
Jeśli macierz Pauli i tablica qubit mają różne długości, operacja kończy się niepowodzeniem.
`Measure` ma sygnaturę `((Pauli[], Qubit[]) => Result)` .

Należy zauważyć, że wspólne pomiary nie są takie same jak pomiary każdego qubit indywidualnie.
Rozważmy na przykład stan $ \ket {11} = \ket {1} \otimes \Ket {1} = X\otimes X \ket {00} $.
Pomiary $Z _0 $ i $Z _1 $ osobno, uzyskujemy wyniki $r _0 = $1 i $r _1 = $1.
Pomiar $Z _0 Z_1 $, jednak pobieramy pojedynczy wynik $r _ {\textrm{joint}}d = $0, co oznacza, że para wartości $ \ket {11} $ jest dodatnia.
Umieść inaczej: $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.
Ze względu na to, że pouczymy się *tylko* o tym, że dane z tego pomiaru są zgodne, wszystkie informacje o Quantum, reprezentowane w położeniu między stanem 2 2-qubit pozytywnej parzystości, $ \ket {00} $ i $ \ket {11} $, są zachowywane.
Ta właściwość będzie istotna w przyszłości, ponieważ omawiamy korekcję błędów.

Dla wygody Preludium również obejmuje dwie inne operacje do mierzenia qubits.
Najpierw ponieważ wykonywanie pomiarów qubit jest dość popularne, Preludium definiuje skrót dla tego przypadku.
<xref:Microsoft.Quantum.Intrinsic.M>Operacja mierzy operator Pauli $Z $ na jednym qubit i ma sygnaturę `(Qubit => Result)` .
`M(q)` jest równoważne `Measure([PauliZ], [q])`.

<xref:Microsoft.Quantum.Measurement.MultiM>Mierzy operator Pauli $Z $ *oddzielnie* na każdej tablicy qubits, zwracając *tablicę* `Result` wartości uzyskanych dla każdego qubit.
W niektórych przypadkach może to być zoptymalizowane. Ma sygnaturę ( `Qubit[] => Result[])` .
`MultiM(qs)` jest równoważne:

```qsharp
mutable rs = new Result[Length(qs)];
for (index in 0..Length(qs)-1)
{
    set rs[index] = M(qs[index]);
}
return rs;
```

## <a name="extension-functions-and-operations"></a>Funkcje i operacje rozszerzenia ##

Ponadto Preludium definiuje bogaty zestaw funkcji konwersji matematycznych i typów na poziomie platformy .NET do użycia w Q# kodzie.
Na przykład <xref:Microsoft.Quantum.Math> przestrzeń nazw definiuje użyteczne operacje, takie jak <xref:Microsoft.Quantum.Math.Sin> i <xref:Microsoft.Quantum.Math.Log> .
Implementacja udostępniona przez zestaw Quantum Development Kit używa klasycznej biblioteki klas .NET, co może wiązać się z dodatkową komunikacją między programami Quantum i ich klasycznymi sterownikami.
Chociaż nie ma to problemu dla lokalnego symulatora, może to być problem z wydajnością w przypadku korzystania z zdalnego symulatora lub rzeczywistego sprzętu jako maszyny docelowej.
Ten sam komputer docelowy może wyeliminować ten wpływ na wydajność, zastępując te operacje niektórymi wersjami, które są bardziej wydajne dla danego systemu.

### <a name="math"></a>Math ###

<xref:Microsoft.Quantum.Math>Przestrzeń nazw zawiera wiele przydatnych funkcji z [ `System.Math` klasy](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1&preserve-view=true)podstawowej biblioteki klas programu .NET.
Te funkcje mogą być używane w taki sam sposób jak inne Q# funkcje:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Gdzie metoda statyczna platformy .NET została przeciążona na podstawie typu argumentów, odpowiadająca Q# Funkcja jest oznaczona sufiksem wskazującym typ danych wejściowych:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Operacje bitowe ###

Na koniec <xref:Microsoft.Quantum.Bitwise> przestrzeń nazw zapewnia kilka przydatnych funkcji manipulowania liczbami całkowitymi za pomocą operatorów bitowych.
Na przykład <xref:Microsoft.Quantum.Bitwise.Parity> zwraca bitową parzystość liczby całkowitej jako inną liczbę całkowitą.
