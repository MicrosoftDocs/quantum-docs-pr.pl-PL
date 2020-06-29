---
title: Podstawowe informacje o numerze Q
description: 'Podstawowe pojęcia dotyczące pytań i odpowiedzi #'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: 45e6f2f33dafc2aec177091d3cfa94aca14fbf0a
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415367"
---
# <a name="q-basics"></a>Podstawowe informacje o numerze Q

W tym artykule przedstawiono krótkie wprowadzenie do podstawowych bloków konstrukcyjnych języka Q #.

Aby dowiedzieć się, co to jest funkcja Q # i gdzie jest ona zgodna ze składnikiem zestawu Quantum Development Kit, zobacz [co to jest q #?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Co to jest program Quantum?

Z perspektywy technicznej, program Quantum jest określonym zestawem klasycznych podprocedur, które po wywołaniu należy wykonać pewne operacje w systemie Quantum.
Ważnym wynikiem tego widoku jest to, że program Q # nie bezpośrednio modeluje qubits, ale raczej opisuje, jak klasyczny komputer współdziała z tymi qubitsami.
Zgodnie z projektem, Q # nie definiuje bezpośrednio Stanów Quantum lub innych właściwości Mechanics Quantum.
Na przykład rozważmy stan $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ omówiony w przewodniku [koncepcji obliczeniowej usługi Quantum](xref:microsoft.quantum.concepts.intro) .
Aby przygotować ten stan w Q #, Zacznij od faktów, że qubits są inicjowane w stanie $ \ket {0} $ i że $ \ket{+} = H\ket {0} $, gdzie $H $ jest [przekształceniem Hadamard](xref:microsoft.quantum.glossary#hadamard), implementowanym przez [ `H` operację](xref:microsoft.quantum.intrinsic.h). Podstawowy kod Q #, aby zainicjować i przekształcić qubit, wygląda następująco:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Aby uzyskać więcej informacji na temat inicjowania lub *alokowania*qubits, zobacz [Praca z qubits](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-q"></a>Stany Quantum w Q #

Z tego powodu poprzedni program nie odwołuje się jawnie do stanu w odpowiedzi Q #, ale został *opisany w tym, jak* program przerobił stan.
Korzystając z tej metody, można całkowicie niezależny od na temat tego, co stan Quantum *jest* nawet na każdej maszynie docelowej, co może mieć różne interpretacje w zależności od maszyny. 

Program Q # nie może Introspect stanu qubit.
Zamiast tego program może wywoływać operacje, takie jak [`Measure`](xref:microsoft.quantum.intrinsic.measure) Aby poznać informacje z qubit i wywoływać operacje, takie jak [`X`](xref:microsoft.quantum.intrinsic.x) i [`H`](xref:microsoft.quantum.intrinsic.h) do działania na stanie qubit.
Te *operacje są wykonywane* tylko w konkretnym miejscu przez maszynę docelową używaną do uruchamiania określonego programu Q #.
Na przykład, jeśli uruchamiasz program w [symulatorze pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), symulator wykonuje odpowiednie operacje matematyczne w symulowanym systemie Quantum.
Jednak w przyszłości, gdy maszyna docelowa jest rzeczywistym komputerem z systemem Quantum, wywołanie takich operacji w Q # kieruje komputer Quantum do wykonywania odpowiednich *rzeczywistych* operacji na *rzeczywistym* systemie Quantum, na przykład precyzyjne impulsy laserowe.

Program Q # ponownie łączy te operacje jako zdefiniowane przez maszynę docelową w celu utworzenia nowych, wyższych operacji na potrzeby obliczeń Quantum.
W ten sposób Q # ułatwia wyrażanie logiki podstawowych algorytmów Quantum i hybrydowych procesów Quantum — klasycznych, a także ogólnie w odniesieniu do struktury maszyny docelowej lub symulatora.

## <a name="q-operations-and-functions"></a>Operacje i funkcje pytań i odpowiedzi

W konkretnym przypadku program Q # obejmuje *operacje*, *funkcje*i wszelkie typy zdefiniowane przez użytkownika. 

Operacje są używane do opisywania transformacji systemów Quantum i są najbardziej podstawowymi blokami konstrukcyjnymi programów Q #. Każda operacja zdefiniowana w Q # może następnie wywołać dowolną liczbę innych operacji.

W przeciwieństwie do operacji, funkcje są używane do opisywania przejrzystie *deterministycznych* zachowań klasycznych i nie mają żadnych efektów poza obliczaniem klasycznych wartości. Załóżmy na przykład, że chcesz zmierzyć qubits na końcu programu i dodać wyniki pomiarów do tablicy.
W tym przypadku `Measure` jest *operacją* , która instruuje maszynę docelową, aby wykonywała pomiary w qubits (rzeczywista lub symulowana). W tym samym czasie *Funkcja* obsługuje klasyczny proces dodawania zwracanych wyników do tablicy.

