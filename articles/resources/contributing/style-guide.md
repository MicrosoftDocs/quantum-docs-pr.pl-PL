---
title: Q#Przewodnik po stylu Microsoft
description: Poznaj konwencje nazewnictwa, wprowadzania, dokumentacji i formatowania dla Q# programów i bibliotek.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
no-loc:
- Q#
- $$v
ms.openlocfilehash: 27a2ae5ae9d00329fc369268edae24228a9a9d0d
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867593"
---
# <a name="no-locq-style-guide"></a>Q#Styl — Przewodnik #
## <a name="general-conventions"></a>Konwencje ogólne ##

Konwencje sugerowane w tym przewodniku mają na celu ułatwienie Q# odczytywania i zrozumienia programów oraz bibliotek.

## <a name="guidance"></a>Wskazówki

Sugerujemy:

- Nigdy nie należy ignorować Konwencji, chyba że jest to celowe w celu zapewnienia bardziej czytelnego i zrozumiałego kodu dla użytkowników.

## <a name="naming-conventions"></a>Konwencje nazewnictwa ##

W ofercie zestawu Quantum Development Kit dążymy do nazywania funkcji i operacji, które ułatwiają deweloperom Quantum pisanie programów łatwych w odczytaniu i minimalizujących niespodziewane działanie.
Ważną częścią tego jest to, że w przypadku wybrania nazw dla funkcji, operacji i typów firma Microsoft ustala *słownictwo* , którego programiści używają do wyrażania koncepcji Quantum; Dzięki naszym wyborom firma Microsoft może powstrzymywać i utrudniać ich wysiłki w celu wyraźnego komunikowania się.
Dzięki temu firma Microsoft musi upewnić się, że wprowadzone nazwy oferują przejrzystość, a nie przesłania.
W tej sekcji szczegółowo opisano sposób, w jaki firma Microsoft spełnia ten obowiązek w zakresie jawnych wskazówek, które ułatwiają nam optymalne działanie Q# społeczności deweloperów.

### <a name="operations-and-functions"></a>Operacje i funkcje ###

Jedną z najważniejszych rzeczy, które powinien określić nazwa, jest to, czy dany symbol reprezentuje funkcję czy operację.
Różnica między funkcjami i operacjami ma kluczowe znaczenie dla zrozumienie, jak działa blok kodu.
Aby komunikować się z rozróżnieniem między funkcjami i operacjami użytkowników, korzystamy z tych Q# modeli operacji Quantum przy użyciu efektów ubocznych.
Oznacza to, że operacja *wykonuje* coś.

Z kolei funkcje opisują relacje matematyczne między danymi.
Wyrażenie `Sin(PI() / 2.0)` *jest* `1.0` i oznacza brak informacji o stanie programu lub jego qubits.

Podsumowywanie, operacje wykonywane w trakcie wykonywania funkcji.
Takie rozróżnienie sugeruje, że nazwy operacji są nazywane czasownikami i funkcjami jako rzeczownikami.

> [!NOTE]
> Po zadeklarowaniu typu zdefiniowanego przez użytkownika, Nowa funkcja, która konstruuje wystąpienia tego typu jest niejawnie zdefiniowana w tym samym czasie.
> W tej perspektywie typy zdefiniowane przez użytkownika powinny być nazwane jako rzeczowniki, tak aby oba typy i funkcje konstruktora miały spójne nazwy.

W odpowiednim przypadku upewnij się, że nazwy operacji zaczynają się od czasowników jasno wskazujących wpływ operacji.
Na przykład:

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

Jeden przypadek, który zachowuje szczególną wzmiankę, jest, gdy operacja wykonuje inną operację jako dane wejściowe i wywołuje ją.
W takich przypadkach Akcja podejmowana przez operację wejściową nie jest wyczyszczona, gdy została zdefiniowana operacja zewnętrzna, w taki sposób, że właściwe zlecenie nie jest natychmiast czyszczone.
Zalecamy zlecenie `Apply` , jak w `ApplyIf` , `ApplyToEach` i `ApplyToFirst` .
Inne zlecenia mogą być również przydatne w tym przypadku, jak w `IterateThroughCartesianPower` .

