---
title: Informacje na temat obliczeń kwantowych
description: Co to są komputery kwantowe i jak korzystają z zasad mechaniki kwantowej?
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
no-loc:
- Q#
- $$v
ms.openlocfilehash: 214fe809aaeba759005fa76ba3615f376d402bc9
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866965"
---
# <a name="understanding-quantum-computing"></a>Informacje na temat obliczeń kwantowych

Dzięki obliczeniom kwantowym można przetwarzać informacje, bazując na zasadach mechaniki kwantowej. Z tego względu wykonywanie obliczeń kwantowych wymaga innego podejścia niż w przypadku obliczeń klasycznych.  Jednym z przykładów obrazujących tę różnicę jest procesor używany do obliczeń kwantowych.  Podczas gdy klasyczne komputery używają znanych mikroukładów opartych na krzemie, komputery kwantowe korzystają z materiałów kwantowych, takich jak atomy, jony, fotony lub elektrony.  

Materiał kwantowy zachowuje się zgodnie z prawami mechaniki kwantowej, w której używa się pojęć, takich jak obliczenia probabilistyczne, superpozycja czy splątanie. Te pojęcia stanowią podstawę algorytmów kwantowych, które wykorzystują moc obliczeń kwantowych do rozwiązywania złożonych problemów. W tym artykule opisano niektóre podstawowe pojęcia mechaniki kwantowej, na której bazują obliczenia kwantowe.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>Mechanika kwantowa z lotu ptaka

Mechanika kwantowa, nazywana także teorią kwantową, to gałąź fizyki, która zajmuje się cząstkami na poziomie atomowym i subatomowym. Jednak na poziomie kwantowym wiele praw mechaniki, które przyjmujemy za pewnik, nie ma zastosowania. Superpozycja, pomiar kwantowy i splątanie to trzy zjawiska, które są kluczowe dla obliczeń kwantowych.  

### <a name="superposition-vs-binary-computing"></a>Superpozycja a obliczenia binarne

Wyobraź sobie, że ćwiczysz u siebie w salonie. Skręcasz ciało maksymalnie w lewą stronę, a później w prawą. A teraz spróbuj jednocześnie skręcić w lewo i w prawo. Nie jest to możliwe (chyba, że się rozdzielisz na co najmniej dwie części).  Oczywiście nie możesz jednocześnie znajdować się w obu tych stanach — nie możesz patrzeć w tym samym czasie w lewo i w prawo.

Jeśli jednak w wyobraźni zmienisz się w cząstkę kwantową, będziesz mieć pewne prawdopodobieństwo, że *patrzysz w lewą stronę* ORAZ pewne prawdopodobieństwo, że *patrzysz w prawą stronę*. Odpowiedzialne jest za to pewne zjawisko o nazwie **superpozycja** (zwane też **koherencją**).

Cząstka kwantowa, taka jak elektron, ma swoje własne właściwości „patrzenia w lewo lub patrzenia w prawo”. Jedną z nich jest na przykład **spin** mający wartości w górę lub w dół, które po przetłumaczeniu na język bardziej zrozumiały w świecie klasycznych obliczeń binarnych odpowiadałyby wartościom 1 i 0. Gdy cząstka kwantowa jest w stanie superpozycji, staje się liniową kombinacją nieskończonej liczby stanów z zakresu od 1 do 0, ale nie wiadomo, w jakim konkretnie jest stanie, dopóki na nią nie spojrzymy. Konsekwencją takiego działania jest występowanie naszego następnego zjawiska — **pomiaru kwantowego**.

### <a name="quantum-measurement"></a>Pomiar kwantowy

Teraz załóżmy, że przychodzi Twój znajomy i chce zrobić Ci zdjęcie, kiedy ćwiczysz. Najprawdopodobniej uzyska rozmazany obraz Twojej osoby skręcającej się w lewo i w prawo.

Ale przyjmując, że jesteś cząstką kwantową, wystąpi tu ciekawe zjawisko. Bez względu na to, w jakiej pozycji będziesz podczas robienia zdjęcia, na fotografii będziesz albo w pozycji maksymalnego wychylenia w lewo, albo w prawo, bez jakichkolwiek pośrednich pozycji.

Dzieje się tak, ponieważ sam akt obserwacji lub pomiaru cząstki kwantowej **redukuje** stan superpozycji (to zjawisko jest również znane pod nazwą **dekoherencji**), a cząstka przyjmuje klasyczny stan binarny 1 lub 0.

