---
title: Pomiary Pauli
description: Dowiedz się, jak korzystać z operacji pomiaru pojedynczego i qubit Pauli.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 115c1703e433f24930e4be61b545048c95da28d1
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630298"
---
# <a name="pauli-measurements"></a>Pomiary Pauli

W poprzednich dyskusjach koncentrujemy się na obliczaniu pomiarów bazowych.
W rzeczywistości istnieją inne typowe pomiary związane z przetwarzaniem jednostek Quantum, które z perspektywy notacji są wygodne do wyrażania na podstawie obliczeniowych pomiarów.
Podczas pracy z pytaniami Q # najbardziej typowym rodzajem pomiarów, które będą używane, prawdopodobnie będą *pomiary Pauli*, które uogólnią obliczenia obliczające pomiary w celu uwzględnienia pomiarów w innych bazach i parzystości między różnymi qubits.
W takich przypadkach często omawia się pomiar pomiaru operatora Pauli, w ogólności operatora, takiego jak $X, Y, Z $ lub $Z \otimes Z, x \otimes x, x \otimes Y $ i tak dalej.

> [!TIP]
> W pytaniach Q # qubit operatory Pauli są ogólnie reprezentowane przez tablice typu `Pauli[]` .
> Na przykład, aby reprezentować $X \otimes Z \otimes Y $ , można użyć tablicy `[PauliX, PauliZ, PauliY]` .

Omawianie pomiaru w warunkach operatorów Pauli jest szczególnie powszechne w podpolu korekcji błędów Quantum.
W pytaniach Q # przestrzegamy podobnej Konwencji; teraz wyjaśnimy ten alternatywny widok pomiarów.

Przed napisaniem szczegółowych informacji o tym, jak sądzisz o pomiarze Pauli, warto zastanowić się nad tym, co mierzy jeden qubit wewnątrz komputera Quantum w stanie Quantum.
Załóżmy, że mamy $n $ qubit Quantum, a następnie zmierzenie jednego qubitu natychmiast reguły mające na celu odłożenia, $ że stanem może być wartość $2 ^ n.
Innymi słowy, pomiar projektuje stan Quantum na jedną z dwóch miejsc.
Możemy uogólnić sposób, w jaki myślimy o pomiarach, aby odzwierciedlić ten Intuition.

Aby zwięzłie zidentyfikować te podobszary, należy zapoznać się z językiem.
Jednym ze sposobów opisywania dwóch podobszarów jest określenie ich za pośrednictwem macierzy, która ma dwie unikalne eigenvalues, podejmowane przez Konwencję jako $ \Pm 1 $ .
Aby zapoznać się z prostym przykładem opisywania obszarów w ten sposób, należy rozważyć $Z $ :

$ $ \begin{align}
  Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .
\end{align}
$$

Odczytując elementy ukośne macierzy Pauli $Z $ , widzimy, że $Z $ ma dwa eigenvectors, $ \ket{0 } $ i $ \ket{1 } $, z odpowiednimi eigenvalues $ \Pm 1 $ .
W takim przypadku, jeśli mierzę qubit i uzyskamy `Zero` (odpowiadający stanowi $ \ket{0 } $), wiemy, że stan naszego qubit to $ + 1 $ eigenstate $ operatora $Z.
Podobnie, jeśli uzyskamy `One` , wiemy, że stan naszego qubit to $-1 $ eigenstate $Z $ .
Ten proces jest określany w języku Pauli pomiarów jako "pomiar Pauli $Z $ " i jest całkowicie równoważny do wykonywania obliczeniowej miary.

Każda \times macierz $2 2 $ , która jest przekształceniem jednostkowym $Z $ również spełnia te kryteria.
Oznacza to, że możemy również użyć macierzy $A = U ^ \dagger Z U $ , gdzie $U $ to każda inna macierz jednostkowa, aby udostępnić macierz, która definiuje dwa wyniki pomiaru w jego $ \Pm 1 $ eigenvectors.
Notacja Pauli jest odwołująca się do tej równoważnej jednostki, identyfikując $X, Y, Z $ pomiarów jako równoważne pomiary, które mogą wykonać, aby uzyskać informacje z qubit.
Te pomiary są podane poniżej dla wygody.


|Pomiar Pauli  |Transformacja jednostkowa  |
|-------------------|------------------------|
| $Z$               | $ \boldone$             |
| $X$               | $H$                    |
| $Y$               | $HS ^ {\dagger}$         |

