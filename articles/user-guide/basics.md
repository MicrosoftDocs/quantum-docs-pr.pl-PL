---
title: Q# Nazwie
description: Podstawowe pojęcia związane z Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: b3bc0841eabeac5d3968776f9dab3a02b1a1eef9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691633"
---
# <a name="no-locq-basics"></a>Q# Nazwie

W tym artykule przedstawiono krótkie wprowadzenie do podstawowych bloków konstrukcyjnych Q# .

Aby Q# dowiedzieć się, co to jest i gdzie mieści się w ramach podstawowego składnika zestawu Quantum Development Kit, zobacz [co to jest Q# ?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Co to jest program Quantum?

Z perspektywy technicznej, program Quantum jest określonym zestawem klasycznych podprocedur, które po wywołaniu należy wykonać pewne operacje w systemie Quantum.
Istotną konsekwencją tego widoku jest to, że Q# program nie jest bezpośrednio modelem qubits, ale raczej opisuje, w jaki sposób klasyczny komputer współdziała z tymi qubitsami.
Zgodnie z projektem, nie Q# definiuje bezpośrednio Stanów Quantum ani innych właściwości Mechanics Quantum.
Na przykład rozważmy stan $ \ket{+} = \left (\ket {0} + \ket {1} \right)/\sqrt {2} $ omówiony w przewodniku [koncepcji obliczeniowej usługi Quantum](xref:microsoft.quantum.concepts.intro) .
Aby przygotować ten stan w programie Q# , Zacznij od faktów, że qubits są inicjowane w stanie $ \ket {0} $ i że $ \ket{+} = H\ket {0} $, gdzie $H $ to [Hadamard Transform](xref:microsoft.quantum.glossary#hadamard), zaimplementowany przez [ `H` operację](xref:Microsoft.Quantum.Intrinsic.H). Kod podstawowy Q# do zainicjowania i przekształcenia qubit jest następujący:

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
Aby uzyskać więcej informacji na temat inicjowania lub *alokowania* qubits, zobacz [Praca z qubits](xref:microsoft.quantum.guide.qubits).

## <a name="quantum-states-in-no-locq"></a>Stany Quantum w Q#

Z tego powodu poprzedni program nie odwołuje się jawnie do stanu w ramach Q# programu, ale opisano, w jaki sposób ten program *przekształca* stan.
Korzystając z tej metody, można całkowicie niezależny od na temat tego, co stan Quantum *jest* nawet na każdej maszynie docelowej, co może mieć różne interpretacje w zależności od maszyny. 

Q#Program nie może Introspect stanu qubit.
Zamiast tego program może wywoływać operacje, takie jak [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) Aby poznać informacje z qubit i wywoływać operacje, takie jak [`X`](xref:Microsoft.Quantum.Intrinsic.X) i [`H`](xref:Microsoft.Quantum.Intrinsic.H) do działania na stanie qubit.
Te *operacje są wykonywane* tylko w konkretnym miejscu przez maszynę docelową używaną do uruchamiania określonego Q# programu.
Na przykład, jeśli uruchamiasz program w [symulatorze pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), symulator wykonuje odpowiednie operacje matematyczne w symulowanym systemie Quantum.
Jednak w przyszłości, gdy maszyna docelowa jest rzeczywistym komputerem z systemem Quantum, wywołanie takich operacji powoduje Q# kierowanie komputera Quantum do wykonywania odpowiednich *rzeczywistych* operacji na *rzeczywistym* systemie Quantum, na przykład precyzyjne impulsy laserowe.

Q#Program ponownie łączy te operacje w sposób zdefiniowany przez maszynę docelową w celu utworzenia nowych, wyższych operacji do wyrażenia Quantum obliczeń.
W ten sposób można Q# łatwo wyrażać logikę podstawowych algorytmów Quantum i hybrydowe, a także ogólnie w odniesieniu do struktury maszyny docelowej lub symulatora.

## <a name="no-locq-operations-and-functions"></a>Q# operacje i funkcje

W konkretnym przypadku Q# program składa się z *operacji* , *funkcji* i wszystkich typów zdefiniowanych przez użytkownika. 

Operacje są używane do opisywania transformacji systemów Quantum i są najbardziej podstawowymi blokami konstrukcyjnymi Q# programów. Każda operacja zdefiniowana w programie Q# może następnie wywołać dowolną liczbę innych operacji.

