---
title: Wewnętrzne operacje i funkcje w QDK
description: Dowiedz się więcej na temat wewnętrznych operacji i funkcji w QDK, w tym funkcji klasycznych, operacji związanych z jednostką, rotacją i pomiarem.
author: QuantumWriter
uid: microsoft.quantum.libraries.standard.prelude
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b1c26c632f36b6c254d940a89b13638f7592ab80
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907209"
---
# <a name="the-prelude"></a>Preludium #

Kompilator Q # i maszyny docelowe dołączone do zestawu Quantum Development Kit zapewniają zestaw funkcji wewnętrznych i operacji, które mogą być używane podczas pisania programów Quantum w Q #.

## <a name="intrinsic-operations-and-functions"></a>Operacje i funkcje wewnętrzne ##

Operacje wewnętrzne zdefiniowane w bibliotece standardowej w przybliżeniu należą do jednej z kilku kategorii:

- Najważniejsze funkcje klasyczne, zbierane w przestrzeni nazw <xref:microsoft.quantum.core>.
- Operacje reprezentujące unitaries złożone z [Clifford i $T $ bramy](xref:microsoft.quantum.concepts.qubit).
- Operacje reprezentujące rotacje różnych operatorów.
- Operacje implementujące pomiary.

Ze względu na to, że zestaw bram Clifford + $T $ jest [uniwersalny](xref:microsoft.quantum.concepts.multiple-qubits) dla przetwarzania Quantum, te operacje wystarczą do około wdrożenia dowolnego algorytmu Quantum w ramach niewielkiego błędu.
Dostarczając również rotacje, program Q # umożliwia programistom współpracę w ramach jednej biblioteki bramy qubit i CNOT. Ta biblioteka jest znacznie łatwiejsza, ponieważ nie wymaga od programisty bezpośredniego wyrażenia Clifford + $T $ dekompozycji i ponieważ istnieją wysoce wydajne metody kompilowania jednego qubit unitaries do Clifford i $T $ (zobacz [tutaj](xref:microsoft.quantum.more-information) , aby uzyskać więcej informacji).

Tam, gdzie to możliwe, operacje zdefiniowane w Preludium, które działają na qubits zezwala na stosowanie wariantu `Controlled`, w taki sposób, że maszyna docelowa wykona odpowiednią dekompozycję.

Wiele funkcji i operacji zdefiniowanych w tej części Preludium znajdują się w przestrzeni nazw @"microsoft.quantum.intrinsic", w taki sposób, że większość plików źródłowych Q # będzie miała `open Microsoft.Quantum.Intrinsic;` dyrektywy bezpośrednio po wstępnej deklaracji przestrzeni nazw.
Przestrzeń nazw <xref:microsoft.quantum.core> jest automatycznie otwierana, dzięki czemu funkcje takie jak <xref:microsoft.quantum.core.length> mogą być używane bez instrukcji `open`.

### <a name="common-single-qubit-unitary-operations"></a>Typowe operacje jednostkowe pojedynczego qubit ###

Preludium definiuje także wiele typowych [operacji pojedynczych qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).
Wszystkie te operacje umożliwiają zarówno `Controlled`, jak i `Adjoint` funktory.

#### <a name="pauli-operators"></a>Operatory Pauli ####

Operacja <xref:microsoft.quantum.intrinsic.x> implementuje operatora Pauli $X $.
Jest to czasami nazywane bramą `NOT`.
Ma `(Qubit => Unit is Adj + Ctl)`podpisu.
Odnosi się do jednostki pojedynczej qubit:

\begin{Equation} \begin{bmatrix} 0 & 1 \\\\% FIXME: obecnie używa to hakera quadwhack.
1 & 0 \end{bmatrix} \end{Equation}

Operacja <xref:microsoft.quantum.intrinsic.y> implementuje operatora Pauli $Y $.
Ma `(Qubit => Unit is Adj + Ctl)`podpisu.
Odnosi się do jednostki pojedynczej qubit:

\begin{Equation} \begin{bmatrix} 0 &-i \\\\% FIXME: obecnie korzysta to z.
i & 0 \end{bmatrix} \end{Equation}

Operacja <xref:microsoft.quantum.intrinsic.z> implementuje operatora Pauli $Z $.
Ma `(Qubit => Unit is Adj + Ctl)`podpisu.
Odnosi się do jednostki pojedynczej qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: obecnie używa to hakera quadwhack.
0 &-1 \end{bmatrix} \end{Equation}

Zobaczymy, że te przekształcenia są zamapowane na [Bloch sfery](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere) (oś obrotu w każdym przypadku jest wyróżniona czerwony):

