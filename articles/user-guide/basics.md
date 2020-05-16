---
title: Podstawowe informacje o numerze Q
description: 'Podstawowe pojęcia dotyczące pytań i odpowiedzi #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431159"
---
# <a name="q-basics"></a>Podstawowe informacje o numerze Q

W tej sekcji przedstawiamy krótkie wprowadzenie do podstawowych bloków konstrukcyjnych języka Q #.

Aby uzyskać szybki przegląd informacji o tym, co to jest funkcja Q # i gdzie pasuje do podstawowego składnika zestawu Quantum Development Kit, możesz sprawdzić, [co to jest Q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Co to jest program Quantum?

Z perspektywy technicznej, program Quantum może być traktowany jako określony zestaw klasycznych podprocedur, które, po wywołaniu, wykonują pewne operacje w systemie Quantum.
Istotną konsekwencją tego widoku jest to, że program pisany w języku Q # nie bezpośrednio modeluje qubits, ale raczej opisuje, jak klasyczny formant współdziała z tymi qubitsami.
Zgodnie z projektem, Q # nie definiuje bezpośrednio Stanów Quantum lub innych właściwości Quantum Mechanics.
Na przykład rozważmy stan $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ omówiony w przewodniku [koncepcji obliczeniowej usługi Quantum](xref:microsoft.quantum.concepts.intro) .
Aby przygotować ten stan w Q #, używamy faktów, że qubits są inicjowane w stanie $ \ket {0} $ i że $ \ket{+} = H\ket {0} $, gdzie $H $ to Hadamard przekształcenia, implementowane przez [ `H` Operation] (] (linki XREF: Microsoft. Quantum. wewnętrzna. H):

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a>Stany Quantum w Q #

Ważne jest, aby podczas pisania powyższego programu nie odwoływał się jawnie do stanu z pytaniami Q #, ale zamiast opisywania sposobu, w jaki został on *przekształcony* przez nasz program.
Pozwala to na całkowite niezależny od informacji o stanie *Quantum nawet na* każdej maszynie docelowej, co może mieć różne interpretacje w zależności od maszyny. 

Program Q # nie ma możliwości Introspect stanu qubit.
Zamiast tego program może wywoływać operacje, takie jak [`Measure`](xref:microsoft.quantum.intrinsic.measure) Aby poznać informacje z qubit i wywoływać operacje, takie jak [`X`](xref:microsoft.quantum.intrinsic.x) i [`H`](xref:microsoft.quantum.intrinsic.h) do działania na stanie qubit.
Operacje, *które faktycznie są* wykonywane, są tworzone wyłącznie przez maszynę docelową używaną do uruchamiania określonego programu Q #.
Na przykład, jeśli uruchamiasz program w [symulatorze pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), symulator wykona odpowiednie operacje matematyczne w symulowanym systemie Quantum.
Jednak w przyszłości, gdy maszyna docelowa jest rzeczywistym komputerem z systemem Quantum, wywołanie takich operacji w Q # spowoduje skierowanie komputera Quantum do wykonywania odpowiednich *rzeczywistych* operacji na *rzeczywistym* systemie Quantum (np. precyzyjne impulsy laserowe).

Program Q # ponownie łączy te operacje jako zdefiniowane przez maszynę docelową w celu utworzenia nowych, wyższych operacji na potrzeby obliczeń Quantum.
W ten sposób Q # ułatwia wyrażanie logiki podstawowych algorytmów Quantum i hybrydowych procesów Quantum — klasycznych, a także ogólnie w odniesieniu do struktury maszyny docelowej lub symulatora.

## <a name="q-operations-and-functions"></a>Operacje i funkcje pytań i odpowiedzi

W konkretnym przypadku program Q # składa się z *operacji*, *funkcji*i wszystkich typów zdefiniowanych przez użytkownika. 

Operacje są używane do opisywania transformacji systemów Quantum i są najbardziej podstawowymi blokami konstrukcyjnymi programów Q #. Każda operacja zdefiniowana w Q # może następnie wywołać dowolną liczbę innych operacji.

W przeciwieństwie do operacji, funkcje są używane do opisywania przejrzystie *deterministycznych* zachowań klasycznych i nie mają żadnych efektów poza obliczaniem klasycznych wartości. Załóżmy na przykład, że chcemy zmierzyć nasze qubits na końcu programu i dodać wyniki pomiarów do tablicy.
W tym przypadku `Measure` jest to *operacja* , która instruuje maszynę docelową, aby wykonywała pomiary na (rzeczywista lub symulowana) qubits, a klasyczny proces dodawania zwracanych wyników do tablicy zostanie obsłużony przez *funkcje*.

