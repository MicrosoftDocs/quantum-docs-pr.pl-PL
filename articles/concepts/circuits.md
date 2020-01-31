---
title: Obwody Quantum | Microsoft Docs
description: Obwody kwantowe
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: fe845aa0dde7c780ea6721dfe2559119e90b4aa5
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820797"
---
# <a name="quantum-circuits"></a>Obwody Quantum
Rozważ chwilę przekształcenie jednostkowe $ \Text{CNOT} _{01}(H\otimes 1) $.
Ta sekwencja bram ma podstawowe znaczenie dla przetwarzania Quantum, ponieważ tworzy stan Maximally Entangled dwa qubit:

$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $

Operacje o tej lub większej złożoności są powszechnie stosowane w algorytmach Quantum i korekcji błędów Quantum, dlatego powinna być to świetna, że istnieje prosta metoda dla wizualizacji zwanej *diagramem obwodu Quantum*.
Diagram obwodu do przygotowywania tego stanu Maximally Entangled Quantum to:

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a>Konwencje diagramu obwodu Quantum
Ten język wizualny dla operacji Quantum może być bardziej digestible niż zapisanie odpowiedniej macierzy po zrozumieniu Konwencji dla wyrażenia Quantum.
Omawiamy poniższe konwencje.

W diagramie obwodu każdy pełny wiersz przedstawia qubit lub bardziej ogólnie rejestr qubit.
Zgodnie z Konwencją Górna linia to qubit Register $0 $, a reszta jest oznaczona sekwencyjnie. Powyższy przykładowy obwód jest przedstawiany jako działający na dwóch qubits (lub równorzędnych dwóch rejestrach składających się z jednego qubit).
Bramy działające na co najmniej jednym rejestrie qubit są oznaczane jako pole.
Na przykład symbol

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

jest bramą [Hadamard](xref:microsoft.quantum.intrinsic.h) działającą w rejestrze o pojedynczej qubit.

Bramy Quantum są uporządkowane w kolejności chronologicznej z bramą z lewej strony, jako brama po raz pierwszy zastosowana do qubits.
Innymi słowy, jeśli zdjęcia są nastawione jako przechowanie stanu Quantum, przewody te przesuwają stan Quantum za pośrednictwem każdej bramy na diagramie od lewej do prawej.
To znaczy 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

jest macierzą jednostkową $CBA $.
Mnożenie macierzy przestrzega konwencji przeciwległej: najpierw zastosowano najbardziej odpowiednią macierz. W przypadku diagramów obwodów Quantum należy najpierw zastosować bramę z lewej strony.
Różnica ta może czasami prowadzić do pomyłki, dlatego ważne jest, aby zauważyć znaczącą różnicę między liniową notacją algebraicznych a diagramami obwodów Quantum.

## <a name="inputs-and-outputs-of-quantum-circuits"></a>Dane wejściowe i wyjściowe obwodów Quantum
Wszystkie poprzednie przykłady mają dokładnie taką samą liczbę przewodów (qubits) jako bramę Quantum jako liczbę przewodów z bramy Quantum.
Może być na początku uzasadnione, że obwody Quantum mogą mieć więcej lub mniej danych wyjściowych niż w ogóle.
Jest to niemożliwe, jednak ponieważ wszystkie operacje Quantum, Save pomiary, są jednostkowe i w związku z tym odwracalne.
Jeśli nie mają tej samej liczby danych wyjściowych, ponieważ nie byłyby one odwracalne i dlatego nie są przypadające na jednostki, co jest sprzeczne.
Z tego powodu każde pole rysowane na diagramie obwodu musi mieć dokładnie taką samą liczbę przewodów, jak to zostało zakończone.

Diagramy obwodów qubit są zgodne z podobnymi konwencjami do jednego qubit.
Przykładowo można zdefiniować operację jednostkową dwuqubitą, $B $ (H S\otimes X) $ i wyznaczać obwód jako

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