| Czasownik | Oczekiwany efekt |
| ---- | ------ |
| Zastosuj | Operacja podana jako dane wejściowe jest wywoływana |
| Assert | Hipoteza dotycząca wyniku możliwego pomiaru Quantum jest sprawdzana przez symulator |
| Szacowanie | Wartość jest zwracana, reprezentująca oszacowanie pobrane z co najmniej jednego pomiaru |
| Measure | Pomiar Quantum jest wykonywany, a jego wynik jest zwracany do użytkownika |
| Przygotowywanie | Dana Rejestracja qubits jest inicjowana w określonym stanie |
| Przykład | Wartość klasyczna jest zwracana losowo z pewnej dystrybucji |

W przypadku funkcji sugerujemy unikanie korzystania z czasowników na rzecz typowych rzeczowników (Zobacz wskazówki dotyczące odpowiednich rzeczowników poniżej) lub przymiotników:

- `ConstantArray`
- `Head`
- `LookupFunction`

W szczególności we wszystkich przypadkach sugerujemy użycie Past participles, gdzie jest to konieczne, aby wskazać, że nazwa funkcji jest silnie połączona z akcją lub efektem ubocznym w innym miejscu w programie Quantum.
Na przykład `ControlledOnInt` używa części Participle form czasownika "Control", aby wskazać, że funkcja działa jako przymiotnik, aby zmodyfikować jego argument.
Ta nazwa ma dodatkową korzyść do dopasowania semantyki wbudowanych `Controlled` Funktor, zgodnie z poniższym opisem poniżej.
Podobnie _rzeczowniki agentów_ mogą służyć do konstruowania nazw funkcji i UDT z nazw operacji, tak jak w przypadku nazwy `Encoder` typu UDT, która jest silnie skojarzona z `Encode` .

# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Użyj czasowników dla nazw operacji.
- Używaj rzeczowników lub przymiotników dla nazw funkcji.
- Używaj rzeczowników dla typów i atrybutów zdefiniowanych przez użytkownika.
- Dla wszystkich nazwanych nazw można użyć `CamelCase` w silnym preferencjzie do `pascalCase` , `snake_case` , lub `ANGRY_CASE` . W szczególności upewnij się, że nazwy, które można wywołać, zaczynają się wielką literą.
- Dla wszystkich zmiennych lokalnych Użyj `pascalCase` w silnym preferencjzie do `CamelCase` , `snake_case` lub `ANGRY_CASE` . W szczególności upewnij się, że zmienne lokalne zaczynają się od małych liter.
- Unikaj używania podkreśleń `_` w nazwach funkcji i operacji. Jeśli potrzebujesz dodatkowych poziomów hierarchii, użyj przestrzeni nazw i aliasów przestrzeni nazw.

# <a name="examples"></a>[Przykłady](#tab/examples)

|   | Nazwa | Opis |
|---|------|-------------|
| ☑ | `operation ReflectAboutStart` | Wyczyść użycie czasownika ("odbicie"), aby wskazać efekt operacji. |
| ☒ | <s>`operation XRotation`</s> | Użycie funkcji z sugestią typu rzeczownik zamiast operacji. |
| ☒ | <s>`operation search_oracle`</s> | Użycie `snake_case` Q# notacji contravenes. |
| ☒ | <s>`operation Search_Oracle`</s> | Użycie podkreśleń wewnętrznych dla nazwy operacji Q# notacji contravenes. |
| ☑ | `function StatePreparationOracle` | Użycie frazy rzeczownik sugeruje, że funkcja zwraca operację. |
| ☑ | `function EqualityFact` | Wyczyść użycie rzeczownika ("fakt"), aby wskazać, że jest to funkcja, natomiast przymiotnik. |
| ☒ | <s>`function GetRotationAngles`</s> | Użycie czasownika ("Get") sugeruje, że jest to operacja. |
| ☑ | `newtype GeneratorTerm` | Użycie frazy rzeczownik jasno odwołuje się do wyniku wywołania konstruktora UDT. |
| ☒ | <s>`@Attribute() newtype RunOnce()`</s> | Użycie wyrażenia orzeczenia sugeruje, że Konstruktor UDT jest operacją. |
| ☑ | `@Attribute() newtype Deprecated(Reason : String)` | Użycie frazy rzeczownik komunikuje się z użyciem atrybutu. |

***

### <a name="entry-points"></a>Punkty wejścia

