---
title: Słowniczek obliczeń kwantowych
description: Słowniczek wspólnych terminów, działań i obiektów używanych w obliczeniach kwantowych.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482228"
---
# <a name="quantum-computing-glossary"></a>Słowniczek obliczeń kwantowych

## <a name="adjoint"></a>Przyleganie do

Złożony koniugat transponować [operację](xref:microsoft.quantum.glossary#operation). W przypadku operacji, które implementują [operator unitarny,](xref:microsoft.quantum.glossary#unitary-operator) przyłącze jest odwrotnością operacji i jest oznaczone symbolem sztyletu. Na przykład, jeśli `U` operacja reprezentuje operator unitary $U$, a następnie `Adjoint U` reprezentuje $U^\sztylet$. Aby uzyskać więcej informacji, zobacz [Przyłącze](xref:microsoft.quantum.language.file-structure#adjoint).

## <a name="ancilla"></a>Ancilla (Ancilla)

[Kubit,](xref:microsoft.quantum.glossary#qubit) który służy jako pamięć tymczasowa dla komputera kwantowego i jest przydzielany i de-przydzielone w razie potrzeby.  Aby uzyskać więcej informacji, zobacz [Wiele kubitów](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Stan dzwonu

Jeden z czterech konkretnych maksymalnie [splątanych](xref:microsoft.quantum.glossary#entanglement) [stanów kwantowych](xref:microsoft.quantum.glossary#quantum-state) dwóch kubitów. Cztery stany są zdefiniowane $\ket{\beta_{ij}} = (\mathbb{I} \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$. Stan Dzwonu jest również znany jako [para EPR.](xref:microsoft.quantum.glossary#epr-pair)

## <a name="bloch-sphere"></a>Kula blocha

Graficzna reprezentacja [pojedynczego kubitu stanu kwantowego](xref:microsoft.quantum.glossary#quantum-state) jako punktu w trójwymiarowej sferze jednostki.[qubit](xref:microsoft.quantum.glossary#qubit) Aby uzyskać więcej informacji, zobacz [Wizualizacja Kubitów i Przekształceń przy użyciu kuli bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Nieopłacona

[Operacja](xref:microsoft.quantum.glossary#operation) lub [funkcja](xref:microsoft.quantum.glossary#function) w języku Q#. Aby uzyskać więcej informacji, zobacz [Działanie i typy funkcji](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="clifford-group"></a>Grupa Clifford

Zestaw operacji, które zajmują oktawy [kuli Blocha](xref:microsoft.quantum.glossary#bloch-sphere) i permutacje efektów [operatorów Pauli](xref:microsoft.quantum.glossary#pauli-operators). Należą do nich operacje [$X $](xref:microsoft.quantum.intrinsic.x), [$Y $](xref:microsoft.quantum.intrinsic.y), $Z [$](xref:microsoft.quantum.intrinsic.z), [$H $](xref:microsoft.quantum.intrinsic.h) i $S [$](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Kontrolowane

[Operacja](xref:microsoft.quantum.glossary#operation) kwantowa, która przyjmuje jeden lub więcej [kubitów](xref:microsoft.quantum.glossary#qubit) jako czynników umożliwiających operację docelową. Aby uzyskać więcej informacji, zobacz [Kontrolowane](xref:microsoft.quantum.language.type-model#controlled).

## <a name="dirac-notation"></a>Notacja Diraca

Symboliczny skrót, który upraszcza reprezentację [stanów kwantowych](xref:microsoft.quantum.glossary#quantum-state), zwany także *opisem bra-ket.*  Część *biustonosza* reprezentuje wektor wiersza, na przykład $\bra{A} = \begin{bmatrix} A{_1} & A{_2} \end{bmatrix}$ a część *ket* reprezentuje wektor kolumny, $\ket{B} \\ \\ = \begin{bmatrix} B{_1} B{_2} \end{bmatrix}$. Aby uzyskać więcej informacji, zobacz [Dirac Notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Wartość eigenvalue

Współczynnik, za pomocą którego wielkość [wektora wektora wektora](xref:microsoft.quantum.glossary#eigenvector) danego przekształcania jest zmieniana przez zastosowanie transformacji.  Biorąc pod uwagę macierz kwadratową $M$ i wektora weentoru $v$, a następnie $Mv = cv$, gdzie $c$ jest wartością własnych i może być złożoną liczbą dowolnego argumentu. Aby uzyskać więcej informacji, zobacz [Pojęcia macierzy zaawansowanej](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Wektor weszusznik wespodmiaczy

Wektor, którego kierunek jest niezmieniony przez daną transformację i którego wielkość jest zmieniana przez współczynnik [odpowiadający wartości eigenvalue wektora](xref:microsoft.quantum.glossary#eigenvalue). Biorąc pod uwagę macierz kwadratową $M$ i wartością własnych $c$, a następnie $Mv = cv$, gdzie $v$ jest wektorem wektorem macierzy i może być złożoną liczbą dowolnego argumentu. Aby uzyskać więcej informacji, zobacz [Pojęcia macierzy zaawansowanej](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Uwikłanie

Cząstki kwantowe, takie jak [kubity,](xref:microsoft.quantum.glossary#qubit)mogą być połączone lub *splątane* w taki sposób, że nie mogą być opisane niezależnie od siebie. Ich wyniki pomiarów są skorelowane nawet wtedy, gdy są oddzielone nieskończenie daleko. Splątanie jest niezbędne do [pomiaru](xref:microsoft.quantum.glossary#measurement) [stanu](xref:microsoft.quantum.glossary#quantum-state) kubitu.  Aby uzyskać więcej informacji, zobacz [Pojęcia macierzy zaawansowanej](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>Para EPR

Jeden z czterech konkretnych maksymalnie splątanych [stanów kwantowych](xref:microsoft.quantum.glossary#quantum-state) dwóch [kubitów.](xref:microsoft.quantum.glossary#qubit) Cztery{1} stany są zdefiniowane $\ket{\beta_{ij}} = (\mathbb \otimes X^iZ^j) (\ket{00} + \ket{11}) / \sqrt{2}$. Para EPR jest również znana jako [stan Dzwonu](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Ewolucji

Jak [stan kwantowy](xref:microsoft.quantum.glossary#quantum-state) zmienia się w czasie. Aby uzyskać więcej informacji, zobacz [Macierzy wykładniczej](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funkcja
Rodzaj podprocedury w języku Q#, który jest czysto klasyczny (nietłęki). Podczas gdy funkcje są używane w algorytmach kwantowych, nie mogą działać na [kubity](xref:microsoft.quantum.glossary#qubit) lub [operacje](xref:microsoft.quantum.glossary#operation)wywołania. Aby uzyskać więcej informacji, zobacz [Działanie i typy funkcji](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="gate"></a>Gate

Termin legacy dla [operacji](xref:microsoft.quantum.glossary#operation)kwantowej, w oparciu o koncepcję klasycznych bram logicznych. [Obwód kwantowy](xref:microsoft.quantum.glossary#quantum-circuit-diagram) to sieć bram (lub operacji), oparta na podobnej koncepcji klasycznych obwodów logicznych.

## <a name="global-phase"></a>Faza globalna

Gdy dwa [stany](xref:microsoft.quantum.glossary#quantum-state) są identyczne do wielokrotności liczby zespolonej $e^{i\phi}$, mówi się, że różnią się one do fazy globalnej. W przeciwieństwie do faz lokalnych, fazy globalne nie mogą być obserwowane przez żadne [pomiary.](xref:microsoft.quantum.glossary#measurement) Aby uzyskać więcej informacji, zobacz [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard ( Hadamard )

Operacja Hadamarda (zwana również bramą Hadamarda lub transformacją) działa na jednym [kubitu](xref:microsoft.quantum.glossary#qubit) {0}i umieszcza ją{1}w nawet [superpozycji](xref:microsoft.quantum.glossary#superposition) $\ket{0}$ lub $\ket $ jeśli kubit jest początkowo w stanie $\ket $. W języku Q#ta operacja jest stosowana [`H`](xref:microsoft.quantum.intrinsic.h) przez wstępnie zdefiniowaną operację.

## <a name="immutable"></a>Niezmienialny

Zmienna, której wartości nie można zmienić. Zmienna niezmienna w Q# jest `let` tworzona przy użyciu słowa kluczowego. Aby zadeklarować zmienne, które *można* zmienić, użyj `set` [modyfikowalnego](xref:microsoft.quantum.glossary#immutable) słowa kluczowego do zadeklarowania i słowa kluczowego, aby zmodyfikować wartość. 

## <a name="measurement"></a>Miara

Manipulacja [kubitem](xref:microsoft.quantum.glossary#qubit) (lub zestawem kubitów), która daje wynik obserwacji, w efekcie uzyskując klasyczny bit. Aby uzyskać więcej informacji, zobacz [Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Modyfikowalny

Zmienna, której wartość może zostać zmieniona po jej utworzeniu. Zmienna modyfikowalna w Q# jest zadeklarowana przy użyciu `mutable` słowa kluczowego i modyfikowana przy użyciu słowa kluczowego. `set` Zmienne utworzone `let` za pomocą słowa kluczowego są [niezmienne](xref:microsoft.quantum.glossary#immutable) i ich wartości nie można zmienić.

## <a name="namespace"></a>Przestrzeń nazw

Etykieta dla kolekcji powiązanych nazw (tj. [operacji,](xref:microsoft.quantum.glossary#operation) [funkcji](xref:microsoft.quantum.glossary#function)i [typów zdefiniowanych przez użytkownika).](xref:microsoft.quantum.glossary#user-defined-type) Na przykład obszar nazw [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) etykiety wszystkich symboli zdefiniowanych w standardowej bibliotece, które pomagają w przygotowaniu stanów początkowych.

## <a name="operation"></a>Operacja

Podstawowa jednostka wykonania kwantowego w Q#. Jest w przybliżeniu równoważne funkcji w języku C, C++ lub Python lub metody statycznej w języku C# lub Java. Aby uzyskać więcej informacji, zobacz [Działanie i typy funkcji](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="operator-application"></a>Aplikacja operatora

Wykonywanie operacji kwantowej. Zazwyczaj stosuje się macedo-jednostkową macierz do bieżącego wektora stanu kwantowego.

## <a name="oracle"></a>Oracle

Podprocedura, która dostarcza informacji zależnych od danych do algorytmu kwantowego w czasie wykonywania. Zazwyczaj celem jest zapewnienie [superpozycji](xref:microsoft.quantum.glossary#superposition) wyjść odpowiadających wejściom, które są w superpozycji. Aby uzyskać więcej informacji, zobacz [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Częściowe zastosowanie

Wywoływanie [funkcji](xref:microsoft.quantum.glossary#function) lub [operacji](xref:microsoft.quantum.glossary#operation) bez wszystkich wymaganych danych wejściowych. Zwraca nowy [wywoływany,](xref:microsoft.quantum.glossary#callable) który wymaga tylko brakujących parametrów (wskazanych przez podkreślenie) do dostarczenia podczas przyszłej aplikacji. Na przykład, biorąc `MyFunc(x : int, y : int) : int {return x + y;}` pod uwagę funkcję, można `let NewFunc = MyFunc(_, 3)`częściowo zastosować ją do nowej funkcji . Następnie można wywołać nową funkcję w późniejszym `NewFunc(2)` czasie z brakującym parametrem, który zwraca wartość *5*.  Aby uzyskać więcej informacji, zobacz [Częściowe zastosowanie](xref:microsoft.quantum.language.expressions#partial-application).

## <a name="pauli-operators"></a>Operatorzy Pauli

Zestaw trzech 2 x 2 jednolitych macierzy znanych jako `X`operacje kwantowe `Y` i `Z` kwantowe. Macierz tożsamości, $I$, jest często uwzględniona w zestawie.  $I = \begin{bmatrix} 1 & 0 \\ \\ 0 & 1 \end{bmatrix}$, $X = \begin{bmatrix} 0 & \\ \\ 1 1 & 0 \end{bmatrix}$, $Y = \begin{bmatrix} 0 \\ \\ & -i & 0 \end{bmatrix}$, $Z = \begin{bmatrix} 1 \\ \\ & 0 0 & -1 \end{bmatrix}$.   Aby uzyskać więcej informacji, zobacz [Operacje pojedynczego kubitu](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Schemat obwodu kwantowego

Metoda graficznie reprezentująca sekwencję [operacji](xref:microsoft.quantum.glossary#operation) (lub [bram)](xref:microsoft.quantum.glossary#gate)dla prostych ![programów](~/media/qpe.png)kwantowych, na przykład diagram obwodu przykładowego. Aby uzyskać więcej informacji, zobacz [Obwody kwantowe](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Biblioteki kwantowe

Kolekcje [operacji,](xref:microsoft.quantum.glossary#operation) [funkcje](xref:microsoft.quantum.glossary#function) i [typy zdefiniowane](xref:microsoft.quantum.glossary#user-defined-type) przez użytkownika do tworzenia programów Q#. [Biblioteka standardowa](xref:microsoft.quantum.libraries.standard.intro) jest instalowana domyślnie. Inne dostępne biblioteki to [biblioteka chemii,](xref:microsoft.quantum.chemistry.concepts.intro) [biblioteka numerics](xref:microsoft.quantum.numerics.intro) i [biblioteka uczenia maszynowego.](xref:microsoft.quantum.machine-learning.concepts.intro)

## <a name="quantum-state"></a>Stan kwantowy

Dokładny stan izolowanego układu kwantowego, z którego można wydobyć prawdopodobieństwa [pomiaru.](xref:microsoft.quantum.glossary#measurement) W obliczeniach kwantowych symulator kwantowy wykorzystuje te informacje do symulacji reakcji kubitów na operacje. Aby uzyskać więcej informacji, zobacz [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Kubit

Podstawowa jednostka informacji kwantowej, analogiczna do *nieco* w klasycznej informatyce. Aby uzyskać więcej informacji, zobacz [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Powtarzaj do sukcesu

Algorytm kwantowy, który probabilistycznie odnosi sukces. Po niepowodzeniu procedura ponowi próbę do czasu pomyślnego (lub osiągnięcia limitu). Aby uzyskać więcej informacji, zobacz [Powtarzanie do sukcesu (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>Biblioteki standardowe

[Operacje](xref:microsoft.quantum.glossary#operation), [funkcje](xref:microsoft.quantum.glossary#function) i [typy zdefiniowane przez użytkownika,](xref:microsoft.quantum.glossary#user-defined-type) które są instalowane wraz z kompilatorem Q# podczas instalacji. Implementacja biblioteki standardowej jest niezależna w odniesieniu do maszyn docelowych. Aby uzyskać więcej informacji, zobacz [Biblioteki standardowe](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Superpozycji

Koncepcja w obliczeniach kwantowych, że [kubit](xref:microsoft.quantum.glossary#qubit) jest liniową kombinacją dwóch stanów: $\ket{\0}$ i $\ket{\1}$, dopóki nie zostanie [zmierzona.](xref:microsoft.quantum.glossary#measurement)  Aby uzyskać więcej informacji, zobacz [Co to jest informatyka kwantowa](xref:microsoft.quantum.overview.what).

## <a name="target-machine"></a>Maszyna docelowa

Cel kompilacji, który obniża abstrakcyjny program kwantowy w kierunku sprzętu lub symulacji. Zazwyczaj obejmuje to ponowne zapisy do wielu celów, w tym wymiany bramy, kodowania do korekcji błędów, układu geometrycznego i innych. Aby uzyskać więcej informacji, zobacz [Symulatory kwantowe i aplikacje hosta](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportacja

Metoda regeneracji danych lub [stanu kwantowego](xref:microsoft.quantum.glossary#quantum-state)jednego [kubitu](xref:microsoft.quantum.glossary#qubit) z jednego miejsca do drugiego bez fizycznego przesuwania kubitu, za pomocą [splątania](xref:microsoft.quantum.glossary#entanglement) i [pomiaru.](xref:microsoft.quantum.glossary#measurement)  Aby uzyskać więcej informacji, zobacz [Obwody kwantowe](xref:microsoft.quantum.concepts.circuits) i [łącząc to wszystko razem](xref:microsoft.quantum.techniques.puttingittogether).

## <a name="tuple"></a>Krotki

Kolekcja wartości oddzielonych przecinkami, która działa jako pojedyncza wartość. *Typ* krotki jest zdefiniowany przez typy wartości, które zawiera. W Q#krotek są [niezmienne](xref:microsoft.quantum.glossary#immutable) i mogą być zagnieżdżone, zawierają tablice lub używane w tablicy. Aby uzyskać więcej informacji, zobacz [typy krotek](xref:microsoft.quantum.language.type-model#tuple-types).

## <a name="unitary-operator"></a>Operator unitarny

Operator, którego odwrotność jest równa jego [przyległej](xref:microsoft.quantum.glossary#adjoint), tzn. $UU^{\sztylet} = \id$.

## <a name="user-defined-type"></a>Typ zdefiniowany przez użytkownika

Kolekcja wbudowanych lub wcześniej zdefiniowanych typów, które mogą być określane jako pojedyncza jednostka. Aby uzyskać więcej informacji, zobacz [Typy zdefiniowane przez użytkownika](xref:microsoft.quantum.language.type-model#user-defined-types).