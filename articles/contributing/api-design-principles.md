---
title: 'Zasady projektowania interfejsu API Q #'
description: 'Zasady projektowania interfejsu API Q #'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: 03c32331f8988181ec6fedcfc207d752b4a880b2
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024206"
---
# <a name="q-api-design-principles"></a>Zasady projektowania interfejsu API Q #

## <a name="introduction"></a>Wprowadzenie

Jako język i jako platforma, Q # umożliwia użytkownikom pisanie, uruchamianie, poznawanie i eksplorowanie aplikacji Quantum.
Aby zwiększyć możliwości użytkowników, podczas projektowania bibliotek Q # korzystamy z zestawu zasad projektowania interfejsu API, który będzie omawiał nasze projekty i aby pomóc nam w tworzeniu przydatnych bibliotek dla społeczności deweloperskiej usługi Quantum.
W tym artykule wymieniono te zasady i przedstawiono przykłady, które ułatwiają stosowanie ich podczas projektowania interfejsów API pytań i odpowiedzi.

> [!TIP]
> Jest to dość szczegółowy dokument, który jest przeznaczony do obsługi projektowania biblioteki i szczegółowego udziału w bibliotece.
> Prawdopodobnie okaże się to przydatne, jeśli piszesz własne biblioteki w usłudze Q # lub jeśli chcesz uzyskać większe funkcje w [repozytorium bibliotek Q #](https://github.com/microsoft/QuantumLibraries).
>
> Z drugiej strony, jeśli chcesz dowiedzieć się, jak bardziej ogólnie współtworzyć pakiet Quantum Development Kit, zalecamy rozpoczęcie od [przewodnika po udziale](xref:microsoft.quantum.contributing).
> Jeśli szukasz bardziej ogólnych informacji na temat sposobu, w jaki zalecamy formatowanie kodu Q #, możesz chcieć zaewidencjonować [Przewodnik po stylu](xref:microsoft.quantum.contributing.style).

## <a name="general-principles"></a>Zasady ogólne

**Kluczowa zasada:** Uwidaczniaj interfejsy API, które koncentrują się na aplikacjach Quantum.

- ✅ **Wybierz** operacje i nazwy funkcji, które odzwierciedlają strukturę algorytmów i aplikacji wysokiego poziomu.
- ⛔️ **nie** ujawniaj interfejsów API, które koncentrują się głównie na szczegółach implementacji niskiego poziomu.

**Kluczowa zasada:** Uruchom każdy projekt interfejsu API z przykładowymi przypadkami użycia, aby upewnić się, że interfejsy API są intuicyjne.

- ✅ **upewnij** się, że każdy składnik publicznego interfejsu API dysponuje odpowiednim przypadkiem użycia, zamiast próbować projektować wszystkie możliwe zastosowania od początku.
    Umieszczaj inaczej, nie wprowadzaj publicznych interfejsów API, jeśli są użyteczne, ale upewnij się, że każda część interfejsu API ma *konkretny* przykład, w którym będzie przydatna.

  *Pokazują*
  - @"microsoft.quantum.canon.applytoeachca" można użyć jako `ApplyToEachCA(H, _)` do przygotowania rejestrów w jednolitym stanie nadpozycji, czyli typowym zadaniem w wielu algorytmach Quantum. Tej samej operacji można także użyć dla wielu innych zadań w ramach przygotowywania, liczb i algorytmów opartych na oprogramowaniu Oracle.

- ✅ **przeprowadzenie** burzy mózgów i warsztatów nowych projektów interfejsu API w celu sprawdzenia, czy są one intuicyjne i spełniają proponowane przypadki użycia.

  *Pokazują*
  - Sprawdź bieżący kod Q\#, aby zobaczyć, jak nowe projekty interfejsu API mogą uprościć i wyjaśnić istniejące implementacje.
  - Przejrzyj proponowane projekty interfejsów API z przedstawicielami głównych odbiorców.

**Kluczowa zasada:** Projektuj interfejsy API do obsługi i Zachęcaj do odczytu kodu.

