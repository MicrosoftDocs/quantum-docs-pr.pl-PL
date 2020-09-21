---
title: Q# Zasady projektowania interfejsu API
description: Q# Zasady projektowania interfejsu API
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8714d3290e4099f901dab20a9ee9334699c4ad81
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834913"
---
# <a name="no-locq-api-design-principles"></a>Q# Zasady projektowania interfejsu API

## <a name="introduction"></a>Wprowadzenie

Jako język i jako platforma, umożliwiają Q# użytkownikom pisanie, uruchamianie, poznawanie i eksplorowanie aplikacji Quantum.
Aby zwiększyć możliwości użytkowników, podczas projektowania Q# bibliotek korzystamy z zestawu zasad projektowania interfejsu API do obsługi naszych projektów oraz do tworzenia przydatnych bibliotek dla społeczności deweloperskiej usługi Quantum.
W tym artykule wymieniono te zasady i przedstawiono przykłady, które ułatwiają stosowanie ich podczas projektowania Q# interfejsów API.

> [!TIP]
> Jest to dość szczegółowy dokument, który jest przeznaczony do obsługi projektowania biblioteki i szczegółowego udziału w bibliotece.
> Prawdopodobnie okaże się to przydatne, jeśli piszesz własne biblioteki w programie Q# , lub jeśli chcesz uzyskać większe funkcje do [ Q# repozytorium bibliotek](https://github.com/microsoft/QuantumLibraries).
>
> Z drugiej strony, jeśli chcesz dowiedzieć się, jak bardziej ogólnie współtworzyć pakiet Quantum Development Kit, zalecamy rozpoczęcie od [przewodnika po udziale](xref:microsoft.quantum.contributing).
> Jeśli szukasz bardziej ogólnych informacji o tym, jak zalecamy formatowanie Q# kodu, możesz chcieć zaewidencjonować [Przewodnik po stylu](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Zasady ogólne

**Kluczowa zasada:** Uwidaczniaj interfejsy API, które koncentrują się na aplikacjach Quantum.

- ✅**Wybierz operacje** i nazwy funkcji, które odzwierciedlają strukturę wysokiego poziomu algorytmów i aplikacji.
- ⛔️ **nie** ujawniaj interfejsów API, które koncentrują się głównie na szczegółach implementacji niskiego poziomu.

**Kluczowa zasada:** Uruchom każdy projekt interfejsu API z przykładowymi przypadkami użycia, aby upewnić się, że interfejsy API są intuicyjne.

- ✅**Upewnij się** , że każdy składnik publicznego interfejsu API ma odpowiadający mu przypadek użycia, zamiast próbować projektować wszystkie możliwe zastosowania od początku.
    Umieszczaj inaczej, nie wprowadzaj publicznych interfejsów API, jeśli są użyteczne, ale upewnij się, że każda część interfejsu API ma *konkretny* przykład, w którym będzie przydatna.

  *Przykłady:*
  - @"microsoft.quantum.canon.applytoeachca" może służyć jako `ApplyToEachCA(H, _)` do przygotowywania rejestrów w jednolitym stanie nadpozycji, typowe zadanie w wielu algorytmach Quantum. Tej samej operacji można także użyć dla wielu innych zadań w ramach przygotowywania, liczb i algorytmów opartych na oprogramowaniu Oracle.

- ✅**Wykonaj** nowe projekty interfejsu API w ramach burzy mózgów i warsztatów, aby sprawdzić, czy są one intuicyjne i spełniają proponowane przypadki użycia.

  *Przykłady:*
  - Sprawdź bieżący kod Q, \# Aby zobaczyć, jak nowe projekty interfejsu API mogą uprościć i wyjaśnić istniejące implementacje.
  - Przejrzyj proponowane projekty interfejsów API z przedstawicielami głównych odbiorców.

**Kluczowa zasada:** Projektuj interfejsy API do obsługi i Zachęcaj do odczytu kodu.