Oznacza to, że przy użyciu tego języka "miara $Y $ " jest równoznaczna z zastosowaniem $HS ^ \dagger, $ a następnie mierzenia w oparciu o obliczenia, gdzie [`S`](xref:microsoft.quantum.intrinsic.s) jest wewnętrzną operacją Quantum czasami nazywaną "bramą fazowy" i może być symulowane przez macierz jednostkową

$ $ \begin{align}
    S = \begin{bmatrix}
        1 & 0 \\ \\ 0 & i \end{ bmatrix } .
\end{align}
$$

Jest to również równoznaczne z zastosowaniem $HS ^ \dagger $ do wektora stanu Quantum, a następnie zmierzenie $Z, w taki sposób, $ że Następująca operacja jest równoznaczna z `Measure([PauliY], [q])` :

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

Prawidłowy stan można znaleźć w wyniku przekształcenia z powrotem do podstawy obliczeniowej, co oznacza zastosowanie $SH $ do wektora stanu Quantum; w powyższym fragmencie, przekształcenie z powrotem do podstawy obliczeniowej jest obsługiwane automatycznie przez użycie `within … apply` bloku.

W polu Q # wyrażamy wynik---to znaczy, że klasyczne informacje wyodrębnione ze względu na współdziałanie ze stanem---są `Result` określane przez wartość $j \In \\ {\Texttt{zero } , \texttt{one } \\ } $ wskazującą, czy wynik znajduje się w $ (-1) ^ j $ eigenspace operatora Pauli.


## <a name="multiple-qubit-measurements"></a>Pomiary z wieloma qubitami

Pomiary operatorów Pauli wieloqubitowych są zdefiniowane w podobny sposób, jak pokazano w:

$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 \\\\ 0&0&0&1 \end { bmatrix } .
$$

W ten sposób produkty dwuetapowe dwóch operatorów Pauli $Z $ tworzą macierz składającą się z dwóch spacji składających się z elementów $ + 1 $ i $-1 $ eigenvalues.
Podobnie jak w przypadku pojedynczej qubit, oba stanowią pół obszaru, co połowa dostępnego miejsca wektorowego należy do $ + 1 $ eigenspace i pozostała połowa do $-1 $ eigenspace.
Ogólnie rzecz biorąc, można łatwo zapoznać się z definicją iloczynu dwuczęściowego, że każdy dwuczęściowy produkt operatorów Pauli-$Z $ i tożsamość również przestrzega tego.
Na przykład

$ $ \begin{align}
    Z \otimes \boldone = \begin{bmatrix}
        1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .
\end{align}
$$

Tak jak wcześniej, każda jednostkowa transformacja takich macierzy również opisuje dwie spacje oznaczone przez $ \Pm 1 $ eigenvalues.
Na przykład $X \otimes X = h \otimes h (z \otimes ) h h \otimes $ od tożsamości, która $Z = HXH $ .
Podobnie jak w przypadku qubit, wszystkie dwie qubit Pauli-pomiary mogą być zapisywane jako $U ^ \dagger (Z \otimes \id) U $ dla $4 \times 4 $ macierzy jednostkowych $U $ . Wyliczmy przekształcenia w poniższej tabeli.

