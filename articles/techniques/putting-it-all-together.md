---
title: 'Techniki Q # — całą całość | Microsoft Docs'
description: 'Techniki Q # — umieszczanie ich razem'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: f65b3e260f98a7a90da13b62edd6cc63d200f5af
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183271"
---
# <a name="putting-it-all-together-teleportation"></a>Wszystkie razem: teleportowanie #
Wróćmy do przykładowego obwodu teleportowego zdefiniowanego w [obwodach Quantum](xref:microsoft.quantum.concepts.circuits). Zamierzamy użyć tego przykładu do zilustrowania koncepcji, które już poznasz. W przypadku osób, które nie znają tego teorii, należy zapoznać się z opisem teleportów Quantum, a następnie wskazówki dotyczące implementacji kodu w Q #. 

## <a name="quantum-teleportation-theory"></a>Teleportowanie Quantum: teoretyczne
Teleportowanie Quantum jest techniką wysyłania nieznanego stanu Quantum (do którego odwołuje się jako "__wiadomość__") z qubit w jednej lokalizacji do qubit w innej lokalizacji (odwołujemy się do tych qubits jako "__tutaj__" i "__tam__"). odpowiednio). Możemy reprezentować nasz __komunikat__ jako wektor przy użyciu notacji Dirac: 

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Stan qubit __komunikatu__ jest nieznany dla nas, ponieważ nie znam wartości $ \Alpha $ i $ \beta $.

### <a name="step-1-create-an-entangled-state"></a>Krok 1. Tworzenie stanu Entangled
Aby wysłać __wiadomość__ , której potrzebujemy, qubit w __tym miejscu__ , aby Entangled __z qubit.__ Można to osiągnąć, stosując bramę Hadamard, a następnie bramę CNOT. Przyjrzyjmy się zapisowi matematycznemu za te operacje na bramie.

Zaczniemy od qubits __tutaj__ __i w__ stanie $ \ket{0}$. Po Entangling tych qubits są w stanie:

$ $ \ket{\phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $

### <a name="step-2-send-the-message"></a>Krok 2. wysłanie wiadomości
Aby wysłać __wiadomość__ , należy najpierw zastosować bramę CNOT z __komunikatem__ qubit i __w tym miejscu__ qubit jako dane wejściowe ( __komunikat__ qubit o kontrolce, a w tym __miejscu__ qubit to element docelowy qubit, w tym wystąpieniu). Ten stan danych wejściowych można napisać:

$ $ \ket{\psi}\ket{\phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $

Rozszerza to:

$ $ \ket{\psi}\ket{\phi ^ +} = \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} \frac{\beta}{\sqrt{2}} \ket{111} $ $

W wyniku tego Brama CNOT przerzuca element docelowy qubit, gdy kontrolka qubit ma wartość 1. Na przykład, dane wejściowe klasy $ \ket{000}$ nie spowodują zmian, ponieważ pierwszy qubit (formant) to 0. Należy jednak wziąć pod przypadek, gdzie pierwszy qubit to 1 — na przykład dane wejściowe $ \ket{100}$. W tym przypadku dane wyjściowe to $ \ket{110}$, ponieważ drugi qubit (obiekt docelowy) jest przerzucany przez bramę CNOT.

Teraz Rozważmy nasze dane wyjściowe po przejściu bramy CNOT na nasze dane wejściowe powyżej. Wynik:

$ $ \frac{\Alpha}{\sqrt{2}} \ket{000} + \frac{\Alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $

Następnym krokiem do wysłania __wiadomości__ jest zastosowanie bramy Hadamard do __wiadomości__ qubit (to pierwsze qubit każdego z tych terminów). 

W wyniku tego Brama Hadamard wykonuje następujące czynności:

Dane wejściowe | Dane wyjściowe
---------------------------| ---------------------------------------------------------------
$ \ket{0}$  | $ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $
$ \ket{1}$  | $ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $

Jeśli stosujemy bramę Hadamard do pierwszego qubit każdego z powyższych danych wyjściowych powyżej, otrzymamy następujący wynik:

$ $ \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\Alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{ \sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $

Należy zauważyć, że każdy termin ma $2 \frac{1}{\sqrt{2}} $. Możemy pomnożyć te wartości, dając następujące wyniki:

$ $ \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\Alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $

Wartość $ \frac{1}{2}$ jest wspólna dla każdego warunku, dzięki czemu możemy teraz wykonać ją poza nawiasami:

$ $ \frac{1}{2}\big [\Alpha (\ket{0} + \ket{1}) \ket{00} + \Alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $

Następnie można rozmnożyć nawiasy dla każdego terminu, podając:

$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001} \beta\ket{101}\big] $ $

### <a name="step-3-measure-the-result"></a>Krok 3. mierzenie wyniku

Ze względu __na to,__ __że__ Entangled, wszelkie pomiary w __tym miejscu__ będą miały wpływ na stan tej __lokalizacji__. Jeśli mierzę pierwszy i drugi qubit (__komunikat__ i __tutaj__), możemy dowiedzieć się, jaki stan __istnieje__ , ze względu na tę właściwość Entanglement. 

* Jeśli mierzę i uzyskasz wynik 00, nadpozycja zwija, pozostawiając tylko warunki zgodne z tym wynikiem. To $ \alpha\ket{000} + \beta\ket{001}$. Można ją refaktoryzację do $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $. W związku z tym, jeśli mierzę pierwszy i drugi qubit jako 00, wiemy, że trzecia __qubit, w__stanie $ (\alpha\ket{0} + \beta\ket{1}) $.
* Jeśli mierzę i otrzymasz wynik 01, nadpozycja zwija, pozostawiając tylko warunki zgodne z tym wynikiem. To $ \alpha\ket{011} + \beta\ket{010}$. Można ją refaktoryzację do $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $. W związku z tym, jeśli mierzę pierwszy i drugi qubit jako 01, wiemy, że trzecia __qubit, w__stanie $ (\alpha\ket{1} + \beta\ket{0}) $.
* Jeśli mierzę i otrzymasz wynik 10, nadpozycja zwija, pozostawiając tylko warunki zgodne z tym wynikiem. To jest $ \alpha\ket{100}-\beta\ket{101}$. Można ją refaktoryzację do $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $. W związku z tym, jeśli mierzę pierwszy i drugi qubit na 10, wiemy, że trzecia __qubit, w__stanie $ (\alpha\ket{0}-\beta\ket{1}) $.
* Jeśli mierzę i uzyskasz wynik 11, nadpozycja zwija, pozostawiając tylko warunki zgodne z tym wynikiem. To jest $ \alpha\ket{111}-\beta\ket{110}$. Można ją refaktoryzację do $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $. W związku z tym, jeśli mierzę pierwszy i drugi qubit jako 11, wiemy, że trzecia __qubit, w__stanie $ (\alpha\ket{1}-\beta\ket{0}) $.

### <a name="step-4-interpret-the-result"></a>Krok 4. interpretowanie wyniku

Jako przypomnienie oryginalna __wiadomość__ , którą chcemy wysłać, to:

$ $ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $ $

Musimy __uzyskać qubit w__ tym stanie, tak aby otrzymany stan był zamierzony. 

* Jeśli wartość jest mierzona i otrzyma wynik __00, trzecia qubit, w__stanie $ (\alpha\ket{0} + \beta\ket{1}) $. Ponieważ jest to zamierzony __komunikat__, nie jest wymagana żadna zmiana.
* W przypadku pomiaru i otrzymaniu wyniku 01 qubit __trzecia, w__stanie $ (\alpha\ket{1} + \beta\ket{0}) $. Różni się to od zamierzonego __komunikatu__, jednak zastosowanie niebramy daje nam żądany stan $ (\alpha\ket{0} + \beta\ket{1}) $.
* W przypadku pomiaru i uzyskaniu wyniku 10 trzecia __qubit, w__stanie $ (\alpha\ket{0}-\beta\ket{1}) $. Różni się to od zamierzonego __komunikatu__, ale zastosowanie bramy z daje nam żądany stan $ (\alpha\ket{0} + \beta\ket{1}) $.
* W przypadku pomiaru i uzyskaniu wyniku 11 qubit __trzecia, w__stanie $ (\alpha\ket{1}-\beta\ket{0}) $. Różni się to od zamierzonego __komunikatu__, ale zastosowanie bramy nie powoduje, że jest ona pożądanym stanem $ (\alpha\ket{0} + \beta\ket{1}) $.

Aby podsumować, jeśli mierzę i pierwszy qubit to 1, stosowana jest brama Z. Jeśli mierzę, a drugi qubit wynosi 1, zostanie zastosowana Brama nie.

### <a name="summary"></a>Podsumowanie
Poniższa poniżej znajduje się książka tekstowa Quantum obwodu, który implementuje teleport. Od lewej do prawej można zobaczyć:
- Krok 1. Entangling tutaj i __w__ __tym miejscu__ , stosując bramę HADAMARD i bramę CNOT.
- Krok 2. Wysyłanie __komunikatu__ przy użyciu bramy CNOT i bramy Hadamard.
- Krok 3. przejęcie pomiaru pierwszego i drugiego qubits, __komunikatu__ i __tutaj__.
- Krok 4. stosowanie bramy NOT bramowej lub Z, w zależności od wyniku pomiaru w kroku 3.

!["Teleport (MSG: qubit, tam: qubit): Unit"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Teleportowanie Quantum: kod

Mamy nasz Obwód na teleportowanie Quantum:

!["Teleport (MSG: qubit, tam: qubit): Unit"](~/media/teleportation.svg)

Teraz możemy przetłumaczyć każdy z kroków tego obwodu Quantum na Q #.

### <a name="step-0-definition"></a>Krok 0: definicja
Gdy wykonujesz teleportowanie, musimy znać __komunikat__ , który chcemy wysłać, i gdzie chcemy go wysłać. Z tego powodu rozpoczynamy od zdefiniowania nowej operacji teleport, która ma dwa qubits jako argumenty `msg` i `there`:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Musimy również przydzielić `here` qubit, które są dostępne w bloku `using`:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Krok 1. Tworzenie stanu Entangled
Następnie możemy utworzyć parę Entangled między `here` i `there` przy użyciu operacji @"microsoft.quantum.primitive.h" i @"microsoft.quantum.primitive.cnot":

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Krok 2. wysłanie wiadomości
Następnie użyjemy kolejnych bram $ \operatorname{CNOT} $ i $H $, aby przenieść qubit wiadomości:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Krok 3 & 4: mierzenie i interpretacja wyniku
Na koniec używamy @"microsoft.quantum.primitive.m" do wykonywania pomiarów i wykonywania niezbędnych operacji bram w celu uzyskania żądanego stanu, zgodnie z instrukcją `if`:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

Spowoduje to zakończenie definicji naszego operatora teleportowego, aby można było cofnąć alokację `here`, zakończyć treść i zakończyć operację.

```qsharp
    }
}
```
