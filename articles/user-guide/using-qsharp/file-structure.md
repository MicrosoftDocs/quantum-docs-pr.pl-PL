---
title: 'Struktura pliku Q #'
description: 'Opisuje strukturę i składnię pliku Q #.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327462"
---
# <a name="q-file-structure"></a>Struktura pliku Q #

Każda operacja Q #, funkcja i typ zdefiniowany przez użytkownika są zdefiniowane w przestrzeni nazw.

Plik Q # składa się z sekwencji *nazw deklaracji*.
Każda deklaracja przestrzeni nazw zawiera deklaracje dla typów, operacji i funkcji zdefiniowanych przez użytkownika.
Deklaracja przestrzeni nazw może zawierać dowolną liczbę typów deklaracji i w dowolnej kolejności.
Skorzystaj z poniższych linków, aby uzyskać więcej informacji na temat deklarowania typów, [operacji](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)i [funkcji](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) [zdefiniowanych przez użytkownika](xref:microsoft.quantum.guide.types#user-defined-types)w przestrzeni nazw.

Jedynym tekstem, który może występować poza deklaracją przestrzeni nazw, jest komentarz.
W szczególności Komentarze do dokumentacji (więcej szczegółów poniżej) dla przestrzeni nazw poprzedzają deklarację.

## <a name="namespace-declarations"></a>Deklaracje przestrzeni nazw

Plik Q # zazwyczaj ma dokładnie jedną deklarację przestrzeni nazw, ale może mieć wartość None (i być pusty lub zawierać komentarze) lub może zawierać wiele przestrzeni nazw.
Deklaracje przestrzeni nazw nie mogą być zagnieżdżane.

Ta sama przestrzeń nazw może być zadeklarowana w wielu plikach Q #, które są kompilowane razem, o ile nie istnieją deklaracje typu, operacji lub funkcji o tej samej nazwie.
W szczególności nie można zdefiniować tego samego typu w tej samej przestrzeni nazw w wielu plikach, nawet jeśli deklaracje są identyczne.

Deklaracja przestrzeni nazw składa się ze słowa kluczowego `namespace` , po którym następuje nazwa przestrzeni nazw, otwierającego nawiasu klamrowego `{` , deklaracji zawartych w przestrzeni nazw i zamykającego nawiasu klamrowego `}` .
Nazwy przestrzeni nazw są zgodne ze wzorcem .NET sekwencji jednego lub więcej symboli dozwolonych oddzielonych kropkami `.` .
Na przykład `MyQuantumStuff` i `Microsoft.Quantum.Intrinsic` są prawidłowymi nazwami przestrzeni nazw.
Według Konwencji symbole w nazwie przestrzeni nazw są pisane wielkimi literami, ale nie jest to wymagane.

Odwołania do typów lub wartości, które zostały zadeklarowane w sposób nieokreślony w pliku, są rozwiązywane prawidłowo; nie ma potrzeby składania deklaracji typu, operacji lub funkcji przed odwołaniem do niej.

## <a name="open-directives"></a>Otwarte dyrektywy

W bloku przestrzeni nazw `open` dyrektywa może być używana do importowania wszystkich typów i wywoływanych deklaracji w określonym obszarze nazw i odwoływania się do nich według ich nazwy niekwalifikowanej.
Taka `open` dyrektywa składa się ze `open` słowa kluczowego, po którym następuje przestrzeń nazw, która ma zostać otwarta i kończąca się średnikiem.

> [!NOTE] 
> Wszystkie `open` dyrektywy muszą występować przed dowolnymi `function` `operation` `newtype` deklaracjami w bloku przestrzeni nazw.

Opcjonalnie, krótka nazwa otwartej przestrzeni nazw może być zdefiniowana, tak że wszystkie elementy z tej przestrzeni nazw mogą (i muszą) być kwalifikowane przez zdefiniowaną krótką nazwę. Na przykład uwzględniając następującą deklarację przestrzeni nazw i otwarte dyrektywy,

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

Jeśli operacja, którą deklarujemy, używa operacji `Op` z `Microsoft.Quantum.Intrinsic` , możemy ją wywołać za pomocą polecenia `Op` .
Jeśli jednak chciałem wywołać określoną funkcję `Fn` z usługi `Microsoft.Quantum.Math` , musimy ją wywołać przy użyciu `Math.Fn` .

`open`Dyrektywa ma zastosowanie do całego bloku przestrzeni nazw w pliku.
W związku z tym, jeśli wcześniej zdefiniujesz dodatkową przestrzeń nazw w tym samym pliku Q # jak `NS` powyżej, wówczas wszystkie operacje/funkcje/typy zdefiniowane w drugim obszarze nazw nie będą miały dostępu do niczego z `Microsoft.Quantum.Intrinsic` lub `Microsoft.Quantum.Math` , chyba że powtarzają otwarte dyrektywy. 

Typ lub możliwy do odłożenia zdefiniowany w innej przestrzeni nazw, który *nie* jest otwarty w bieżącej przestrzeni nazw, musi odwoływać się do jego w pełni kwalifikowanej nazwy.
Na przykład operacja o nazwie `Op` z `X.Y` przestrzeni nazw musi być przywoływana przez jej w pełni kwalifikowaną nazwę `X.Y.Op` , chyba że `X.Y` przestrzeń nazw została otwarta wcześniej w bieżącym bloku. Jak wspomniano powyżej, nawet jeśli `X` przestrzeń nazw została otwarta, nie można odwołać się do operacji jako `Y.Op` .
Jeśli krótka nazwa `Z` `X.Y` została zdefiniowana w tej przestrzeni nazw i pliku, `Op` musi być określona jako `Z.Op` . 

Zwykle lepiej jest dołączyć przestrzeń nazw przy użyciu `open` dyrektywy.
Użycie w pełni kwalifikowanej nazwy jest wymagane, jeśli dwie przestrzenie nazw definiują konstrukcje o tej samej nazwie, a bieżące źródło używa konstrukcji z obu tych typów.

Pytania i odpowiedzi są zgodne z tymi samymi regułami dotyczącymi nazewnictwa w innych językach .NET.
Jednak polecenie Q # nie obsługuje względnych odwołań do przestrzeni nazw.
Oznacza to, że jeśli przestrzeń nazw `a.b` została otwarta, odwołanie do operacji o nazwie `c.d` *nie* zostanie rozpoznane do operacji o pełnej nazwie `a.b.c.d` .

## <a name="formatting"></a>Formatowanie

Większość instrukcji i dyrektyw Q # kończy się średnikiem, `;` .
Instrukcje i deklaracje, takie jak `for` i `operation` kończące się blokiem instrukcji (patrz poniżej) nie wymagają kończącego się średnika.
Każdy opis instrukcji wskazuje, czy jest wymagany średnik kończący.

Instrukcje, takie jak wyrażenia, deklaracje i dyrektywy, mogą być rozbite w wielu wierszach.
Należy unikać wielu instrukcji w pojedynczym wierszu.

## <a name="statement-blocks"></a>Bloki instrukcji

Instrukcje Q # są pogrupowane w bloki instrukcji.
Blok instrukcji rozpoczyna się od otwarcia `{` i kończącego się zamykaniem `}` .

Blok instrukcji, który jest leksykalny w innym bloku, jest traktowany jako podblok bloku zawierającego; bloki zawierające i podrzędne są również nazywane blokami zewnętrznymi i wewnętrznymi.

## <a name="comments"></a>Komentarze

Komentarze zaczynają się od dwóch ukośników `//` i są kontynuowane do końca wiersza.
Komentarz może pojawić się w dowolnym miejscu w pliku źródłowym Q #.

## <a name="documentation-comments"></a>Komentarze dokumentacji

Komentarze zaczynające się od trzech ukośników, `///` są traktowane specjalnie przez kompilator, gdy są wyświetlane bezpośrednio przed przestrzenią nazw, operacją, specjalizacją, funkcją lub definicją typu.
W takim przypadku ich zawartość jest pobierana jako Dokumentacja dla zdefiniowanego lub zdefiniowanego przez użytkownika typu, tak jak w przypadku innych języków .NET.

W `///` komentarzach tekst, który ma być wyświetlany jako część dokumentacji interfejsu API, jest sformatowany jako [promocji](https://daringfireball.net/projects/markdown/syntax), z różnymi częściami dokumentacji wskazywanych przez nagłówki o specjalnie określonym nazwie.
Jako rozszerzenie do promocji, odwołania krzyżowe do operacji, funkcji i typów zdefiniowanych przez użytkownika w Q # można uwzględnić przy użyciu `@"<ref target>"` , gdzie `<ref target>` jest zastępowana w pełni kwalifikowana nazwa obiektu kodu, do którego istnieje odwołanie.
Opcjonalnie aparat dokumentacji może również obsługiwać dodatkowe rozszerzenia promocji.

Przykład:

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

Następujące nazwy są rozpoznawane jako nagłówki komentarzy do dokumentacji.

- **Podsumowanie**: krótkie podsumowanie zachowania funkcji lub operacji albo do celu typu. Pierwszy akapit podsumowania jest używany na potrzeby informacji o aktywowaniu. Powinien być zwykły tekst.
- **Opis**: Opis zachowania funkcji lub operacji lub do celu typu. Podsumowanie i opis są łączone w celu utworzenia wygenerowanego pliku dokumentacji dla funkcji, operacji lub typu.
  Opis może zawierać symbole i równania sformatowane w wierszu.
- **Dane wejściowe**: Opis krotki wejściowej dla operacji lub funkcji.
  Może zawierać dodatkowe podsekcje promocji wskazujące każdy pojedynczy element spójnej kolekcji wejściowej.
- **Dane wyjściowe**: Opis krotki zwracanej przez operację lub funkcję.
- **Parametry typu**: pusta sekcja, która zawiera jedną dodatkową podsekcję dla każdego parametru typu ogólnego.
- **Przykład**: krótki przykład operacji, funkcji lub typu w użyciu.
- **Uwagi**: różne Prose opisujące aspekt operacji, funkcji lub typu.
- **Zobacz również**: Lista w pełni kwalifikowanych nazw wskazujących powiązane funkcje, operacje lub typy zdefiniowane przez użytkownika.
- **Odwołania**: lista odwołań i cytatów dla udokumentowanego elementu.

## <a name="next-steps"></a>Następne kroki

Informacje o [operacjach i funkcjach](xref:microsoft.quantum.guide.operationsfunctions) w usłudze Q #.