- ✅**Upewnij się** , że kod jest czytelny dla ekspertów domeny i nie są podobne do ekspertów.
- ✅**Należy** skoncentrować się na efektach każdej operacji i funkcji w algorytmie wysokiego poziomu, korzystając z dokumentacji, aby zapoznać się z informacjami dotyczącymi implementacji, zgodnie z potrzebami.
- ✅Jeśli ma to zastosowanie **, postępuj** zgodnie ze wspólnym [ \# przewodnikiem stylu Q](xref:microsoft.quantum.contributing.style) .

**Kluczowa zasada:** Projektuj interfejsy API, które mają być stabilne i zapewniają zgodność z przesyłaniem dalej.

- ✅**Należy** bezpiecznie zaniechać starych interfejsów API, gdy wymagane jest wprowadzenie zmian.

- ✅**Podaj operacje** i funkcje "podkładki", które umożliwiają prawidłowe działanie istniejącego kodu użytkownika podczas jego wymuszania.

  *Przykłady:*
  - Podczas zmieniania nazwy operacji wywoływanej `EstimateExpectation` do   `EstimateAverage` , należy wprowadzić nową operację o nazwie,   `EstimateExpectation` która wywołuje oryginalną operację przy użyciu nowej nazwy, tak aby istniejący kod nadal działał poprawnie.

- ✅**Użyj** atrybutu, @"microsoft.quantum.core.deprecated" Aby komunikować się z zaniechaniem użytkownika.

- ✅ Podczas zmieniania nazwy operacji lub funkcji należy **podać nową** nazwę jako ciąg wejściowy do `@Deprecated` .

- ⛔️ **nie** usuwać istniejących funkcji ani operacji bez okresu wycofania wynoszącego co najmniej sześć miesięcy w przypadku wersji zapoznawczej lub co najmniej dwa lata dla obsługiwanych wersji.

## <a name="functions-and-operations"></a>Funkcje i operacje

**Zasada klucza:** upewnij się, że każda funkcja i operacja mają jeden dobrze zdefiniowany cel w ramach interfejsu API.

- ⛔️ **nie** ujawniaj funkcji i operacji, które wykonują wiele niepowiązanych zadań.

**Kluczowa zasada:** Projektuj funkcje i operacje, tak jak to możliwe, oraz przewidywanie przyszłych potrzeb.

- ✅Twórz funkcje i **operacje projektowania w** celu tworzenia dobrze z innymi funkcjami i operacjami, zarówno w tym samym interfejsie API, jak i w wcześniej istniejących bibliotekach.

  *Przykłady:*
  - @"microsoft.quantum.canon.delay"Operacja powoduje minimalny wpływ na dane wejściowe i w ten sposób może być używana do opóźniania aplikacji w ramach Q# standardowej biblioteki lub zdefiniowanej przez użytkowników.
    <!-- TODO: define bad example. -->

- ✅W przypadku funkcji, a nie operacji, **należy** uwidocznić czysto zaklasyczną logikę.

  *Przykłady:*
  - Podprocedura, która kwadratów danych wejściowych zmiennoprzecinkowych może być pisanych niejednoznacznie i dlatego powinna być udostępniona użytkownikowi, `Squared : Double -> Double` a nie jako operacja `Square : Double => Double` . Pozwala to na wywoływanie podprocedury w większej liczbie miejsc (np. w innych funkcjach) i udostępnia przydatne informacje optymalizacji kompilatorowi, który może mieć wpływ na wydajność i optymalizacje.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` i `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` różnią się w zależności od tego, czy są one przydatne w różnych sytuacjach.
  - Procedury interfejsu API, które przekształcają stosowanie operacji Quantum, często mogą być wykonywane w sposób deterministyczny i dlatego mogą być udostępniane jako funkcje takie jak   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` .

- ✅**Uogólnij** typ danych wejściowych o ile jest to odpowiednie dla każdej funkcji i operacji, przy użyciu parametrów typu w razie potrzeby.

  *Przykłady:*
  - `ApplyToEach` ma typ `<'T>(('T => Unit), 'T[]) => Unit` , a nie konkretny typ najczęściej używanej aplikacji `((Qubit => Unit), Qubit[]) => Unit` .

> [!TIP]
> Ważne jest, aby przewidzieć przyszłe potrzeby, ale ważne jest również rozwiązywanie konkretnych problemów dla użytkowników.
> W związku z tym, należy w ten sposób zawsze wymagać starannego rozważenia i zrównoważenia, aby uniknąć tworzenia interfejsów API "tylko w przypadku".

**Kluczowa zasada:** wybierz typy danych wejściowych i wyjściowych dla funkcji i operacji, które są przewidywalne, i które komunikują cel możliwy do uzyskania.

- ✅**Używaj typów** krotek do logicznego grupowania danych wejściowych i wyjściowych, które są ważne tylko wtedy, gdy są brane pod uwagę. Rozważ użycie w takich przypadkach typu zdefiniowanego przez użytkownika.

  *Przykłady:*
  - Funkcja do wyprowadzania lokalnych wartości minimum innej funkcji może wymagać przełączenia interwału wyszukiwania jako dane wejściowe, co `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` może być odpowiednią sygnaturą.
  - Operacja szacowania pochodnego klasyfikatora uczenia maszynowego przy użyciu techniki przesunięcia parametrów może wymagać przesunięcia i przesunięcia wektorów parametrów jako danych wejściowych. Dane wejściowe podobne do `(unshifted : Double[], shifted : Double[])` mogą być odpowiednie w tym przypadku.

- ✅**Porządkuj** elementy w spójnych i wyjściowych krotki spójnie w różnych funkcjach i operacjach.

  *Przykłady:*
  - Jeśli rozważasz dwa lub funkcje lub operacje, które każda z nich przyjmuje kąt obrotu i docelowy qubit jako dane wejściowe, upewnij się, że są one uporządkowane tak samo w każdej spójnej kolekcji. To jest, Preferuj `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` i `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` do `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` i `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` .

**Kluczowa zasada:** Projektuj funkcje i operacje, aby dobrze współpracować z \# funkcjami języka Q, takimi jak częściowa aplikacja.

- ✅**Wykonaj** zamówienie elementów w spójnych kolekcjach, tak aby najczęściej stosowane dane wejściowe były wykonywane w pierwszej kolejności (tj. w taki sposób, że częściowa aplikacja działa podobnie do currying).

  *Przykłady:*
  - Operacja `ApplyRotation` , która pobiera liczbę zmiennoprzecinkową i qubit jako dane wejściowe, może być często stosowana częściowo z danymi wejściowymi zmiennoprzecinkowymi jako pierwszą do użycia z operacjami, które oczekują wejścia typu `Qubit => Unit` . W rezultacie sygnatura `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      może być najbardziej spójna z częściową aplikacją.
  - Zwykle te wskazówki oznaczają umieszczenie wszystkich danych klasycznych przed wszystkimi qubits w spójnych krotkach, ale używają dobrych orzeczeń i sprawdzenia, jak interfejs API jest wywoływany w ćwiczeń.

## <a name="user-defined-types"></a>Typy zdefiniowane przez użytkownika

**Kluczowa zasada:** Użyj typów zdefiniowanych przez użytkownika, aby ułatwić tworzenie i Używanie interfejsów API.

- ✅**Wprowadź nowe** typy zdefiniowane przez użytkownika, aby zapewnić pomocne skróty dla długich i/lub skomplikowanych typów.

  *Przykłady:*
  - W przypadkach, gdy typ operacji z trzema danymi wejściowymi tablicy qubit jest często traktowany jako dane wejściowe lub zwracane jako dane wyjściowe, dostarczając typ UDT, taki jak `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      może pomóc w zapewnieniu przydatnej skróconej składni.

- ✅**Wprowadź nowe** typy zdefiniowane przez użytkownika, aby wskazać, że dany typ podstawowy ma być używany tylko w konkretnym sensie.

  *Przykłady:*
  - Operacja, która powinna być interpretowana jako operacja, która koduje dane klasyczne w rejestrze Quantum, może być odpowiednia do etykietowania z typem zdefiniowanym przez użytkownika `newtype InputEncoder = (Apply : (Qubit[] => Unit))` .

- ✅**Wprowadź nowe** typy zdefiniowane przez użytkownika z nazwanymi elementami, które zezwalają na przyszłą rozszerzalność (np.: Struktura wyników, która może zawierać dodatkowe nazwane elementy w przyszłości).

  *Przykłady:*
  - Gdy operacja `TrainModel` uwidacznia dużą liczbę opcji konfiguracji, narażając te opcje jako nowe   `TrainingOptions` UDT i dostarczając nową funkcję,   `DefaultTrainingOptions : Unit -> TrainingOptions` Użytkownicy mogą przesłonić określone nazwane elementy w TrainingOptions wartości UDT, jednocześnie umożliwiając deweloperom biblioteki Dodawanie nowych elementów UDT odpowiednio do potrzeb.

- ✅**Zadeklaruj nazwane** elementy dla nowych typów zdefiniowanych przez użytkownika w preferencjach, aby wymagać od użytkowników znajomości poprawnej dekonstrukcji krotki.

  *Przykłady:*
  - Gdy reprezentujesz liczbę zespoloną w swojej dekompozycji biegunowej, wolisz   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)`   `newtype ComplexPolar = (Double, Double)` .

**Kluczowa zasada:** Użyj typów zdefiniowanych przez użytkownika w taki sposób, aby zmniejszyć obciążenie poznawcze i nie wymagał od użytkownika poznania dodatkowych koncepcji i nomenklatury.

- ⛔️ **nie** należy wprowadzać typów zdefiniowanych przez użytkownika, które wymagają, aby użytkownik mógł często korzystać z operatora `!` rozpakowywania () lub który często wymaga wielu poziomów rozwinięcia. Możliwe strategie zaradcze obejmują:

  - Podczas uwidaczniania typu zdefiniowanego przez użytkownika za pomocą jednego elementu należy rozważyć zdefiniowanie nazwy dla tego elementu. Na przykład rozważmy `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` preferencję `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` .

  - Upewnienie się, że inne funkcje i operacje mogą akceptować "opakowane" wystąpienia UDT bezpośrednio.

- ⛔️ **nie** wprowadzaj nowych typów zdefiniowanych przez użytkownika, które duplikują typy wbudowane bez udostępniania dodatkowych wyrazistości.

  *Przykłady:*
  - UDT `newtype QubitRegister = Qubit[]` nie zapewnia żadnych dodatkowych wyrazistości `Qubit[]` i jest trudniejsze do użycia bez korzyści discernable.
  - Typ UDT `newtype LittleEndian = Qubit[]` dokumentów, w jaki ma być używany i interpretowany źródłowy rejestr i w ten sposób zapewnia dodatkowe wyrazistości w porównaniu z jego typem podstawowym.

- ⛔️ **nie** należy wprowadzać funkcji akcesora, chyba że jest to absolutnie wymagane;   silnie Preferuj nazwane elementy w tym przypadku.

  *Przykłady:*
  - Wprowadzając UDT `newtype Complex = (Double, Double)` , wolisz modyfikować definicję do   `newtype Complex = (Real : Double, Imag : Double)` wprowadzenia funkcji `GetReal : Complex -> Double` i   `GetImag : Complex -> Double` .

## <a name="namespaces-and-organization"></a>Przestrzenie nazw i organizacja

**Kluczowa zasada:** wybierz nazwy przestrzeni nazw, które są przewidywalne i wyraźnie komunikują przeznaczenie funkcji, operacji i typów zdefiniowanych przez użytkownika w każdej przestrzeni nazw.

- ✅**Nazywaj** przestrzenie nazw jako `Publisher.Product.DomainArea` .

  *Przykłady:*
  - Funkcje, operacje i UDTs opublikowane przez firmę Microsoft jako część funkcji symulacji Quantum zestawu Quantum Development Kit są umieszczane w   `Microsoft.Quantum.Simulation` przestrzeni nazw.
  - `Microsoft.Quantum.Math` reprezentuje obszar nazw Opublikowany przez firmę Microsoft w ramach zestawu Quantum Development Kit odnoszący się do obszaru domeny matematyki.

- ✅**Należy** umieścić operacje, funkcje i typy zdefiniowane przez użytkownika używane do określonych funkcji w przestrzeni nazw, która opisuje tę funkcję, nawet jeśli ta funkcja jest używana w różnych domenach problemów.

  *Przykłady:*
  - Interfejsy API przygotowania stanu opublikowane przez firmę Microsoft w ramach zestawu Quantum Development Kit byłyby umieszczane w systemie   `Microsoft.Quantum.Preparation` .
  - Interfejsy API symulacji Quantum opublikowane przez firmę Microsoft w ramach zestawu Quantum Development Kit byłyby umieszczane w systemie   `Microsoft.Quantum.Simulation` .

- ✅Operacje **umieszczania** , funkcje i typy zdefiniowane przez użytkownika używane tylko w określonych domenach w przestrzeni nazw wskazujące ich domenę narzędzia. W razie potrzeby użyj subnazw, aby wskazać zadania ukierunkowane w obrębie poszczególnych nazw specyficznych dla domeny.

  *Przykłady:*
  - Biblioteka Quantum Machine Learning Library opublikowana przez firmę Microsoft jest w dużym stopniu umieszczana w @"microsoft.quantum.machinelearning" przestrzeni nazw, ale przykładowe zestawy danych są dostarczane przez @"microsoft.quantum.machinelearning.datasets"   przestrzeń nazw.
  - Chemiczne interfejsy API Quantum opublikowane przez firmę Microsoft jako część zestawu Quantum Development Kit powinny być umieszczone w `Microsoft.Quantum.Chemistry` . Funkcja specyficzna dla wdrożenia programu Jordania--Wigner dekompozycji może zostać umieszczona w `Microsoft.Quantum.Chemistry.JordanWigner` , aby interfejs podstawowy dla obszaru domeny chemii Quantum nie był objęty implementacjami.

**Kluczowa zasada:** Używaj przestrzeni nazw i modyfikatorów dostępu, aby zamierzać powierzchnię interfejsu API narażoną na użytkowników i ukrywać szczegóły wewnętrzne związane z implementacją i testowaniem interfejsów API.

- ✅ W każdym przypadku **należy umieścić wszystkie** funkcje i operacje, które są potrzebne do zaimplementowania interfejsu API w tej samej przestrzeni nazw co zaimplementowany interfejs API, ale oznaczone za pomocą słów kluczowych "Private" lub "internal", aby wskazać, że nie są one częścią publicznej powierzchni interfejsu API biblioteki. Użyj nazwy rozpoczynającej się od znaku podkreślenia ( `_` ) w celu wizualnego odróżnienia operacji prywatnych i wewnętrznych oraz funkcji od publicznych.

  *Przykłady:*
  - Nazwa operacji `_Features` wskazuje funkcję, która jest prywatna dla danego obszaru nazw i zestawu i powinna być dołączona `internal` słowa kluczowego.

- ✅ W rzadkich przypadkach, gdy do zaimplementowania interfejsu API dla danego obszaru nazw jest wymagany obszerny zestaw funkcji lub operacji **prywatnych, należy** umieścić je w nowej przestrzeni nazw zgodnej z zaimplementowaną i końcową przestrzenią nazw `.Private` .

- ✅**Należy** umieścić wszystkie testy jednostkowe w przestrzeni nazw pasujące do przestrzeni nazw w ramach testu i kończąc na `.Tests` .

## <a name="naming-conventions-and-vocabulary"></a>Konwencje nazewnictwa i słownictwo

**Kluczowa zasada:** Wybierz nazwy i terminologię, które są jasne, dostępne i czytelne dla różnorodnych odbiorców, w tym dla początkujących i ekspertów usługi Quantum.

- ⛔️ **nie** używać rozróżniacza ani wykluczania nazw identyfikatorów ani terminologii w komentarzach dokumentacji interfejsu API.

- ✅**Użyj komentarzy** dokumentacji interfejsu API, aby zapewnić odpowiedni kontekst, przykłady i odwołania, szczególnie w przypadku bardziej trudnych koncepcji.

- ⛔️ **nie** Używaj nazw identyfikatorów, które są niekoniecznie Esoteric, lub które wymagają znaczącej wiedzy o algorytmach Quantum do odczytu.

  *Przykłady:*
  - Preferuj "iteracja wzmocnienia amplitudy" na "iteracja Grover".

- ✅**Wybierz operacje** i nazwy funkcji, które wyraźnie komunikują oczekiwany efekt możliwego do przeprowadzenia, a nie jego implementację. Należy pamiętać, że implementacja może i powinna być udokumentowana w [komentarzach dokumentacji interfejsu API](xref:microsoft.quantum.guide.filestructure#documentation-comments).

  *Przykłady:*
  - Preferuj "oszacowanie nakładania się" na "test Hadamard", ponieważ ten drugi komunikuje się, jak dawna jest implementacja.

- ✅**Używaj słów** w spójny sposób dla wszystkich \# interfejsów API Q:

  - **Słowa**

    - **Potwierdzenie**: należy sprawdzić, czy założono założenie stanu maszyny docelowej i jej qubits, prawdopodobnie przy użyciu zasobów niefizycznych. Operacje korzystające z tego zlecenia powinny zawsze być bezpiecznie usuwalne bez wpływu na funkcjonalność bibliotek i programów wykonywalnych. Należy zauważyć, że w przeciwieństwie do faktów, potwierdzenia mogą zasadniczo zależeć od stanu zewnętrznego, takiego jak stan rejestru qubit, środowisko uruchomieniowe lub tak dalej. Ponieważ zależność od stanu zewnętrznego jest rodzajem efektu ubocznego, potwierdzenia muszą być uwidocznione jako operacje, a nie funkcje.

    - **Oszacowanie**: użycie jednego lub większej liczby możliwych do powtórzenia pomiarów, oszacowanie klasycznej ilości wyników pomiarów.

      *Przykłady:*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Przygotowywanie**: stosowanie operacji Quantum lub sekwencji operacji do jednego lub większej liczby qubits założono, że wystąpiły w określonym stanie początkowym (zazwyczaj $ \ket{00\cdots 0} $), powodując, że stan tych qubits będzie się rozwijać do żądanego stanu końcowego. Ogólnie rzecz biorąc, działające na Stanach innych niż dany stan początkowy **może** skutkować niezdefiniowaną transformację jednostkową, ale mimo to nadal **należy** zachować operację i jej podległych "anulować" i zastosować wartość No-op.

      *Przykłady:*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Miara**: stosowanie operacji Quantum lub sekwencji operacji do co najmniej jednego qubits, odczytywanie klasycznych danych z powrotem.

      *Przykłady:*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Zastosuj**: stosowanie operacji Quantum lub sekwencji operacji do jednego lub większej liczby qubits, co powoduje spójny stan tych qubits. To zlecenie jest najbardziej ogólnym zleceniem w \# nomenklaturze Q i **nie powinno być** używane, gdy bardziej szczegółowe zlecenie jest bardziej istotne.

  - **Rzeczowniki**:

    - **Fakt**: warunek logiczny, który zależy tylko od danych wejściowych, a nie na stanie maszyny docelowej, jego środowisku lub stanu qubits maszyny. W przeciwieństwie do potwierdzenia fakt jest tylko wrażliwy na *wartości* podane dla tego faktu. Przykład:

      *Przykłady:*
      - @"microsoft.quantum.diagnostics.equalityfacti": reprezentuje fakt dotyczący dwóch danych wejściowych z liczbą całkowitą; liczby całkowite podane jako dane wejściowe są równe siebie lub nie są niezależne od żadnego innego stanu programu.

    - **Opcje:** Typ UDT zawierający kilka nazwanych elementów, które mogą działać jako argumenty opcjonalne do funkcji lub operacji. Przykład:

      *Przykłady:*
      - @"microsoft.quantum.machinelearning.trainingoptions"UDT zawiera nazwane elementy dla stawki szkoleniowej, rozmiar minibatch oraz inne konfigurowalne parametry szkolenia ml.

  - **Przymiotniki**:

    - ⛔️ **New**: **nie należy** używać tego przymiotnika, aby uniknąć nieporozumień z użyciem jako czasownika w wielu językach programowania (np.: C++, C#, Java, TypeScript, PowerShell).

  - **Położenia pozycyjne:** W niektórych przypadkach, można użyć pozycji, aby bardziej odróżnić lub wyjaśnić role rzeczowników i czasowników w nazwach funkcji i operacji. Należy jednak zachować ostrożność i spójność.

    - **Jako:** Reprezentuje, że dane wejściowe i wyjściowe funkcji reprezentują te same informacje, ale dane wyjściowe przedstawiają te informacje **jako** *X* , a nie oryginalną reprezentację. Jest to szczególnie typowe w przypadku funkcji konwersji typów.

      *Przykłady:*
      - `IntAsDouble(2)` wskazuje, że zarówno dane wejściowe ( `2` ), jak i dane wyjściowe ( `2.0` ) reprezentują jakościowe te same informacje, ale przy użyciu różnych \# typów danych Q.

    - **Z:** Aby zapewnić spójność, ta pozycja   **nie powinna** być używana do wskazania funkcji konwersji typu lub innego przypadku **,** gdzie jest to odpowiednie.

    - ⛔️ **:** **nie należy** używać tego położenia przedniego, aby uniknąć nieporozumień z użyciem jako czasownika w wielu językach programowania.
