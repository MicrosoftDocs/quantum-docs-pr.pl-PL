---
title: Informacje o wersji zestawu Quantum Development Kit
description: Uzyskaj informacje o najnowszych aktualizacjach zestawu Microsoft Quantum Development Kit (wersja zapoznawcza).
author: bradben
ms.author: v-benbra
ms.date: 8/30/2020
ms.topic: article
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: d38482be17e67f180441440ee8ccc7f1f64ebc9d
ms.sourcegitcommit: fb75d8f30f1d91f644b2a594f46867eb5968cfda
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94448348"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Informacje o wersji zestawu Microsoft Quantum Development Kit

Ten artykuł zawiera informacje dotyczące poszczególnych wersji zestawu Quantum Development Kit.

Instrukcje instalacji znajdują się w [przewodniku instalacji](xref:microsoft.quantum.install).

Instrukcje dotyczące aktualizacji znajdują się w [przewodniku aktualizacji](xref:microsoft.quantum.update).

## <a name="version-01320111004"></a>0.13.20111004 wersja

*Data wydania: 10 listopada, 2020*

Ta wersja wyłącza funkcje IntelliSense dla Q# plików w programie Visual Studio i Visual Studio Code, gdy plik projektu nie istnieje. W ten sposób można rozwiązać problem polegający na tym, że funkcje IntelliSense mogą przestać działać po dodaniu nowego Q# pliku do projektu (zobacz [qsharp-Compiler # 720](https://github.com/microsoft/qsharp-compiler/issues/720)).

## <a name="version-01320102604"></a>0.13.20102604 wersja

*Data wydania: 27 października, 2020*

To wydanie zawiera następujące elementy:

