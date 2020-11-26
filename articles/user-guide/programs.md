---
title: 'Q # Introdution'
description: 'Szybkie wprowadzenie do programów Quantum w usłudze Q #'
author: beheim
ms.author: beheim
ms.date: 11/08/2020
ms.topic: article
uid: microsoft.quantum.guide.programs
ms.openlocfilehash: 975bcda5e0042406b465a83f17f1d2d3f5a1ec4f
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96233975"
---
# <a name="q-quantum-programming-language"></a>Język programowania Q # Quantum

Wszystko, co musisz wiedzieć o języku programowania Q #, opisano szczegółowo w [przewodniku językowym q #](xref:microsoft.quantum.qsharp.index). Podobnie jak w przypadku innych, nasz [proces projektowania języka](https://github.com/microsoft/qsharp-language#q-language-and-core-libraries-design) jest typu open source i Zapraszamy do powitania.
Aby uzyskać więcej informacji o wykrytych i motywacji za Q #, zobacz [Dlaczego potrzebuję q #?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).  
Polecenie Q # jest dostarczane jako część zestawu Quantum Development Kit (QDK), aby zapoznać się z szybkim omówieniem, Dowiedz [się, co to jest QDK?](xref:microsoft.quantum.overview.q-sharp). 

## <a name="what-is-a-quantum-program"></a>Co to jest program Quantum?

Program Quantum może być traktowany jako konkretny zestaw klasycznych podprocedur, które, po wywołaniu, wykonują obliczenia poprzez współdziałanie z systemem Quantum; Program pisany w języku Q # nie bezpośrednio modeluje stan Quantum, ale raczej opisuje, jak klasyczny formant współdziała z qubits.
Pozwala to na całkowite niezależny od informacji o stanie *Quantum nawet na* każdej maszynie docelowej, co może mieć różne interpretacje w zależności od maszyny. 

Ważną konsekwencją jest to, że funkcja Q # nie ma możliwości Introspect do stanu qubit lub innych właściwości Quantum Mechanics bezpośrednio, co gwarantuje, że program Q # może być fizycznie wykonywany na komputerze Quantum.
Zamiast tego program może wywołać operacje, takie jak [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) Wyodrębnienie informacji klasycznych z qubit.

Po przydzieleniu qubit może być przekazane do operacji i funkcji *, nazywanych również jako możliwe* do wypróbowania. W niektórych przypadkach jest to wszystko, że program Q # może wykonać qubit; Wszystkie bezpośrednie działania w stanie qubit są wszystkie zdefiniowane przez *wewnętrzne* , takie jak [`X`](xref:Microsoft.Quantum.Intrinsic.X) i [`H`](xref:Microsoft.Quantum.Intrinsic.H) -tj., których implementacje nie są zdefiniowane w Q #, ale są definiowane przez maszynę docelową. Operacje, *które faktycznie są* wykonywane, są tworzone wyłącznie przez maszynę docelową używaną do uruchamiania określonego programu Q #.

Na przykład, jeśli uruchamiasz program w [symulatorze pełnego stanu](xref:microsoft.quantum.machines.full-state-simulator), symulator wykonuje odpowiednie operacje matematyczne w symulowanym systemie Quantum.
Jednak w przyszłości, gdy maszyna docelowa jest rzeczywistym komputerem z systemem Quantum, wywołanie takich operacji w Q # spowoduje skierowanie komputera Quantum do wykonywania odpowiednich *rzeczywistych* operacji na *rzeczywistym* systemie Quantum (np. precyzyjne impulsy laserowe).

Program Q # ponownie łączy te operacje jako zdefiniowane przez maszynę docelową w celu utworzenia nowych, wyższych operacji na potrzeby obliczeń Quantum.
W ten sposób Q # ułatwia wyrażanie logiki podstawowych algorytmów Quantum i hybrydowych procesów Quantum — klasycznych, a także ogólnie w odniesieniu do struktury maszyny docelowej lub symulatora.

Prostym przykładem jest następujący program, który przydziela jeden qubit w stanie $ \ket {0} $, a następnie stosuje do niego operację Hadamard `H` i mierzy wynik `PauliZ` .

```qsharp
@EntryPoint()
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // we reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, we return the result of the measurement.
        return result;
    }
}
```

Nasze [Katas Quantum](https://github.com/microsoft/QuantumKatas#introduction) zapewniają dobre wprowadzenie w oparciu o [koncepcje przetwarzania Quantum](https://github.com/microsoft/QuantumKatas#quantum-computing-concepts-qubits-and-gates) , takie jak typowe operacje Quantum i sposób manipulowania qubits. Więcej przykładów można znaleźć w temacie [operacje wewnętrzne i funkcje](xref:microsoft.quantum.libraries.standard.prelude).