Razem operacje i funkcje są nazywane *możliwymi*do przełożenia. Ich podstawowa struktura i zachowanie są wprowadzane i szczegółowo opisane w [operacjach i funkcjach w Q #](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="q-syntax-overview"></a>Omówienie składni Q #

Składnia języka opisuje różne kombinacje symboli, które tworzą poprawny w składni program.
W polu Q # elementy składni są klasyfikowane do trzech różnych grup: typów, wyrażeń i instrukcji.

### <a name="types"></a>Typy
Q # to wulgarny język, w taki sposób, że staranne użycie typów może pomóc kompilatorowi zapewnić silne gwarancje dotyczące programów Q # w czasie kompilacji.
Oprócz standardowych i opartych na Quantum typów pierwotnych, na przykład,,, `Int` `Bool` `Qubit` i `Result` , Q # zapewnia obsługę typów zdefiniowanych przez użytkownika.

Aby zapoznać się z opisami wszystkich typów pierwotnych, szczegóły dotyczące typów tablic i krotek oraz kroki definiowania nowych typów w pliku Q #, zobacz [typy w Q #](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Wyrażenia
Wyrażenie w języku programowania jest kombinacją jednej lub więcej stałych, zmiennych, operatorów i funkcji interpretowanych przez język programowania i obliczanych w określonej wartości.
W przypadku każdego typu w języku wyrażenia tego typu mogą być *literałami* lub symbolami związanymi z wartością tego typu.
Na przykład, `5` to `Int` literał (również wyrażenie typu `Int` ) i jeśli symbol `count` jest powiązany z wartością całkowitą `5` , `count` jest również wyrażeniem liczby całkowitej.

Ponadto wyrażenie może składać się z innych wyrażeń połączonych przez niektóre operatory.
Na przykład inne `Int` wyrażenie, którego wynikiem jest wartość `5` `2+3` .

Aby uzyskać więcej informacji na temat wyrażeń i zgodnych operatorów w Q #, zobacz [wyrażenia typu w q #](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Instrukcje 
Instrukcja jest jednostką składniową bezwzględnego języka programowania, która wyraża pewne działania do wykonania. Różnice instrukcji z wyrażeniami w tych instrukcjach nie zwracają wyników i są wykonywane wyłącznie dla ich efektów ubocznych. Wyrażenia, jednak zawsze zwracają wynik i często nie mają efektów ubocznych. W krótkim czasie są wykonywane instrukcje Q #, podczas gdy wyrażenia są oceniane.

Prosty przykład instrukcji w Q # przypisuje symbol do wyrażenia:
```qsharp
let count = 5;
```

Bardziej interesujący przykład to `for` instrukcja, która obsługuje iterację i zawiera *blok instrukcji*.
Załóżmy `qubits` , że symbol jest powiązany z rejestrem qubits (technicznie typu `Qubit[]` lub tablicy `Qubit` typów). Następnie
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
jest instrukcją, która wykonuje iterację na każdym qubit w rejestrze, wykonując `H` operację na każdej z nich. Należy zauważyć, że `H(qubit);` jest również instrukcją w samej siebie.

Można użyć dowolnego wyrażenia wywołania typu `Unit` ( `Unit` Typ nie zwraca żadnych informacji) jako instrukcji.
Ten typ wyrażenia jest przydatny podczas wywoływania operacji na qubits, które zwracają, `Unit` ponieważ celem instrukcji jest zmodyfikowanie niejawnego stanu Quantum.
Instrukcje oceny wyrażeń wymagają zakończenia średnika.

Instrukcje służą do kompilowania niemal każdego aspektu programu Q # i żadna pojedyncza strona nie może obejmować wszystkich informacji odnoszących się do nich.
Aby uzyskać więcej informacji na temat struktury i formatowania leksykalnego, zobacz [Q # File Structure](xref:microsoft.quantum.guide.filestructure); w przypadku przypisywania i zakresu powiązań symboli zobacz [zmienne w Q #](xref:microsoft.quantum.guide.variables); i w przypadku pętli przepływu sterowania, takich jak `for` , zobacz [przepływ sterowania w Q #](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Następne kroki

Rozpocznij uczenie o [typach w Q #](xref:microsoft.quantum.guide.types).

Aby uzyskać więcej informacji o wykrytych i motywacji za Q #, zobacz [Dlaczego potrzebuję q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