Można również wyświetlić $B $ jako mające na celu działanie w jednym rejestrze z dwoma qubit zamiast rejestrów 2 1-qubit w zależności od kontekstu, w którym jest używany obwód. Prawdopodobnie najbardziej przydatną właściwością takich diagramów obwodów abstrakcyjnych jest umożliwienie opisywania skomplikowanych algorytmów Quantum na wysokim poziomie bez konieczności kompilowania ich na podstawowe bramy.
Oznacza to, że można uzyskać Intuition o przepływie danych dla dużego algorytmu Quantum bez konieczności zrozumienia wszystkich szczegółowych informacji o sposobie działania poszczególnych podprocedur w algorytmie.

## <a name="controlled-gates"></a>Kontrolowane bramy
Druga konstrukcja, która jest wbudowana w wieloqubit diagramy obwodu Quantum jest formantem.
Działanie bramki Quantum pojedynczo sterowanej, oznaczona jako $ \Lambda (G) $, gdzie wartość jednej qubit kontroluje zastosowanie $G $, można zrozumieć, przeglądając następujący przykład danych wejściowych stanu produktu $ \Lambda (G) (\Alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \Alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket {\ psi} $.
Oznacza to, że kontrolowana brama ma zastosowanie $G $ do rejestru zawierającego $ \psi $ if i tylko wtedy, gdy kontrolka qubit przyjmuje wartość $1 $.
Ogólnie rzecz biorąc, firma Microsoft opisuje takie kontrolowane operacje na diagramach obwodów jako

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

W tym miejscu czarne kółko oznacza bit Quantum, na którym Brama jest kontrolowana, a przewod pionowy oznacza jednostkę, która jest stosowana, gdy kontrolka qubit przyjmuje wartość $1 $.
W przypadku specjalnych przypadków, w których $G = X $ i $G = Z $ wprowadzamy następującą notację do opisywania kontrolowanej wersji bram (należy zauważyć, że brama sterowana X jest [bramą $CNOT $](xref:microsoft.quantum.intrinsic.cnot)):

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

Polecenie Q # udostępnia metody automatycznego generowania kontrolowanej wersji operacji, która polega na tym, że programista nie ma konieczności ręcznego wykonywania kodu. Poniżej przedstawiono przykład:

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a>Operator pomiaru
Pozostałą operacją wizualizacji na diagramach obwodu jest pomiar.
Miara przyjmuje rejestr qubit, mierzy go i wyprowadza wynik jako informacje klasyczne.
Operacja pomiaru jest określana przez symbol miernika i zawsze przyjmuje jako dane wejściowe qubit Rejestr (oznaczany przez linię ciągłą) i wyprowadza klasyczne informacje (oznaczone podwójnym wierszem).
W związku z tym, taki obwód jest podobny do:

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![obwód pomiarowy](~/media/concepts_7.png)

Q # implementuje [operator miary](xref:microsoft.quantum.intrinsic.measure) do tego celu.
Zapoznaj się z [sekcją pomiary](xref:microsoft.quantum.libraries.standard.prelude#measurements) , aby uzyskać więcej informacji.

Analogicznie, podobwód

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

zapewnia zarządzaną w trybie klasycznym bramę, w której zastosowano $G $ w warunku na klasycznej kontrolce o wartości $1 $.

## <a name="teleportation-circuit-diagram"></a>Diagram obwodu teleportowego
[Teleportowanie Quantum](xref:microsoft.quantum.techniques.puttingittogether) jest prawdopodobnie najlepszym algorytmem Quantum dla zilustrowania tych składników.
Teleportowanie Quantum to metoda przenoszenia danych na komputerze z systemem Quantum (lub nawet między odległymi komputerami Quantum w sieci Quantum) za pomocą Entanglement i pomiaru.
Z tego względu można w rzeczywistości przenieść stan Quantum, wypowiedzieć wartość w danym qubit, od jednego qubit do innego, bez znajomości wartości qubit.
Jest to niezbędne do działania protokołu zgodnie z przepisami Mechanics Quantum.
Poniżej znajduje się obwód transportowy Quantum. Udostępniamy również dodaną do adnotacji wersję obwodu, która ilustruje sposób odczytywania obwodu Quantum.

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