> [!NOTE]
> W poniższej tabeli użyto $ \operatorname{SWAP } $ do wskazania macierzy $ $ \begin{align}
>     \operatorname{SWAP } & = \left (\begin{Matrix}
>         1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}
> $ $ używany do symulowania operacji wewnętrznej [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Pomiar Pauli     |Transformacja jednostkowa  |
|----------------------|------------------------|
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $Z \otimes \boldone$ | $ \boldone \otimes \boldone$ |
| $X \otimes \boldone$ | $H \otimes \boldone$ |
| $Y \otimes \boldone$ | $HS ^ \dagger \otimes \boldone$ |
| $ \boldone \otimes Z$ | $ \operatorname{SWAP}$ |
| $ \boldone \otimes X$ | $ (H \otimes \boldone) \operatorname{swap}$ |
| $ \boldone \otimes Y$ | $ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$ |
| $Z \otimes Z$ | $ \operatorname{CNOT } \_ {10}$ |
| $X \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $ |
| $Y \otimes Z$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $ |
| $Z \otimes X$ | $ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $ |
| $X \otimes X$ | $ \operatorname{CNOT } \_ {10 } (h \otimes h) $ |
| $Y \otimes X$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $ |
| $Z \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $ |
| $X \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $ |
| $Y \otimes Y$ | $ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $ |

W tym miejscu [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operacja zostanie wyświetlona z następującej przyczyny.
Każda miara Pauli, która nie obejmuje macierzy $ \boldone, $ jest równoważna do jednostki do $Z \otimes z z $ powyższego powodu.
Eigenvalues z $Z \otimes z $ są zależne od parzystości qubits, która składa się z każdego wektora obliczeniowego, a operacje kontrolowane nie służą do obliczenia tej parzystości i zapisania jej w pierwszym bitach.
Następnie po przemierzeniu pierwszego bitu możemy odzyskać tożsamość wynikowego, który jest równoważny do mierzenia operatora Pauli.

Jedna dodatkowa Uwaga: Chociaż może być skłonny do założenia, że pomiary $Z \otimes z $ są takie same jak pomiary sekwencyjne $Z \otimes \mathbb{1 $, } a następnie $ \mathbb{1 } \otimes Z $ , to założenie miałoby wartość false.
Powodem jest to, że pomiar $Z \otimes z $ projektów w stanie Quantum do wartości $ + 1 $ lub $-1 $ eigenstate tych operatorów.
Pomiar $Z \otimes \mathbb{1 } $, a następnie $ \Mathbb{1 } \otimes z $ projektów, wektor stanu Quantum najpierw w połowie miejsca $Z \otimes \mathbb{1 } $, a następnie do połowy miejsca na $ \mathbb{1 } \otimes z $ . Ponieważ istnieją cztery wektory obliczeniowe, przeprowadzenie obydwu pomiarów zmniejsza stan do kwartału, a tym samym redukuje go do jednego wektora obliczanego na podstawie.

## <a name="correlations-between-qubits"></a>Korelacje między qubits
Innym sposobem na pomiar iloczynów ilościowych macierzy Pauli, takich jak $X \otimes X $ lub $Z \otimes Z $ , jest to, że pomiary umożliwiają przeszukanie informacji przechowywanych w korelacji między tymi dwoma qubits.
Pomiar $X \otimes \id $ umożliwia przeglądanie informacji przechowywanych lokalnie w pierwszej qubit.
Mimo że oba typy pomiarów są równie cenne w przypadku obliczeń opartych na usługach Quantum
Wykaże, że w ramach przetwarzania Quantum, często informacje, które chcesz poznać, nie są przechowywane w żadnym z pojedynczych qubit, ale raczej są przechowywane nielokalnie we wszystkich qubitsach i dlatego tylko przez ich przechodzenie przez wspólną miarę (np. $Z \otimes Z $ ) czy te informacje stają się manifestem.

Na przykład w przypadku korekcji błędów często chcemy dowiedzieć się, jaki błąd wystąpił podczas uczenia niczego o stanie, który próbujesz chronić.
[Przykładowy kod przerzucania bitów](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) przedstawia przykład sposobu, w jaki można to zrobić przy użyciu pomiarów, takich jak $Z \otimes Z \otimes \id $ i $ \id \Otimes z \otimes z $ .
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

Można również mierzyć dowolne operatory Pauli, takie jak $X \otimes Y \Otimes Z \otimes \boldone $ .
Wszystkie te produkty dwuskładnikowe operatorów Pauli mają tylko dwa eigenvalues $ \Pm 1 $ , a oba eigenspaces stanowią pół miejsca całego obszaru wektora.
W ten sposób są one zgodne z wymaganiami określonymi powyżej.

W Q #, takie pomiary zwracają $j, $ Jeśli pomiar daje wynik w eigenspace znak $ (-1) ^ j $ .
Pauli pomiary jako Wbudowana funkcja w Q # jest przydatne, ponieważ pomiary takich operatorów wymagają długich łańcuchów kontrolowanych i nieopartych na bramach i transformacji bazowych, aby opisać bramę diagonalizing $U, która jest $ niezbędna do wyrażenia działania jako iloczyn dwuskładnikowego $Z $ i $ \id $ . Aby określić, że chcesz wykonać jedną z tych wstępnie zdefiniowanych pomiarów, nie musisz martwić się o to, jak przekształcić swoją podstawę, tak aby pomiar bazowy obliczał informacje.
W programie Q # wszystkie wymagane przekształcenia podstawowe są obsługiwane automatycznie.
Aby uzyskać więcej informacji, zobacz [`Measure`](xref:microsoft.quantum.intrinsic.measure) i [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operacje.

## <a name="the-no-cloning-theorem"></a>Theorem bez klonowania

Informacje o Quantum są zaawansowane.
Umożliwia nam wykonywanie niezwykłych rzeczy, takich jak liczba czynników, które są wykładniczo szybsze niż najlepsze znane klasyczne algorytmy, lub efektywnie symuluje skorelowane systemy elektronów, które w sposób klasyczny wymagają wykładniczego kosztu, aby symulować dokładne symulacje.
Istnieją jednak ograniczenia dotyczące mocy obliczeniowej Quantum.
Takie ograniczenie jest określone przez *theorem bez klonowania*.

Theorem No-kloning ma nazwę aptly.
Nie zezwala na klonowanie ogólnych Stanów Quantum przez komputer Quantum.
Potwierdzenie theorem jest niezwykle proste.
Gdy Pełna weryfikacja theorem nie jest w stanie nieco zbyt technicznym w naszej dyskusji, w przypadku braku dodatkowych qubits pomocniczych znajduje się w naszym zakresie (pomocnicze qubits to qubits używany do wyznaczania miejsca podczas obliczeń i są łatwe w użyciu i zarządzane w usłudze Q [#).](xref:microsoft.quantum.guide.qubits#borrowed-qubits)

W przypadku takiego komputera z systemem Quantum Operacja klonowania musi być opisana przez macierz jednostkową.
Nie można wymusić pomiaru, ponieważ spowodowałoby to uszkodzenie stanu Quantum, który próbujemy sklonować.
Aby symulować operację klonowania, chcemy, aby macierz jednostkowa używała właściwości $ $ U \ket { \psi } \ket{0 } = \ket { \psi } \ket { \psi}
$ $ dla dowolnego stanu $ \ket { \psi } $.
Właściwość liniowości mnożenia macierzy wskazuje, że dla każdego drugiego stanu Quantum $ \ket { \phi } $,

$ $ \begin{align}
    U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi \right } ) \right] \ket{0}
    & = \frac{1 } {\sqrt{2 } } U \ket { \phi } \ket{0}
      + \frac{1 } {\sqrt{2 } } U \ket { \psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \phi } \ket { \phi } + \ket { \psi } \ket { \psi}
        \right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \phi } + \ket { \psi } \right) \right).