- Szacowanie zasobów teraz emituje jednocześnie osiągalne głębokość i oszacowania o szerokości oprócz liczby qubit. Zobacz [tutaj](xref:microsoft.quantum.machines.resources-estimator#metrics-reported) , aby uzyskać szczegółowe informacje.

Zapoznaj się z pełną listą zamkniętych żądań ściągnięcia dla [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [kompilatorów](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) [ Q# i i](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22).

## <a name="version-01220100504"></a>0.12.20100504 wersja

*Data wydania: 5 października, 2020*

W tej wersji rozwiązano usterkę wpływającą na ładowanie Q# notesów (zobacz [iqsharp # 331](https://github.com/microsoft/iqsharp/pull/331)).

## <a name="version-01220092803"></a>0.12.20092803 wersja

*Data wydania: 29 września, 2020*

To wydanie zawiera następujące elementy:

- Specyfikacja anonsu i szkicu [reprezentacji pośredniej Quantum (QIR)](https://github.com/microsoft/qsharp-language/tree/main/Specifications/QIR#quantum-intermediate-representation-qir) , która jest w typowym formacie dla różnych frontonów i zaplecza. Zobacz również nasz [wpis w blogu](https://devblogs.microsoft.com/qsharp/introducing-quantum-intermediate-representation-qir) w witrynie QIR.
- Uruchom nasz nowy [ Q# repozytorium języka](https://github.com/microsoft/qsharp-language) zawierające także pełną [ Q# dokumentację](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language).
- Udoskonalenia wydajności dla QuantumSimulator w przypadku programów obejmujących dużą liczbę qubits: lepszym zastosowaniem decyzji związanych z syntezą bram; Ulepszona przetwarzanie równoległe w systemie Linux; dodano inteligentne planowanie wykonywania bram; poprawki błędów.
- Funkcje IntelliSense są teraz obsługiwane Q# w przypadku plików w programie Visual Studio i Visual Studio Code nawet bez pliku projektu.
- Różne Q# ulepszenia współdziałania/Python i poprawki błędów, w tym lepsza obsługa typów danych numpy.
- Ulepszenia w przestrzeni nazw Microsoft. Quantum. Arrays (zobacz [Microsoft/QuantumLibraries # 313](https://github.com/microsoft/QuantumLibraries/issues/313)).
- Dodano nowy [przykład REPEAT-until-Success](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/repeat-until-success) , który używa tylko dwóch qubits.

Od momentu ostatniego wydania nazwa domyślnego rozgałęzienia w każdym z naszych repozytoriów typu open source została zmieniona na `main` .

Zapoznaj się z pełną listą zamkniętych żądań ściągnięcia dla [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [kompilatorów](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) [ Q# i i](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24).

## <a name="version-01220082513"></a>0.12.20082513 wersja

*Data wydania: 25 sierpnia 2020*

To wydanie zawiera następujące elementy:

- Nowa [przestrzeń nazw Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random), zapewniająca wygodniejszy sposób próbkowania losowo wybranych wartości z Q# programów. ([QuantumLibraries # 311](https://github.com/microsoft/QuantumLibraries/pull/311), [qsharp-Runtime # 328](https://github.com/microsoft/qsharp-runtime/pull/328))
- Ulepszona [przestrzeń nazw Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics) z nową [ `DumpOperation` operacją](xref:Microsoft.Quantum.Diagnostics.DumpOperation)i nowe operacje ograniczające qubite i wywołania programu Oracle. ([QuantumLibraries # 302](https://github.com/microsoft/QuantumLibraries/pull/302))
- Nowe [ `%project` polecenie Magic](xref:microsoft.quantum.iqsharp.magic-ref.project) w Q# i i [ `qsharp.projects` interfejs API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) w języku Python do obsługi odwołań do Q# projektów poza bieżącym folderem obszaru roboczego. Zobacz [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) , aby poznać bieżące ograniczenia tej funkcji. 
- Obsługa automatycznego ładowania `.csproj` plików dla Q# hostów/Python i umożliwia ładowanie zewnętrznych odwołań do projektu lub pakietu w czasie inicjacji. Aby uzyskać więcej informacji, zobacz Przewodnik dotyczący używania [ Q# z notesami Python i Jupyter](xref:microsoft.quantum.guide.host-programs) .
- Dodano przykład ErrorCorrection. Syndrome.
- Dodano sprzężenie możliwość dostosowania do SimpleIsing.
- Zaktualizowano przykład HiddenShift.
- Dodano przykład do rozwiązywania Sudoku z algorytmem Grover (udział zewnętrzny)
- Ogólne poprawki błędów.

Zapoznaj się z pełną listą zamkniętych żądań ściągnięcia dla [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatorów](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) [ Q# i i](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01220072031"></a>0.12.20072031 wersja

*Data wydania: 21 lipca, 2020*

To wydanie zawiera następujące elementy:

- Otwarte przestrzenie nazw w Q# notesach są teraz dostępne podczas uruchamiania wszystkich przyszłych komórek. Dzięki temu można na przykład otwierać obszary nazw raz w komórce w górnej części notesu zamiast otwierać odpowiednie przestrzenie nazw w każdej komórce kodu. Nowe `%lsopen` polecenie Magic wyświetla listę obecnie otwartych przestrzeni nazw.

Zapoznaj się z pełną listą zamkniętych żądań ściągnięcia dla [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatorów](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) [ Q# i i](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01220070124"></a>0.12.20070124 wersja

*Data wydania: 2 lipca, 2020*

To wydanie zawiera następujące elementy:

- Nowe `qdk-chem` Narzędzie do konwertowania starszej wersji formatu serializacji problemu ze strukturą elektroniczną (np.: FCIDUMP) do [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)
- Nowe funkcje i operacje w [`Microsoft.Quantum.Synthesis`](xref:Microsoft.Quantum.Synthesis) przestrzeni nazw spójnie stosują klasyczne firmy Oracle przy użyciu algorytmów syntezy opartej na transformacjach i dekompozycji.
- Q#Teraz zezwalamy na stosowanie argumentów `%simulate` , `%estimate` i innych poleceń Magic. Aby uzyskać więcej informacji, zobacz [ `%simulate` dokumentacja poleceń Magic](xref:microsoft.quantum.iqsharp.magic-ref.simulate) .
- Opcje wyświetlania nowej fazy w I Q# . Aby uzyskać więcej informacji, zobacz [ `%config` dokumentacja poleceń Magic](xref:microsoft.quantum.iqsharp.magic-ref.config) .
- Q#I i `qsharp` pakiet języka Python są teraz udostępniane za pośrednictwem pakietów Conda ([qsharp](https://anaconda.org/quantum-engineering/qsharp) i [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) w celu uproszczenia lokalnej instalacji Q# funkcji Jupyter i języka Python w środowisku Conda. Więcej informacji można znaleźć w [ Q# notesach Jupyter](xref:microsoft.quantum.install.jupyter) i w przewodnikach instalacji języka [ Q# Python](xref:microsoft.quantum.install.python) .
- W przypadku korzystania z symulatora qubits nie musi być w stanie | 0 ⟩ w momencie wydania, ale można je zresetować automatycznie, jeśli zostały zmierzone bezpośrednio przed zwolnieniem.
- Aktualizacje ułatwiające Q# użytkownikom korzystanie z pakietów bibliotek z różnymi wersjami QDK, co wymaga, aby tylko główne & numery wersji pomocniczej nie były dokładnie takie same.
- Usunięto przestarzałą `Microsoft.Quantum.Primitive.*` przestrzeń nazw
- Przeniesiono operacje:
  - `Microsoft.Quantum.Intrinsic.Assert` jest teraz `Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb` jest teraz `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- Poprawki błędów 

Zapoznaj się z pełną listą zamkniętych żądań ściągnięcia dla [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatorów](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) [ Q# i i](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0112006403"></a>Wersja 0.11.2006.403

*Data wydania: 4 czerwca 2020 r.*

Ta wersja rozwiązuje usterkę wpływającą na kompilację Q# projektów.

## <a name="version-0112006207"></a>Wersja 0.11.2006.207

*Data wydania: 3 czerwca 2020*

To wydanie zawiera następujące elementy:

- Q# Notesy i programy hosta języka Python nie będą już kończyć się niepowodzeniem, gdy Q# punkt wejścia jest obecny
- Aktualizacje w [bibliotece standardowej](xref:microsoft.quantum.libraries.standard.intro) pozwalające używać modyfikatorów dostępu
- Teraz kompilator zezwala na wtyczkę kroków ponownego zapisu między wbudowanymi krokami ponownego zapisu
- Kilka przestarzałych funkcji i operacji zostało usuniętych zgodnie z harmonogramem opisanym w naszych [zasadach dotyczących interfejsu API](xref:microsoft.quantum.contributing.api-design). Q# programy i biblioteki, które kompilują bez ostrzeżeń w wersji 0.11.2004.2825, będą nadal działały niemodyfikowane.

Zapoznaj się z pełną listą zamkniętych żądań ściągnięcia dla [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatorów](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) [ Q# i i](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

> [!NOTE]
> Ta wersja zawiera usterkę wpływającą na kompilację Q# projektów. Zalecamy uaktualnienie do nowszej wersji.

## <a name="version-01120042825"></a>Wersja 0.11.2004.2825

*Data wydania: 30 kwietnia 2020 r.*

To wydanie zawiera następujące elementy:

- Nowe wsparcie dla Q# aplikacji, które nie wymagają już pliku hosta C# lub Python. Aby uzyskać więcej informacji na temat rozpoczynania pracy z Q# aplikacjami, zobacz [tutaj](xref:microsoft.quantum.install.standalone).
- Zaktualizowano przewodnik Szybki start kwantowego generatora liczb losowych, aby nie wymagał już pliku hosta języka C# ani Python. Zobacz zaktualizowany przewodnik [Szybki start](xref:microsoft.quantum.quickstarts.qrng)
- Ulepszenia wydajności do Q# obrazów platformy Docker

> [!NOTE]
> Q# aplikacje korzystające z nowego [`@EntryPoint()`](xref:Microsoft.Quantum.Core.EntryPoint) atrybutu obecnie nie mogą być wywoływane z programów Python i .NET.
> Więcej informacji można znaleźć w przewodnikach współdziałania z językiem [Python](xref:microsoft.quantum.install.python) i platformą [.NET](xref:microsoft.quantum.install.cs).

## <a name="version-01120033107"></a>Wersja 0.11.2003.3107

*Data wydania: 31 marca 2020 r.*

Ta wersja zawiera poprawki niewielkich usterek występujących w wersji 0.11.2003.2506.

## <a name="version-01120032506"></a>Wersja 0.11.2003.2506

*Data wydania: 26 marca 2020 r.*

To wydanie zawiera następujące elementy:

- Nowa obsługa modyfikatorów dostępu w programie Q# , aby uzyskać więcej informacji, zobacz [struktury plików](xref:microsoft.quantum.guide.filestructure)
- Aktualizacja do zestawu .NET Core SDK 3.1

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020022610"></a>Wersja 0.10.2002.2610

*Data wydania: 27 lutego 2020 r.*

To wydanie zawiera następujące elementy:

- Nowa biblioteka Quantum Machine Learning; więcej informacji zawiera [strona z dokumentacją biblioteki QML](xref:microsoft.quantum.machine-learning.concepts.intro)
- Q#Poprawki błędów, co spowodowało wzrost wydajności do 10 20x podczas ładowania pakietów NuGet

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020012831"></a>Wersja 0.10.2001.2831

*Data wydania: 29 stycznia 2020 r.*

To wydanie zawiera następujące elementy:

- Nowy pakiet NuGet Microsoft.Quantum.SDK, który zastąpi pakiet NuGet Microsoft.Quantum.Development.Kit podczas tworzenia nowych projektów. Pakiet NuGet Microsoft.Quantum.Development.Kit będzie nadal obsługiwany dla istniejących projektów. 
- Obsługa Q# rozszerzeń kompilatora, włączonych przez nowy pakiet NuGet Microsoft. Quantum. Sdk Pakiet, aby uzyskać więcej informacji, zobacz [dokumentację dotyczącą usługi GitHub](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler), [przykład rozszerzeń kompilatora](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions) i [ Q# blog dev](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/)
- Dodano obsługę platformy .NET Core 3.1; zdecydowanie zaleca się zainstalowanie wersji 3.1.100, ponieważ kompilowanie przy użyciu starszych wersji zestawu .NET Core SDK może powodować problemy
- Nowe przekształcenia kompilatorów są dostępne w ramach elementu Microsoft.Quantum.QsCompiler.Experimental
- Nowe funkcje uwidaczniające wektory stanu wyjściowego jako HTMLQ#
- Dodano obsługę elementu EstimateFrequencyA do przestrzeni nazw Microsoft.Quantum.Characterization dla testów Hadamard i SWAP
- Przestrzeń nazw AmplitudeAmplification teraz używa Q# przewodnika po stylu

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019120501"></a>Wersja 0.10.1912.0501

*Data wydania: 5 grudnia 2019 r.*

To wydanie zawiera następujące elementy:

- Nowy atrybut testu dla Q# testów jednostkowych, zobacz zaktualizowana dokumentacja interfejsu API [tutaj](xref:Microsoft.Quantum.Diagnostics.Test) i zaktualizowane instrukcje testowania & debugowanie [tutaj](xref:microsoft.quantum.guide.testingdebugging)
- Dodano ślad stosu w przypadku Q# błędu uruchomienia programu
- Obsługa punktów przerwania w programie Visual Studio Code dzięki aktualizacji [rozszerzenia OmniSharp C# programu Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Wersja 0.10.1911.1607

*Data wydania: 17 listopada 2019 r.*

To wydanie zawiera następujące elementy:

- Poprawka wydajności dla samouczków [Quantum Katas](https://github.com/Microsoft/QuantumKatas) i notesów Jupyter

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Wersja 0.10.1911.307

*Data wydania: 1 listopada 2019 r.*

To wydanie zawiera następujące elementy:

- Aktualizacje programu Visual Studio Code & rozszerzenia programu Visual Studio w celu wdrożenia serwera języka jako samodzielnego pliku wykonywalnego, eliminując zestaw .NET Core SDK zależności wersji  
- Migracja do platformy .NET Core 3.0
- Istotna zmiana w elemencie Microsoft.Quantum.Simulation.Core.IOperationFactory po wprowadzeniu nowej metody `Fail`. Dotyczy ona tylko symulatorów niestandardowych, które nie rozszerzają elementu SimulatorBase. Aby uzyskać więcej informacji, [wyświetl pełne żądanie ściągnięcia w usłudze GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Nowa obsługa przestarzałych atrybutów

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Wersja 0.9.1909.3002

*Data wydania: 30 września 2019 r.*

To wydanie zawiera następujące elementy:

- Nowa obsługa Q# uzupełniania kodu w programie Visual Studio 2019 (wersje 16,3 & nowszy) & Visual Studio Code
- Nowy samouczek [Quantum Kata](https://github.com/Microsoft/QuantumKatas) dla osób dodających zasoby kwantowe

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Wersja 0.9 ( *PackageReference 0.9.1908.2902* )

*Data wydania: 29 sierpnia 2019 r.*

To wydanie zawiera następujące elementy:

- Nowa obsługa [instrukcji sprzężonych](xref:microsoft.quantum.guide.operationsfunctions#conjugations) w Q#
- Nowe akcje kodu w kompilatorze, takie jak „zamień na”, „dodaj dokumentację” i prosta aktualizacja elementu tablicy
- Dodano szablon instalacji i nowe polecenia projektu do rozszerzenia edytora Visual Studio Code
- Dodano nowe odmiany kombinatora ApplyIf, takie jak [Microsoft.Quantum.Canon.ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- Dodatkowe samouczki [Quantum Kata](https://github.com/Microsoft/QuantumKatas) przekształcono w notesy Jupyter
- Rozszerzenie programu Visual Studio wymaga teraz programu Visual Studio 2019

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [kompilatora](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [środowiska uruchomieniowego](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) i [samouczków Kata](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Podsumowano zmiany i przedstawiono instrukcje uaktualniania istniejących programów.  Przeczytaj więcej na temat tych zmian na [ Q# blogu dev](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Wersja 0.8 ( *PackageReference 0.8.1907.1701* )

*Data wydania: 12 lipca 2019 r.*

To wydanie zawiera następujące elementy:

- Nowe lokalizacje indeksowania dla tablic wycinków. [Zobacz informacje dotyczące języka](xref:microsoft.quantum.guide.expressions#array-slices), aby uzyskać więcej informacji.
- Dodano pliku dockerfile hostowane w [Container Registry firmy Microsoft](https://github.com/microsoft/ContainerRegistry). [ Q# Aby uzyskać więcej informacji, zobacz repozytorium I](https://github.com/microsoft/iqsharp/blob/main/README.md)
- Zmiana powodująca niezgodność dotycząca [symulatora śledzenia](xref:microsoft.quantum.machines.qc-trace-simulator.intro), aktualizacja ustawień konfiguracji, zmiany nazw. Zobacz [Przeglądarka interfejsów API na platformie .NET — zaktualizowanie nazwy](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) i [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Wersja 0.7 ( *PackageReference 0.7.1905.3109* )

*Data wydania: 31 maja 2019 r.*

To wydanie zawiera następujące elementy:
- Dodatki do Q# języka, 
- Aktualizacje biblioteki chemicznej 
- Nowa biblioteka liczbowa

Zobacz pełną listę zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) i [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Podsumowano zmiany i przedstawiono instrukcje uaktualniania istniejących programów.  Przeczytaj więcej na temat tych zmian na [ Q# blogu dev](https://devblogs.microsoft.com/qsharp).

### <a name="no-locq-language-syntax"></a>Q# Składnia języka
W tej wersji dodano nową Q# składnię języka:
* Dodano nazwane elementy dla [typów zdefiniowanych przez użytkownika](xref:microsoft.quantum.guide.types#user-defined-types).  
* Konstruktory typów zdefiniowanych przez użytkownika mogą być teraz używane jako funkcje.
* W typach zdefiniowanych przez użytkownika dodano obsługę wyrażeń [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions) oraz [apply-and-reassign](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols).
* Blok naprawy dla pętli [repeat-until-success](xref:microsoft.quantum.guide.controlflow#repeat-until-success-loop) jest teraz opcjonalny.
* Obsługa pętli while w funkcjach (nie w operacjach).

### <a name="library"></a>Biblioteka 

W tej wersji dodano bibliotekę liczbową: Dowiedz się więcej o sposobie [korzystania z nowej biblioteki liczbowej](xref:microsoft.quantum.numerics.usage) i wypróbuj [nowe przykłady](https://github.com/microsoft/quantum/tree/main/Numerics).  [Żądanie ściągnięcia nr 102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Ta wersja reorganizuje rozszerzania i aktualizuje bibliotekę chemiczną:
* Poprawiono modułowość składników i rozszerzalność oraz przeprowadzono ogólne czyszczenie kodu.  [Żądanie ściągnięcia nr 58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Dodano obsługę [funkcji falowych z wieloma odwołaniami](xref:microsoft.quantum.chemistry.concepts.multireference) — zarówno rozrzedzonych funkcji falowych z wieloma odwołaniami, jak i unitarnego klastra sprzężonego.  [Żądanie ściągnięcia nr 110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Dzięki Wam!) Współautor [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Ocena energii przy użyciu założenia zmiennego. [Żądanie ściągnięcia nr 120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Zaktualizowano schemat [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) do nowej [wersji 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), dodano specyfikację unitarnego klastra sprzężonego. [Problem nr 65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Dodano współdziałania języka Python z funkcjami biblioteki chemicznej. Wypróbuj ten [przykład](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration). [Problem 53](https://github.com/microsoft/QuantumLibraries/issues/53) [Żądanie ściągnięcia 110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Wersja 0.6.1905

*Data wydania: 3 maja 2019 r.*

To wydanie zawiera następujące elementy:
- wprowadza zmiany w Q# języku, 
- Dokonano restrukturyzacji bibliotek zestawu Quantum Development Kit 
- Dodano nowe przykłady 
- Naprawiono błędy  Kilka zamkniętych żądań ściągnięcia dotyczących [bibliotek](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) i [przykładów](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Podsumowano zmiany i przedstawiono instrukcje uaktualniania istniejących programów.  Więcej informacji na temat tych zmian można znaleźć w pod adresem devblogs.microsoft.com/qsharp.

### <a name="no-locq-language-syntax"></a>Q# Składnia języka
W tej wersji dodano nową Q# składnię języka:
* Dodano [skrócony sposób wyrażania specjalizacji operacji kwantowych](xref:microsoft.quantum.guide.operationsfunctions#controlled-and-adjoint-operations) (kontroli i dołączania) za pomocą operatorów `+`.  Stara składnia jest przestarzała.  Programy używające starej składni (np. `: adjoint`) będą nadal działać, ale zostanie wygenerowane ostrzeżenie dotyczące czasu kompilacji.  
* Dodano nowy operator dla wyrażenia [copy-and-update](xref:microsoft.quantum.guide.expressions#copy-and-update-expressions). W celu wyrażenia tworzenia tablicy jako modyfikacji istniejącej tablicy można używać operatora `w/`.
* Dodano wspólną [instrukcję apply-and-update](xref:microsoft.quantum.guide.variables#rebinding-of-mutable-symbols), np. `+=`, `w/=`.
* Dodano sposób określania krótkiej nazwy przestrzeni nazw w [otwartych dyrektywach](xref:microsoft.quantum.guide.filestructure#open-directives).

W tej wersji nie zezwalamy już na określanie elementu tablicy po lewej stronie instrukcji ustawiania.  Wynika to z faktu, że składnia implikuje, że tablice są modyfikowalne, a w rzeczywistości wynikiem operacji zawsze było utworzenie nowej tablicy z modyfikacją.  Zamiast tego będzie generowany błąd kompilatora z sugestią użycia nowego operatora copy-and-update, `w/`, w celu osiągnięcia tego samego wyniku.  

### <a name="library-restructuring"></a>Restrukturyzacja biblioteki
Ta wersja reorganizuje biblioteki, aby umożliwić ich spójny wzrost:
* Zmieniono nazwę przestrzeni nazw Microsoft.Quantum.Primitive na Microsoft.Quantum.Intrinsic.  Te operacje są implementowane przez maszynę docelową.  Przestrzeń nazw Microsoft.Quantum.Primitive jest przestarzała.  Jeśli programy będą wywoływać operacje i funkcje przy użyciu przestarzałych nazw, zostanie wygenerowane ostrzeżenie środowiska uruchomieniowego.

* Zmieniono nazwę pakietu Microsoft.Quantum.Canon na Microsoft.Quantum.Standard.  Ten pakiet zawiera przestrzenie nazw, które są wspólne dla większości Q# programów.  Obejmuje to:  
    - Microsoft.Quantum.Canon na potrzeby najczęściej wykonywanych operacji
    - Microsoft.Quantum.Arithmetic na potrzeby operacji arytmetycznych ogólnego zastosowania
    - Microsoft.Quantum.Preparation na potrzeby operacji przygotowywania stanu kubitu
    - Microsoft.Quantum.Simulation na potrzeby funkcji symulacji

Po wprowadzeniu tych zmian programy, które zawierają pojedynczą instrukcję „open” dla przestrzeni nazw Microsoft.Quatum.Canon, mogą napotkać błędy kompilacji, jeśli program odwołuje się do operacji przeniesionych do tych trzech nowych przestrzeni nazw.  Ten problem można rozwiązać w prosty sposób, dodając dodatkowe instrukcje „open” dla trzech nowych przestrzeni nazw.  

* Niektóre przestrzenie nazw stały się przestarzałe, ponieważ znajdujące się w nich operacje zostały przeniesione do innych przestrzeni nazw. Programy korzystające z tych przestrzeni nazw będą nadal działały, a wyświetlone w czasie kompilacji ostrzeżenie będzie wskazywało przestrzeń nazw, w której jest zdefiniowana operacja.  

* Znormalizowano przestrzeń nazw Microsoft.Quantum.Arithmetic, aby korzystała ze zdefiniowanego przez użytkownika typu <xref:Microsoft.Quantum.Arithmetic.LittleEndian>. Jeśli zajdzie konieczność przekształcenia do formy little endian, należy użyć funkcji [BigEndianAsLittleEndian](xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian).  

* Nazwy kilku wywoływanych (funkcji i operacji) zostały zmienione tak, aby były zgodne z [ Q# prowadnicą stylu](xref:microsoft.quantum.contributing.style).  Stare nazwy elementów wywoływanych stały się przestarzałe.  Programy używające starych elementów wywoływanych będą nadal działały z ostrzeżeniem w czasie kompilacji. 

### <a name="new-samples"></a>Nowe przykłady

Dodaliśmy [przykład użycia Q# z sterownikiem języka F #](https://github.com/Microsoft/Quantum/pull/164).  

**Dziękujemy** wymienionemu poniżej współautorowi bazy otwartego kodu w repozytorium http://github.com/Microsoft/Quantum. Te wkłady znacznie znacząco rozbudowane przykłady Q# kodu:

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Synteza funkcji firmy Oracle. [Żądanie ściągnięcia nr 135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migrowanie istniejących projektów do wersji 0.6.1905.

Informacje na temat aktualizowania zestawu QDK znajdują się w [przewodniku instalacji](xref:microsoft.quantum.install).
  
Jeśli masz istniejące Q# projekty z wersji 0,5 zestawu Quantum Development Kit, wykonaj następujące kroki, aby przeprowadzić migrację tych projektów do najnowszej wersji.

1. Projekty muszą zostać uaktualnione w odpowiedniej kolejności.  Jeśli masz rozwiązanie z wieloma projektami, zaktualizuj poszczególne projekty w kolejności, w jakiej są przywoływane.
2. W wierszu polecenia Uruchom polecenie, `dotnet clean` Aby usunąć wszystkie istniejące dane binarne i pliki pośrednie.
3. W edytorze tekstów otwórz plik csproj i zmień wersję wszystkich elementów „Microsoft. Quantum” `PackageReference` na wersję 0.6.1904, a następnie zmień nazwę pakietu „Microsoft.Quantum.Canon” na „Microsoft.Quantum.Standard”, na przykład:

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. W wierszu polecenia Uruchom następujące polecenie: `dotnet msbuild`  
5. Po uruchomieniu tego polecenia może być konieczne ręczne usunięcie błędów powstałych w wyniku wprowadzenia opisanych powyżej zmian.  W wielu przypadkach te błędy będą również raportowane przez funkcję IntelliSense w programie Visual Studio lub edytorze Visual Studio Code.
    - Otwórz folder główny projektu lub obejmujące rozwiązanie w programie Visual Studio 2019 bądź w edytorze Visual Studio Code.
    - Po otwarciu pliku. QS w edytorze należy zobaczyć dane wyjściowe Q# rozszerzenia języka w oknie danych wyjściowych.
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

- Dodaje obsługę Jupyter Notebook, która oferuje doskonały sposób uczenia się Q# .  [Zapoznaj się z nowymi przykładami notesów Jupyter i dowiedz się, jak pisać własne notesy](xref:microsoft.quantum.install). 

- Do biblioteki Quantum Canon dodano arytmetyczny sumator liczb całkowitych.  Zobacz również notes Jupyter z [opisem sposobu korzystania z nowych sumatorów liczb całkowitych](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb).

- Poprawka usterki dla problemu DumpRegister zgłoszonego przez społeczność ([nr 148](https://github.com/Microsoft/Quantum/issues/148)).

- Dodano możliwość powrotu z [instrukcji using](xref:microsoft.quantum.guide.qubits#allocating-qubits).

- Odnowiono [przewodnik Wprowadzenie](xref:microsoft.quantum.install).


## <a name="version-051902"></a>Wersja 0.5.1902

*Data wydania: 27 lutego 2019 r.*

To wydanie zawiera następujące elementy:

- Dodano obsługę międzyplatformowego hosta języka Python.  `qsharp`Pakiet dla języka Python ułatwia symulowanie Q# operacji i funkcji z poziomu języka Python. Dowiedz się więcej na temat [współdziałania w języku Python](xref:microsoft.quantum.install). 

- Rozszerzenia programu Visual Studio i edytora Visual Studio Code obsługują teraz zmianę nazw symboli (np. funkcji i operacji).

- Rozszerzenie programu Visual Studio można teraz instalować w programie Visual Studio 2019.

## <a name="version-041901"></a>Wersja 0.4.1901

*Data wydania: 30 stycznia 2019 r.*

To wydanie zawiera następujące elementy:

- Dodano obsługę nowego typu pierwotnego BigInt, który reprezentuje liczbę całkowitą ze znakiem o dowolnym rozmiarze.  Dowiedz się więcej na temat [typu BigInt](xref:microsoft.quantum.guide.types).
- Dodano nowy symulator Toffoli będący szybkim symulatorem specjalnego przeznaczenia, który może symulować operacje X, CNOT i kontrolowane wielokrotnie operacje kwantowe X na bardzo dużych liczbach kubitów.  Dowiedz się więcej na temat [symulatora Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).
- Dodaje prosty szacowania zasobów, który szacuje zasoby wymagane do uruchomienia danego wystąpienia Q# operacji na komputerze Quantum.  Dowiedz się więcej o [estymatorze zasobów](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Wersja 0.3.1811.2802

*Data wydania: 28 listopada 2018 r.*

Mimo że nasze rozszerzenie edytora VS Code nie korzystało z tego pakietu NPM, zostało oflagowane i usunięte z platformy handlowej podczas [czyszczenia rozszerzeń](https://code.visualstudio.com/blogs/2018/11/26/event-stream) związanego z pakietem NPM `event-stream`. Ta wersja usuwa wszystkie zależności środowiska uruchomieniowego, które mogą spowodować, że rozszerzenie wyzwoli jakieś czerwone flagi.

Jeśli wcześniej zainstalowano rozszerzenie, konieczna będzie jego ponowna instalacja. W tym celu należy przejść na stronę rozszerzenia [Microsoft Quantum Development Kit dla programu Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) w witrynie Marketplace programu Visual Studio i nacisnąć przycisk Install (Instaluj). Przepraszamy za tę niedogodność.


## <a name="version-0318111511"></a>Wersja 0.3.1811.1511

*Data wydania: 20 listopada 2018 r.*

W tej wersji naprawiono usterkę, która uniemożliwiała niektórym użytkownikom pomyślne załadowanie rozszerzenia programu Visual Studio.

## <a name="version-031811203"></a>Wersja 0.3.1811.203

*Data wydania: 2 listopada 2018 r.*

Ta wersja zawiera kilka poprawek usterek, w tym następujące:

* Wywołanie obiektu `DumpMachine` może w pewnych sytuacjach zmienić stan symulatora.
* Usunięto ostrzeżenia kompilacji wyświetlane podczas kompilowania projektów na platformie .NET Core w wersjach wcześniejszych niż 2.1.403.
* Przeprowadzono czyszczenie dokumentacji, w szczególności etykietek narzędzi wyświetlanych po umieszczeniu wskaźnika myszy na elemencie interfejsu programu VS Code lub Visual Studio.

## <a name="version-0318102508"></a>Wersja 0.3.1810.2508

*Data wydania: 29 października 2018 r.*

Ta wersja zawiera nowe funkcje językowe i udoskonalone środowisko programistyczne:

* Ta wersja zawiera serwer języka dla programu Q# , a także integracje klienta dla programu Visual Studio i Visual Studio Code. Dzięki temu może działać nowy zestaw funkcji IntelliSense wraz ze wskazówkami wyświetlanymi podczas pisania w postaci falistego podkreślenia błędów i ostrzeżeń. 
* Ta aktualizacja znacznie usprawnia wyświetlanie ogólnych komunikatów diagnostycznych, przez co ułatwia nawigację i precyzowanie zakresów danych diagnostycznych, a także powoduje wyświetlanie dodatkowych szczegółów w aktywnych okienkach.
* Q#Język został rozszerzony w sposób, który łączy, że deweloperzy mogą wykonywać typowe operacje i nowe ulepszenia funkcji języka, aby wydajnie wyrażać obliczenia Quantum.  W tej wersji kilku się o istotne zmiany w Q# języku.   

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
* Dokumentacja zawiera opis sposobu korzystania z programu NWChem do generowania dodatkowych modeli chemicznych dla symulacji Quantum przy użyciu programu Q# .

Dowiedz się więcej o [bibliotece chemicznej zestawu Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

Po wprowadzeniu nowej biblioteki chemicznej przenosimy biblioteki do nowego repozytorium GitHub [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Przykłady pozostają w repozytorium [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Zapraszamy do wnoszenia własnego wkładu w obu tych repozytoriach!

Ta wersja zawiera poprawki błędów i rozwiązania problemów zgłaszanych przez społeczność:

* Czy funkcja IntelliSense Q# ? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* Pliki qs ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Ulepszenie komunikatu o błędzie wyświetlanego, gdy nawiasy klamrowe są skracane w instrukcji if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Obsługa dekonstrukcji krotki podczas modyfikowalnego wiązania (lub ponownego wiązania) ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Błąd podczas uruchamiania udostępnionego przykładu BitFlipCode ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* Interfejs H2SimulationGUI wyświetla czasami wysokie wartości szczytowe ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Współtworzenie w ramach społeczności

**Dziękujemy** wymienionym poniżej współautorom bazy otwartego kodu w repozytorium http://github.com/Microsoft/Quantum. Te wkłady znacznie znacząco rozbudowane przykłady Q# kodu:

* Rolf Huisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): Ulepszone środowisko dla QASM/ Q# deweloperów, tworząc QASM do Q# translatora. [Żądanie ściągnięcia nr 58](https://github.com/Microsoft/Quantum/pull/58).

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

Te wersje to zaledwie szybka poprawka [#48 problemu zgłoszonego w witrynie GitHub](https://github.com/Microsoft/Quantum/issues/48) ( Q# kompilacja kończy się niepowodzeniem, jeśli nazwa użytkownika zawiera puste miejsce). Należy wykonać taką samą procedurę aktualizacji jak w przypadku wersji `0.2.1806.1503` z odpowiednią nową wersją (`0.2.1806.3001-preview`).

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

Dowiedz się więcej na temat [testowania i debugowania](xref:microsoft.quantum.guide.testingdebugging).

### <a name="community-contributions"></a>Współtworzenie w ramach społeczności

Q#Społeczność kodu rośnie i ekscytacją się, że są one widoczne dla pierwszego użytkownika biblioteki i przykłady, które zostały przesłane do naszej bazy kodu Open http://github.com/Microsoft/quantum .  **Ogromne podziękowania** dla wymienionych poniżej współautorów:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)): dostarczył przykład definiujący bazującą na transformacji metodę syntezy logicznej, która konstruuje sieci Toffoli w celu zaimplementowania danej permutacji. Kod jest zapisywana w całości w Q# funkcjach i operacjach.  [Żądanie ściągnięcia nr 41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): Microsoft MVP Rolf Huisman, który generuje kod płaski QASM z Q# kodu dla ograniczonej klasy programów, które nie mają klasycznego przepływu sterowania i ograniczone operacje Quantum. [Żądanie ściągnięcia nr 59](https://github.com/Microsoft/Quantum/pull/59)
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

Ta wersja jest w pełni zgodna z poprzednimi wersjami. Wystarczy zaktualizować pakiety nuget w projektach do wersji `0.2.1806.1503-preview` i wykonać **pełną ponowną kompilację** , aby mieć pewność, że wszystkie pliki pośrednie zostaną ponownie wygenerowane.

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
1. Utwórz nowy projekt platformy .NET Core przy użyciu odpowiedniego typu Q# szablonu projektu (aplikacji, biblioteki lub projektu testowego).
2. Skopiuj istniejące pliki qs i cs/fs ze starego projektu do nowego (przy użyciu menu Dodaj > Istniejący element). Nie kopiuj pliku AssemblyInfo.cs.
3. Skompiluj i uruchom nowy projekt.

Należy pamiętać, że operacja RandomWalkPhaseEstimation z przestrzeni nazw Microsoft.Quantum.Canon została przeniesiona do przestrzeni nazw Microsoft.Research.Quantum.RandomWalkPhaseEstimation w repozytorium [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Znane problemy

- `--filter`Opcja nie `dotnet test` działa poprawnie dla testów zapisanych Q# .
  W związku z tym poszczególne testy jednostkowe nie mogą być uruchamiane w Visual Studio Code; Zalecamy korzystanie z `dotnet test` wiersza polecenia w celu ponownego uruchomienia wszystkich testów.

## <a name="version-0118011707"></a>Wersja 0.1.1801.1707

*Data wydania: 18 stycznia 2018 r.*

Ta wersja zawiera rozwiązania niektórych problemów zgłaszanych przez społeczność. Oto one:

- Symulator działa teraz z wczesnymi procesorami z wyłączonymi instrukcjami AVX.
- Regionalne ustawienia dziesiętne nie spowodują Q# błędu analizatora.
- Operacja pierwotna `SignD` zwraca teraz typ `Int`, a nie `Double`.


## <a name="version-011712901"></a>Wersja 0.1.1712.901

*Data wydania: 11 grudnia 2017 r.*

### <a name="known-issues"></a>Znane problemy

#### <a name="hardware-and-software-requirements"></a>Wymagania dotyczące sprzętu i oprogramowania

- Symulator dołączony do zestawu Quantum Development Kit wymaga zainstalowania 64-bitowego systemu Microsoft Windows.
- Symulator kwantowy firmy Microsoft instalowany z zestawem Quantum Development Kit wykorzystuje instrukcje Advanced Vector Extensions (AVX) i wymaga procesorów z włączonymi instrukcjami AVX. Procesory firmy Intel od modelu Sandy Bridge (dostarczanego od 1. kwartału 2011 r.) obsługują instrukcje AVX. Rozważamy obsługę wcześniejszych procesorów i być może, że szczegółowe informacje na ten temat zostaną ogłoszone w późniejszym czasie.

#### <a name="project-creation"></a>Tworzenie projektu

- Podczas tworzenia rozwiązania (. sln), które będzie używane Q# , rozwiązanie musi być jednym katalogiem wyższym niż każdy projekt (. csproj) w rozwiązaniu. Podczas tworzenia nowego rozwiązania można to zagwarantować przez zaznaczenie pola wyboru „Utwórz katalog dla rozwiązania” w oknie dialogowym „Nowy projekt”. Jeśli nie zostanie to zrobione, pakiety NuGet zestawu Quantum Development Kit będą musiały zostać zainstalowane ręcznie.

#### Q#

- Funkcja IntelliSense nie wyświetla prawidłowych błędów dla Q# kodu. Upewnij się, że wyświetlane są błędy kompilacji w Lista błędów programu Visual Studio, aby wyświetlić poprawne Q# błędy. Należy również zauważyć, że Q# błędy nie będą wyświetlane, dopóki nie zostanie ukończona kompilacja.
- Użycie modyfikowalnej tablicy w częściowej aplikacji może prowadzić do nieoczekiwanego zachowania.
- Powiązanie niezmiennej tablicy z tablicą modyfikowalną (let a = b, gdzie b jest tablicą modyfikowalną) może prowadzić do nieoczekiwanego zachowania.
- Profilowanie, pokrycie kodu i inne wtyczki programu VS mogą nie zawsze określać Q# wierszy i bloków.
- Q#Kompilator nie sprawdza poprawności ciągów interpolowanych. Istnieje możliwość tworzenia błędów kompilacji w języku C# przez błędne nazwy zmiennych lub użycie wyrażeń w Q# ciągach interpolowanych.

#### <a name="simulation"></a>Symulacja

- Symulator kwantowy korzysta z interfejsu OpenMP do zrównoleglenia wymaganej algebry liniowej. Domyślnie interfejs OpenMP korzysta ze wszystkich dostępnych wątków sprzętowych, co oznacza, że programy z niewielką liczbą kubitów często działają wolniej, ponieważ wymóg koordynacji powoduje spowolnienie rzeczywistej pracy. Można to naprawić przez ustawienie zmiennej środowiskowej OMP_NUM_THREADS na małą liczbę. Można kierować się zasadą, że w przybliżeniu 1 wątek jest wystarczający dla około 4 kubitów. Następnie na jeden kubit powinien przypadać jeden dodatkowy wątek. Jest to jednak szacowanie wysoce zależne od konkretnego algorytmu.

#### <a name="debugging"></a>Debugowanie

- F11 (Step In) nie działa w Q# kodzie.
- Wyróżnianie kodu w kodzie w punkcie Q# przerwania lub wstrzymanie pojedynczego kroku jest czasami niedokładne. Jest co prawda wyróżniany prawidłowy wiersz, ale czasami wyróżnienie rozpoczyna się i kończy w nieprawidłowych kolumnach wiersza.

#### <a name="testing"></a>Testowanie

- Testy muszą być uruchamiane w trybie 64-bitowym. Jeśli testy kończą się niepowodzeniem ze zgłoszonym wyjątkiem BadImageFormatException, przejdź do menu testu, a następnie wybierz pozycję Ustawienia testu > Domyślna architektura procesora > X64.
- Niektóre testy są długotrwałe (w zależności od komputera mogą trwać do 5 minut). Jest to normalne w przypadku użycia ponad dwudziestu kubitów. Nasz największy test aktualnie działa z 23 kubitami.

#### <a name="samples"></a>Samples

- Na niektórych komputerach niektóre małe przykłady mogą działać wolno, jeśli zmienna środowiskowa OMP_NUM_THREADS nie zostanie ustawiona na wartość „1”. Zobacz również uwagi dotyczące wersji w sekcji „Symulacja”.

#### <a name="libraries"></a>Biblioteki

- Istnieje niejawne założenie, że kubity przekazane do operacji w różnych argumentach są unikatowe. Na przykład we wszystkich operacjach biblioteki (i wszystkich symulatorach) przyjęto założenie, że dwa kubity przekazane do kontrolowanej negacji są różnymi kubitami. Naruszenie tego założenia może prowadzić do nieoczekiwanego zachowania. Możliwe jest przetestowanie tego założenia za pomocą symulatora śledzenia komputera kwantowego.
- Funkcja Microsoft.Quantum.Bind może nie działać zgodnie z oczekiwaniami we wszystkich przypadkach.
- W przestrzeni nazw Microsoft.Quantum.Extensions.Math funkcja SignD zwraca liczbę typu Double, a nie Int, mimo że bazowa funkcja System.Math.Sign zawsze zwraca liczbę całkowitą. Można bezpiecznie porównać wynik z liczbami 1,0, -1,0 i 0,0, ponieważ wszystkie te liczby typu Double mają dokładne reprezentacje binarne.