Razem operacje i funkcje są *określane jako możliwe*do wypróbowania, a ich podstawowa struktura i zachowanie są wprowadzane na stronie [operacje i funkcje w obszarze Q #](xref:microsoft.quantum.guide.operationsfunctions) .


## <a name="q-syntax-overview"></a>Omówienie składni Q #

Składnia języka opisuje różne kombinacje symboli, które tworzą poprawny w składni program.
W Q # możemy sklasyfikować elementy jego składni w trzech różnych grupach: typy, wyrażenia i instrukcje.

### <a name="types"></a>Typy
Q # to wulgarny język, w taki sposób, że staranne użycie typów może pomóc kompilatorowi zapewnić silne gwarancje dotyczące programów Q # w czasie kompilacji.
Oprócz standardowych i opartych na Quantum typów pierwotnych (np.,, `Int` `Bool` `Qubit` i `Result` ), Q # zapewnia obsługę typów zdefiniowanych przez użytkownika.
Wszystkie typy pierwotne Q # są opisane na stronie [typy w q #](xref:microsoft.quantum.guide.types) , wraz ze szczegółami dotyczącymi typów tablicowych i krotek oraz jak definiować nowe typy w pliku q #.

### <a name="expressions"></a>Wyrażenia
Wyrażenie w języku programowania jest kombinacją jednej lub więcej stałych, zmiennych, operatorów i funkcji interpretowanych przez język programowania i obliczanych w określonej wartości.
W przypadku każdego typu w języku wyrażenia tego typu mogą być *literałami* lub symbolami związanymi z wartością tego typu.
Na przykład, `5` to `Int` literał (również wyrażenie typu `Int` ) i jeśli symbol `count` jest powiązany z wartością całkowitą `5` , `count` jest również wyrażeniem liczby całkowitej.

Ponadto wyrażenie może składać się z innych wyrażeń połączonych z określonymi operatorami.
W związku z tym inny przykład `Int` wyrażenia, którego wynikiem `5` jest wartość `2+3` .

Możliwe wyrażenia typów w Q #, a także zgodne operatory, których można użyć do ich tworzenia, są szczegółowo opisane w [wyrażeniach typu na stronie Q #](xref:microsoft.quantum.guide.expressions) . 

### <a name="statements"></a>Instrukcje 
Instrukcja jest jednostką składniową bezwzględnego języka programowania, która wyraża pewne działania do przeprowadzenia. Różnice instrukcji z wyrażeniami w tych instrukcjach nie zwracają wyników i są wykonywane wyłącznie dla ich efektów ubocznych, natomiast wyrażenia zawsze zwracają wynik i często nie mają efektów ubocznych.
Takie rozróżnienie jest często obserwowane w wyrazach: wyrażenie jest oceniane, podczas gdy instrukcja jest wykonywana.

Bardzo podstawowy przykład instrukcji w Q # przypisuje symbol do wyrażenia:
```qsharp
let count = 5;
```

Nieco bardziej interesujący przykład to `for` instrukcja, która obsługuje iterację i zawiera *blok instrukcji*.
Załóżmy, że `qubits` symbol jest powiązany z rejestrem qubits (technicznie typu `Qubit[]` , czyli tablicą `Qubit` typów). Następnie
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
jest instrukcją, która wykonuje iterację na każdym qubit w rejestrze, wykonując `H` operację na każdym z nich. Należy zauważyć, że `H(qubit);` jest również instrukcją w samej siebie.

W rzeczywistości każde wyrażenie wywołania typu `Unit` (te, które nie zwracają żadnych informacji) mogą być używane jako instrukcja.
Jest to głównie używane podczas wywoływania operacji na qubits, które zwracają, `Unit` ponieważ celem instrukcji jest zmodyfikowanie niejawnego stanu Quantum.
Instrukcje oceny wyrażeń wymagają zakończenia średnika.

Niemal każdy aspekt programu Q # jest kompilowany przy użyciu instrukcji, więc żadna pojedyncza strona nie może obejmować wszystkich informacji odnoszących się do nich.
Jednak ich struktury i formatowanie leksykalne są opisane na stronie [struktury plików q #](xref:microsoft.quantum.guide.filestructure) , przypisanie powiązania symboli i zakres w [zmiennych w q #](xref:microsoft.quantum.guide.variables)i pętle przepływu sterowania, takie jak `for` w [przepływie sterowania w kontrolce q #](xref:microsoft.quantum.guide.controlflow).


## <a name="whats-next"></a>Co dalej?
W pozostałej części tego przewodnika pokazano, jak używać funkcji Q # do konstruowania złożonych programów Quantum za pośrednictwem podstawowych bloków konstrukcyjnych operacji, funkcji i typów.

Aby rozpocząć, możesz rozpocząć uczenie się o [typach w Q #](xref:microsoft.quantum.guide.types).

Jeśli chcesz dowiedzieć się więcej na temat podstaw i motywacji za Q #, zapoznaj się z informacjami o [tym, dlaczego potrzebuję q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
