---
title: Informacje o wersji zapoznawczej zestawu Quantum Development Kit
description: Informacje o wersji zapoznawczej zestawu Quantum Development Kit
author: natke
ms.author: nakersha
ms.date: 09/30/2019
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: be1eff8127be9fb024a1dc2de3ec82952ac2dc2b
ms.sourcegitcommit: b7e205aaa7fa1ca9f0daa163e46154945f4bc965
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/18/2020
ms.locfileid: "77441033"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Informacje o wersji zestawu Microsoft Quantum Development Kit

Ten artykuł zawiera informacje dotyczące poszczególnych wersji zestawu Quantum Development Kit.

Instrukcje instalacji znajdują się w [przewodniku instalacji](xref:microsoft.quantum.install).

Instrukcje dotyczące aktualizacji znajdują się w [przewodniku aktualizacji](xref:microsoft.quantum.update).


## <a name="version-01020012831"></a>Wersja 0.10.2001.2831

*Data wydania: 29 stycznia 2020 r.*

To wydanie zawiera następujące elementy:

- Nowy pakiet NuGet Microsoft.Quantum.SDK
- Dodano obsługę platformy .NET Core 3.1; zdecydowanie zaleca się zainstalowanie wersji 3.1.100, ponieważ kompilowanie przy użyciu starszych wersji zestawu .NET Core SDK może powodować problemy
- Nowe przekształcenia kompilatorów są dostępne w ramach elementu Microsoft.Quantum.QsCompiler.Experimental
- Nowa funkcja uwidaczniająca wyjściowe wektory stanu jako kod HTML w jądrze IQ#
- Dodano obsługę elementu EstimateFrequencyA do przestrzeni nazw Microsoft.Quantum.Characterization dla testów Hadamard i SWAP
- Przestrzeń nazw AmplitudeAmplification używa teraz przewodnika dotyczącego stylu języka Q#

## <a name="version-01019120501"></a>Wersja 0.10.1912.0501

*Data wydania: 5 grudnia 2019 r.*

To wydanie zawiera następujące elementy:

- Nowy atrybut testu na potrzeby testowania jednostkowego Q#; zobacz zaktualizowaną dokumentację interfejsu API [w tym miejscu](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) oraz zaktualizowany przewodnik po testowaniu i debugowaniu [tutaj](xref:microsoft.quantum.techniques.testing-and-debugging)
- Dodano ślad stosu w przypadku błędu wykonywania programu Q#
- Obsługa punktów przerwania w programie Visual Studio Code dzięki aktualizacji [rozszerzenia OmniSharp C# programu Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Wersja 0.10.1911.1607

*Data wydania: 17 listopada 2019 r.*

To wydanie zawiera następujące elementy:

- Poprawka wydajności dla samouczków [Quantum Katas](https://github.com/Microsoft/QuantumKatas) i notesów Jupyter

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Wersja 0.10.1911.307

*Data wydania: 1 listopada 2019 r.*

To wydanie zawiera następujące elementy:

- Aktualizacje rozszerzeń programów Visual Studio Code i Visual Studio dotyczące wdrażania serwera języka jako autonomicznego pliku wykonywalnego, eliminując w ten sposób zależność od wersji zestawu .NET Core SDK  
- Migracja do platformy .NET Core 3.0
- Istotna zmiana w elemencie Microsoft.Quantum.Simulation.Core.IOperationFactory po wprowadzeniu nowej metody `Fail`. Dotyczy ona tylko symulatorów niestandardowych, które nie rozszerzają elementu SimulatorBase. Aby uzyskać więcej informacji, [wyświetl pełne żądanie ściągnięcia w usłudze GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Nowa obsługa przestarzałych atrybutów

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Wersja 0.9.1909.3002

*Data wydania: 30 września 2019 r.*

To wydanie zawiera następujące elementy:

- Nowa obsługa uzupełniania kodu języka Q# w programie Visual Studio 2019 (wersje 16.3 i nowsze) i w edytorze Visual Studio Code
- Nowy samouczek [Quantum Kata](https://github.com/Microsoft/QuantumKatas) dla osób dodających zasoby kwantowe

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Wersja 0.9 (*PackageReference 0.9.1908.2902*)

*Data wydania: 29 sierpnia 2019 r.*

To wydanie zawiera następujące elementy:

- Nowa obsługa [instrukcji sprzężeń](xref:microsoft.quantum.language.statements#conjugations) w języku Q#
- Nowe akcje kodu w kompilatorze, takie jak „zamień na”, „dodaj dokumentację” i prosta aktualizacja elementu tablicy
- Dodano szablon instalacji i nowe polecenia projektu do rozszerzenia edytora Visual Studio Code
- Dodano nowe odmiany kombinatora ApplyIf, takie jak [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)
- Dodatkowe samouczki [Quantum Kata](https://github.com/Microsoft/QuantumKatas) przekształcono w notesy Jupyter
- Rozszerzenie programu Visual Studio wymaga teraz programu Visual Studio 2019

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Podsumowano zmiany i przedstawiono instrukcje uaktualniania istniejących programów.  Więcej informacji na temat tych zmian można znaleźć na [blogu deweloperów języka Q#](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Wersja 0.8 (*PackageReference 0.8.1907.1701*)

*Data wydania: 12 lipca 2019 r.*

To wydanie zawiera następujące elementy:

- Nowe lokalizacje indeksowania dla tablic wycinków. [Zobacz informacje dotyczące języka](xref:microsoft.quantum.language.expressions#array-slices), aby uzyskać więcej informacji.
- Dodano obsługę pliku Dockerfile hostowanego w usłudze [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry). Zobacz [repozytorium IQ#, aby uzyskać więcej informacji](https://github.com/microsoft/iqsharp/blob/master/README.md)
- Zmiana powodująca niezgodność dotycząca [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro), aktualizacja ustawień konfiguracji, zmiany nazw. Zobacz [Przeglądarka interfejsów API na platformie .NET — zaktualizowanie nazwy](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) i [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Wersja 0.7 (*PackageReference 0.7.1905.3109*)

*Data wydania: 31 maja 2019 r.*

To wydanie zawiera następujące elementy:
- Dodatki do języka Q# 
- Aktualizacje biblioteki chemicznej 
- Nowa biblioteka liczbowa

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) i [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Podsumowano zmiany i przedstawiono instrukcje uaktualniania istniejących programów.  Więcej informacji na temat tych zmian można znaleźć na [blogu deweloperów języka Q#](https://devblogs.microsoft.com/qsharp).

### <a name="q-language-syntax"></a>Składnia języka Q#
W tej wersji dodano nowe elementy składni języka Q#:
* Dodano nazwane elementy dla [typów zdefiniowanych przez użytkownika](xref:microsoft.quantum.language.type-model#user-defined-types).  
* Konstruktory typów zdefiniowanych przez użytkownika mogą być teraz używane jako funkcje.
* W typach zdefiniowanych przez użytkownika dodano obsługę wyrażeń [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) oraz [apply-and-reassign]((xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)).
* Blok naprawy dla pętli [repeat-until-success](xref:microsoft.quantum.language.statements#repeat-until-success-loop) jest teraz opcjonalny.
* Obsługa pętli while w funkcjach (nie w operacjach).

### <a name="library"></a>Biblioteka 

W tej wersji dodano bibliotekę liczbową: Dowiedz się więcej o sposobie [korzystania z nowej biblioteki liczbowej](xref:microsoft.quantum.numerics.usage) i wypróbuj [nowe przykłady](https://github.com/microsoft/quantum/tree/master/Numerics).  [Żądanie ściągnięcia nr 102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Ta wersja reorganizuje rozszerzania i aktualizuje bibliotekę chemiczną:
* Poprawiono modułowość składników i rozszerzalność oraz przeprowadzono ogólne czyszczenie kodu.  [Żądanie ściągnięcia nr 58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Dodano obsługę [funkcji falowych z wieloma odwołaniami](xref:microsoft.quantum.chemistry.concepts.multireference) — zarówno rozrzedzonych funkcji falowych z wieloma odwołaniami, jak i unitarnego klastra sprzężonego.  [Żądanie ściągnięcia nr 110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Dzięki Wam!) Współautor [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Ocena energii przy użyciu założenia zmiennego. [Żądanie ściągnięcia nr 120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Zaktualizowano schemat [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) do nowej [wersji 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), dodano specyfikację unitarnego klastra sprzężonego. [Problem nr 65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Dodano współdziałania języka Python z funkcjami biblioteki chemicznej. Wypróbuj ten [przykład](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration). [Problem 53](https://github.com/microsoft/QuantumLibraries/issues/53) [Żądanie ściągnięcia 110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Wersja 0.6.1905

*Data wydania: 3 maja 2019 r.*

To wydanie zawiera następujące elementy:
- Wprowadzono zmiany w języku Q# 
- Dokonano restrukturyzacji bibliotek zestawu Quantum Development Kit 
- Dodano nowe przykłady 
- Naprawiono błędy  Kilka zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) i [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Podsumowano zmiany i przedstawiono instrukcje uaktualniania istniejących programów.  Więcej informacji na temat tych zmian można znaleźć w pod adresem devblogs.microsoft.com/qsharp.

### <a name="q-language-syntax"></a>Składnia języka Q#
W tej wersji dodano nowe elementy składni języka Q#:
* Dodano [skrócony sposób wyrażania specjalizacji operacji kwantowych](xref:microsoft.quantum.language.type-model#functors) (kontroli i dołączania) za pomocą operatorów `+`.  Stara składnia jest przestarzała.  Programy używające starej składni (np. `: adjoint`) będą nadal działać, ale zostanie wygenerowane ostrzeżenie dotyczące czasu kompilacji.  
* Dodano nowy operator dla wyrażenia [copy-and-update](xref:microsoft.quantum.language.expressions#copy-and-update-expressions). W celu wyrażenia tworzenia tablicy jako modyfikacji istniejącej tablicy można używać operatora `w/`.
* Dodano wspólną [instrukcję apply-and-upate](xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols), np. `+=`, `w/=`.
* Dodano sposób określania krótkiej nazwy przestrzeni nazw w [otwartych dyrektywach](xref:microsoft.quantum.language.file-structure#open-directives).

W tej wersji nie zezwalamy już na określanie elementu tablicy po lewej stronie instrukcji ustawiania.  Wynika to z faktu, że składnia implikuje, że tablice są modyfikowalne, a w rzeczywistości wynikiem operacji zawsze było utworzenie nowej tablicy z modyfikacją.  Zamiast tego będzie generowany błąd kompilatora z sugestią użycia nowego operatora copy-and-update, `w/`, w celu osiągnięcia tego samego wyniku.  

### <a name="library-restructuring"></a>Restrukturyzacja biblioteki
Ta wersja reorganizuje biblioteki, aby umożliwić ich spójny wzrost:
* Zmieniono nazwę przestrzeni nazw Microsoft.Quantum.Primitive na Microsoft.Quantum.Intrinsic.  Te operacje są implementowane przez maszynę docelową.  Przestrzeń nazw Microsoft.Quantum.Primitive jest przestarzała.  Jeśli programy będą wywoływać operacje i funkcje przy użyciu przestarzałych nazw, zostanie wygenerowane ostrzeżenie środowiska uruchomieniowego.

* Zmieniono nazwę pakietu Microsoft.Quantum.Canon na Microsoft.Quantum.Standard.  Ten pakiet zawiera przestrzenie nazw, które są wspólne dla większości programów tworzonych za pomocą języka Q#.  Obejmuje to:  
    - Microsoft.Quantum.Canon na potrzeby najczęściej wykonywanych operacji
    - Microsoft.Quantum.Arithmetic na potrzeby operacji arytmetycznych ogólnego zastosowania
    - Microsoft.Quantum.Preparation na potrzeby operacji przygotowywania stanu kubitu
    - Microsoft.Quantum.Simulation na potrzeby funkcji symulacji

Po wprowadzeniu tych zmian programy, które zawierają pojedynczą instrukcję „open” dla przestrzeni nazw Microsoft.Quatum.Canon, mogą napotkać błędy kompilacji, jeśli program odwołuje się do operacji przeniesionych do tych trzech nowych przestrzeni nazw.  Ten problem można rozwiązać w prosty sposób, dodając dodatkowe instrukcje „open” dla trzech nowych przestrzeni nazw.  

* Niektóre przestrzenie nazw stały się przestarzałe, ponieważ znajdujące się w nich operacje zostały przeniesione do innych przestrzeni nazw. Programy korzystające z tych przestrzeni nazw będą nadal działały, a wyświetlone w czasie kompilacji ostrzeżenie będzie wskazywało przestrzeń nazw, w której jest zdefiniowana operacja.  

* Znormalizowano przestrzeń nazw Microsoft.Quantum.Arithmetic, aby korzystała ze zdefiniowanego przez użytkownika typu <xref:microsoft.quantum.arithmetic.littleendian>. Jeśli zajdzie konieczność przekształcenia do formy little endian, należy użyć funkcji [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian).  

* Zmieniono nazwy kilku elementów wywoływanych (funkcji i operacji) tak, aby były zgodne z [przewodnikiem dotyczącym stylu języka Q#](xref:microsoft.quantum.contributing.style).  Stare nazwy elementów wywoływanych stały się przestarzałe.  Programy używające starych elementów wywoływanych będą nadal działały z ostrzeżeniem w czasie kompilacji. 

### <a name="new-samples"></a>Nowe przykłady

Dodaliśmy [przykład użycia języka Q# ze sterownikiem F#](https://github.com/Microsoft/Quantum/pull/164).  

**Dziękujemy** wymienionemu poniżej współautorowi bazy otwartego kodu w repozytorium http://github.com/Microsoft/Quantum. Te współtworzone elementy wiele wnoszą do bogatych przykładów kodu Q#:

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Synteza funkcji firmy Oracle. [Żądanie ściągnięcia nr 135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migrowanie istniejących projektów do wersji 0.6.1905.

Informacje na temat aktualizowania zestawu QDK znajdują się w [przewodniku instalacji](xref:microsoft.quantum.install).
  
Jeśli masz istniejące projekty języka Q# z wersji 0.5 zestawu Quantum Development Kit, poniżej przedstawiono procedurę migrowania tych projektów do najnowszej wersji.

    1. Projekty muszą zostać uaktualnione w odpowiedniej kolejności.  Jeśli masz rozwiązanie z wieloma projektami, zaktualizuj poszczególne projekty w kolejności, w jakiej są przywoływane.
    2. W wierszu polecenia uruchom polecenie `dotnet clean`, aby usunąć wszystkie istniejące dane binarne i pliki pośrednie.
    3. W edytorze tekstów otwórz plik csproj i zmień wersję wszystkich elementów „Microsoft. Quantum” `PackageReference` na wersję 0.6.1904, a następnie zmień nazwę pakietu „Microsoft.Quantum.Canon” na „Microsoft.Quantum.Standard”, na przykład:

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. W wierszu polecenia uruchom następujące polecenie: `dotnet msbuild`  
    5. Po uruchomieniu tego polecenia może być konieczne ręczne usunięcie błędów powstałych w wyniku wprowadzenia opisanych powyżej zmian.  W wielu przypadkach te błędy będą również raportowane przez funkcję IntelliSense w programie Visual Studio lub edytorze Visual Studio Code.
        - Otwórz folder główny projektu lub obejmujące rozwiązanie w programie Visual Studio 2019 bądź w edytorze Visual Studio Code.
        - Po otwarciu pliku qs w edytorze powinny zostać wyświetlone dane wyjściowe rozszerzenia języka Q# w oknie danych wyjściowych.
        - Po pomyślnym załadowaniu projektu (zostanie to zasygnalizowane w oknie danych wyjściowych) otwórz każdy plik i ręcznie rozwiąż wszystkie pozostałe problemy.

> [!NOTE]
> * W wersji 0.6 serwer języka dołączony do zestawu Quantum Development Kit nie obsługuje wielu obszarów roboczych.
> * Aby można było korzystać z projektu w edytorze Visual Studio Code, otwórz folder główny zawierający projekt i wszystkie przywoływane projekty.   
> * Aby można było korzystać z rozwiązania w programie Visual Studio, wszystkie projekty zawarte w rozwiązaniu muszą znajdować się w tym samym folderze co rozwiązanie lub w jednym z jego podfolderów.  
> * Odwołania między projektami zmigrowanymi do wersji 0.6 i nowszych oraz projekty korzystające ze starszych wersji pakietu **nie** są obsługiwane.

## <a name="version-051904"></a>Wersja 0.5.1904

*Data wydania: 15 kwietnia 2019 r.*

Ta wersja zawiera poprawki błędów.


## <a name="version-051903"></a>Wersja 0.5.1903

*Data wydania: 27 marca 2019 r.*

To wydanie zawiera następujące elementy:

- Dodano obsługę aplikacji Jupyter Notebook, która oferuje doskonały sposób pogłębiania wiedzy na temat języka Q#.  [Zapoznaj się z nowymi przykładami notesów Jupyter i dowiedz się, jak pisać własne notesy](xref:microsoft.quantum.install). 

- Do biblioteki Quantum Canon dodano arytmetyczny sumator liczb całkowitych.  Zobacz również notes Jupyter z [opisem sposobu korzystania z nowych sumatorów liczb całkowitych](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).

- Poprawka usterki dla problemu DumpRegister zgłoszonego przez społeczność ([nr 148](https://github.com/Microsoft/Quantum/issues/148)).

- Dodano możliwość powrotu z [instrukcji using](xref:microsoft.quantum.language.statements).

- Odnowiono [przewodnik Wprowadzenie](xref:microsoft.quantum.install).


## <a name="version-051902"></a>Wersja 0.5.1902

*Data wydania: 27 lutego 2019 r.*

To wydanie zawiera następujące elementy:

- Dodano obsługę międzyplatformowego hosta języka Python.  Pakiet `qsharp` dla języka Python ułatwia symulowanie operacji i funkcji języka Q# z poziomu języka Python. Dowiedz się więcej na temat [współdziałania w języku Python](xref:microsoft.quantum.install). 

- Rozszerzenia programu Visual Studio i edytora Visual Studio Code obsługują teraz zmianę nazw symboli (np. funkcji i operacji).

- Rozszerzenie programu Visual Studio można teraz instalować w programie Visual Studio 2019.

## <a name="version-041901"></a>Wersja 0.4.1901

*Data wydania: 30 stycznia 2019 r.*

To wydanie zawiera następujące elementy:

- Dodano obsługę nowego typu pierwotnego BigInt, który reprezentuje liczbę całkowitą ze znakiem o dowolnym rozmiarze.  Dowiedz się więcej na temat [typu BigInt](xref:microsoft.quantum.language.type-model).
- Dodano nowy symulator Toffoli będący szybkim symulatorem specjalnego przeznaczenia, który może symulować operacje X, CNOT i kontrolowane wielokrotnie operacje kwantowe X na bardzo dużych liczbach kubitów.  Dowiedz się więcej na temat [symulatora Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).
- Dodano prosty estymator zasobów, który szacuje zasoby wymagane do uruchomienia danego wystąpienia operacji Q# na komputerze kwantowym.  Dowiedz się więcej o [estymatorze zasobów](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Wersja 0.3.1811.2802

*Data wydania: 28 listopada 2018 r.*

Mimo że nasze rozszerzenie edytora VS Code nie korzystało z tego pakietu NPM, zostało oflagowane i usunięte z platformy handlowej podczas [czyszczenia rozszerzeń](https://code.visualstudio.com/blogs/2018/11/26/event-stream) związanego z pakietem NPM `event-stream`. Ta wersja usuwa wszystkie zależności środowiska uruchomieniowego, które mogą spowodować, że rozszerzenie wyzwoli jakieś czerwone flagi.

Jeśli wcześniej zainstalowano rozszerzenie, konieczna będzie jego ponowna instalacja. W tym celu należy przejść na stronę rozszerzenia [Microsoft Quantum Development Kit dla programu Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) w witrynie Marketplace programu Visual Studio i nacisnąć przycisk Install (Instaluj). Przepraszamy za tę niedogodność.


## <a name="version-0318111511"></a>Wersja 0.3.1811.1511

*Data wydania: 20 listopada 2018 r.*

W tej wersji naprawiono usterkę, która uniemożliwiała niektórym użytkownikom pomyślne załadowanie rozszerzenia programu Visual Studio.

Jeśli uaktualniasz zestaw Quantum Development Kit z wersji 0.2, dowiedz się więcej na temat [zmian w języku Q# i migrowania programu napisanego w języku Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-031811203"></a>Wersja 0.3.1811.203

*Data wydania: 2 listopada 2018 r.*

Ta wersja zawiera kilka poprawek usterek, w tym następujące:

* Wywołanie obiektu `DumpMachine` może w pewnych sytuacjach zmienić stan symulatora.
* Usunięto ostrzeżenia kompilacji wyświetlane podczas kompilowania projektów na platformie .NET Core w wersjach wcześniejszych niż 2.1.403.
* Przeprowadzono czyszczenie dokumentacji, w szczególności etykietek narzędzi wyświetlanych po umieszczeniu wskaźnika myszy na elemencie interfejsu programu VS Code lub Visual Studio.

Jeśli uaktualniasz zestaw Quantum Development Kit z wersji 0.2, dowiedz się więcej na temat [zmian w języku Q# i migrowania programu napisanego w języku Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-0318102508"></a>Wersja 0.3.1810.2508

*Data wydania: 29 października 2018 r.*

Ta wersja zawiera nowe funkcje językowe i udoskonalone środowisko programistyczne:

* Ta wersja zawiera serwer języka Q#, a także integracje klienta dla programu Visual Studio i Visual Studio Code. Dzięki temu może działać nowy zestaw funkcji IntelliSense wraz ze wskazówkami wyświetlanymi podczas pisania w postaci falistego podkreślenia błędów i ostrzeżeń. 
* Ta aktualizacja znacznie usprawnia wyświetlanie ogólnych komunikatów diagnostycznych, przez co ułatwia nawigację i precyzowanie zakresów danych diagnostycznych, a także powoduje wyświetlanie dodatkowych szczegółów w aktywnych okienkach.
* Język Q# został rozszerzony w taki sposób, że ujednolica metody wykonywania przez deweloperów najczęstszych operacji, a nowe ulepszenia funkcji języka wydajnie wyrażają kwantowe możliwości obliczeniowe.  W tym wydaniu wprowadzono w języku Q# kilka zmian powodujących niezgodność.   

Dowiedz się więcej na temat [zmian w języku Q# i migrowania programów napisanych w języku Q#](xref:microsoft.quantum.relnotes.migration-0-3).

Ta wersja zawiera również nową bibliotekę dla chemii kwantowej:

* Biblioteka chemiczna zawiera nowe funkcje symulacji Hamiltona, w tym:
    - Integratory Suzuki-Trottera dowolnej równej kolejności umożliwiające zwiększenie dokładności symulacji.
    - Technika symulacji kubityzacji z optymalizacjami specyficznymi dla chemii w celu zmniejszenia złożoności bramy $T$-gate.
* Wprowadzono nowy schemat typu open source o nazwie Broombridge (jego nazwa pochodzi od [charakterystycznego obiektu](https://en.wikipedia.org/wiki/Broom_Bridge) uznawanego za miejsce wynalezienia hamiltonianów) umożliwiający importowanie reprezentacji molekuł i ich symulację.
* Zdefiniowano wiele reprezentacji chemicznych przy użyciu schematu Broombridge.  Te modele zostały wygenerowane przez wysoce wydajne narzędzie typu open source do obliczeń chemicznych [NWChem](http://www.nwchem-sw.org/).
* W samouczkach i przykładach opisano, jak używać biblioteki chemicznej i modeli danych Broombridge do wykonywania następujących zadań:
    - Konstruowanie prostych hamiltonianów przy użyciu biblioteki chemicznej
    - Wizualizowanie energii stanu podstawowego i wzbudzonego wodorku litu przy użyciu szacowania fazy.
    - Wykonywanie szacowania zasobów na potrzeby kwantowej symulacji chemicznej.
    - Szacowanie poziomów energii molekuł reprezentowanych przez schemat Broombridge.
* W dokumentacji opisano, jak używać narzędzia NWChem do generowania dodatkowych modeli chemicznych na potrzeby symulacji kwantowych w języku Q#.

Dowiedz się więcej o [bibliotece chemicznej zestawu Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

Po wprowadzeniu nowej biblioteki chemicznej przenosimy biblioteki do nowego repozytorium GitHub [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Przykłady pozostają w repozytorium [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Zapraszamy do wnoszenia własnego wkładu w obu tych repozytoriach!

Ta wersja zawiera poprawki błędów i rozwiązania problemów zgłaszanych przez społeczność:

* Funkcja IntelliSense dla języka Q#? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* Pliki qs ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Ulepszenie komunikatu o błędzie wyświetlanego, gdy nawiasy klamrowe są skracane w instrukcji if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Obsługa dekonstrukcji krotki podczas modyfikowalnego wiązania (lub ponownego wiązania) ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Błąd podczas uruchamiania udostępnionego przykładu BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* Interfejs H2SimulationGUI wyświetla czasami wysokie wartości szczytowe ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Współtworzenie w ramach społeczności

**Dziękujemy** wymienionym poniżej współautorom bazy otwartego kodu w repozytorium http://github.com/Microsoft/Quantum. Te współtworzone elementy wiele wnoszą do bogatych przykładów kodu Q#:

* Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Ulepszył środowisko QASM/Q# dla deweloperów, tworząc translator z języka QASM do Q#. [Żądanie ściągnięcia nr 58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  Udostępnił przykład implementacji gry kwantowej CHSH Game demonstrującej nielokalność.  [Żądanie ściągnięcia nr 84](https://github.com/Microsoft/Quantum/pull/84).

Serdeczne podziękowania kierujemy także do Rohita Gupty ([@guptarohit](https://github.com/guptarohit),[żądanie ściągnięcia nr 90](https://github.com/Microsoft/quantum/pull/90)), Tanaki Takayoshiego ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[żądanie ściągnięcia nr 289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) i Jamesa O'Riordana ([@mlxd](https://github.com/mlxd),[żądanie ściągnięcia nr 96](https://github.com/Microsoft/Quantum/pull/96)) za ich pracę nad ulepszaniem zawartości dokumentacji, a także za poprawianie błędów językowych i literówek. 

## <a name="version-021809701"></a>Wersja 0.2.1809.701

*Data wydania: 10 września 2018 r.*

Ta wersja zawiera poprawki błędów i rozwiązania problemów zgłaszanych przez społeczność. W tym:

* Nie możność użycia operatora przesunięcia ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* Funkcje `DumpMachine` / `DumpRegister` kończą się niepowodzeniem w symulatorze `QCTraceSimulator` podczas drukowania w konsoli ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Zezwalanie na przydzielenie 0 kubitów ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* Funkcja `AssertQubitState` wymaga jawnego wywołania funkcji Complex() ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* Operacja `Measure` zawsze zwraca `One` w systemie macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Dziękujemy. 

## <a name="version-0218063001"></a>Wersja 0.2.1806.3001

*Data wydania: 30 czerwca 2018 r.*

Ta wersja to tylko szybka poprawka [problemu nr 48 raportowanego w witrynie GitHub](https://github.com/Microsoft/Quantum/issues/48) (kompilacja języka Q# kończy się niepowodzeniem, jeśli nazwa użytkownika zawiera puste miejsce). Należy wykonać taką samą procedurę aktualizacji jak w przypadku wersji `0.2.1806.1503` z odpowiednią nową wersją (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Wersja 0.2.1806.1503

*Data wydania: 22 czerwca 2018 r.*

Ta wersja zawiera kilka elementów współtworzonych przez społeczność, a także oferuje ulepszone środowisko debugowania i lepszą wydajność.  Są to:

* Ulepszenia wydajności dotyczące zarówno małych, jak i dużych symulacji dla maszyny docelowej QuantumSimulator.
* Ulepszono funkcję debugowania.
* Elementy współtworzone przez społeczność dotyczące poprawek błędów, nowych funkcji pomocnika, operacji i nowych przykładów.

### <a name="performance-improvements"></a>Ulepszenia wydajności

W tej aktualizacji znacząco zwiększono wydajność symulacji dużych i małych liczb kubitów dla wszystkich maszyn docelowych.  To ulepszenie można łatwo zauważyć w przypadku symulacji H<sub>2</sub>, która jest standardowym przykładem w zestawie Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Ulepszono funkcje debugowania

W tej aktualizacji dodano nowe funkcje debugowania:
* Dodano dwie nowe operacje, @"microsoft.quantum.extensions.diagnostics.dumpmachine" i @"microsoft.quantum.extensions.diagnostics.dumpregister", których danymi wyjściowymi są informacje o funkcji falowej docelowego komputera kwantowego w danym momencie.  
* W programie Visual Studio prawdopodobieństwo mierzenia wartości $\ket{1}$ na pojedynczym kubicie jest teraz automatycznie wyświetlane w oknie debugowania dla maszyny docelowej QuantumSimulator.
* W programie Visual Studio ulepszono wyświetlanie właściwości zmiennych w oknach debugowania **Automatyczne** i **Elementy lokalne**. 

Dowiedz się więcej na temat [testowania i debugowania](xref:microsoft.quantum.techniques.testing-and-debugging).

### <a name="community-contributions"></a>Współtworzenie w ramach społeczności

Społeczność osób tworzących kod Q# jest coraz większa i z ogromną przyjemnością odnotowaliśmy pierwsze współtworzone przez użytkowników biblioteki i przykłady, które zostały przesłane do naszej otwartej bazy kodu w repozytorium http://github.com/Microsoft/quantum.  **Ogromne podziękowania** dla wymienionych poniżej współautorów:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): dostarczył przykład definiujący bazującą na transformacji metodę syntezy logicznej, która konstruuje sieci Toffoli w celu zaimplementowania danej permutacji. Kod składa się w całości z funkcji i operacji języka Q#.  [Żądanie ściągnięcia nr 41](https://github.com/Microsoft/Quantum/pull/41).
* Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)): Rolf Huisman, uczestnik programu Microsoft MVP, udostępnił przykład, który generuje płaski kod QASM z kodu Q# dla ograniczonej klasy programów, które nie mają klasycznego przepływu sterowania i ograniczonych operacji kwantowych. [Żądanie ściągnięcia nr 59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)): pomogła ulepszyć naszą bazę kodu, przesyłając funkcję biblioteki dla kontrolowanych operacji. [Żądanie ściągnięcia nr 53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)): poprawiła szacowanie @"microsoft.quantum.canon.quantumphaseestimation" i utworzyła nowe testy jednostkowe.  [Żądanie ściągnięcia nr 54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)): oczyścił przykład Teleportation, zapewniając, że wystąpienie symulatora QuantumSimulator zostało usunięte. [Żądanie ściągnięcia nr 20](https://github.com/Microsoft/Quantum/pull/20)

Ponadto ogromne **podziękowania** dla tych inżynierów oprogramowania firmy Microsoft — współpracowników zespołu ds. usług inżynierii komercyjnej, którzy wprowadzili cenne zmiany w naszej dokumentacji podczas maratonu programistycznego Hackathon.  Wprowadzone przez nich zmiany znacząco poprawiły przejrzystość i środowisko dołączania dla nas wszystkich:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Aktualizowanie istniejących projektów

Ta wersja jest w pełni zgodna z poprzednimi wersjami. Wystarczy zaktualizować pakiety nuget w projektach do wersji `0.2.1806.1503-preview` i wykonać **pełną ponowną kompilację**, aby mieć pewność, że wszystkie pliki pośrednie zostaną ponownie wygenerowane.

W programie Visual Studio postępuj zgodnie z normalnymi instrukcjami dotyczącymi [aktualizowania pakietu](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Aby zaktualizować szablony projektu dla wiersza polecenia, uruchom następujące polecenie:
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Po uruchomieniu tego polecenia wszystkie nowe projekty utworzone za pomocą polecenia `dotnet new <project-type> -lang Q#` będą automatycznie używać tej wersji zestawu Quantum Development Kit.

Aby zaktualizować istniejący projekt do korzystania z najnowszej wersji, uruchom następujące polecenie w katalogu dla każdego projektu:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Jeśli istniejący projekt używa integracji XUnit do testowania jednostek, można użyć podobnego polecenia, aby zaktualizować również ten pakiet:
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

W zależności od wersji narzędzia XUnit używanej przez projekt testowy może być również konieczne zaktualizowanie narzędzia XUnit do wersji 2.3.1:
```
dotnet add package xunit -v "2.3.1" 
```

Po aktualizacji upewnij się, że zostały usunięte wszystkie pliki tymczasowe wygenerowane przez poprzednią wersję. W tym celu wykonaj następujące czynności:
```
dotnet clean 
```

### <a name="known-issues"></a>Znane problemy

Nie ma dodatkowych znanych problemów, które należy zgłosić.


## <a name="version-0218022202"></a>Wersja 0.2.1802.2202

*Data wydania: 26 lutego 2018 r.*

W tej wersji wprowadzono obsługę programowania dla większej liczby platform, współdziałanie języków i ulepszenia wydajności. Są to:

- Obsługa programowania w systemach macOS i Linux. 
- Zgodność z platformą .NET Core, w tym obsługa edytora Visual Studio Code na wielu platformach.
- Pełna licencja typu open source dla bibliotek zestawu Quantum Development Kit.
- Ulepszona wydajność symulatora dla projektów wymagających 20 lub więcej kubitów.
- Współdziałanie z językiem Python (wersja zapoznawcza dostępna dla systemu Windows).

### <a name="net-editions"></a>Wersje dla platformy .NET

Platforma .NET jest dostępna w dwóch różnych wersjach: jako program .NET Framework dostarczany z systemem Windows i jako platforma .NET Core dostępna w systemach Windows, macOS i Linux.
W tej wersji większość składników zestawu Quantum Development Kit jest udostępniana w postaci bibliotek dla środowiska .NET Standard — zestawu klas wspólnych zarówno dla programu Framework, jak i dla platformy Core.
Dzięki temu te biblioteki są zgodne z najnowszymi wersjami programu .NET Framework i platformy .NET Core.

W związku z tym w celu zagwarantowania, że projekty napisane przy użyciu zestawu Quantum Development Kit będą maksymalnie przenośne, zalecamy, aby elementem docelowym dla projektów bibliotek napisanych za pomocą zestawu Quantum Development Kit było środowisko .NET Standard, natomiast dla aplikacji konsolowych — platforma .NET Core.
Ponieważ wcześniejsze wersje zestawu Quantum Development Kit obsługiwały tylko program .NET Framework, może być konieczne przeprowadzenie migracji istniejących projektów. Poniżej znajdują się szczegółowe informacje o tym, jak to zrobić.

### <a name="project-migration"></a>Migracja projektu

Projekty utworzone przy użyciu poprzednich wersji zestawu Quantum Development Kit będą nadal działały, o ile nie zostaną zaktualizowane użyte w nich pakiety NuGet. Aby przeprowadzić migrację istniejącego kodu do nowej wersji, wykonaj następujące czynności:
1. Utwórz nowy projekt platformy .NET Core przy użyciu odpowiedniego typu szablonu projektu Q# (aplikacji, biblioteki lub projektu testowego).
2. Skopiuj istniejące pliki qs i cs/fs ze starego projektu do nowego (przy użyciu menu Dodaj > Istniejący element). Nie kopiuj pliku AssemblyInfo.cs.
3. Skompiluj i uruchom nowy projekt.

Należy pamiętać, że operacja RandomWalkPhaseEstimation z przestrzeni nazw Microsoft.Quantum.Canon została przeniesiona do przestrzeni nazw Microsoft.Research.Quantum.RandomWalkPhaseEstimation w repozytorium [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Znane problemy

- Opcja `--filter` polecenia `dotnet test` nie działa prawidłowo w przypadku testów napisanych w języku Q#.
  W związku z tym poszczególne testy jednostkowe nie mogą być uruchamiane w edytorze Visual Studio Code. Zalecamy użycie polecenia `dotnet test` w wierszu polecenia w celu ponownego uruchomienia wszystkich testów.

## <a name="version-0118011707"></a>Wersja 0.1.1801.1707

*Data wydania: 18 stycznia 2018 r.*

Ta wersja zawiera rozwiązania niektórych problemów zgłaszanych przez społeczność. Oto one:

- Symulator działa teraz z wczesnymi procesorami z wyłączonymi instrukcjami AVX.
- Regionalne ustawienia dla liczb dziesiętnych nie będą już powodować błędu analizatora języka Q#.
- Operacja pierwotna `SignD` zwraca teraz typ `Int`, a nie `Double`.


## <a name="version-011712901"></a>Wersja 0.1.1712.901

*Data wydania: 11 grudnia 2017 r.*

### <a name="known-issues"></a>Znane problemy

#### <a name="hardware-and-software-requirements"></a>Wymagania dotyczące sprzętu i oprogramowania

- Symulator dołączony do zestawu Quantum Development Kit wymaga zainstalowania 64-bitowego systemu Microsoft Windows.
- Symulator kwantowy firmy Microsoft instalowany z zestawem Quantum Development Kit wykorzystuje instrukcje Advanced Vector Extensions (AVX) i wymaga procesorów z włączonymi instrukcjami AVX. Procesory firmy Intel od modelu Sandy Bridge (dostarczanego od 1. kwartału 2011 r.) obsługują instrukcje AVX. Rozważamy obsługę wcześniejszych procesorów i być może, że szczegółowe informacje na ten temat zostaną ogłoszone w późniejszym czasie.

#### <a name="project-creation"></a>Tworzenie projektu

- Podczas tworzenia rozwiązania (plik sln), które będzie korzystać z języka Q#, katalog rozwiązania musi znajdować się w hierarchii katalogów o jeden poziom wyżej niż poszczególne projekty (pliki csproj) rozwiązania. Podczas tworzenia nowego rozwiązania można to zagwarantować przez zaznaczenie pola wyboru „Utwórz katalog dla rozwiązania” w oknie dialogowym „Nowy projekt”. Jeśli nie zostanie to zrobione, pakiety NuGet zestawu Quantum Development Kit będą musiały zostać zainstalowane ręcznie.

#### <a name="q"></a>Q#

- Funkcja IntelliSense nie wyświetla prawidłowych błędów dla kodu Q#. Aby były wyświetlane prawidłowe błędy języka Q#, upewnij się, że na liście błędów w programie Visual Studio są wyświetlane błędy kompilacji. Należy również pamiętać, że błędy języka Q# nie będą wyświetlane, dopóki nie zostanie przeprowadzona kompilacja.
- Użycie modyfikowalnej tablicy w częściowej aplikacji może prowadzić do nieoczekiwanego zachowania.
- Powiązanie niezmiennej tablicy z tablicą modyfikowalną (let a = b, gdzie b jest tablicą modyfikowalną) może prowadzić do nieoczekiwanego zachowania.
- Wtyczki profilowania, pokrycia kodu i inne wtyczki programu VS mogą czasami niedokładnie zliczać wiersze i bloki w kodzie Q#.
- Kompilator języka Q# nie sprawdza poprawności ciągów interpolowanych. Istnieje możliwość występowania błędów kompilacji kodu C# spowodowanych błędnymi nazwami zmiennych lub użyciem wyrażeń w ciągach interpolowanych kodu Q#.

#### <a name="simulation"></a>Symulacja

- Symulator kwantowy korzysta z interfejsu OpenMP do zrównoleglenia wymaganej algebry liniowej. Domyślnie interfejs OpenMP korzysta ze wszystkich dostępnych wątków sprzętowych, co oznacza, że programy z niewielką liczbą kubitów często działają wolniej, ponieważ wymóg koordynacji powoduje spowolnienie rzeczywistej pracy. Można to naprawić przez ustawienie zmiennej środowiskowej OMP_NUM_THREADS na małą liczbę. Można kierować się zasadą, że w przybliżeniu 1 wątek jest wystarczający dla około 4 kubitów. Następnie na jeden kubit powinien przypadać jeden dodatkowy wątek. Jest to jednak szacowanie wysoce zależne od konkretnego algorytmu.

#### <a name="debugging"></a>Debugowanie

- Klawisz F11 (Wkrocz) nie działa w przypadku kodu Q#.
- Wyróżnianie kodu języka Q# w punkcie przerwania lub podczas wstrzymania pojedynczego kroku jest czasami niedokładne. Jest co prawda wyróżniany prawidłowy wiersz, ale czasami wyróżnienie rozpoczyna się i kończy w nieprawidłowych kolumnach wiersza.

#### <a name="testing"></a>Testowanie

- Testy muszą być wykonywane w trybie 64-bitowym. Jeśli testy kończą się niepowodzeniem ze zgłoszonym wyjątkiem BadImageFormatException, przejdź do menu testu, a następnie wybierz pozycję Ustawienia testu > Domyślna architektura procesora > X64.
- Niektóre testy są długotrwałe (w zależności od komputera mogą trwać do 5 minut). Jest to normalne w przypadku użycia ponad dwudziestu kubitów. Nasz największy test aktualnie działa z 23 kubitami.

#### <a name="samples"></a>Samples

- Na niektórych komputerach niektóre małe przykłady mogą działać wolno, jeśli zmienna środowiskowa OMP_NUM_THREADS nie zostanie ustawiona na wartość „1”. Zobacz również uwagi dotyczące wersji w sekcji „Symulacja”.

#### <a name="libraries"></a>Biblioteki

- Istnieje niejawne założenie, że kubity przekazane do operacji w różnych argumentach są unikatowe. Na przykład we wszystkich operacjach biblioteki (i wszystkich symulatorach) przyjęto założenie, że dwa kubity przekazane do kontrolowanej negacji są różnymi kubitami. Naruszenie tego założenia może prowadzić do nieoczekiwanego zachowania. Możliwe jest przetestowanie tego założenia za pomocą symulatora śledzenia komputera kwantowego.
- Funkcja Microsoft.Quantum.Bind może nie działać zgodnie z oczekiwaniami we wszystkich przypadkach.
- W przestrzeni nazw Microsoft.Quantum.Extensions.Math funkcja SignD zwraca liczbę typu Double, a nie Int, mimo że bazowa funkcja System.Math.Sign zawsze zwraca liczbę całkowitą. Można bezpiecznie porównać wynik z liczbami 1,0, -1,0 i 0,0, ponieważ wszystkie te liczby typu Double mają dokładne reprezentacje binarne.
