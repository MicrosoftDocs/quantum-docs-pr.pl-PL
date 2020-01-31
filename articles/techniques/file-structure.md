---
title: 'Omówienie programu q # — techniki pytań i odpowiedzi | Microsoft Docs'
description: 'Przegląd programu q # — techniki dla technologii Q #'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.file-structure
ms.openlocfilehash: e8f52e6b0d4382331665a8e845ef19a3a1beabf9
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820831"
---
# <a name="q-program-overview"></a>Przegląd programu Q#

Q # to skalowalny, wielowymiarowy, specyficzny dla domeny język programowania dla przetwarzania Quantum. Q # to język programowania Quantum w systemie, który może służyć do opisywania sposobu wykonywania instrukcji na maszynach Quantum. Maszyny, które mogą być przeznaczone do zakresu od symulatorów do rzeczywistego sprzętu Quantum. Polecenie Q # jest skalowalne: może służyć do pisania prostych programów demonstracyjnych, takich jak teleport, które działają na kilku qubits, ale również obsługuje pisanie dużych, zaawansowanych programów, takich jak symulacje złożonych cząsteczek, które będą wymagały dużych maszyn z milionami qubits. Mimo że duże maszyny fizyczne są nadal w przyszłości, funkcja Q # umożliwia programistom programowanie złożonych algorytmów Quantum teraz. Co więcej, funkcja Q # obsługuje różne zadania, takie jak debugowanie, profilowanie, szacowanie zasobów i pewne symulacje specjalnego przeznaczenia w sposób skalowalny. 

Z perspektywy technicznej, program Quantum może być traktowany jako określony zestaw funkcji klasycznych, które po wywołaniu generują obwody Quantum jako ich efekty uboczne. Istotną konsekwencją tego widoku jest to, że program pisany w języku Q # nie bezpośrednio modeluje qubits, ale raczej opisuje, jak klasyczny formant współdziała z tymi qubitsami.
W związku z tym pytania Q nie definiują w ten sposób Stanów Quantum i innych właściwości Mechanics Quantum, ale raczej pośrednio przez działanie różnych podprocedur zdefiniowanych w języku.
Na przykład rozważmy stan $ \ket{+} = \left (\ket{0} + \ket{1}\right)/\sqrt{2}$ omówiony w przewodniku dotyczący [koncepcji przetwarzania Quantum](xref:microsoft.quantum.concepts.intro) .
Aby przygotować ten stan w Q #, używamy faktów, że qubits są inicjowane w stanie $ \ket{0}$, i że $ \ket{+} = H\ket{0}$, gdzie $H $ to Hadamard Transform:

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a>Q # tranformations Stanów Quantum

Ważne jest, aby podczas pisania powyższego programu nie odwoływał się jawnie do stanu z pytaniami Q #, ale zamiast opisywania sposobu, w jaki został on *przekształcony* przez nasz program.
W ten sposób podobnie jak program do cieniowania grafiki gromadzi opis przekształceń do każdego wierzchołka, program Quantum w Q # gromadzi przekształcenia do Stanów Quantum.
Pozwala to na całkowite niezależny od informacji o stanie *Quantum nawet na* każdej maszynie docelowej, co może mieć różne interpretacje w zależności od maszyny. 

Z perspektywy programu Q # qubit jest całkowicie nieprzezroczystym odwołaniem do wewnętrznej struktury maszyny docelowej.
Program Q # nie ma możliwości Introspect stanu qubit, jego reprezentacji na komputerze docelowym lub nawet tego, czy jest to ten sam qubit, co inne qubit dostępne dla programu.
Zamiast tego program może wywoływać operacje, takie jak `Measure`, aby poznać informacje z qubit i wywoływać operacje, takie jak `X` i `H` do działania na stanie qubit.
Te operacje nie mają wewnętrznej definicji w języku i są przeznaczone tylko dla maszyny docelowej używanej do uruchamiania określonego programu Q #.
Program Q # ponownie łączy te operacje jako zdefiniowane przez maszynę docelową w celu utworzenia nowych, wyższych operacji na potrzeby obliczeń Quantum.
W ten sposób Q # ułatwia wyrażanie logiki podstawowych algorytmów Quantum i hybrydowych, a także ogólne w odniesieniu do struktury maszyny docelowej lub symulatora.

## <a name="q-operations-and-functions"></a>Operacje i funkcje pytań i odpowiedzi

W konkretnym przypadku program Q # składa się z co najmniej jednej *operacji*, co najmniej jednej *funkcji*i typów zdefiniowanych przez użytkownika. Operacje są używane do opisywania transformacji stanu maszyny Quantum i są najbardziej podstawowymi blokami konstrukcyjnymi programów Q #. Każda operacja zdefiniowana w Q # może następnie wywołać dowolną liczbę innych operacji, łącznie z wbudowanymi *wewnętrznymi* operacjami implementowanymi przez maszynę docelową.
Po skompilowaniu każda operacja jest reprezentowana jako typ klasy .NET, który można dostarczyć dla maszyn docelowych.

W przeciwieństwie do operacji, funkcje są używane do opisywania przejrzystie klasycznego zachowania i nie mają żadnych efektów poza obliczaniem klasycznej wartości wyjściowej. Q # jest silnie wpisaną językiem i zawiera zestaw wbudowanych typów pierwotnych, a także obsługę typów zdefiniowanych przez użytkownika. 

W dalszej części tego przewodnika zobaczymy, jak używać różnych pojęć i konstrukcji języka, aby pomóc nam definiować złożone programy Quantum za pośrednictwem podstawowych bloków konstrukcyjnych operacji, funkcji i typów. 

## <a name="structure-of-q-source-files"></a>Struktura plików źródłowych Q #

Co więcej, plik źródłowy Q # składa się z *deklaracji przestrzeni nazw*, która określa przestrzeń nazw platformy .NET, która będzie zawierać definicje w pliku źródłowym.
Definicje z innych plików źródłowych i bibliotek Q # można uwzględnić przy użyciu instrukcji `open`.
Na przykład większość operacji definiujących podstawowe bramy jest definiowana w przestrzeni nazw <xref:microsoft.quantum.intrinsic>.
Aby udostępnić ten kod, po prostu `open` tę przestrzeń nazw u góry każdego pliku:

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

W przestrzeni nazw każdy plik źródłowy Q # może definiować dowolną kombinację *operacji*, *funkcji*i *typów zdefiniowanych przez użytkownika*.
W pozostałej części tej sekcji opiszemy każdą z nich i dostarczymy przykłady ich użycia w programie w celu zapewnienia użytecznych programów Quantum.