Podczas definiowania punktu wejścia do Q# programu Q# kompilator rozpoznaje [ `@EntryPoint()` atrybut](xref:microsoft.quantum.core.entrypoint) , a nie wymaga, aby punkty wejścia miały określoną nazwę (np.: `main` , `Main` lub `__main__` ).
Oznacza to, że w perspektywie Q# dewelopera punkty wejścia to zwykłe operacje opatrzone adnotacją `@EntryPoint()` .
Ponadto Q# punkty wejścia mogą być punktami wejścia dla całej aplikacji (tj. w Q# autonomicznych plikach wykonywalnych) lub mogą być interfejsem między Q# programem i programem hosta dla aplikacji (tj. w przypadku korzystania Q# z języka Python lub .NET), w taki sposób, że nazwa "główna" może być myląca w przypadku zastosowania do Q# punktu wejścia.

Sugerujemy używanie punktów wejścia nazw w celu odzwierciedlenia użycia `@EntryPoint()` atrybutu przy użyciu ogólnej porady dotyczącej nazw operacji wymienionych powyżej.


# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Nie należy nazywać operacji punktu wejścia jako "Main".
- Wprowadzanie nazw operacji punktu wejścia jako zwykłych operacji.

# <a name="examples"></a>[Przykłady](#tab/examples)

|   | Nazwa | Opis |
|---|------|-------------|
| ☑ | `@EntryPoint() operation RunSimulation` | Jasno komunikuje przeznaczenie punktu wejścia przez nazwę operacji. |
| ☒ | <s>`@EntryPoint() operation Main`</s> | Użycie `Main` nie jest jasno przekazane do celów punktu wejścia i jest nadmiarowe z `@EntryPoint()` atrybutem. |

***

### <a name="shorthand-and-abbreviations"></a>Skróty i skróty ###

Powyższe porady nie poprzednia, istnieje wiele form skróconych, które widzą typowe i powszechne użycie w ramach przetwarzania Quantum.
Sugerujemy używanie istniejących i wspólnych skrótów, gdzie istnieje, szczególnie w przypadku operacji, które są wewnętrzne dla działania maszyny docelowej.
Na przykład wybieramy nazwę `X` zamiast `ApplyX` , a `Rz` nie `RotateAboutZ` .
W przypadku korzystania z takich skrótów skróty nazw operacji powinny mieć wielkie litery (np.: `MAJ` ).

W przypadku stosowania niniejszej Konwencji w przypadku powszechnie używanych akronimów i initialisms takich jak "QFT" dla "transformacji Fouriera Quantum" wymagane jest pewne uwagi.
Sugerujemy następujące ogólne konwencje platformy .NET na potrzeby używania akronimów i initialisms w pełnych nazwach, które określają, że:

- Dwuliterowe akronimy i initialisms są nazwane wielkimi literami (np.: `BE` dla "Big-Endian"),
- wszystkie dłuższe akronimy i initialisms są nazywane w `CamelCase` (np.: `Qft` dla "Quantum Fouriera Transform")

W ten sposób operacja implementująca QFT może zostać wywołana `QFT` jako skrót lub zapisywana jako `ApplyQft` .

Dla szczególnie często używanych operacji i funkcji może być pożądane podanie nazwy skróconej jako _aliasu_ dla dłuższej postaci:

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- W razie potrzeby Rozważ często akceptowane i powszechnie używane nazwy skrócone.
- Używaj wielkich liter dla skróconej składni.
- Używaj wielkich liter dla krótkich (dwuliterowych) akronimów i initialisms.
- Użyj `CamelCase` do dłuższej (trzy lub więcej liter) akronimów i initialisms.

# <a name="examples"></a>[Przykłady](#tab/examples)

|   | Nazwa | Opis |
|---|------|-------------|
| ☑ | `X` | Dobrze zrozumiały skrót dla "Zastosuj transformację $X $" |
| ☑ | `CNOT` | Dobrze zrozumiałe skróty dla "kontrolowane-nie" |
| ☒ | <s>`Cnot`</s> | Skrót nie powinien znajdować się w `CamelCase` . |
| ☑ | `ApplyQft` | Wspólna początkowa wartość "QFT" jest wyświetlana jako część nazwy długiej. |
| ☑ | `QFT` | Wspólna początkowa wartość "QFT" jest wyświetlana jako część nazwy skróconej. |



