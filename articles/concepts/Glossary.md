---
title: Słownik przetwarzania Quantum
description: Słownik typowych warunków, akcji i obiektów używanych w ramach przetwarzania Quantum.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
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
ms.openlocfilehash: 2a3b1fe480b9886d0c11255bb1b1e01402dce4f7
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630102"
---
# <a name="quantum-computing-glossary"></a>Słownik przetwarzania Quantum

## <a name="adjoint"></a>Sąsiadująco

Złożone sprzężenie sprzężone [operacji](xref:microsoft.quantum.glossary#operation). W przypadku operacji implementujących operator [jednostkowy](xref:microsoft.quantum.glossary#unitary-operator) sąsiadujący jest odwrotną operacją i jest wskazywany przez symbol Dagger. Na przykład, jeśli operacja `U` reprezentuje $U operatora $ , a następnie `Adjoint U` reprezentuje $U ^ \dagger $ . Aby uzyskać więcej informacji, zobacz [sąsiadująco](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="ancilla"></a>Ancilla

[Qubit](xref:microsoft.quantum.glossary#qubit) , który służy jako pamięć tymczasowa dla komputera z systemem Quantum i jest przypisywany i cofa alokację w razie potrzeby.  Aby uzyskać więcej informacji, zobacz [wiele qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Stan dzwonka

Jeden z czterech konkretnych Maximally [Entangled](xref:microsoft.quantum.glossary#entanglement) [Quantum](xref:microsoft.quantum.glossary#quantum-state) z dwóch qubits. Cztery Stany są zdefiniowane jako $ \ket { \ beta_ {IJ } } = (\Mathbb{I } \Otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $. Stan dzwonka jest również znany jako [para EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Bloch sfera

Graficzna reprezentacja[jednoqubitowego](xref:microsoft.quantum.glossary#qubit) [stanu Quantum](xref:microsoft.quantum.glossary#quantum-state) jako punktu w trójwymiarowej sferze jednostki. Aby uzyskać więcej informacji, zobacz [Wizualizacja Qubits i transformacji przy użyciu sfery Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Żądanie

[Operacja](xref:microsoft.quantum.glossary#operation) lub [Funkcja](xref:microsoft.quantum.glossary#function) w języku Q #. Aby uzyskać więcej informacji, zobacz [operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="clifford-group"></a>Grupa Clifford

Zestaw operacji, które zajmują octantsą w [sferze Blochej](xref:microsoft.quantum.glossary#bloch-sphere) i permutacji dla [operatorów Pauli](xref:microsoft.quantum.glossary#pauli-operators). Są to między innymi [operacje $ $X](xref:microsoft.quantum.intrinsic.x), [$Y $ ](xref:microsoft.quantum.intrinsic.y), [ $ $Z](xref:microsoft.quantum.intrinsic.z), [ $ $H](xref:microsoft.quantum.intrinsic.h) i [$S $ ](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Kontrolowane

[Operacja](xref:microsoft.quantum.glossary#operation) Quantum, która przyjmuje co najmniej jeden [qubits](xref:microsoft.quantum.glossary#qubit) jako element do obsługi dla operacji docelowej. Aby uzyskać więcej informacji, zobacz [kontrolowane i sąsiednie operacje](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations).

## <a name="dirac-notation"></a>Notacja Dirac

Symboliczny skrót, który upraszcza reprezentację [Stanów Quantum](xref:microsoft.quantum.glossary#quantum-state), nazywany również notacją *bra-KET* .  Część *bra* reprezentuje wektor wierszy, na przykład $ \bra{A } = \begin{ bmatrix } a {_1 } & a {_2 } \end{ bmatrix } $ i *KET* część reprezentuje wektor kolumny, $ \ket{B } = \begin{ bmatrix } b {_1 } \\ \\ b {_2 } \end{ bmatrix } $. Aby uzyskać więcej informacji, zobacz [notacja Dirac](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Współczynnik, przez który rozmiary [eigenvector](xref:microsoft.quantum.glossary#eigenvector) danego przekształcenia są zmieniane przez aplikację transformacji.  Za pomocą $M macierzy kwadratowej $ i $v eigenvector $ , a następnie $MV = CV $ , gdzie $c $ jest eigenvalue i może być złożoną liczbą dowolnego argumentu. Aby uzyskać więcej informacji, zobacz [zaawansowane koncepcje dotyczące macierzy](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Wektor, którego kierunek jest niezmieniony przez daną transformację i którego wielkość jest zmieniana przez współczynnik odpowiadający [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)tego wektora. W przypadku $M macierzy kwadratowej $ i $c eigenvalue $ , a następnie $MV = CV $ , gdzie $v $ jest eigenvector macierzy i może być złożoną liczbą dowolnego argumentu. Aby uzyskać więcej informacji, zobacz [zaawansowane koncepcje dotyczące macierzy](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Splątanie

Cząstki Quantum, takie jak [qubits](xref:microsoft.quantum.glossary#qubit), mogą być połączone lub *Entangled* w taki sposób, że nie mogą być opisane niezależnie od siebie. Wyniki pomiarów są skorelowane nawet wtedy, gdy są oddzielone nieskończonie. Entanglement jest niezbędne do [mierzenia](xref:microsoft.quantum.glossary#measurement) [stanu](xref:microsoft.quantum.glossary#quantum-state) qubit.  Aby uzyskać więcej informacji, zobacz [zaawansowane koncepcje dotyczące macierzy](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>Para EPR

Jeden z czterech konkretnych Maximally Entangled [Quantum](xref:microsoft.quantum.glossary#quantum-state) z dwóch [qubits](xref:microsoft.quantum.glossary#qubit). Cztery Stany są zdefiniowane jako $ \ket { \ beta_ {IJ } } = (\Mathbb{1 } \Otimes X ^ iz ^ j) (\ket{00 } + \ket{11 } )/\sqrt{2 } $. Para EPR jest również znana jako [stan dzwonka](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Działanie

Jak zmienia się [stan Quantum](xref:microsoft.quantum.glossary#quantum-state) w czasie. Aby uzyskać więcej informacji, zobacz informacje o [macierzy wykładniczej](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funkcja
Typ procedury podrzędnej w języku Q #, który jest czysto klasyczny (non-Quantum). Chociaż funkcje są używane w algorytmach Quantum, nie mogą działać na [qubits](xref:microsoft.quantum.glossary#qubit) lub wywołania [operacji](xref:microsoft.quantum.glossary#operation). Aby uzyskać więcej informacji, zobacz [operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="gate"></a>Bram

Starszy termin [operacji](xref:microsoft.quantum.glossary#operation)Quantum na podstawie koncepcji klasycznej bramy logiki. [Obwód Quantum](xref:microsoft.quantum.glossary#quantum-circuit-diagram) to sieć bram (lub operacji), oparta na podobnej koncepcji klasycznych obwodów logiki.

## <a name="global-phase"></a>Faza globalna

Gdy dwa [Stany](xref:microsoft.quantum.glossary#quantum-state) są identyczne do wielokrotności liczby zespolonej $e ^ {i \phi } $, są one określane jako różne fazy globalne. W przeciwieństwie do faz lokalnych, fazy globalne nie mogą być przestrzegane przy [mierzeniu](xref:microsoft.quantum.glossary#measurement). Aby uzyskać więcej informacji, zobacz [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

Operacja Hadamard (określana także jako brama Hadamard lub transformacja) działa na jednym [qubit](xref:microsoft.quantum.glossary#qubit) i umieszcza ją w parzystej [pozycji](xref:microsoft.quantum.glossary#superposition) $ \ket{0 } $ lub $ \ket{1 } $, jeśli qubit jest początkowo w stanie $ \ket{0 } $. W polu Q # ta operacja jest stosowana przez wstępnie zdefiniowaną [`H`](xref:microsoft.quantum.intrinsic.h) operację.

## <a name="immutable"></a>Immutable

Zmienna, której wartość nie może zostać zmieniona. Zmienna niezmienna w Q # jest tworzona za pomocą `let` słowa kluczowego. Aby zadeklarować zmienne, które *można* zmienić, użyj słowa kluczowego [mutable](xref:microsoft.quantum.glossary#immutable) do zadeklarowania i `set` słowa kluczowego w celu zmodyfikowania wartości. 

## <a name="measurement"></a>Miara

Manipulowanie [qubit](xref:microsoft.quantum.glossary#qubit) (lub zestaw qubits), które daje wynik obserwacji, w efekcie uzyskania klasycznego bitu. Aby uzyskać więcej informacji, zobacz [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Modyfikowalny

Zmienna, której wartość może zostać zmieniona po utworzeniu. Zmienna mutable w Q # jest zadeklarowana przy użyciu `mutable` słowa kluczowego i modyfikowane przy użyciu `set` słowa kluczowego. Zmienne utworzone za pomocą `let` słowa kluczowego są [niezmienne](xref:microsoft.quantum.glossary#immutable) i nie można zmienić ich wartości.

## <a name="namespace"></a>Przestrzeń nazw

Etykieta kolekcji pokrewnych nazw (tj. [operacji](xref:microsoft.quantum.glossary#operation), [funkcji](xref:microsoft.quantum.glossary#function)i [typów zdefiniowanych przez użytkownika](xref:microsoft.quantum.glossary#user-defined-type)). Na przykład przestrzeń nazw [Microsoft. Quantum. preparats](xref:microsoft.quantum.preparation) ma wszystkie symbole zdefiniowane w standardowej bibliotece, która pomaga w przygotowywaniu Stanów początkowych.

## <a name="operation"></a>Operacja

Podstawowa jednostka wykonywania Quantum w Q #. Jest w przybliżeniu odpowiednikiem funkcji w języku C, C++ lub Python albo metodą statyczną w C# lub Java. Aby uzyskać więcej informacji, zobacz [operacje i funkcje](xref:microsoft.quantum.guide.operationsfunctions).

## <a name="operator-application"></a>Aplikacja operatora

Wykonywanie operacji Quantum. Zwykle jest to stosowana macierz jednostkowa do bieżącego wektora stanu Quantum.

## <a name="oracle"></a>Oracle

Podprocedura, która dostarcza informacje zależne od danych do algorytmu Quantum w czasie wykonywania. Zazwyczaj celem jest zapewnienie nadmiaru danych [superposition](xref:microsoft.quantum.glossary#superposition) wyjściowych odpowiadających danym wejściowym, które znajdują się w położeniu. Aby uzyskać więcej informacji, zobacz [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Aplikacja częściowa

Wywoływanie [funkcji](xref:microsoft.quantum.glossary#function) lub [operacji](xref:microsoft.quantum.glossary#operation) bez wszystkich wymaganych danych wejściowych. Spowoduje to zwrócenie nowego elementu, który wymaga tylko brakujących parametrów (wskazywanych przez podkreślenie) [, które mają](xref:microsoft.quantum.glossary#callable) być dostarczone podczas przyszłej aplikacji. Na przykład dana funkcja `MyFunc(x : int, y : int) : int {return x + y;}` może zostać częściowo zastosowana do nowej funkcji `let NewFunc = MyFunc(_, 3)` . Następnie można wywołać nową funkcję w późniejszym czasie z brakującym parametrem, `NewFunc(2)` który zwraca wartość *5*.  Aby uzyskać więcej informacji, zobacz [częściowa aplikacja](xref:microsoft.quantum.guide.operationsfunctions#partial-application).

## <a name="pauli-operators"></a>Operatory Pauli

Zestaw trzech 2 x 2 macierzy jednostkowych znanych jako `X` `Y` `Z` operacje Quantum i. Macierz tożsamości, $I $ , jest często uwzględniana w zestawie.  $I = \begin{ bmatrix } 1 & 0 \\ \\ 0 & 1 \end{ bmatrix } $, $X = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } $, $Y = \begin{ bmatrix } 0 &-i \\ \\ & 0 \end{ bmatrix } $, $Z = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } $.   Aby uzyskać więcej informacji, zobacz [operacje pojedynczego qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagram obwodu Quantum

Metoda graficznego reprezentowania sekwencji [operacji](xref:microsoft.quantum.glossary#operation) (lub [bram](xref:microsoft.quantum.glossary#gate)) dla prostych programów Quantum, na przykład 

![Przykładowy diagram obwodu](~/media/qpe.png). 

Aby uzyskać więcej informacji, zobacz [obwodów Quantum](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Biblioteki Quantum

Kolekcje [operacji](xref:microsoft.quantum.glossary#operation), [funkcji](xref:microsoft.quantum.glossary#function) i [typów zdefiniowanych przez użytkownika](xref:microsoft.quantum.glossary#user-defined-type) do tworzenia programów pytań i odpowiedzi. [Standardowa biblioteka](xref:microsoft.quantum.libraries.standard.intro) jest instalowana domyślnie. Dostępne są inne biblioteki [chemiczne](xref:microsoft.quantum.chemistry.concepts.intro), [biblioteki liczbowe](xref:microsoft.quantum.numerics.intro) i [Biblioteka uczenia maszynowego](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Stan Quantum

Dokładny stan izolowanego systemu Quantum, z którego można wyodrębnić prawdopodobieństwa [pomiaru](xref:microsoft.quantum.glossary#measurement) . W przypadku przetwarzania Quantum symulatory Quantum używa tych informacji do symulowania sposobu reagowania qubits na operacje. Aby uzyskać więcej informacji, zobacz [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Podstawowa jednostka informacji Quantum, analogiczna do *bitu* w środowisku klasycznym. Aby uzyskać więcej informacji, zobacz [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Powtarzaj-do-sukces

Algorytm Quantum, który probabilistically się pomyślnie. W przypadku niepowodzenia procedura ponowi próbę do momentu pomyślnego (lub limit został osiągnięty). Aby uzyskać więcej informacji, zobacz [powtarzanie do momentu sukcesu (jednostek ru)](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop)

## <a name="standard-libraries"></a>Biblioteki standardowe

[Operacje](xref:microsoft.quantum.glossary#operation), [funkcje](xref:microsoft.quantum.glossary#function) i [typy zdefiniowane przez użytkownika](xref:microsoft.quantum.glossary#user-defined-type) , które są instalowane wraz z kompilatorem Q # podczas instalacji. Implementacja biblioteki standardowej jest niezależny od w odniesieniu do komputerów docelowych. Aby uzyskać więcej informacji, zobacz [biblioteki standardowe](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Nadpozycja

Koncepcja w ramach przetwarzania Quantum polega na tym, że [qubit](xref:microsoft.quantum.glossary#qubit) jest kombinacją liniową dwóch stanów, $ \ket{0 } $ i $ \ket{1 } $, dopóki nie zostanie ona [zmierzona](xref:microsoft.quantum.glossary#measurement).  Aby uzyskać więcej informacji, zobacz [Omówienie przetwarzania Quantum](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Maszyna docelowa

Element docelowy kompilacji, który obniża abstrakcyjny program Quantum do sprzętu lub symulacji. Obejmuje to zwykle ponowne zapisy w wielu celach, w tym zastępowanie bram, kodowanie dla korekcji błędów, układ geometryczny i inne. Aby uzyskać więcej informacji, zobacz [symulatory Quantum i aplikacje hosta](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportacja

Metoda służąca do ponownego generowania danych lub [stan Quantum](xref:microsoft.quantum.glossary#quantum-state), jednego [qubit](xref:microsoft.quantum.glossary#qubit) z jednego miejsca do drugiego bez fizycznego przesuwania qubit przy użyciu [Entanglement](xref:microsoft.quantum.glossary#entanglement) i [pomiaru](xref:microsoft.quantum.glossary#measurement).  Aby uzyskać więcej informacji, zobacz [obwodów Quantum](xref:microsoft.quantum.concepts.circuits) i odpowiednich Kata na [Quantum Katas](xref:microsoft.quantum.overview.katas).

## <a name="tuple"></a>Spoin

Kolekcja wartości rozdzielonych przecinkami, które pełnią funkcję pojedynczej wartości. *Typ* krotki jest definiowany przez typy wartości, które zawiera. W pytaniach Q # kolekcje są [niezmienne](xref:microsoft.quantum.glossary#immutable) i mogą być zagnieżdżone, zawierać tablice lub używane w tablicy. Aby uzyskać więcej informacji, zobacz [typy krotek](xref:microsoft.quantum.guide.types#tuple-types).

## <a name="unitary-operator"></a>Operator jednostkowy

Operator, którego odwrotność jest równa jego [sąsiedniej](xref:microsoft.quantum.glossary#adjoint), tj. $uu ^ {\dagger } = \id $ .

## <a name="user-defined-type"></a>Typ zdefiniowany przez użytkownika

Kolekcja wbudowanych lub wcześniej zdefiniowanych typów, które mogą być określane jako pojedyncza jednostka. Aby uzyskać więcej informacji, zobacz [typy zdefiniowane przez użytkownika](xref:microsoft.quantum.guide.types#user-defined-types).