![Operacje Pauli zamapowane na sferę Bloch](~/media/prelude_pauliBloch.png)

Należy pamiętać, że zastosowanie tej samej bramy Pauli dwa razy do tego samego qubit powoduje anulowanie operacji (ponieważ teraz wykonano pełny obrót 2π (360 °) przez powierzchnię do kuli Bloch, a tym samym dociera do punktu początkowego. Pozwala to na poniższą tożsamość:

$ $ X ^ 2 = Y ^ 2 = Z ^ 2 = \boldone $ $

Może to być visualised w sferze Bloch:

![XX = I](~/media/prelude_blochIdentity.png)

#### <a name="other-single-qubit-cliffords"></a>Inne pojedyncze qubit Cliffords ####

Operacja <xref:microsoft.quantum.intrinsic.h> implementuje bramę Hadamard.
Ta zmiana polega na tym, że Pauli $X $ i $Z $ osi docelowej qubit, takich jak $H \ket{0} = \ket{+} \mathrel{: =} (\ket{0} + \ket{1})/\sqrt{2}$ i $H \ket{+} = \ket{0}$.
Ma `(Qubit => Unit is Adj + Ctl)`podpisu i odpowiada jednemu z jednostek qubit:

\begin{Equation} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\% FIXME: obecnie jest to e.
1 &-1 \end{bmatrix} \end{Equation}

Brama Hadamard jest szczególnie ważna, ponieważ może służyć do tworzenia nadpozycji $ \ket{0}$ i $ \ket{1}$ States. W reprezentacji w sferze Bloch, najłatwiej jest traktować ją jako rotacja $ \ket{\psi} $ wokół osi x przez $ \pi $ RADIANS ($ 180 ^ \circ $), po której następuje rotacja (w prawo) wokół osi y przez $ \ pi/2 $ RADIANS ($ 90 ^ \circ $):

![Operacja Hadamard zamapowana na sferę Bloch](~/media/prelude_hadamardBloch.png)

Operacja <xref:microsoft.quantum.intrinsic.s> implementuje bramę fazy $S $.
To jest pierwiastek kwadratowy macierzy Pauli $Z $ operacji.
Oznacza to, że $S ^ 2 = Z $.
Ma `(Qubit => Unit is Adj + Ctl)`podpisu i odpowiada jednemu z jednostek qubit:

\begin{Equation} \begin{bmatrix} 1 & 0 \\\\% FIXME: obecnie używa to hakera quadwhack.
0 & i \end{bmatrix} \end{Equation}

#### <a name="rotations"></a>Obrotów ####

Oprócz powyższych operacji Pauli i Clifford, Q # Preludium oferuje różne sposoby wyrażania rotacji.
Zgodnie z opisem w [operacjach pojedynczego qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations), możliwość rotacji jest niezwykle ważna dla algorytmów Quantum.

Zaczynamy od tego, że możemy wyrazić jakąkolwiek operację qubit za pomocą bram $H $ i $T $, gdzie $H $ jest operacją Hadamard i gdzie \begin{Equation} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\\\% FIXME
0 & e ^ {i \pi/4} \end{bmatrix} \end{Equation} to jest pierwiastek kwadratowy operacji <xref:microsoft.quantum.intrinsic.s>, taki, który $T ^ 2 = S $.
Brama $T $ jest zaimplementowana przez operację <xref:microsoft.quantum.intrinsic.t> i ma `(Qubit => Unit is Adj + Ctl)`sygnatury, co oznacza, że jest operacją jednostkową na jednym qubit.

Mimo że jest to zasadniczo wystarczające do opisywania dowolnej operacji pojedynczej qubit, różne maszyny docelowe mogą być bardziej wydajnymi reprezentacjami dla rotacji o operatory Pauli, tak że Preludium zawiera różne sposoby convienently wyrażanie takich rotacji.
Najbardziej podstawowe są następujące operacje <xref:microsoft.quantum.intrinsic.r>, które implementują obrót wokół określonej osi Pauli, \begin{Equation} R (\sigma, \phi) \mathrel{: =} \exp (-i \phi \sigma/2), \end{Equation} gdzie $ \sigma $ jest operatorem Pauli, $ \phi $ to kąt i gdzie $ \exp $ reprezentuje wartość wykładniczą macierzy.
Ma `((Pauli, Double, Qubit) => Unit is Adj + Ctl)`podpisu, gdzie pierwsze dwie części danych wejściowych reprezentują klasyczne argumenty $ \sigma $ i $ \phi $, które są niezbędne do określenia operatora jednostkowego $R (\sigma, \phi) $.
Firma Microsoft może częściowo zastosować $ \sigma $ i $ \phi $, aby uzyskać operację, której typem jest moduł jednostki pojedynczej qubit.
Na przykład `R(PauliZ, PI() / 4, _)` ma `(Qubit => Unit is Adj + Ctl)`typu.

> [!NOTE]
> Operacja <xref:microsoft.quantum.intrinsic.r> dzieli kąt wejścia na 2 i mnoży ją przez-1.
> W przypadku $Z $ rotacji oznacza to, że $ \ket{0}$ eigenstate jest obrócona o $-\phi/$2, a $ \ket{1}$ eigenstate jest obrócona o $ \phi/$2, tak aby $ \ket{1}$ eigenstate został obrócony przez $ \phi $ względem elementu $ \ket{0}$ eigenstate.
>
> W szczególności oznacza to, że `T` i `R(PauliZ, PI() / 8, _)` różnią się tylko nieistotną [fazą globalną](xref:microsoft.quantum.glossary#global-phase).
> Z tego powodu $T $ jest czasami znany jako $ \frac{\pi}{8}$-bramę.
>
> Należy również pamiętać, że obracanie wokół `PauliI` po prostu stosuje globalną fazę $ \phi/$2. Chociaż takie fazy nie mają znaczenia, jak zostało to zatwierdzono w [dokumentach koncepcyjnych](xref:microsoft.quantum.concepts.qubit), są one istotne dla kontrolowanych `PauliI` obrotu.

W ramach algorytmów Quantum często warto wyrazić rotację jako ułamki dyadic, takie jak $ \phi = \pi k/2 ^ n $ dla niektórych $k \In \mathbb{Z} $ i $n \In \mathbb{N} $.
Operacja <xref:microsoft.quantum.intrinsic.rfrac> implementuje rotację wokół określonej osi Pauli przy użyciu tej Konwencji.
Różni się od <xref:microsoft.quantum.intrinsic.r> w tym, że kąt obrotu jest określony jako dwa dane wejściowe typu `Int`, interpretowany jako ułamek dyadic.
W tym celu `RFrac` ma `((Pauli, Int, Int, Qubit) => Unit is Adj + Ctl)`sygnatury.
Implementuje qubit jednostki $ \exp (\pi k \sigma/2 ^ n) $, gdzie $ \sigma $ jest matrycą Pauli odpowiadającą pierwszemu argumentowi, $k $ jest drugim argumentem, a $n $ to trzeci argument.
`RFrac(_,k,n,_)` jest taka sama jak `R(_,-πk/2^n,_)`; Należy zauważyć, że kąt jest *wartością ujemną* części ułamkowej.

Operacja <xref:microsoft.quantum.intrinsic.rx> implementuje obrót wokół osi Pauli $X $.
Ma `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.
`Rx(_, _)` jest taka sama jak `R(PauliX, _, _)`.

Operacja <xref:microsoft.quantum.intrinsic.ry> implementuje obrót wokół osi Pauli $Y $.
Ma `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.
`Ry(_, _)` jest taka sama jak `R(PauliY,_ , _)`.

Operacja <xref:microsoft.quantum.intrinsic.rz> implementuje obrót wokół osi Pauli $Z $.
Ma `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.
`Rz(_, _)` jest taka sama jak `R(PauliZ, _, _)`.

Operacja <xref:microsoft.quantum.intrinsic.r1> implementuje obrót o podaną ilość około $ \ket{1}$, $-$1 eigenstate $Z $.
Ma `((Double, Qubit) => Unit is Adj + Ctl)`podpisu.
`R1(phi,_)` jest taka sama jak `R(PauliZ,phi,_)`, a następnie `R(PauliI,-phi,_)`.

Operacja <xref:microsoft.quantum.intrinsic.r1frac> implementuje rotację ułamkową o podaną ilość wokół eigenstate Z = 1.
Ma `((Int,Int, Qubit) => Unit is Adj + Ctl)`podpisu.
`R1Frac(k,n,_)` jest taka sama jak `RFrac(PauliZ,-k.n+1,_)`, a następnie `RFrac(PauliI,k,n+1,_)`.

Poniżej przedstawiono przykład operacji obrotu (wokół osi Pauli $Z $, w tym wystąpieniu) zamapowanej na sferę Bloch:

![Operacja obrotu zamapowana na Bloch sferę](~/media/prelude_rotationBloch.png)

#### <a name="multi-qubit-operations"></a>Operacje wykonywane przez wiele qubit ####

Oprócz operacji pojedynczych qubit, Preludium także definiuje kilka operacji qubit.

Najpierw operacja <xref:microsoft.quantum.intrinsic.cnot> wykonuje standardowe, kontrolowane bramy`NOT`, \begin{Equation} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & \end{bmatrix}.
\end{Equation} ma sygnaturę `((Qubit, Qubit) => Unit is Adj + Ctl)`, co oznacza, że $ \operatorname{CNOT} $ działa unitarily na dwóch poszczególnych qubitsach.
`CNOT(q1, q2)` jest taka sama jak `(Controlled X)([q1], q2)`.
Ponieważ `Controlled` Funktor umożliwia kontrolę nad rejestrem, używamy literału Array `[q1]`, aby wskazać, że chcemy tylko jedną kontrolkę.

Operacja <xref:microsoft.quantum.intrinsic.ccnot> wykonuje podwójnie sterowaną bramą bez bramy, czasami również znaną jako brama Toffoli.
Ma `((Qubit, Qubit, Qubit) => Unit is Adj + Ctl)`podpisu.
`CCNOT(q1, q2, q3)` jest taka sama jak `(Controlled X)([q1, q2], q3)`.

Operacja <xref:microsoft.quantum.intrinsic.swap> zamienia Stany Quantum z dwóch qubitsów.
Oznacza to, że implementuje macierz jednostkową \begin{Equation} \operatorname{SWAP} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}.
\end{Equation} ma sygnaturę `((Qubit, Qubit) => Unit is Adj + Ctl)`.
`SWAP(q1,q2)` jest równoważne `CNOT(q1, q2)`, a następnie `CNOT(q2, q1)` a następnie `CNOT(q1, q2)`.

> [!NOTE]
> Brama wymiany *nie* jest taka sama jak zmiana układu elementów zmiennej typu `Qubit[]`.
> Zastosowanie `SWAP(q1, q2)` powoduje zmianę stanu qubits, do którego odwołuje się `q1` i `q2`, natomiast `let swappedRegister = [q2, q1];` ma wpływ tylko na te qubits.
> Ponadto `(Controlled SWAP)([q0], (q1, q2))` pozwala na Kondycjonowanie `SWAP` na stanie qubit trzeciego, którego nie można reprezentować przez ponowne rozmieszczenie elementów.
> Brama przełączenia kontrolowanego, znana także jako brama Fredkin, jest wystarczająco wydajna, aby obejmowała wszystkie klasyczne obliczenia.

Na koniec Preludium zawiera dwie operacje do reprezentowania wykładniczych operatorów wieloqubitowych Pauli.
Operacja <xref:microsoft.quantum.intrinsic.exp> wykonuje rotację na podstawie iloczynu Pauli macierzy. reprezentowane przez wieloqubitne \begin{Equation} \operatorname{Exp} (\vec{\sigma}, \phi) \mathrel{: =} \exp\left (i \phi \ sigma_0 \otimes \ sigma_1 \otimes \cdots \otimes \ sigma_n \right), \end{Equation} WHERE $ \vec{\sigma} = (\ sigma_0, \ sigma_1, \dots, \ sigma_n) $ jest sekwencją operatorów pojedyncze-qubit Pauli i gdzie $ \phi $ jest kątem.
Obrót `Exp` reprezentuje $ \vec{\sigma} $ jako tablicę elementów `Pauli`, tak że ma `((Pauli[], Double, Qubit[]) => Unit is Adj + Ctl)`sygnatur.

Operacja <xref:microsoft.quantum.intrinsic.expfrac> wykonuje ten sam obrót przy użyciu notacji dyadic ułamków opisanej powyżej.
Ma `((Pauli[], Int, Int, Qubit[]) => Unit is Adj + Ctl)`podpisu.

> [!WARNING]
> Wartość wykładnicza iloczynu dwuczęściowego w operatorach Pauli nie jest taka sama jak iloczynów dwuczęściowych operatorów Pauli.
> Oznacza to, że $e ^ {i (Z \otimes Z) \phi} \ne e ^ {i Z \phi} \otimes e ^ {i Z \phi} $.

### <a name="measurements"></a>Miary ###

Podczas mierzenia, wartość + 1 eigenvaluea operatora jest mierzona w wyniku `Zero` i-1 eigenvalue do wyniku `One`.

> [!NOTE]
> Chociaż ta konwencja może wydawać się nieparzysta, ma dwie zalety.
> Po pierwsze obserwowanie wyniku $ \ket{0}$ jest reprezentowane przez `Result` wartość `Zero`, podczas gdy przestrzeganie $ \ket{1}$ odpowiada `One`.
> Następnie możemy napisać, że eigenvalue $ \lambda $ odpowiadający wynikowi $r $ to $ \lambda = (-1) ^ r $.

Operacje pomiarów obsługują nie `Adjoint` ani `Controlled` Funktor.

Operacja <xref:microsoft.quantum.intrinsic.measure> wykonuje wspólne pomiary co najmniej jednego qubits w określonym produkcie operatorów Pauli.
Jeśli macierz Pauli i tablica qubit mają różne długości, operacja kończy się niepowodzeniem.
`Measure` ma `((Pauli[], Qubit[]) => Result)`sygnatury.

Należy zauważyć, że wspólne pomiary nie są takie same jak pomiary każdego qubit indywidualnie.
Rozważmy na przykład stan $ \ket{11} = \ket{1} \otimes \ket{1} = X\otimes X \ket{00}$.
Pomiary $Z _0 $ i $Z _1 $ osobno, uzyskujemy wyniki $r _0 = $1 i $r _1 = $1.
Pomiar $Z _0 Z_1 $, jednak pobieramy pojedynczy wynik $r _ {\textrm{joint}}d = $0, co oznacza, że para $ \ket{11}$ jest dodatnia.
Umieść inaczej: $ (-1) ^ {r_0 + r_1} = (-1) ^ r_ {\textrm{joint}}) $.
Ze względu na to, że pouczymy się *tylko* o parzystości z tego pomiaru, wszystkie informacje o Quantum, które są reprezentowane w rozłożeniu między 2 2 qubit Stanów pozytywnej parzystości, $ \ket{00}$ i $ \ket{11}$, są zachowywane.
Ta właściwość będzie istotna w przyszłości, ponieważ omawiamy korekcję błędów.

Dla wygody Preludium również obejmuje dwie inne operacje do mierzenia qubits.
Najpierw ponieważ wykonywanie pomiarów qubit jest dość popularne, Preludium definiuje skrót dla tego przypadku.
Operacja <xref:microsoft.quantum.intrinsic.m> mierzy operator Pauli $Z $ na jednym qubit i ma `(Qubit => Result)`sygnatur.
`M(q)` jest równoznaczna z `Measure([PauliZ], [q])`.

<xref:microsoft.quantum.measurement.multim> mierzy operator Pauli $Z $ *osobno* dla każdej tablicy qubits, zwracając *tablicę* wartości `Result` uzyskanych dla każdego qubit.
W niektórych przypadkach może to być zoptymalizowane. Ma sygnaturę (`Qubit[] => Result[])`.
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

Ponadto Preludium definiuje bogaty zestaw funkcji konwersji matematycznych i typów na poziomie platformy .NET do użycia w kodzie Q #.
Na przykład przestrzeń nazw <xref:microsoft.quantum.extensions.math> definiuje użyteczne operacje, takie jak <xref:microsoft.quantum.extensions.math.sin> i <xref:microsoft.quantum.extensions.math.log>.
Implementacja udostępniona przez zestaw Quantum Development Kit używa klasycznej biblioteki klas .NET, co może wiązać się z dodatkową komunikacją między programami Quantum i ich klasycznymi sterownikami.
Chociaż nie ma to problemu dla lokalnego symulatora, może to być problem z wydajnością w przypadku korzystania z zdalnego symulatora lub rzeczywistego sprzętu jako maszyny docelowej.
Ten sam komputer docelowy może wyeliminować ten wpływ na wydajność, zastępując te operacje niektórymi wersjami, które są bardziej wydajne dla danego systemu.

### <a name="math"></a>Dodatku ###

Przestrzeń nazw <xref:microsoft.quantum.extensions.math> zawiera wiele przydatnych funkcji z [klasy`System.Math`](https://docs.microsoft.com/dotnet/api/system.math?view=netframework-4.7.1)biblioteki klas podstawowych platformy .NET.
Te funkcje mogą być używane w taki sam sposób jak w przypadku innych funkcji Q #:

```qsharp
open Microsoft.Quantum.Math;
// ...
let y = Sin(theta);
```

Gdzie metoda statyczna platformy .NET została przeciążona na podstawie typu argumentów, odpowiednia funkcja Q # ma adnotację z sufiksem wskazującym typ danych wejściowych:

```qsharp
let x = AbsI(-3); // x : Int = 3
let y = AbsD(-PI()); // y : Double = 3.1415...
```


### <a name="bitwise-operations"></a>Operacje bitowe ###

Na koniec przestrzeń nazw <xref:microsoft.quantum.extensions.bitwise> zawiera kilka przydatnych funkcji służących do manipulowania liczbami całkowitymi za pomocą operatorów bitowych.
Na przykład, <xref:microsoft.quantum.extensions.bitwise.parity> zwraca bitową parzystość liczby całkowitej jako inną liczbę całkowitą.