***


### <a name="proper-nouns-in-names"></a>Poprawne rzeczowniki w nazwach ###

W czasie, gdy chodzi o to, często należy nazywać się tą osobą po pierwszej stronie, aby opublikować na ich temat, a większość z nich nie jest znana.
Użycie zbyt dużej liczby konwencji nazewnictwa z fizyką może w ten sposób stanowić znaczną barierę do wejścia, ponieważ użytkownicy z innych teł muszą poznać dużą liczbę nieprzezroczystych nazw, aby używać typowych operacji i koncepcji.
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
Z tego względu zalecamy, aby w miarę rozsądnych, wspólnych rzeczowników, które opisują koncepcję, zostały przyjęte w silnym preferencjzie dla właściwych rzeczowników opisujących historię publikacji koncepcji.
Na przykład, pojedynczo kontrolowane operacje SWAP i podwójnie kontrolowane nie są często nazywane operacjami "Fredkin" i "Toffoli" w literaturze akademickiej, ale są one identyfikowane Q# głównie jako `CSWAP` i `CCNOT` .
W obu przypadkach komentarze dokumentacji interfejsu API zawierają nazwy synonimów na podstawie odpowiednich rzeczowników wraz ze wszystkimi odpowiednimi cytatami.

Ta preferencja jest szczególnie ważna w przypadku, gdy pewne użycie właściwych rzeczowników będzie zawsze konieczne — zgodnie Q# z tradycją dla wielu języków klasycznych, na przykład, i odwołuje się do `Bool` typów w odniesieniu do logiki logicznej, która jest z kolei przyznana jako "George bool".
Kilka koncepcji Quantum podobnie nazywa się w podobny sposób, łącznie z `Pauli` typem wbudowanym do Q# języka.
Minimalizując użycie właściwych rzeczowników, w których takie użycie nie jest niezbędne, zmniejszamy wpływ na to, gdzie nie można rozsądnie uniknąć odpowiednich rzeczowników.

# <a name="guidance"></a>[Wskazówki](#tab/guidance) 

Sugerujemy:

- Unikaj używania właściwych rzeczowników w nazwach.

# <a name="examples"></a>[Przykłady](#tab/examples)

***

### <a name="type-conversions"></a>Konwersje typu ###

Ponieważ Q# jest silnie i statycznie wpisanym językiem, wartość jednego typu może być używana tylko jako wartość innego typu za pomocą jawnego wywołania funkcji konwersji typu.
Jest to w przeciwieństwie do języków, które umożliwiają niejawną zmianę typów wartości (np.: Promocja typu) lub poprzez rzutowanie.
W związku z tym funkcje konwersji typów odgrywają ważną rolę w Q# tworzeniu biblioteki i składają się z jednej z najczęściej wykrytych decyzji dotyczących nazewnictwa.
Pamiętaj jednak, że ponieważ konwersje typów są zawsze _deterministyczne_, można je napisać jako funkcje i w związku z tym powyższym.
W szczególności sugerujemy, aby funkcje konwersji typów nigdy nie były nazwane jako czasowniki (np.: `ConvertToX` ) lub parametrów przedpozycyjnych fraz ( `ToX` ), ale powinny być nazwane jako niezależne wyrażenia przymiotników, które wskazują typy źródłowe i docelowe ( `XAsY` ).
Podczas wyświetlania listy typów tablicowych w nazwach funkcji konwersji typów zaleca się użycie skrótu `Arr` .
Z zablokowaniem wyjątkowej sytuacji zalecamy, aby wszystkie funkcje konwersji typów były nazwane przy użyciu, `As` Aby można je było szybko zidentyfikować.

# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Jeśli funkcja konwertuje wartość typu `X` na wartość typu `Y` , należy użyć nazwy `AsY` lub `XAsY` .

# <a name="examples"></a>[Przykłady](#tab/examples)

