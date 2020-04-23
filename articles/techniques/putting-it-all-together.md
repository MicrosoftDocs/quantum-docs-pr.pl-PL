---
title: Techniki Q# - Łącząc to wszystko razem
description: Przejdź przez podstawowy program Q#, który demonstruje teleportację kwantową.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030569"
---
# <a name="putting-it-all-together-teleportation"></a>Wszystko razem: Teleportacja #
Wróćmy do przykładu obwodu teleportacji zdefiniowanego w [obwodach kwantowych.](xref:microsoft.quantum.concepts.circuits) Wykorzystamy to do zilustrowania pojęć, których do tej pory się nauczyliśmy. Wyjaśnienie teleportacji kwantowej znajduje się poniżej dla tych, którzy nie są zaznajomieni z teorią, a następnie instruktaż implementacji kodu w Q#. 

## <a name="quantum-teleportation-theory"></a>Teleportacja kwantowa: Teoria
Teleportacja kwantowa jest techniką wysyłania nieznanego stanu kwantowego (który będziemy odnosić się jako "__wiadomość__") z kubitu w jednym miejscu do kubitu w innym miejscu (będziemy odnosić się do tych kubitów jako "__tutaj__" i "__tam__', odpowiednio). Możemy reprezentować nasze __przesłanie__ jako wektor za pomocą notacji Dirac: 

$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$

Stan kubitu __wiadomości__ jest nam nieznany, ponieważ nie znamy wartości $\alpha$ i $\beta$.

### <a name="step-1-create-an-entangled-state"></a>Krok 1: Tworzenie stanu splątanego
Aby wysłać __wiadomość__ musimy kubit __tutaj__ być uwikłany w kubit __tam__. Osiąga się to poprzez zastosowanie bramy Hadamarda, a następnie bramy CNOT. Spójrzmy na matematykę za tymi operacjami bramek.

Zaczniemy od kubitów __tu__ i __tam__ zarówno w{0}stanie $\ket $. Po oplątanie tych kubitów, są one w stanie:

$$ \ket{\phi^+} ={1}\frac{2}{\sqrt{00} }(\ket + \ket{11}) $$

### <a name="step-2-send-the-message"></a>Krok 2: Wyślij wiadomość
Aby wysłać __wiadomość,__ najpierw stosujemy bramę CNOT z kubitem __wiadomości__ i __tutaj__ kubit jako dane wejściowe (kubit __wiadomości__ jest formantem, a kubit __tutaj__ jest kubitem docelowym, w tym przypadku). Ten stan wejściowy może być zapisany:

$${0} \ket{\psi}\ket{\phi^+} = (\alpha\ket +{1}\beta\ket{1})(\frac {\sqrt{2}}(\ket{00} + \ket{11})) $$

Spowoduje to rozszerzenie o:

$$ \ket{\psi}\ket{\phi^+} ={2}\frac{\alpha}{\sqrt{000} }\ket + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} +{2}\frac{/beta}{\sqrt }{\sqrt }{\pl/ket}{\ket}{\ket}{\ket}{\ket}{\ket}{\ket}\ket}\ket}\ket}\ket }\ket{111} $$

Przypominamy, że brama CNOT odwraca kubit docelowy, gdy kubit kontrolny wynosi 1. Na przykład wejście $\ket{000}$ spowoduje brak zmian, ponieważ pierwszy kubit (formant) wynosi 0. Jednak weź przypadek, w którym pierwszy kubit jest 1 -{100}na przykład wejście $\ket $. W tym przypadku dane wyjściowe{110}to $\ket $ jako drugi kubit (cel) jest odwrócony przez bramę CNOT.

Rozważmy teraz nasze dane wyjściowe, gdy brama CNOT działała na nasze dane wejściowe powyżej. Rezultatem jest:

{2}$$ \frac{\alpha}{\sqrt }\ket{000} + \frac{\alpha}{\sqrt{011} {2}{110} {2}{101} {2}}\ket + \frac{\beta}{\sqrt }\ket + \frac{\beta}{\sqrt }\ket $$

Następnym krokiem do wysłania __wiadomości__ jest zastosowanie bramy Hadamarda do kubitu __wiadomości__ (to pierwszy kubit każdego terminu). 

Przypominamy, że brama Hadamarda wykonuje następujące czynności:

Dane wejściowe | Dane wyjściowe
---------------------------| ---------------------------------------------------------------
$\ket{0}$  | $\frac{1}{\sqrt{2}}(\ket{0} +{1}\ket )$
$\ket{1}$  | $\frac{1}{\sqrt{2}}(\ket{0} -{1}\ket )$