W przeciwieństwie do operacji, funkcje są używane do opisywania przejrzystie *deterministycznych* zachowań klasycznych i nie mają żadnych efektów poza obliczaniem klasycznych wartości. Załóżmy na przykład, że chcesz zmierzyć qubits na końcu programu i dodać wyniki pomiarów do tablicy.
W tym przypadku `Measure` jest *operacją* , która instruuje maszynę docelową, aby wykonywała pomiary w qubits (rzeczywista lub symulowana). W tym samym czasie *Funkcja* obsługuje klasyczny proces dodawania zwracanych wyników do tablicy.

Razem operacje i funkcje są nazywane *możliwymi* do przełożenia. Ich podstawowa struktura i zachowanie są wprowadzane i szczegółowo opisane w temacie [operacje Q# i funkcje w ](xref:microsoft.quantum.guide.operationsfunctions).


## <a name="no-locq-syntax-overview"></a>Q# Omówienie składni

Składnia języka opisuje różne kombinacje symboli, które tworzą poprawny w składni program.
W programie Q# elementy składni są klasyfikowane do trzech różnych grup: typów, wyrażeń i instrukcji.

### <a name="types"></a>Typy
Q# jest językiem o jednoznacznie określonym typie, w taki sposób, że staranne użycie typów może pomóc kompilatorowi zapewnić mocne gwarancje dotyczące Q# programów w czasie kompilacji.
Oprócz standardowych i opartych na Quantum typów pierwotnych, na przykład,,, `Int` `Bool` `Qubit` i `Result` , Q# zapewnia obsługę typów zdefiniowanych przez użytkownika.

Aby zapoznać się z opisami wszystkich typów pierwotnych, szczegóły dotyczące typów tablic i krotek oraz kroki definiowania nowych typów w Q# pliku, zobacz [typy w Q# ](xref:microsoft.quantum.guide.types).

### <a name="expressions"></a>Wyrażenia
Wyrażenie w języku programowania jest kombinacją jednej lub więcej stałych, zmiennych, operatorów i funkcji interpretowanych przez język programowania i obliczanych w określonej wartości.
W przypadku każdego typu w języku wyrażenia tego typu mogą być *literałami* lub symbolami związanymi z wartością tego typu.
Na przykład, `5` to `Int` literał (również wyrażenie typu `Int` ) i jeśli symbol `count` jest powiązany z wartością całkowitą `5` , `count` jest również wyrażeniem liczby całkowitej.

Ponadto wyrażenie może składać się z innych wyrażeń połączonych przez niektóre operatory.
Na przykład inne `Int` wyrażenie, którego wynikiem jest wartość `5` `2+3` .

Aby uzyskać więcej informacji na temat wyrażeń i zgodnych operatorów w Q# , zobacz [typu Expressions in Q# ](xref:microsoft.quantum.guide.expressions). 

### <a name="statements"></a>Instrukcje 
Instrukcja jest jednostką składniową bezwzględnego języka programowania, która wyraża pewne działania do wykonania. Różnice instrukcji z wyrażeniami w tych instrukcjach nie zwracają wyników i są uruchamiane wyłącznie dla ich efektów ubocznych. Wyrażenia, jednak zawsze zwracają wynik i często nie mają żadnych efektów ubocznych. W krótkim Q# czasie są wykonywane instrukcje, podczas gdy wyrażenia są oceniane.

Prosty przykład instrukcji w programie Q# przypisuje symbol do wyrażenia:
```qsharp
let count = 5;
```

Bardziej interesujący przykład to `for` instrukcja, która obsługuje iterację i zawiera *blok instrukcji* .
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

Instrukcje służą do kompilowania niemal każdego aspektu Q# programu, a żadna pojedyncza strona nie może obejmować wszystkich informacji odnoszących się do nich.
Aby uzyskać więcej informacji na temat ich struktury i formatowania leksykalnego, zobacz [ Q# Struktura pliku](xref:microsoft.quantum.guide.filestructure); w przypadku przypisywania i zakresu powiązań symboli, patrz [zmienne w Q# ](xref:microsoft.quantum.guide.variables); i w przypadku pętli przepływu sterowania, takich jak `for` , zobacz [Flow Control in Q# ](xref:microsoft.quantum.guide.controlflow).

## <a name="next-steps"></a>Następne kroki

Rozpocznij uczenie [na temat Q# typów w ](xref:microsoft.quantum.guide.types).

Aby uzyskać więcej informacji o wykrytych i motywacji Q# , zobacz [dlaczego są potrzebne Q# ?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).