|   | Nazwa | Opis |
|---|------|-------------|
| ☒ | <s>`ToDouble`</s> | Pozycja "do" powoduje wyrażenie orzeczenia, wskazujące operację, a nie funkcję. |
| ☒ | <s>`AsDouble`</s> | Typ danych wejściowych nie jest wyczyszczony z nazwy funkcji. |
| ☒ | <s>`PauliArrFromBoolArr`</s> | Typy wejściowe i wyjściowe są wyświetlane w niewłaściwej kolejności. |
| ☑ | `ResultArrAsBoolArr` | Typy wejściowe i typy wyjściowe są jasne. |

***

### <a name="private-or-internal-names"></a>Nazwy prywatne lub wewnętrzne ###

W wielu przypadkach nazwa jest przeznaczona wyłącznie do użytku wewnętrznego dla biblioteki lub projektu i nie jest zagwarantowanam elementem interfejsu API oferowanym przez bibliotekę.
Warto jasno wskazać, że jest to przypadek w przypadku nazywania funkcji i operacji, tak aby przypadkowe zależności w kodzie wewnętrznym były oczywiste.
Jeśli operacja lub funkcja nie jest przeznaczona do użytku bezpośredniego, ale powinna być używana przez pasujące zadanie, które działa przez częściową aplikację, rozważ użycie nazwy rozpoczynającej się od `internal` słowa kluczowego dla możliwego do odtworzenia.

# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Gdy funkcja, operacja lub typ zdefiniowany przez użytkownika nie jest częścią publicznego interfejsu API dla Q# biblioteki lub programu, upewnij się, że jest oznaczona jako wewnętrzna poprzez umieszczenie `internal` słowa kluczowego przed `function` `operation` `newtype` deklaracją, lub.

# <a name="examples"></a>[Przykłady](#tab/examples)

|   | Nazwa | Opis |
|---|------|-------------|
| ☒ | <s>`operation _ApplyDecomposedOperation`</s> | Nie używaj znaku podkreślenia `_` , aby wskazać, że ta operacja jest tylko do użytku wewnętrznego. |
| ☑ | `internal operation ApplyDecomposedOperation` | `internal`Słowo kluczowe na początku jasno wskazuje, że ta operacja jest tylko do użytku wewnętrznego. |

***
### <a name="variants"></a>elementy Variant ###

Mimo że to ograniczenie może nie pogorszyć w przyszłych wersjach programu, jest to gotowe do użycia w Q# przypadku często grup powiązanych operacji lub funkcji, które są rozróżniane przez funktory ich obsługę danych wejściowych lub konkretne typy argumentów.
Te grupy można rozróżnić przy użyciu tej samej nazwy głównej, po której następuje jedna lub dwie litery wskazujące jej wariant.

| Przedrostk | Znaczenie |
|--------|---------|
| `A` | Oczekiwano danych wejściowych do obsługi`Adjoint` |
| `C` | Oczekiwano danych wejściowych do obsługi`Controlled` |
| `CA` | Oczekiwano danych wejściowych do obsługi `Controlled` i`Adjoint` |
| `I` | Dane wejściowe lub wejścia są typu`Int` |
| `D` | Dane wejściowe lub wejścia są typu`Double` |
| `L` | Dane wejściowe lub wejścia są typu`BigInt` |

# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Jeśli funkcja lub operacja nie jest powiązana z żadną podobną funkcją lub operacji według typów i obsługi danych wejściowych Funktor, nie należy używać sufiksu.
- Jeśli funkcja lub operacja jest powiązana z innymi podobnymi funkcjami lub operacjami przez typy i obsługę Funktor ich danych wejściowych, użyj sufiksów jak w powyższej tabeli, aby rozróżnić warianty.

# <a name="examples"></a>[Przykłady](#tab/examples)

***

### <a name="arguments-and-variables"></a>Argumenty i zmienne ###

Kluczowy cel Q# kodu dla funkcji lub operacji jest przeznaczony do łatwego odczytywania i interpretowania.
Podobnie nazwy danych wejściowych i argumentów typu powinny komunikować się, w jaki sposób funkcja lub argument będą używane po podaniu.


# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Dla wszystkich nazw zmiennych i wejściowych Użyj `pascalCase` w silnym preferencjzie do `CamelCase` , `snake_case` lub `ANGRY_CASE` .
- Nazwy wejściowe powinny być opisowe; należy unikać jednej lub dwóch nazw liter, jeśli jest to możliwe.
- Operacje i funkcje akceptujące dokładnie jeden argument typu powinny wskazywać ten argument typu przez, `T` gdy jego rola jest oczywista.
- Jeśli funkcja lub operacja przyjmuje wiele argumentów typu lub Jeśli rola pojedynczego typu argumentu nie jest oczywista, należy rozważyć użycie krótkiego wyrazu z prefiksem `T` (np.: `TOutput` ) dla każdego typu.
- Nie dołączaj nazw typów w nazwach argumentów i zmiennych; te informacje mogą być udostępniane przez środowisko deweloperskie.
- Należy zauważyć typy skalarne według ich nazw literałów ( `flagQubit` ) i typów tablicowych w liczbie mnogiej ( `measResults` ).
  W szczególności dla tablic qubits należy rozważyć określenie takich typów, `Register` gdzie nazwa odwołuje się do sekwencji qubits, które są ściśle powiązane w jakiś sposób.
- Zmienne używane jako indeksy w tablicach powinny zaczynać się od `idx` i powinny być pojedyncze (np.: `things[idxThing]` ).
  W szczególności zdecydowanie Unikaj używania nazw zmiennych o pojedynczej literze jako indeksów; Rozważ użycie `idx` co najmniej.
- Zmienne używane do przechowywania długości tablic powinny zaczynać się od `n` i powinny być w liczbie mnogiej (np.: `nThings` ).

# <a name="examples"></a>[Przykłady](#tab/examples)

***

### <a name="user-defined-type-named-items"></a>Typ zdefiniowany przez użytkownika o nazwie Items ###

Nazwane elementy w typach zdefiniowanych przez użytkownika powinny być nazwane jako `CamelCase` , nawet w danych wejściowych dla konstruktorów UDT.
Ułatwia to łatwe oddzielenie nazwanych elementów od odwołań do zmiennych w zakresie lokalnie podczas korzystania z notacji metody dostępu (np.: `callable::Apply` ) lub notacji kopiowania i aktualizacji ( `set arr w/= Data <- newData` ).

# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Nazwane elementy w konstruktorach UDT powinny mieć nazwę `CamelCase` ; oznacza to, że powinny rozpoczynać się od początkowej wielkiej litery.
- Nazwane elementy, które są rozpoznawane jako operacje, powinny być nazwane jako etapy zleceń.
- Nazwane elementy, które nie są rozpoznawane do operacji, powinny być nazwane jako frazy rzeczowników.
- Dla UDTs, które zawijają operacje, należy zdefiniować pojedynczy nazwany element o nazwie `Apply` .

# <a name="examples"></a>[Przykłady](#tab/examples)

|   | Fragment kodu | Opis |
|---|---------|-------------|
| ☑ | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | Nazwa `Apply` jest `CamelCase` podsformatowaną frazą czasownikową, sugerując, że nazwany element jest operacją. |
| ☒ | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | Nazwane elementy powinny rozpoczynać się od początkowej wielkiej litery. |
| ☒ | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | Nazwane elementy, które rozwiązują funkcje, powinny być nazwane jako frazy rzeczownikowe, a nie jako wyrażenia czasownikowe. |

***

## <a name="input-conventions"></a>Konwencje wejściowe ##

Gdy deweloper wywołuje operację lub funkcję, różne dane wejściowe do tej operacji lub funkcji muszą być określone w określonej kolejności, zwiększając obciążenie poznawcze, które są używane przez twarzy dla deweloperów.
W szczególności zadanie zapamiętywania kolejności danych wejściowych jest często rozpraszane z zadania: Programowanie implementacji algorytmu Quantum.
Chociaż rozbudowana obsługa środowiska IDE może w dużym stopniu ograniczyć, dobry projekt i przestrzeganie wspólnych Konwencji może również pomóc w zminimalizowaniu obciążenia poznawczego narzuconego przez interfejs API.

Tam, gdzie to możliwe, może być pomocne zmniejszenie liczby wejść oczekiwanych przez operację lub funkcję, dzięki czemu rola każdego danych wejściowych jest bardziej oczywista bezpośrednio dla deweloperów wywołujących tę operację lub funkcję, a także do deweloperów odczytujących ten kod później.
Szczególnie gdy nie jest możliwe lub uzasadnione zmniejszanie liczby argumentów do operacji lub funkcji, ważne jest, aby mieć spójne porządkowanie, które minimalizuje nieoczekiwane działanie użytkownika podczas przewidywania kolejności danych wejściowych.