- ✅ upewnij się, że kod jest czytelny dla ekspertów domeny i nie są **podobne do ekspertów** .
- ✅ **należy** umieścić fokus na efektach każdej operacji i funkcji w algorytmie wysokiego poziomu, korzystając z dokumentacji, aby zapoznać się ze szczegółami implementacji, zgodnie z potrzebami.
- w każdym **przypadku ✅** postępuj zgodnie ze wspólnym [przewodnikiem po stylu\# pytań](xref:microsoft.quantum.contributing.style) i odpowiedzi.

**Kluczowa zasada:** Projektuj interfejsy API, które mają być stabilne i zapewniają zgodność z przesyłaniem dalej.

- ✅ **DO** bezproblemowo zaniechać starych interfejsów API, gdy wymagane jest wprowadzenie zmian.

- ✅ **DO** podawanie operacji "podkładki" i funkcji, które umożliwiają prawidłowe działanie istniejącego kodu użytkownika podczas jego wycofania.

  *Pokazują*
  - Podczas zmiany nazwy operacji o nazwie `EstimateExpectation` na `EstimateAverage`, należy wprowadzić nową operację o nazwie `EstimateExpectation`, która wywołuje oryginalną operację pod nową nazwą, tak aby istniejący kod nadal działał poprawnie.

- ✅ **użyć** atrybutu @"microsoft.quantum.core.deprecated", aby komunikować się z zaniechaniem użytkownika.

- ✅ podczas zmiany nazwy operacji lub funkcji **należy podać nową** nazwę jako ciąg wejściowy do `@Deprecated`.

- ⛔️ **nie** usuwać istniejących funkcji ani operacji bez okresu wycofania wynoszącego co najmniej sześć miesięcy w przypadku wersji zapoznawczej lub co najmniej dwa lata dla obsługiwanych wersji.

## <a name="functions-and-operations"></a>Funkcje i operacje

**Zasada klucza:** upewnij się, że każda funkcja i operacja mają jeden dobrze zdefiniowany cel w ramach interfejsu API.

- ⛔️ **nie** ujawniaj funkcji i operacji, które wykonują wiele niepowiązanych zadań.

**Kluczowa zasada:** Projektuj funkcje i operacje, tak jak to możliwe, oraz przewidywanie przyszłych potrzeb.

- ✅ **do** projektowania funkcji i operacji w celu tworzenia dobrze z innymi funkcjami i operacjami, zarówno w tym samym interfejsie API, jak i w wcześniej istniejących bibliotekach.

  *Pokazują*
  - Operacja @"microsoft.quantum.canon.delay" zapewnia minimalny wpływ na dane wejściowe i w ten sposób może być używana do opóźniania aplikacji dla każdej operacji w standardowej bibliotece Q # lub zdefiniowanej przez użytkowników.
    <!-- TODO: define bad example. -->

- ✅ dzięki funkcji, **a nie operacji** , uwidaczniaj czysty algorytm klasyczny.

  *Pokazują*
  - Podprocedura, która wskazuje, że punkty wejścia zmiennoprzecinkowego mogą być zapisywane deterministycznie i dlatego powinny być uwidocznione dla użytkownika jako `Squared : Double -> Double`, a nie jako `Square : Double => Double`operacji. Pozwala to na wywoływanie podprocedury w większej liczbie miejsc (np. w innych funkcjach) i udostępnia przydatne informacje optymalizacji kompilatorowi, który może mieć wpływ na wydajność i optymalizacje.
  - `ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` i `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` różnią się w gwarancje w odniesieniu do ustalenia. Oba są przydatne w różnych sytuacjach.
  - Procedury interfejsu API, które przekształcają stosowanie operacji Quantum, często mogą być wykonywane w sposób deterministyczny, dlatego można je udostępnić jako funkcje takie jak `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`.

- ✅ Uogólnij typ danych wejściowych o **ile jest to** rozsądne dla każdej funkcji i operacji, przy użyciu parametrów typu zgodnie z potrzebami.

  *Pokazują*
  - `ApplyToEach` ma typ `<'T>(('T => Unit), 'T[]) => Unit`, a nie określony typ najczęściej używanej aplikacji, `((Qubit => Unit), Qubit[]) => Unit`.

> [!TIP]
> Ważne jest, aby przewidzieć przyszłe potrzeby, ale ważne jest również rozwiązywanie konkretnych problemów dla użytkowników.
> W związku z tym, należy w ten sposób zawsze wymagać starannego rozważenia i zrównoważenia, aby uniknąć tworzenia interfejsów API "tylko w przypadku".

**Kluczowa zasada:** wybierz typy danych wejściowych i wyjściowych dla funkcji i operacji, które są przewidywalne, i które komunikują cel możliwy do uzyskania.

- ✅ **używać** typów krotek do logicznego grupowania danych wejściowych i wyjściowych, które są istotne tylko wtedy, gdy są brane pod uwagę. Rozważ użycie w takich przypadkach typu zdefiniowanego przez użytkownika.

  *Pokazują*
  - Funkcja do wyprowadzania lokalnych wartości minimum innej funkcji może wymagać przełączenia interwału wyszukiwania jako danych wejściowych, tak że `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` może być odpowiednią sygnaturą.
  - Operacja szacowania pochodnego klasyfikatora uczenia maszynowego przy użyciu techniki przesunięcia parametrów może wymagać przesunięcia i przesunięcia wektorów parametrów jako danych wejściowych. Dane wejściowe podobne do `(unshifted : Double[], shifted : Double[])` mogą być odpowiednie w tym przypadku.

- ✅ **do** uporządkowania elementów w kolekcjach wejściowych i wyjściowych spójnie w różnych funkcjach i operacjach.

  *Pokazują*
  - Jeśli rozważasz dwa lub funkcje lub operacje, które każda z nich przyjmuje kąt obrotu i docelowy qubit jako dane wejściowe, upewnij się, że są one uporządkowane tak samo w każdej spójnej kolekcji. Oznacza to, że Preferuj `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` i `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` do `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` i `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.

**Kluczowa zasada:** Projektuj funkcje i operacje, aby dobrze współpracować z funkcjami języka Q\#, takimi jak częściowa aplikacja.

- ✅ **do** porządkowania elementów w spójnych kolekcjach, tak aby najczęściej stosowane dane wejściowe były wykonywane jako pierwsze (tj., aby część aplikacji działała podobnie do currying).

  *Pokazują*
  - Operacja `ApplyRotation`, która przyjmuje liczbę zmiennoprzecinkową i qubit, ponieważ dane wejściowe mogą być często stosowane częściowo z danymi wejściowymi zmiennoprzecinkowymi jako pierwsze do użycia z operacjami, które oczekują wejścia typu `Qubit => Unit`. W rezultacie sygnatura `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`
      może być najbardziej spójna z częściową aplikacją.
  - Zwykle te wskazówki oznaczają umieszczenie wszystkich danych klasycznych przed wszystkimi qubits w spójnych krotkach, ale używają dobrych orzeczeń i sprawdzenia, jak interfejs API jest wywoływany w ćwiczeń.

## <a name="user-defined-types"></a>Typy zdefiniowane przez użytkownika

**Kluczowa zasada:** Użyj typów zdefiniowanych przez użytkownika, aby ułatwić tworzenie i Używanie interfejsów API.

- ✅ **wprowadzić** nowe typy zdefiniowane przez użytkownika, aby zapewnić pomocne skróty dla długich i/lub skomplikowanych typów.

  *Pokazują*
  - W przypadkach, gdy typ operacji z trzema danymi wejściowymi tablicy qubit jest często traktowany jako dane wejściowe lub zwracane jako dane wyjściowe, dostarczając typ UDT, taki jak `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`
      może pomóc w zapewnieniu przydatnej skróconej składni.

- ✅ **wprowadzić** nowe typy zdefiniowane przez użytkownika, aby wskazać, że dany typ podstawowy ma być używany tylko w konkretnym sensie.

  *Pokazują*
  - Operacja, która powinna być interpretowana jako operacja, która koduje klasyczne dane w rejestrze Quantum, może być odpowiednia do etykietowania z typem zdefiniowanym przez użytkownika `newtype InputEncoder = (Apply : (Qubit[] => Unit))`.

- ✅ **wprowadzić** nowe typy zdefiniowane przez użytkownika z nazwanymi elementami, które zezwalają na przyszłą rozszerzalność (np.: Struktura wyników, która może zawierać dodatkowe nazwane elementy w przyszłości).

  *Pokazują*
  - Gdy operacja `TrainModel` uwidacznia wiele opcji konfiguracji, narażając te opcje jako nowe `TrainingOptions` UDT i dostarczając nową funkcję, `DefaultTrainingOptions : Unit -> TrainingOptions` umożliwia użytkownikom przesłanianie określonych nazwanych elementów w TrainingOptions wartości UDT przy jednoczesnym umożliwieniu deweloperom biblioteki dodawania nowych elementów UDT odpowiednio do potrzeb.

- ✅ **należy** zadeklarować nazwane elementy dla nowych typów zdefiniowanych przez użytkownika w preferencjach, aby wymagać od użytkowników znajomości poprawnej dekonstrukcji krotki.

  *Pokazują*
  - Gdy reprezentujesz liczbę zespoloną w swojej dekompozycji biegunowej, Preferuj `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` `newtype ComplexPolar = (Double, Double)`.

**Kluczowa zasada:** Użyj typów zdefiniowanych przez użytkownika w taki sposób, aby zmniejszyć obciążenie poznawcze i nie wymagał od użytkownika poznania dodatkowych koncepcji i nomenklatury.

- ⛔️ **nie** należy wprowadzać typów zdefiniowanych przez użytkownika, które wymagają, aby użytkownik mógł często korzystać z operatora rozpakowywania (`!`) lub który często wymaga wielu poziomów rozwinięcia. Możliwe strategie zaradcze obejmują:

  - Podczas uwidaczniania typu zdefiniowanego przez użytkownika za pomocą jednego elementu należy rozważyć zdefiniowanie nazwy dla tego elementu. Rozważmy na przykład `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` w preferencjach, aby `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.

  - Upewnienie się, że inne funkcje i operacje mogą akceptować "opakowane" wystąpienia UDT bezpośrednio.

- ⛔️ **nie** wprowadzaj nowych typów zdefiniowanych przez użytkownika, które duplikują typy wbudowane bez udostępniania dodatkowych wyrazistości.

  *Pokazują*
  - `newtype QubitRegister = Qubit[]` UDT nie zapewnia żadnych dodatkowych wyrazistości na `Qubit[]`i jest trudniejsze do użycia bez korzyści discernable.
  - Typ UDT `newtype LittleEndian = Qubit[]` dokumenty, w jaki sposób ma być używany i interpretowany źródłowy rejestr i w ten sposób zapewnia dodatkowe wyrazistości w porównaniu z jego typem podstawowym.

- ⛔️ **nie** należy wprowadzać funkcji akcesora, chyba że jest to absolutnie wymagane;   silnie Preferuj nazwane elementy w tym przypadku.

  *Pokazują*
  - Podczas wprowadzania `newtype Complex = (Double, Double)`UDT należy zmodyfikować definicję, aby `newtype Complex = (Real : Double, Imag : Double)` do wprowadzenia funkcji `GetReal : Complex -> Double` i `GetImag : Complex -> Double`.

## <a name="namespaces-and-organization"></a>Przestrzenie nazw i organizacja

**Kluczowa zasada:** wybierz nazwy przestrzeni nazw, które są przewidywalne i wyraźnie komunikują przeznaczenie funkcji, operacji i typów zdefiniowanych przez użytkownika w każdej przestrzeni nazw.

- ✅ **nazywaj przestrzenie nazw jako** `Publisher.Product.DomainArea`.

  *Pokazują*
  - Funkcje, operacje i UDTs opublikowane przez firmę Microsoft jako część funkcji symulacji Quantum zestawu Quantum Development Kit są umieszczane w przestrzeni nazw `Microsoft.Quantum.Simulation`.
  - `Microsoft.Quantum.Math` reprezentuje przestrzeń nazw opublikowana przez firmę Microsoft w ramach zestawu Quantum Development Kit odnoszącego się do obszaru domeny matematyki.

- ✅ **operacje** umieszczania, funkcje i typy zdefiniowane przez użytkownika używane do określonych funkcji w przestrzeni nazw, która opisuje tę funkcję, nawet jeśli ta funkcja jest używana w różnych domenach problemów.

  *Pokazują*
  - Interfejsy API przygotowania stanu opublikowane przez firmę Microsoft w ramach zestawu Quantum Development Kit byłyby umieszczane w `Microsoft.Quantum.Preparation`.
  - Interfejsy API symulacji Quantum opublikowane przez firmę Microsoft w ramach zestawu Quantum Development Kit byłyby umieszczane w `Microsoft.Quantum.Simulation`.

- ✅ **operacje** umieszczania, funkcje i typy zdefiniowane przez użytkownika używane tylko w określonych domenach w przestrzeni nazw wskazujące ich domenę narzędzia. W razie potrzeby użyj subnazw, aby wskazać zadania ukierunkowane w obrębie poszczególnych nazw specyficznych dla domeny.

  *Pokazują*
  - Biblioteka Quantum Machine Learning Library opublikowana przez firmę Microsoft jest w dużym stopniu umieszczana w przestrzeni nazw @"microsoft.quantum.machinelearning", ale przykładowe zestawy danych są dostarczane przez @"microsoft.quantum.machinelearning.datasets" przestrzeni nazw.
  - Chemiczne interfejsy API Quantum opublikowane przez firmę Microsoft jako część zestawu Quantum Development Kit należy umieścić w `Microsoft.Quantum.Chemistry`. Funkcja specyficzna dla wdrożenia programu Jordania--Wigner dekompozycji może zostać umieszczona w `Microsoft.Quantum.Chemistry.JordanWigner`, aby interfejs podstawowy dla obszaru domeny chemii Quantum nie był objęty implementacjami.

**Kluczowa zasada:** Używaj przestrzeni nazw i modyfikatorów dostępu, aby zamierzać powierzchnię interfejsu API narażoną na użytkowników i ukrywać szczegóły wewnętrzne związane z implementacją i testowaniem interfejsów API.

- ✅ zawsze, gdy jest **to** uzasadnione, należy umieścić wszystkie funkcje i operacje, które są potrzebne do zaimplementowania interfejsu API w tej samej przestrzeni nazw co zaimplementowany interfejs API, ale oznaczone za pomocą słów kluczowych "Private" lub "internal", aby wskazać, że nie są one częścią publicznej powierzchni interfejsu API biblioteki. Użyj nazwy rozpoczynającej się od znaku podkreślenia (`_`), aby wizualnie odróżnić prywatne i wewnętrzne operacje i funkcje od publicznych.

  *Pokazują*
  - Nazwa operacji `_Features` wskazuje funkcję, która jest prywatna dla danego obszaru nazw i zestawu, i powinna być dołączona za pomocą słowa kluczowego `internal`.

- ✅ w rzadkich przypadkach, że obszerny zestaw funkcji prywatnych lub operacji jest wymagany do zaimplementowania interfejsu API dla danego obszaru nazw, **należy umieścić je** w nowej przestrzeni nazw zgodnej z zaimplementowaną przestrzenią nazw i kończącą się w `.Private`.

- ✅ **DO** przemieścić wszystkie testy jednostkowe do przestrzeni nazw pasujących do przestrzeni nazw w teście i kończąc na `.Tests`.

## <a name="naming-conventions-and-vocabulary"></a>Konwencje nazewnictwa i słownictwo

**Kluczowa zasada:** Wybierz nazwy i terminologię, które są jasne, dostępne i czytelne dla różnorodnych odbiorców, w tym dla początkujących i ekspertów usługi Quantum.

- ⛔️ **nie** używać rozróżniacza ani wykluczania nazw identyfikatorów ani terminologii w komentarzach dokumentacji interfejsu API.

- ✅ **Użyj** komentarzy dokumentacji interfejsu API w celu zapewnienia odpowiednich kontekstu, przykładów i odwołań, szczególnie w przypadku bardziej trudnych koncepcji.

- ⛔️ **nie** Używaj nazw identyfikatorów, które są niekoniecznie Esoteric, lub które wymagają znaczącej wiedzy o algorytmach Quantum do odczytu.

  *Pokazują*
  - Preferuj "iteracja wzmocnienia amplitudy" na "iteracja Grover".

- ✅ **Wybierz** operacje i nazwy funkcji, które wyraźnie komunikują oczekiwany efekt możliwego do przeprowadzenia, a nie jego implementację. Należy pamiętać, że implementacja może i powinna być

  *Pokazują*
  - Preferuj "oszacowanie nakładania się" na "test Hadamard", ponieważ ten drugi komunikuje się, jak dawna jest implementacja.

- ✅ **Używaj** słów w spójny sposób dla wszystkich interfejsów API\# Q:

  - **Słowa**

    - **Potwierdzenie**: należy sprawdzić, czy założono założenie stanu maszyny docelowej i jej qubits, prawdopodobnie przy użyciu zasobów niefizycznych. Operacje korzystające z tego zlecenia powinny zawsze być bezpiecznie usuwalne bez wpływu na funkcjonalność bibliotek i programów wykonywalnych. Należy pamiętać, że w przeciwieństwie do faktów, potwierdzenia mogą generalnie zależeć od stanu zewnętrznego, takiego jak stan rejestru qubit, środowisko wykonawcze lub tak dalej. Ponieważ zależność od stanu zewnętrznego jest rodzajem efektu ubocznego, potwierdzenia muszą być uwidocznione jako operacje, a nie funkcje.

    - **Oszacowanie**: użycie jednego lub większej liczby możliwych do powtórzenia pomiarów, oszacowanie klasycznej ilości wyników pomiarów.

      *Pokazują*
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - **Przygotowywanie**: stosowanie operacji Quantum lub sekwencji operacji do jednego lub większej liczby qubits założono, że wystąpiły w określonym stanie początkowym (zazwyczaj $ \ket{00\cdots 0} $), powodując, że stan tych qubits będzie się rozwijać do żądanego stanu końcowego. Ogólnie rzecz biorąc, działające na Stanach innych niż dany stan początkowy **może** skutkować niezdefiniowaną transformację jednostkową, ale mimo to nadal **należy** zachować operację i jej podległych "anulować" i zastosować wartość No-op.

      *Pokazują*
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - **Miara**: stosowanie operacji Quantum lub sekwencji operacji do co najmniej jednego qubits, odczytywanie klasycznych danych z powrotem.

      *Pokazują*
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - **Zastosuj**: stosowanie operacji Quantum lub sekwencji operacji do jednego lub większej liczby qubits, co powoduje spójny stan tych qubits. To zlecenie jest najbardziej ogólnym zleceniem w nomenklaturze Q\# i **nie powinno być** używane, gdy bardziej szczegółowe zlecenie jest bardziej odpowiednie.

  - **Rzeczowniki**:

    - **Fakt**: warunek logiczny, który zależy tylko od danych wejściowych, a nie na stanie maszyny docelowej, jego środowisku lub stanu qubits maszyny. W przeciwieństwie do potwierdzenia fakt jest tylko wrażliwy na *wartości* podane dla tego faktu. Na przykład:

      *Pokazują*
      - @"microsoft.quantum.diagnostics.equalityfacti": reprezentuje fakt dotyczący dwóch danych wejściowych w postaci równości; liczby całkowite podane jako dane wejściowe są równe siebie lub nie są niezależne od żadnego innego stanu programu.

    - **Opcje:** Typ UDT zawierający kilka nazwanych elementów, które mogą działać jako argumenty opcjonalne do funkcji lub operacji. Na przykład:

      *Pokazują*
      - @"microsoft.quantum.machinelearning.trainingoptions" UDT zawiera nazwane elementy dla stawki szkoleniowej, rozmiar minibatch oraz inne konfigurowalne parametry szkolenia ML.

  - **Przymiotniki**:

    - ⛔️ **New**: **nie należy** używać tego przymiotnika, aby uniknąć pomyłek z użyciem jako czasownika w wielu językach programowania (np.: C++, C#Java, TypeScript, PowerShell).

  - **Położenia pozycyjne:** W niektórych przypadkach, można użyć pozycji, aby bardziej odróżnić lub wyjaśnić role rzeczowników i czasowników w nazwach funkcji i operacji. Należy jednak zachować ostrożność i spójność.

    - **Jako:** Reprezentuje, że dane wejściowe i wyjściowe funkcji reprezentują te same informacje, ale dane wyjściowe przedstawiają te informacje **jako** *X* , a nie oryginalną reprezentację. Jest to szczególnie typowe w przypadku funkcji konwersji typów.

      *Pokazują*
      - `IntAsDouble(2)` wskazuje, że zarówno dane wejściowe (`2`), jak i dane wyjściowe (`2.0`) reprezentują jakościowe te same informacje, ale przy użyciu różnych typów danych Q\#.

    - **Z:** Aby zapewnić spójność, ta pozycja **nie powinna** być używana do wskazania funkcji konwersji typu lub innego przypadku **,** gdzie jest to odpowiednie.

    - ⛔️ **:** **nie należy** używać tego położenia przedniego, aby uniknąć nieporozumień z użyciem jako czasownika w wielu językach programowania.