Jeśli zastosujemy bramę Hadamarda do pierwszego kubitu każdego okresu naszej produkcji powyżej, uzyskamy następujący wynik:

$${2}\frac{\alpha}{\sqrt }(\frac{1}{\sqrt{2}}(\ket{1}{00} {2}{1}{2}{0} {1}{11} {2}{1}{2}{0} {1}{10} {2}{1}{2}{0} {1}{01} {0} + \ket ))\ket + \frac{\alpha}{\sqrt }(\frac {\sqrt }(\ket + \ket ))\ket + \frac{/beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket + \frac{\beta}{\sqrt }(\frac {\sqrt }(\ket - \ket ))\ket $$

Należy zauważyć, że każdy termin{1}ma dwa{2}$\frac {\sqrt }$ czynników. Możemy je pomnożyć, podając następujący wynik:

$$ \frac{\alpha}{2}(\ket{0} +{1}\ket{00} )\ket +{2}\frac{\alpha} (\ket{0} + \ket{1}{11} )\ket + \frac{\beta}{2}(\ket{0} - \ket{0} {1}{01} {1})\ket{10} + \frac{\beta}{2}(\ket - \ket )\ket $$

Współczynnik $\frac{1}{2}$ jest wspólny dla każdego terminu, więc możemy teraz zabrać go poza nawiasy:

$${1}{2}\frac \big[\alpha(\ket{0} +{1}\ket{00} )\ket +{0} \alpha(\ket + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket - \ket{0} {1})\ket{01}\big] $$

Następnie możemy pomnożyć nawiasy dla każdego terminu dając:

{1}{2}$$ \frac \big[\alpha\ket{000} + \alpha\ket{100} +{011} \alpha\ket{111} + \alpha\ket{010} + \beta\ket -{001} \beta\ket{101}{110} + \beta\ket - \beta\ket \ket \big] $$

### <a name="step-3-measure-the-result"></a>Krok 3: Zmierz wynik

Ze względu na __tu__ i __nie__ jest splątane, każdy pomiar __tutaj__ wpłynie na stan __tam__. Jeśli zmierzymy pierwszy i drugi kubit (__wiadomość__ i __tutaj__) możemy dowiedzieć się, w jakim stanie __jest,__ ze względu na tę właściwość splątania. 

* Jeśli zmierzymy i uzyskamy wynik 00, superpozycja upada, pozostawiając tylko warunki zgodne z tym wynikiem. To $\alpha\ket{000} +\beta\ket{001}$. Można to z refaktoryzować{00}do $\ket (\alpha\ket{0} +/beta\ket{1})$. Dlatego jeśli zmierzymy pierwszy i drugi kubit na 00, wiemy, że trzeci kubit, __tam__,{0} jest w stanie{1}$(\alpha\ket +\beta\ket )$.
* Jeśli zmierzymy i uzyskamy wynik 01, superpozycja upada, pozostawiając tylko warunki zgodne z tym wynikiem. To $\alpha\ket{011} +\beta\ket{010}$. Można to z refaktoryzować{01}do $\ket (\alpha\ket{1} +/beta\ket{0})$. Dlatego jeśli zmierzymy pierwszy i drugi kubit na 01, wiemy, że trzeci kubit, __tam__,{1} jest w stanie{0}$(\alpha\ket +\beta\ket )$.
* Jeśli zmierzymy i uzyskamy wynik 10, superpozycja upada, pozostawiając tylko warunki zgodne z tym wynikiem. To jest $\alpha\ket{100} -\beta\ket{101}$. Można to z refaktoryzować{10}do $\ket (\alpha\ket{0} -\beta\ket{1})$. Dlatego jeśli zmierzymy pierwszy i drugi kubit na 10, wiemy, że trzeci kubit, __tam__,{0} jest w stanie{1}$(\alpha\ket -\beta\ket )$.
* Jeśli zmierzymy i uzyskamy wynik 11, superpozycja upada, pozostawiając tylko warunki zgodne z tym wynikiem. To jest $\alpha\ket{111} -\beta\ket{110}$. Można to z refaktoryzować{11}do $\ket (\alpha\ket{1} -\beta\ket{0})$. Dlatego jeśli zmierzymy pierwszy i drugi kubit na 11, wiemy, że trzeci kubit, __tam__,{1} jest w stanie{0}$(\alpha\ket -\beta\ket )$.

### <a name="step-4-interpret-the-result"></a>Krok 4: Interpretowanie wyniku

Przypominamy, że oryginalna __wiadomość,__ którą chcieliśmy wysłać, brzmiała:

$$ \ket{\psi} = \alpha\ket{0} +{1} \beta\ket $$

Musimy wprowadzić __tam__ kubit do tego stanu, aby otrzymane państwo było tym, które było zamierzone. 

* Jeśli zmierzyliśmy i uzyskaliśmy wynik 00, to trzeci kubit, __tam__, jest{0} w stanie $(\alpha\ket +\beta\ket{1})$. Ponieważ jest to zamierzony __komunikat,__ nie jest wymagana żadna zmiana.
* Jeśli zmierzyliśmy i uzyskaliśmy wynik 01, to trzeci kubit, __tam__, jest{1} w stanie $(\alpha\ket +\beta\ket{0})$. Różni się to od zamierzonego __komunikatu__, jednak zastosowanie nie bramy daje{0} nam żądany stan{1}$(\alpha\ket +\beta\ket )$.
* Jeśli zmierzyliśmy i uzyskaliśmy wynik 10, to trzeci kubit, __tam__, jest{0} w stanie $(\alpha\ket -\beta\ket{1})$. Różni się to od zamierzonego __komunikatu__, jednak zastosowanie bramy Z daje{0} nam żądany stan{1}$(\alpha\ket +\beta\ket )$.
* Jeśli zmierzyliśmy i uzyskaliśmy wynik 11, to trzeci kubit, __tam__, jest{1} w stanie $(\alpha\ket -\beta\ket{0})$. Różni się to od zamierzonego __komunikatu__, jednak zastosowanie nie bramy, po której następuje{0} brama Z,{1}daje nam żądany stan $(\alpha\ket +\beta\ket )$.

Podsumowując, jeśli zmierzymy, a pierwszy kubit wynosi 1, stosowana jest brama Z. Jeśli zmierzymy, a drugi kubit wynosi 1, zostanie zastosowana brama NOT.

### <a name="summary"></a>Podsumowanie
Poniżej pokazano tekst książki obwodu kwantowego, który implementuje teleportacji. Przechodząc od lewej do prawej, możesz zobaczyć:
- Krok 1: Oplątanie __tu__ i __ówdź,__ stosując bramę Hadamarda i bramę CNOT.
- Krok 2: Wysłanie __wiadomości__ za pomocą bramy CNOT i bramy Hadamarda.
- Krok 3: Pomiar pierwszego i drugiego kubitów, __wiadomość__ i __tutaj__.
- Krok 4: Zastosowanie bramy NOT lub Z, w zależności od wyniku pomiaru w kroku 3.

!["Teleport(msg : Qubit, tam: Qubit) : Jednostka"](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a>Teleportacja kwantowa: Kod

Mamy nasz obwód do teleportacji kwantowej:

!["Teleport(msg : Qubit, tam: Qubit) : Jednostka"](~/media/teleportation.svg)

Możemy teraz przetłumaczyć każdy z kroków w tym obwodzie kwantowym na Q#.

### <a name="step-0-definition"></a>Krok 0: Definicja
Kiedy przeprowadzamy teleportację, musimy znać __wiadomość,__ którą chcemy wysłać i gdzie chcemy ją wysłać __(tam).__ Z tego powodu rozpoczynamy od zdefiniowania nowej operacji Teleport, która `msg` jest `there`podana dwa kubity jako argumenty, i:

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

Musimy również przydzielić kubit, `here` który `using` osiągamy za pomocą bloku:

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a>Krok 1: Tworzenie stanu splątanego
Następnie możemy utworzyć splątaną `here` `there` parę między @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" i za pomocą operacji i:

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a>Krok 2: Wyślij wiadomość
Następnie używamy następnego $\operatorname{CNOT}$ i $H$ bramy, aby przenieść nasz kubit wiadomości:

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a>Krok 3 & 4: Pomiar i interpretacja wyniku
Na koniec używamy @"microsoft.quantum.intrinsic.m" do wykonywania pomiarów i wykonywania niezbędnych operacji bramy, aby uzyskać `if` pożądany stan, zgodnie z instrukcjami:

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a>Krok 5: Ponowne uruchomienie rejestru kubitów

Na koniec każdej operacji Q# musimy pozwolić kubity w stanie{0}$\ket $. Możemy użyć, @"microsoft.quantum.intrinsic.reset" aby ponownie uruchomić wszystkie kubity do stanu zerowego, a to zakończy naszą operację.

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