Zalecamy konwencje określania danych wejściowych, które w znacznym stopniu wynikają z działania częściowej aplikacji jako generalizacji currying f (x, y) ≡ f (x) (y).
W związku z tym, częściowe stosowanie pierwszych argumentów powinno skutkować wywoływaniem, który jest przydatny we własnym imieniu, gdy jest to uzasadnione.
Zgodnie z tą zasadą należy rozważyć użycie następującej kolejności argumentów:

- Klasyczne argumenty, które nie można wywołać, takie jak kąty, wektory uprawnień itp.
- Wywoływane argumenty (funkcje i argumenty).
  Jeśli obie funkcje i operacje są traktowane jako argumenty, Rozważ umieszczenie operacji po funkcjach.
- Kolekcje działały na podstawie wywoływanych argumentów w podobny sposób do `Map` ,, `Iter` `Enumerate` i `Fold` .
- Argumenty qubit używane jako formanty.
- Argumenty qubit używane jako elementy docelowe.

Rozważmy operację `ApplyPhaseEstimationIteration` do użycia w ocenie fazy, która przyjmuje kąt i Oracle, przekazuje kąt do `Rz` modyfikacji przez tablicę różnych czynników skalowania, a następnie kontroluje aplikacje firmy Oracle.
Dane wejściowe można zamówić `ApplyPhaseEstimationIteration` w następujący sposób:

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
W specjalnym przypadku minimalizowania niespodziewania niektóre funkcje i operacje naśladowania zachowania wbudowanej funktory `Adjoint` i `Controlled` .
Na przykład `ControlledOnInt<'T>` ma typ `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` , który `ControlledOnInt<Qubit[]>(5, _)` działa podobnie jak `Controlled` Funktor, ale na stanie, w którym Rejestr sterowania reprezentuje stan $ \ket {5} = \ket {101} $.
W ten sposób deweloper oczekuje, że dane wejściowe, które mają zostać `ControlledOnInt` przekształcone w dół, są ostatnio i że wynikowa operacja przyjmuje jako wartość wejściową `(Qubit[], 'T)` ---tej samej kolejności, a następnie dane wyjściowe `Controlled` Funktor.

# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Użyj kolejności danych wejściowych spójnej z użyciem częściowej aplikacji.
- Użyj kolejności danych wejściowych spójnych z wbudowanym funktory.
- Umieść wszystkie klasyczne dane wejściowe przed wszelkimi danymi wejściowymi Quantum.

# <a name="examples"></a>[Przykłady](#tab/examples)

***

## <a name="documentation-conventions"></a>Konwencje dokumentacji ##

Q#Język umożliwia dołączanie dokumentacji do operacji, funkcji i typów zdefiniowanych przez użytkownika za pomocą specjalnie sformatowanych komentarzy do dokumentacji.
Oznacza to `///` , że komentarze w dokumentacji to małe ukośniki (), które mogą [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) być używane do opisywania przeznaczenia każdej operacji, funkcji i typu zdefiniowanego przez użytkownika, jakie dane muszą oczekiwać i tak dalej.
Kompilator dostarczany z zestawem SDK Quantum wyodrębnia te komentarze i korzysta z nich, aby pomóc w poziomego złożenia dokumentacji podobnej do tej https://docs.microsoft.com/quantum .
Podobnie serwer językowy dostarczony z zestawem Quantum Development Kit używa tych komentarzy, aby zapewnić użytkownikom Pomoc po umieszczeniu wskaźnika myszy na symbolach w Q# kodzie.
Korzystanie z komentarzy do dokumentacji może ułatwić użytkownikom zrozumienie kodu przez udostępnienie przydatnego odwołania do szczegółów, które nie są łatwo wyrażone przy użyciu innych konwencji zawartych w tym dokumencie.

