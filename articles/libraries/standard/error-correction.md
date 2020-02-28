---
title: Korekcja błędów w bibliotekach standardowych Q
description: 'Dowiedz się, jak używać poprawiania kodów błędów w programach Q # podczas ochrony stanu qubits.'
author: QuantumWriter
uid: microsoft.quantum.libraries.error-correction
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 514fe68f603b9a3a0b4607390719b08a43fe4967
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907770"
---
# <a name="error-correction"></a>Korekcja błędów #

## <a name="introduction"></a>Wprowadzenie ##

W przypadku klasycznego przetwarzania danych, jeśli jeden chce chronić bit przed błędami, może być często wystarcza do reprezentowania tego bitu przez *bit logiczny* przez powtarzanie bitu danych.
Na przykład, niech $ \overline{0} = $0 to kodowanie danych bit 0, gdzie używamy linii powyżej etykiety 0, aby wskazać, że jest to kodowanie bitu w stanie 0.
Jeśli w podobny sposób zezwolimy na $ \overline{1} = $111, mamy prosty kod powtarzania chroniący przed dowolnym błędem bitu przerzucania.
Oznacza to, że jeśli którykolwiek z trzech bitów zostanie przerzucony, można odzyskać stan bitu logicznego, pobierając większość głosów.
Chociaż klasycznej korekcji błędów jest znacznie bardziej zaawansowana, że ten konkretny przykład (zalecamy [wprowadzenie do teorii lint](https://www.springer.com/us/book/9783540641339)), kod powtórzenia powyżej już wskazuje na możliwy problem w ochronie informacji Quantum.
Oznacza to, że w przypadku, gdy [theorem](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) się, że w przypadku każdej indywidualnej qubit i podania większości głosu przez analogię do klasycznego kodu powyżej zostanie utracone dokładne informacje, które próbujesz chronić.

W ustawieniu Quantum zobaczymy, że pomiar ma problemy. Nadal możemy zaimplementować powyższe kodowanie.
Warto to zrobić, aby zobaczyć, jak możemy uogólniać korekcję błędów do przypadku Quantum.
W tym celu pozwól $ \ket{\overline{0}} = \ket{000} = \ket{0} \otimes \ket{0} \otimes \ket{0}$ i let $ \ket{\overline{1}} = \ket{111}$.
Następnie, według liniowości, definiujemy kod powtarzania dla wszystkich danych wejściowych; na przykład $ \ket{\overline{+}} = (\ket{\overline{0}} + \ket{\overline{1}})/\sqrt{2} = (\ket{000} + \ket{111})/\sqrt{2}$.
W szczególności, wypróbowanie błędu bitowego $X _1 $ Act w środkowym qubite. zobaczymy, że korekta wymagana w obu gałęziach jest dokładnie $X _1 $: $ $ \begin{align} X_1 \ket{\overline{+}} & = \frac{1}{\sqrt{2}} \left (X_1 \ket{000} + X_1 \ket{111} \right) \\\\ & = \frac{1}{\sqrt{2}} \left (\ket{010} + \ket{101} \right).
\end{align} $ $

Aby dowiedzieć się, w jaki sposób można określić, że jest to przypadek bez mierzenia bardzo stanu, który próbujesz chronić, warto napisać, co każdy inny błąd przerzucania bitów ma wpływ na nasze Stany logiczne:

| Błąd $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ |
| --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ |
| $X _0 $ | $ \ket{100}$ | $ \ket{011}$ |
| $X _1 $ | $ \ket{010}$ | $ \ket{101}$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ |

Aby chronić stan, który jest kodowany, musimy mieć możliwość odróżnienia trzech błędów od siebie i od tożsamości $ \boldone $ bez rozróżniania między $ \ket{\overline{0}} $ i $ \ket{\overline{1}} $.
Na przykład jeśli mierzę $Z _0 $, uzyskamy inny wynik dla $ \ket{\overline{0}} $ i $ \ket{\overline{1}} $ w przypadku braku błędów, więc zwija zakodowany stan.
Z drugiej strony należy rozważyć zmierzenie $Z _0 Z_1 $, parzystość pierwszych dwóch bitów w każdym stanie bazowym.
Należy odwołać się do każdego pomiaru operatora Pauli, który eigenvalue mierzony stan odpowiada, więc dla każdego stanu $ \ket{\psi} $ w powyższej tabeli możemy obliczyć $Z _0 Z_1 \ket{\psi} $, aby zobaczyć, czy otrzymamy $ \pm\ket{\psi} $.
Należy zauważyć, że $Z _0 Z_1 \ket{000} = \ket{000}$ i $Z _0 Z_1 \ket{111} = \ket{111}$, dzięki czemu zakończymy, że ta miara jest taka sama jak w przypadku obu zakodowanych Stanów.
Z drugiej strony $Z _0 Z_1 \ket{100} = \ket{100}$ i $Z _0 Z_1 \ket{011} =-\ket{011}$, dlatego wynik pomiaru $Z _0 Z_1 $ ujawnia przydatne informacje o wystąpieniu błędu.

Aby to wyróżnić, powtórzmy powyższą tabelę, ale Dodaj wyniki pomiaru $Z _0 Z_1 $ i $Z _1 Z_2 $ w każdym wierszu.
Należy zwrócić uwagę na wyniki każdego pomiaru przez znak eigenvalue, który jest zaobserwowany, albo $ + $ lub $-$, odpowiednio do wartości Q # `Result` `Zero` i `One`.

| Błąd $E $ | $E \ket{\overline{0}} $ | $E \ket{\overline{1}} $ | Wynik $Z _0 Z_1 $ | Wynik $Z _1 Z_2 $ |
| --- | --- | --- | --- | --- |
| $ \boldone $ | $ \ket{000}$ | $ \ket{111}$ | $+$ | $+$ |
| $X _0 $ | $ \ket{100}$ | $ \ket{011}$ | $-$ | $+$ |
| $X _1 $ | $ \ket{010}$ | $ \ket{101}$ | $-$ | $-$ |
| $X _2 $ | $ \ket{001}$ | $ \ket{110}$ | $+$ | $-$ |

W rezultacie wyniki dwóch pomiarów jednoznacznie decydują o tym, który wystąpił błąd podczas przerzucania bitów, ale bez ujawniania informacji o tym, który ze stanem został zakodowany.
Nazywamy te wyniki *Syndrome*i zapoznaj się z procesem mapowania Syndrome z powrotem do błędu, który spowodował *odzyskanie*.
W szczególności podkreślamy, że odzyskiwanie jest *klasyczną* procedurą wnioskowania, która przyjmuje jako dane wejściowe Syndrome, która wystąpiła, i zwraca receptę dotyczącą sposobu naprawy wszelkich błędów, które mogły wystąpić.

> [!NOTE]
> Powyższy kod bitowy można poprawić tylko w przypadku błędów pojedynczej transmisji bitów. oznacza to, że operacja `X` działa na jednym qubit.
> Zastosowanie `X` do więcej niż jednego qubit spowoduje zamapowanie $ \ket{\overline{0}} $ na $ \ket{\overline{1}} $ po odzyskaniu.
> Podobnie zastosowanie operacji przerzucenia fazy `Z` spowoduje zamapowanie $ \ket{\overline{1}} $ na $-\ket{\overline{1}} $, a tym samym zamapowanie $ \ket{\overline{+}} $ do $ \ket{\overline{-}} $.
> Bardziej ogólnie rzecz biorąc, kody mogą być tworzone w celu obsługi większej liczby błędów oraz do obsługi $Z $ błędów, a także $X $ błędy.

Szczegółowe informacje o tym, że możemy opisać miary w korekcji błędów Quantum, które działają tak samo jak w przypadku wszystkich stanów kodu, jest istoty *formalnego stabilizacji*.
Program Q # Canon oferuje strukturę służącą do opisywania kodowania i dekodowania od kodów stabilizatorów oraz do opisywania, jak jeden odzyskuje błędy.
W tej sekcji opisano te struktury i jej aplikacje do kilku prostych kodów korygujących błędów Quantum.

> [!TIP]
> Pełne wprowadzenie do formalnego stabilizacji wykracza poza zakres tej sekcji.
> Czytelnicy chcą uzyskać więcej informacji na temat [Gottesman 2009](https://arxiv.org/abs/0904.2557).

## <a name="representing-error-correcting-codes-in-q"></a>Reprezentuje kody poprawiające błędy w Q # ##

Aby ułatwić Określanie kodów poprawiania błędów, Q # Canon zawiera kilka różnych typów zdefiniowanych przez użytkownika:

- <xref:microsoft.quantum.errorcorrection.logicalregister> `= Qubit[]`: wskazuje, że rejestr qubits powinien być interpretowany jako blok kodu poprawiania błędów.
- <xref:microsoft.quantum.errorcorrection.syndrome> `= Result[]`: wskazuje, że Tablica wyników pomiaru powinna być interpretowana jako Syndrome mierzona w bloku kodu.
- <xref:microsoft.quantum.errorcorrection.recoveryfn> `= (Syndrome -> Pauli[])`: wskazuje, że funkcja *klasyczna* powinna być używana do interpretowania Syndrome i zwracać poprawkę, która powinna zostać zastosowana.
- <xref:microsoft.quantum.errorcorrection.encodeop> `= ((Qubit[], Qubit[]) => LogicalRegister)`: wskazuje, że operacja przyjmuje qubits reprezentujący dane oraz świeżą Ancilla qubits w celu utworzenia bloku kodu poprawiania błędów.
- <xref:microsoft.quantum.errorcorrection.decodeop> `= (LogicalRegister => (Qubit[], Qubit[]))`: wskazuje, że operacja dekomponowa blok kodu błędu poprawianie kodu do qubits danych i Ancilla qubits używany do reprezentowania informacji o Syndrome.
- <xref:microsoft.quantum.errorcorrection.syndromemeasop> `= (LogicalRegister => Syndrome)`: wskazuje operację, która powinna być używana do wyodrębniania informacji Syndrome z bloku kodu, bez zakłócania stanu chronionego przez kod.

Na koniec, Canon udostępnia typ <xref:microsoft.quantum.errorcorrection.qecc>, aby zebrać inne typy wymagane do zdefiniowania kodu korygującego błąd QUANTUM. Skojarzona z każdym z kodów Quantum dla stabilizatorów to długość kodu $n $, numer $k $ qubits logicznego i minimalna odległość $d $, często wygodnie pogrupowane w notacji ⟦ $n $, $k $, $d $ ⟧. Na przykład funkcja <xref:microsoft.quantum.errorcorrection.bitflipcode> definiuje kod przewrócenia ⟦ 3, 1, 1 ⟧:

```qsharp
let encodeOp = EncodeOp(BitFlipEncoder);
let decodeOp = DecodeOp(BitFlipDecoder);
let syndMeasOp = SyndromeMeasOp(MeasureStabilizerGenerators([
    [PauliZ, PauliZ, PauliI],
    [PauliI, PauliZ, PauliZ]
], _, MeasureWithScratch));
let code = QECC(encodeOp, decodeOp, syndMeasOp);
```

Należy zauważyć, że typ `QECC` *nie zawiera funkcji* odzyskiwania.
Dzięki temu można zmienić funkcję odzyskiwania używaną w korygowaniu błędów bez zmiany definicji samego kodu; Ta możliwość jest szczególnie przydatna w przypadku uwzględniania informacji zwrotnych z pomiarów scharakteryzowania w modelu przyjętym przez funkcję odzyskiwania.

Po zdefiniowaniu kodu w ten sposób możemy użyć operacji <xref:microsoft.quantum.errorcorrection.recover> do odzyskania po błędach:

```qsharp
let code = BitFlipCode();
let fn = BitFlipRecoveryFn();
let X0 = ApplyPauli([PauliX, PauliI, PauliI], _);
using (scratch = Qubit[nScratch]) {
    let logicalRegister = encode(data, scratch);
    // Cause an error.
    X0(logicalRegister);
    Recover(code, fn, logicalRegister);
    let (decodedData, decodedScratch) = decode(logicalRegister);
    ApplyToEach(Reset, decodedScratch);
}
```

Więcej szczegółów znajduje się w [przykładowym kodzie przerzucania bitowego](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code).

Oprócz kodu przewrócenia bitowego Q # Canon jest dostarczany z implementacjami [pięciu qubit idealnego kodu](https://arxiv.org/abs/quant-ph/9602019), a [kod siedmiu qubit](https://arxiv.org/abs/quant-ph/9705052), oba mogą poprawić dowolny błąd pojedynczego qubit.