\end{align}
$$

Zapewnia to podstawowe Intuition za theorem bez klonowania: każde urządzenie, które kopiuje nieznany stan Quantum, musi powodować błędy w co najmniej niektórych stanach, które kopiuje.
Podczas gdy klucz założono, że Cloner działa liniowo na stanie wprowadzania, może zostać naruszony poprzez dodanie i pomiar pomocniczej qubits, takie interakcje także przecieki informacji o systemie za pomocą statystyk pomiarów i zapobiegania dokładnemu klonowi w takich przypadkach.
Aby uzyskać bardziej szczegółowe informacje, zobacz theorem No-kloning, [Aby uzyskać więcej informacji](xref:microsoft.quantum.more-information).

Theorema bez klonowania jest ważna w przypadku jakościowej interpretacji obliczeń opartych na usłudze Quantum, ponieważ w przypadku niedrogiego klonowania Stanów Quantum można udzielić prawie magicalej możliwości uczenia się od Stanów Quantum.
Rzeczywiście można naruszyć zasadę niepewności vaunted Heisenberg.
Alternatywnie można użyć optymalnej Cloner do pobrania pojedynczego przykładu ze złożonej dystrybucji Quantum i dowiedzieć się wszystkiego, co może być możliwe, aby poznać tę dystrybucję z zaledwie jednego przykładu.
Przypomina to Przerzucanie monet i obserwowanie głowic, a następnie na poinformowanie przyjaciela o wyniku odpowiedzi "Ah" dystrybucja tej monety musi być Bernoulliego z $p = 0.512643 \ ldots $ ! "  Taka instrukcja byłaby niesensicala, ponieważ jeden bit informacji (wynik Head) po prostu nie może udostępnić wielu bitów informacji potrzebnych do zakodowania dystrybucji bez poważnych informacji.
Podobnie, bez wcześniejszej informacji, nie możemy idealnie sklonować stanu Quantum, tak samo, jak nie można przygotować kompletu takich monet bez znajomości $p $ .

Informacje nie są bezpłatne w obliczeniach Quantum.
Każda qubit mierzona w postaci pojedynczej informacji, a theorem bez klonowania nie wykazuje, że nie ma tylne wejście, które mogą być wykorzystywane w celu założenia zasadniczego kompromisu między informacjami uzyskanymi na temat systemu a zaistniałymi zakłóceniami.