> [!div class="nextstepaction"]
> [Odwołanie do składni komentarza do dokumentacji](xref:microsoft.quantum.guide.filestructure#documentation-comments).

Aby efektywnie korzystać z tej funkcji w celu ułatwienia użytkownikom, zalecamy zachowywanie kilku rzeczy podczas pisania komentarzy do dokumentacji.

# <a name="guidance"></a>[Wskazówki](#tab/guidance)

Sugerujemy:

- Każda funkcja publiczna, operacja i typ zdefiniowany przez użytkownika powinny być bezpośrednio poprzedzone komentarzem do dokumentacji.
- Co najmniej każdy komentarz dokumentacji powinien zawierać następujące sekcje:
    - Podsumowanie
    - Dane wejściowe
    - Dane wyjściowe (jeśli dotyczy)
- Upewnij się, że wszystkie podsumowania są dwa zdania lub mniej. Jeśli potrzebujesz więcej miejsca, podaj `# Description` sekcję bezpośrednio po `# Summary` zakończeniu szczegółowego.
- W odpowiednich przypadkach nie należy uwzględniać obliczeń matematycznych, ponieważ nie wszyscy klienci obsługują notację TeX w podsumowaniu. Należy pamiętać, że podczas pisania dokumentów Prose (np. TeX lub promocji) może być zalecane użycie dłuższych długości wierszy.
- Podaj wszystkie odpowiednie wyrażenia matematyczne w `# Description` sekcji.
- Podczas opisywania danych wejściowych nie należy powtarzać typów poszczególnych danych wejściowych, ponieważ mogą one zostać wywnioskowane przez kompilator i ryzyko wprowadzające niespójność.
- Podaj odpowiednie przykłady, z których każda znajduje się w osobnej `# Example` sekcji.
- Zwięźle opisz każdy przykład przed listą kodów.
- Pocite wszystkie odpowiednie Publikacje akademickie (np.: dokumenty, postępowania, wpisy w blogu i alternatywne implementacje) w `# References` sekcji jako lista punktowana łączy.
- Upewnij się, że w miarę możliwości wszystkie linki cytatu mają stałe i niezmienne identyfikatory (DOIs lub z wersjami arXiv).
- Gdy operacja lub funkcja jest powiązana z innymi operacjami lub funkcjami według wariantów Funktor, wystaw inne warianty jako punktory w `# See Also` sekcji.
- Pozostaw pustą linię komentarza między sekcjami poziom-1 ( `/// #` ), ale nie pozostawiaj pustego wiersza między sekcjami poziom-2 ( `/// ##` ).

# <a name="examples"></a>[Przykłady](#tab/examples)

#### <a name=""></a>☑ ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a>Konwencje formatowania ##

Oprócz powyższych sugestii pomocne może być wprowadzenie kodu jako czytelnego do używania spójnych reguł formatowania.
Takie reguły formatowania według natury mają być nieco dowolne i silnie do osobistych estetycznych.
Niemniej zalecamy utrzymywanie spójnego zestawu Konwencji formatowania w grupie współpracowników i szczególnie w przypadku dużych Q# projektów, takich jak zestaw Quantum Development Kit.
Te reguły mogą być automatycznie stosowane przy użyciu narzędzia formatowania zintegrowanego z Q# kompilatorem.

# <a name="guidance"></a>[Wskazówki](#tab/guidance) 

Sugerujemy:

- Używaj czterech spacji zamiast kart do przenoszenia.
  Na przykład w VS Code:
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- Zawijanie wierszy o 79 znaków, gdy jest to uzasadnione.
- Używaj spacji wokół operatorów binarnych.
- Używaj spacji po obu stronach dwukropków używanych do adnotacji typu.
- Użyj pojedynczej spacji po przecinkach używanych w literałach tablicowych i krotek (np. w danych wejściowych do funkcji i operacji).
- Nie używaj spacji po funkcjach, operacjach lub nazwach UDT ani po `@` deklaracjach atrybutów.
- Każda deklaracja atrybutu powinna znajdować się w osobnym wierszu.

# <a name="examples"></a>[Przykłady](#tab/examples)

|   | Fragment kodu | Opis |
|---|---------|-------------|
| ☒ | <s>`2+3`</s> | Używaj spacji wokół operatorów binarnych. |
| ☒ | <s>`target:Qubit`</s> | Używaj spacji wokół dwukropka adnotacji typu. |
| ☑ | `Example(a, b, c)` | Elementy w spójnej kolekcji są poprawnie wprowadzane do czytelności. |
| ☒ | <s>`Example (a, b, c)`</s> | Spacje powinny być pomijane po nazwach funkcji, operacji lub UDT. |

***