Ten stan binarny jest przydatny dla nas, ponieważ podczas obliczeń możemy wykonać wiele działań na wartościach 1 i 0. Jednak po zmierzeniu i kolapsie cząstki kwantowej pozostaje ona w takim stanie na zawsze (jak na zrobionym zdjęciu) i zawsze już będzie równa 1 lub 0. Jak zobaczysz później, w obliczeniach kwantowych istnieją jednak operacje, dzięki którym można „zresetować” taką cząstkę z powrotem do stanu superpozycji, dzięki czemu może ona być ponownie użyta do obliczeń kwantowych.

### <a name="entanglement"></a>Splątanie

Prawdopodobnie najbardziej interesującym zjawiskiem w mechanice kwantowej jest możliwość **splątania** ze sobą dwóch lub większej liczby cząstek kwantowych. Gdy cząstki stają się splątane, tworzą jeden system, w którym nie można opisać stanu kwantowego dowolnej pojedynczej cząstki niezależnie od stanu kwantowego pozostałych cząstek. Oznacza to, że każda operacja lub proces zastosowany do jednej cząstki wywołuje konsekwencje w pozostałych cząstkach.

Oprócz tej współzależności cząstki mogą zachować to połączenie nawet wtedy, gdy są oddzielone od siebie na niezwykle duże odległości mierzone nawet w latach świetlnych. Skutki pomiaru kwantowego mają również zastosowanie do cząstek splątanych. W konsekwencji, jeśli jedna cząstka zostanie zmierzona i zredukowana, pozostałe cząstki również się zredukują. Ponieważ istnieje korelacja między splątanymi kubitami, zmierzenie stanu jednego kubitu pozwala na uzyskanie informacji o stanie innego kubitu — ta właściwość jest bardzo przydatna w przypadku obliczeń kwantowych.

### <a name="qubits-and-probability"></a>Kubity i prawdopodobieństwo

Klasyczne komputery przechowują i przetwarzają informacje w postaci bitów. Każdy bit może mieć wartość 1 lub 0, ale nigdy nie może mieć obu tych wartości jednocześnie. Odpowiednikiem bitu w obliczeniach kwantowych jest **kubit**, który reprezentuje stan cząstek kwantowych. Ze względu na zjawisko superpozycji kubity mogą mieć wartości 1, 0 lub dowolną wartość pośrednią. W zależności od konfiguracji kubit ma pewne *prawdopodobieństwo* kolapsu do wartości 1 lub 0. Prawdopodobieństwo kolapsu kubitu do jednej lub innej wartości jest zdeterminowane przez **interferencję kwantową**. 

Czy pamiętasz swojego znajomego, który robił Ci zdjęcie? Załóżmy, że ma on na aparacie specjalne filtry *interferencyjne*. Jeśli wybierze on filtr *70/30* i zacznie robić zdjęcia, na 70% z nich będziesz patrzeć w lewo, a na 30% z nich — w prawo. Filtr zakłócił zwykły stan aparatu i wpłynął na prawdopodobieństwo jego zachowania.

Podobnie interferencja kwantowa wpływa na stan kubitu i tym samym na prawdopodobieństwo uzyskania pewnego wyniku podczas prowadzenia pomiaru. Ten stan probabilistyczny jest polem do popisu dla obliczeń kwantowych.

Przykładowo jeśli mamy dwa bity w klasycznym komputerze, w każdym bicie możemy przechować wartość 1 lub 0, tak więc w obu tych bitach możemy przechować cztery różne wartości — **00**, **01**, **10** i **11**, ale tylko jedną z nich w danym momencie. Jednak w przypadku dwóch kubitów w superpozycji każdy z nich może mieć wartość 1, 0 lub *obie te wartości*, dzięki czemu można reprezentować te same cztery wartości jednocześnie. Za pomocą trzech kubitów można reprezentować osiem wartości, za pomocą czterech kubitów — 16 wartości itd.

## <a name="summary"></a>Podsumowanie

Te pojęcia ledwie dotykają problematyki mechaniki kwantowej, ale są kluczowe do zrozumienia obliczeń kwantowych.

- **Superpozycja** — zdolność cząsteczek kwantowych do istnienia we wszystkich możliwych stanach.
- **Pomiar kwantowy** — akt obserwacji cząstki kwantowej będącej w superpozycji dający w konsekwencji jeden z możliwych stanów.
- **Splątanie** — zdolność cząstek kwantowych do wzajemnego korelowania wyników pomiarów.
- **Kubit** — podstawowa jednostka informacji używana w obliczeniach kwantowych. Kubit reprezentuje cząstkę kwantową w superpozycji wszystkich możliwych stanów.
- **Interferencja** — wewnętrzne zachowanie kubitu spowodowane superpozycją, wpływające na prawdopodobieństwo jego kolapsu w jedną lub drugą stronę.

## <a name="next-steps"></a>Następne kroki

[Komputery kwantowe i symulatory kwantowe](xref:microsoft.quantum.overview.simulators)
