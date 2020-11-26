---
title: Opis słownika przetwarzania Quantum: słownik typowych warunków, akcji i obiektów używanych w ramach przetwarzania Quantum.
Autor: bradben MS. Author: v-benbra MS. Date: 9/1/2020 MS. temat: identyfikator UID artykułu: Microsoft. Quantum. słownik No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="quantum-computing-glossary"></a>Słownik przetwarzania Quantum

## <a name="adjoint"></a>Sąsiadująco

Złożone sprzężenie sprzężone [operacji](xref:microsoft.quantum.glossary#operation). W przypadku operacji implementujących operator [jednostkowy](xref:microsoft.quantum.glossary#unitary-operator) sąsiadujący jest odwrotną operacją i jest wskazywany przez symbol Dagger. Na przykład, jeśli operacja `U` reprezentuje operator jednostki $ U $ , a następnie `Adjoint U` reprezentuje $ U ^ \dagger $ . Aby uzyskać więcej informacji, zobacz [Funktor Application](xref:microsoft.quantum.qsharp.functorapplication#functor-application).

## <a name="ancilla"></a>Ancilla

[Qubit](xref:microsoft.quantum.glossary#qubit) , który służy jako pamięć tymczasowa dla komputera z systemem Quantum i jest przypisywany i cofa alokację w razie potrzeby.  Aby uzyskać więcej informacji, zobacz [wiele qubits](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Stan dzwonka

Jeden z czterech konkretnych Maximally [Entangled](xref:microsoft.quantum.glossary#entanglement) [Quantum](xref:microsoft.quantum.glossary#quantum-state) z dwóch qubits. Cztery Stany są zdefiniowane $ \ket { \beta _ { IJ } } = ( \mathbb { I } \otimes X ^ iz ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Stan dzwonka jest również znany jako [para EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Bloch sfera

Graficzna reprezentacja[jednoqubitowego](xref:microsoft.quantum.glossary#qubit) [stanu Quantum](xref:microsoft.quantum.glossary#quantum-state) jako punktu w trójwymiarowej sferze jednostki. Aby uzyskać więcej informacji, zobacz  [Wizualizacja Qubits i transformacji przy użyciu sfery Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Żądanie

[Operacja](xref:microsoft.quantum.glossary#operation) lub [Funkcja](xref:microsoft.quantum.glossary#function) w [ Q# języku](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language).
Aby uzyskać więcej informacji, zobacz [ Q# programy](xref:microsoft.quantum.guide.programs)

## <a name="clifford-group"></a>Grupa Clifford

Zestaw operacji, które zajmują octantsą w [sferze Blochej](xref:microsoft.quantum.glossary#bloch-sphere) i permutacji dla [operatorów Pauli](xref:microsoft.quantum.glossary#pauli-operators). Obejmują one operacje [ $ X $ ](xref:Microsoft.Quantum.Intrinsic.X), [ $ Y $ ](xref:Microsoft.Quantum.Intrinsic.Y), [ $ Z $ ](xref:Microsoft.Quantum.Intrinsic.Z), [ $ H $ ](xref:Microsoft.Quantum.Intrinsic.H) i [ $ S $ ](xref:Microsoft.Quantum.Intrinsic.S).

## <a name="controlled"></a>Kontrolowane

[Operacja](xref:microsoft.quantum.glossary#operation) Quantum, która przyjmuje co najmniej jeden [qubits](xref:microsoft.quantum.glossary#qubit) jako element do obsługi dla operacji docelowej. Aby uzyskać więcej informacji, zobacz [Funktor Application](xref:microsoft.quantum.qsharp.functorapplication#functor-application).

## <a name="dirac-notation"></a>Notacja Dirac

Symboliczny skrót, który upraszcza reprezentację [Stanów Quantum](xref:microsoft.quantum.glossary#quantum-state), nazywany również notacją *bra-KET* .  Część *bra* reprezentuje wektor wierszy, na przykład _1 a $ \bra { } = \begin{bmatrix} _2, { } & { } \end{bmatrix} $ a część *KET* reprezentuje wektor kolumny, $ \ket { b } = \begin{bmatrix} b { _1 } \\\\ b { _2 } \end{bmatrix} $ . Aby uzyskać więcej informacji, zobacz [notacja Dirac](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Eigenvalue

Współczynnik, przez który rozmiary [eigenvector](xref:microsoft.quantum.glossary#eigenvector) danego przekształcenia są zmieniane przez aplikację transformacji.  Dana macierz kwadratowa $ M $ i eigenvector $ v $ , następnie $ MV = CV $ , gdzie $ c $ jest eigenvalue i może być złożoną liczbą dowolnego argumentu. Aby uzyskać więcej informacji, zobacz [zaawansowane koncepcje dotyczące macierzy](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="eigenvector"></a>Eigenvector

Wektor, którego kierunek jest niezmieniony przez daną transformację i którego wielkość jest zmieniana przez współczynnik odpowiadający [eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)tego wektora. W przypadku macierzy kwadratowej $ M $ i eigenvalue $ c $ , a następnie $ MV = CV $ , gdzie $ v $ jest eigenvector macierzy i może być złożoną liczbą dowolnego argumentu. Aby uzyskać więcej informacji, zobacz [zaawansowane koncepcje dotyczące macierzy](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="entanglement"></a>Splątanie

Cząstki Quantum, takie jak [qubits](xref:microsoft.quantum.glossary#qubit), mogą być połączone lub *Entangled* w taki sposób, że nie mogą być opisane niezależnie od siebie. Wyniki pomiarów są skorelowane nawet wtedy, gdy są oddzielone nieskończonie. Entanglement jest niezbędne do [mierzenia](xref:microsoft.quantum.glossary#measurement) [stanu](xref:microsoft.quantum.glossary#quantum-state) qubit.  Aby uzyskać więcej informacji, zobacz [zaawansowane koncepcje dotyczące macierzy](xref:microsoft.quantum.concepts.matrix-advanced).

## <a name="epr-pair"></a>Para EPR

Jeden z czterech konkretnych Maximally Entangled [Quantum](xref:microsoft.quantum.glossary#quantum-state) z dwóch [qubits](xref:microsoft.quantum.glossary#qubit). Cztery Stany są zdefiniowane $ \ket { \beta _ { IJ } } = ( \mathbb { 1 } \otimes X ^ iz ^ j) ( \ket { 00 }  +  \ket { 11 } )/ \sqrt { 2 } $ . Para EPR jest również znana jako [stan dzwonka](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Działanie

Jak zmienia się [stan Quantum](xref:microsoft.quantum.glossary#quantum-state) w czasie. Aby uzyskać więcej informacji, zobacz informacje o [macierzy wykładniczej](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funkcja
Typ podprocedury w Q# języku, który jest całkowicie deterministyczny. Chociaż funkcje są używane w algorytmach Quantum, nie mogą działać na [qubits](xref:microsoft.quantum.glossary#qubit) lub wywołania [operacji](xref:microsoft.quantum.glossary#operation). Aby uzyskać więcej informacji, zobacz [ Q# programy](xref:microsoft.quantum.guide.programs)

## <a name="gate"></a>Bram

Starszy termin dla niektórych wewnętrznych [operacji](xref:microsoft.quantum.glossary#operation)Quantum oparty na koncepcji klasycznych bram logiki. [Obwód Quantum](xref:microsoft.quantum.glossary#quantum-circuit-diagram) jest siecią bram, w oparciu o podobną koncepcję klasycznych obwodów logiki.

## <a name="global-phase"></a>Faza globalna

Gdy dwa [Stany](xref:microsoft.quantum.glossary#quantum-state) są identyczne do wielokrotności liczby zespolonej $ e ^ { i \phi } $ , są one określane jako różne fazy globalne. W przeciwieństwie do faz lokalnych, fazy globalne nie mogą być przestrzegane przy [mierzeniu](xref:microsoft.quantum.glossary#measurement). Aby uzyskać więcej informacji, zobacz [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

Operacja Hadamard (określana także jako brama Hadamard lub transformacja) działa w ramach jednego [qubitu](xref:microsoft.quantum.glossary#qubit) i umieszcza je w parzystej [pozycji](xref:microsoft.quantum.glossary#superposition) $ \ket { 0 } $ lub $ \ket { 1 } $ , jeśli qubit jest początkowo w $ \ket { } $ stanie 0. W programie Q# Ta operacja jest stosowana przez wstępnie zdefiniowaną [`H`](xref:Microsoft.Quantum.Intrinsic.H) operację.

## <a name="immutable"></a>Immutable

Zmienna, której wartość nie może zostać zmieniona. Zmienna niezmienna w Q# jest tworzona za pomocą `let` słowa kluczowego. Aby zadeklarować zmienne, które *można* zmienić, użyj słowa kluczowego [mutable](xref:microsoft.quantum.glossary#immutable) do zadeklarowania i `set` słowa kluczowego w celu zmodyfikowania wartości. 

## <a name="measurement"></a>Miara

Manipulowanie [qubit](xref:microsoft.quantum.glossary#qubit) (lub zestaw qubits), które daje wynik obserwacji, w efekcie uzyskania klasycznego bitu. Aby uzyskać więcej informacji, zobacz [qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Modyfikowalny

Zmienna, której wartość może zostać zmieniona po utworzeniu. Zmienna modyfikowalna w Q# jest zadeklarowana za pomocą `mutable` słowa kluczowego i modyfikowane przy użyciu `set` słowa kluczowego. Zmienne utworzone za pomocą `let` słowa kluczowego są [niezmienne](xref:microsoft.quantum.glossary#immutable) i nie można zmienić ich wartości.

## <a name="namespace"></a>Przestrzeń nazw

Etykieta kolekcji pokrewnych nazw (tj. [operacji](xref:microsoft.quantum.glossary#operation), [funkcji](xref:microsoft.quantum.glossary#function)i [typów zdefiniowanych przez użytkownika](xref:microsoft.quantum.glossary#user-defined-type)). Na przykład przestrzeń nazw [Microsoft. Quantum. preparats](xref:Microsoft.Quantum.Preparation) ma wszystkie symbole zdefiniowane w standardowej bibliotece, która pomaga w przygotowywaniu Stanów początkowych.

## <a name="operation"></a>Operacja

Jednostka podstawowa obliczeń w Q# . Jest w przybliżeniu odpowiednikiem funkcji w języku C, C++ lub Python albo metodą statyczną w C# lub Java. Aby uzyskać więcej informacji, zobacz [ Q# programy](xref:microsoft.quantum.guide.programs).

## <a name="oracle"></a>Oracle

Podprocedura, która dostarcza informacje zależne od danych do algorytmu Quantum w czasie wykonywania. Zazwyczaj celem jest zapewnienie nadmiaru danych [superposition](xref:microsoft.quantum.glossary#superposition) wyjściowych odpowiadających danym wejściowym, które znajdują się w położeniu. Aby uzyskać więcej informacji, zobacz [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Aplikacja częściowa

Wywoływanie [funkcji](xref:microsoft.quantum.glossary#function) lub [operacji](xref:microsoft.quantum.glossary#operation) bez wszystkich wymaganych danych wejściowych. Spowoduje to zwrócenie nowego elementu, który wymaga tylko brakujących parametrów (wskazywanych przez podkreślenie) [, które mają](xref:microsoft.quantum.glossary#callable) być dostarczone podczas przyszłej aplikacji. Aby uzyskać więcej informacji, zobacz [częściowa aplikacja](xref:microsoft.quantum.qsharp.partialapplication).

## <a name="pauli-operators"></a>Operatory Pauli

Zestaw 3 2 x 2 macierze jednostkowe znane jako `X` `Y` `Z` operacje Quantum i. Macierz tożsamości $ i $ , często znajdują się w zestawie.  $I od = \begin{bmatrix} 1 & 0 0 \\\\ & \end{bmatrix} $ $ do X = \begin{bmatrix} 0 & 1 \\\\ & 0 \end{bmatrix} $ , $ Y = \begin{bmatrix} 0 & -i \\\\ i & 0 \end{bmatrix} $ , $ Z = \begin{bmatrix} 1 0 0 & \\\\ & -1 \end{bmatrix} $ .   Aby uzyskać więcej informacji, zobacz [operacje pojedynczego qubit](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagram obwodu Quantum

Metoda graficznego reprezentowania sekwencji [bram](xref:microsoft.quantum.glossary#gate) dla prostych programów Quantum, na przykład 

![Przykładowy diagram obwodu](~/media/qpe.png). 

Aby uzyskać więcej informacji, zobacz [obwodów Quantum](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Biblioteki Quantum

Kolekcje [operacji](xref:microsoft.quantum.glossary#operation), [funkcji](xref:microsoft.quantum.glossary#function) i [typów zdefiniowanych przez użytkownika](xref:microsoft.quantum.glossary#user-defined-type) do tworzenia Q# programów. [Standardowa biblioteka](xref:microsoft.quantum.libraries.standard.intro) jest instalowana domyślnie. Dostępne są inne biblioteki [chemiczne](xref:microsoft.quantum.chemistry.concepts.intro), [biblioteki liczbowe](xref:microsoft.quantum.numerics.intro) i [Biblioteka uczenia maszynowego](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Stan Quantum

Dokładny stan izolowanego systemu Quantum, z którego można wyodrębnić prawdopodobieństwa [pomiaru](xref:microsoft.quantum.glossary#measurement) . W przypadku przetwarzania Quantum symulatory Quantum używa tych informacji do symulowania sposobu reagowania qubits na operacje. Aby uzyskać więcej informacji, zobacz [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Podstawowa jednostka informacji Quantum, analogiczna do *bitu* w środowisku klasycznym. Aby uzyskać więcej informacji, zobacz [qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Powtarzaj-do-sukces

Koncepcja często używana w algorytmach Quantum, która składa się z wielokrotnego zastosowania obliczeń do momentu spełnienia określonego warunku. Gdy warunek nie jest spełniony, często wymagana jest naprawa przed ponowną próbą, wprowadzając następną iterację. Aby uzyskać więcej informacji, zobacz [ Q# Podręcznik użytkownika](xref:microsoft.quantum.guide)

## <a name="standard-libraries"></a>Biblioteki standardowe

[Operacje](xref:microsoft.quantum.glossary#operation), [funkcje](xref:microsoft.quantum.glossary#function) i [typy zdefiniowane przez użytkownika](xref:microsoft.quantum.glossary#user-defined-type) , które są instalowane wraz z Q# kompilatorem podczas instalacji. Implementacja biblioteki standardowej jest niezależny od w odniesieniu do komputerów docelowych. Aby uzyskać więcej informacji, zobacz [biblioteki standardowe](xref:microsoft.quantum.libraries.standard.intro).

## <a name="superposition"></a>Nadpozycja

Koncepcja w ramach przetwarzania Quantum polega na tym, że [qubit](xref:microsoft.quantum.glossary#qubit) jest kombinacją liniową dwóch stanów, $ \ket { 0 } $ i $ \ket { 1 } $ , dopóki nie zostanie ona [zmierzona](xref:microsoft.quantum.glossary#measurement).  Aby uzyskać więcej informacji, zobacz [Omówienie przetwarzania Quantum](xref:microsoft.quantum.overview.understanding).

## <a name="target-machine"></a>Maszyna docelowa

Element docelowy kompilacji, który obniża abstrakcyjny program Quantum do sprzętu lub symulacji. Obejmuje to zwykle ponowne zapisy w wielu celach, w tym zastępowanie bram, kodowanie dla korekcji błędów, układ geometryczny i inne. Aby uzyskać więcej informacji, zobacz [symulatory Quantum i aplikacje hosta](xref:microsoft.quantum.machines).

## <a name="teleportation"></a>Teleportacja

Metoda służąca do ponownego generowania danych lub [stan Quantum](xref:microsoft.quantum.glossary#quantum-state), jednego [qubit](xref:microsoft.quantum.glossary#qubit) z jednego miejsca do drugiego bez fizycznego przesuwania qubit przy użyciu [Entanglement](xref:microsoft.quantum.glossary#entanglement) i [pomiaru](xref:microsoft.quantum.glossary#measurement).  Aby uzyskać więcej informacji, zobacz [obwodów Quantum](xref:microsoft.quantum.concepts.circuits) i odpowiednich Kata na [Quantum Katas](xref:microsoft.quantum.overview.katas).

## <a name="tuple"></a>Spoin

Kolekcja wartości rozdzielonych przecinkami, które pełnią funkcję pojedynczej wartości. *Typ* krotki jest definiowany przez typy wartości, które zawiera. W programie Q# krotki są [niezmienne](xref:microsoft.quantum.glossary#immutable) i mogą być zagnieżdżane, zawierać tablice lub używane w tablicy. Aby uzyskać więcej informacji, zobacz [krotki](xref:microsoft.quantum.qsharp.valueliterals#tuple-literals).

## <a name="unitary-operator"></a>Operator jednostkowy

Operator, którego odwrotność jest równa jego [sąsiedniej](xref:microsoft.quantum.glossary#adjoint), tj. $ uu ^ { \dagger } = \id $ .

## <a name="user-defined-type"></a>Typ zdefiniowany przez użytkownika

Typ niestandardowy, który może zawierać co najmniej jeden nazwany lub anonimowy element. Aby uzyskać więcej informacji, zobacz [deklaracje typów] Microsoft. Quantum. qsharp. typedeclarations # Type-deklaracjis).
