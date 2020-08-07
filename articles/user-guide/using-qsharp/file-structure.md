---
title: Q#Struktura plików
description: Opisuje strukturę i składnię Q# pliku.
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac73962b1a718cd04aa87ee3476c66781fe3ac2b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867934"
---
# <a name="no-locq-file-structure"></a>Q#Struktura plików

Q#Plik składa się z kolejności *deklaracji przestrzeni nazw*.
Każda deklaracja przestrzeni nazw zawiera deklaracje dla typów, operacji i funkcji zdefiniowanych przez użytkownika, a także może zawierać dowolną liczbę poszczególnych typów deklaracji i w dowolnej kolejności.
Aby uzyskać więcej informacji na temat deklaracji w przestrzeni nazw, zobacz Typy, [operacje](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)i [funkcje](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [zdefiniowane przez użytkownika](xref:microsoft.quantum.guide.types#user-defined-types).

Jedynym tekstem, który może występować poza deklaracją przestrzeni nazw, jest komentarz.
W szczególności Komentarze do dokumentacji dla przestrzeni nazw poprzedzają deklarację. Aby uzyskać więcej informacji, zobacz [Komentarze do dokumentacji](#documentation-comments) w tym artykule. 

## <a name="namespace-declarations"></a>Deklaracje przestrzeni nazw

Q#Plik ma zwykle tylko jedną deklarację przestrzeni nazw, ale może mieć wartość None (i być pusty lub zawierać komentarze) lub może zawierać wiele przestrzeni nazw.
Deklaracje przestrzeni nazw nie mogą być zagnieżdżane.

Można zadeklarować tę samą przestrzeń nazw w wielu Q# plikach, które są kompilowane ze sobą, o ile nie ma deklaracji typu, operacji lub funkcji o tej samej nazwie.
W szczególności nie można zdefiniować tego samego typu w tej samej przestrzeni nazw w wielu plikach, nawet jeśli deklaracje są identyczne.

Deklaracja przestrzeni nazw składa się ze słowa kluczowego `namespace` , po którym następuje nazwa przestrzeni nazw i deklaracji zawartych w przestrzeni nazw ujętej w nawiasy klamrowe `{ }` .
Nazwy przestrzeni nazw są zgodne ze wzorcem .NET sekwencji jednego lub więcej symboli dozwolonych oddzielonych kropkami `.` .
Na przykład `MyQuantumStuff` i `Microsoft.Quantum.Intrinsic` są prawidłowymi nazwami przestrzeni nazw.
Zgodnie z Konwencją wielkie litery symboli w nazwie przestrzeni nazw nie są jednak wymagane.

Odwołania do typów lub wartości, które zostały zgłoszone w dalszej postaci w pliku, są prawidłowo rozwiązywane; nie ma potrzeby składania deklaracji typu, operacji lub funkcji przed odwołaniem do niej.

## <a name="open-directives"></a>Otwarte dyrektywy

W bloku przestrzeni nazw, należy użyć `open` dyrektywy do zaimportowania wszystkich typów i wywoływanych deklaracji zadeklarowanych w określonym obszarze nazw i odwoływania się do nich według ich nazwy niekwalifikowanej.
Taka `open` dyrektywa składa się ze `open` słowa kluczowego, po którym następuje przestrzeń nazw, która ma zostać otwarta i kończąca się średnikiem.

> [!NOTE] 
> Wszystkie `open` dyrektywy muszą występować przed dowolnymi `function` `operation` `newtype` deklaracjami w bloku przestrzeni nazw.

Opcjonalnie można zdefiniować krótką nazwę otwartej przestrzeni nazw. Jeśli zdefiniowano krótką nazwę, należy zakwalifikować wszystkie elementy z tej przestrzeni nazw według zdefiniowanej krótkiej nazwy. Na przykład uwzględniając następującą deklarację przestrzeni nazw i otwarte dyrektywy,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Jeśli zadeklarowana operacja używa operacji `Op` z `Microsoft.Quantum.Intrinsic` , należy wywołać ją po prostu przy użyciu `Op` .
Aby jednak wywołać określoną funkcję `Fn` z `Microsoft.Quantum.Math` , należy wywołać ją przy użyciu polecenia `Math.Fn` .

`open`Dyrektywa ma zastosowanie do całego bloku przestrzeni nazw w pliku.
W związku z tym, jeśli zdefiniujesz dodatkową przestrzeń nazw w tym samym Q# pliku jak `NS` wcześniej, wszystkie operacje/funkcje/typy zdefiniowane w drugim obszarze nazw nie będą miały dostępu do niczego z `Microsoft.Quantum.Intrinsic` lub, `Microsoft.Quantum.Math` chyba że zostaną powtórzone otwarte dyrektywy. 

Aby odwołać się do typu lub możliwego do odłożenia zdefiniowanego w innej przestrzeni nazw, która *nie* jest otwarta w bieżącym obszarze nazw, należy odwołać się do niej przy użyciu w pełni kwalifikowanej nazwy.
Na przykład, dana operacja o nazwie `Op` z `X.Y` przestrzeni nazw:

* Należy odwołać się do niego za pomocą jego w pełni kwalifikowanej nazwy `X.Y.Op` , chyba że `X.Y` przestrzeń nazw została otwarta wcześniej w bieżącym bloku. 
* Nawet jeśli `X` przestrzeń nazw jest otwarta, nie można odwołać się do operacji jako `Y.Op` .
* Jeśli zdefiniowano krótką nazwę `Z` dla `X.Y` w tej przestrzeni nazw i pliku, należy odwołać się do `Op` `Z.Op` . 

Zwykle lepiej jest dołączyć przestrzeń nazw przy użyciu `open` dyrektywy.
Użycie w pełni kwalifikowanej nazwy jest wymagane, jeśli dwie przestrzenie nazw definiują konstrukcje o tej samej nazwie, a bieżące źródło używa konstrukcji z obu tych typów.

Q#obowiązują te same reguły nazewnictwa, jak w przypadku innych języków .NET.
Program Q# nie obsługuje jednak odwołań względnych do przestrzeni nazw.
Na przykład jeśli przestrzeń nazw `a.b` jest otwarta, odwołanie do operacji o nazwie nie `c.d` jest rozpoznawane jako operacja o pełnej nazwie *not* `a.b.c.d` .

## <a name="formatting"></a>Formatowanie

Większość Q# instrukcji i dyrektyw kończy się kończąc średnikiem, `;` .
Instrukcje i deklaracje, takie jak `for` i `operation` kończące się blokiem instrukcji (patrz Poniższa sekcja) nie wymagają kończącego się średnika.
Każdy opis instrukcji wskazuje, czy jest wymagany średnik kończący.

Instrukcje, takie jak wyrażenia, deklaracje i dyrektywy, można rozdzielić między wiele wierszy.
Unikaj umieszczania wielu instrukcji w pojedynczym wierszu.

## <a name="statement-blocks"></a>Bloki instrukcji

Q#instrukcje są pogrupowane w blokach instrukcji, które są zawarte w nawiasach klamrowych `{ }` . Blok instrukcji rozpoczyna się od otwarcia `{` i kończącego się zamykaniem `}` .

Blok instrukcji, który jest leksykalny w innym bloku, jest traktowany jako podblok bloku zawierającego; bloki zawierające i podrzędne są również nazywane blokami zewnętrznymi i wewnętrznymi.

## <a name="comments"></a>Komentarze

Komentarze zaczynają się od dwóch ukośników `//` i są kontynuowane do końca wiersza.
Komentarz może pojawić się w dowolnym miejscu w Q# pliku źródłowym.

## <a name="documentation-comments"></a>Komentarze dokumentacji

Komentarze zaczynające się od trzech ukośników, `///` są traktowane specjalnie przez kompilator, gdy są wyświetlane bezpośrednio przed przestrzenią nazw, operacją, specjalizacją, funkcją lub definicją typu.
W takim przypadku kompilator traktuje je jako dokumentację dla zdefiniowanego typu wywoływanego lub zdefiniowanego przez użytkownika, tak samo jak w przypadku innych języków .NET.

W `///` komentarzach tekst, który ma być wyświetlany jako część dokumentacji interfejsu API, jest sformatowany jako [promocji](https://daringfireball.net/projects/markdown/syntax), z różnymi częściami dokumentacji wskazywanych przez nagłówki o specjalnie określonej nazwie.
W obszarze promocji Użyj `@"<ref target>"` rozszerzenia, aby wykonać operacje między odwołaniami, funkcje i typy zdefiniowane przez użytkownika w programie Q# . Zamień na w `<ref target>` pełni kwalifikowaną nazwę obiektu kodu, do którego istnieje odwołanie.
Różne aparaty dokumentacji mogą również obsługiwać dodatkowe rozszerzenia promocji.

Na przykład:

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

Następujące nazwy są prawidłowe jako nagłówki komentarzy dokumentacji.

- **Podsumowanie**: krótkie podsumowanie zachowania funkcji lub operacji lub celu typu. Pierwszy akapit podsumowania jest używany na potrzeby informacji o aktywowaniu. Powinien być zwykły tekst.
- **Opis**: Opis zachowania funkcji lub operacji lub celu typu. Razem podsumowanie i opis tworzą wygenerowany plik dokumentacji dla funkcji, operacji lub typu.
  Opis obsługuje symbole i równania sformatowane w wierszu.
- **Dane wejściowe**: Opis krotki wejściowej dla operacji lub funkcji.
  Może zawierać dodatkowe podsekcje promocji wskazujące każdy element krotki wejściowej.
- **Dane wyjściowe**: Opis krotki zwracanej przez operację lub funkcję.
- **Parametry typu**: pusta sekcja, która zawiera jedną dodatkową podsekcję dla każdego parametru typu ogólnego.
- **Przykład**: krótki przykład operacji, funkcji lub typu w użyciu.
- **Uwagi**: różne Prose opisujące aspekt operacji, funkcji lub typu.
- **Zobacz również**: Lista w pełni kwalifikowanych nazw wskazujących powiązane funkcje, operacje lub typy zdefiniowane przez użytkownika.
- **Odwołania**: lista odwołań i cytatów dla udokumentowanego elementu.

## <a name="next-steps"></a>Następne kroki

Więcej informacji na temat [operacji i funkcji](xref:microsoft.quantum.guide.operationsfunctions) w programie Q# .