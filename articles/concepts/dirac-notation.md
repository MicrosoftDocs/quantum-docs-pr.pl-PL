---
title: Notacja Diraca
description: Dowiedz się więcej o używaniu notacji Dirac do reprezentowania Stanów Quantum i symulowania operacji Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 958910452109fc722999acddd70894c458e38357
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630381"
---
# <a name="dirac-notation"></a>Notacja Dirac

Podczas gdy notacja wektora kolumn jest powszechna w algebry liniowym, często jest to bardzo trudne w przypadku przetwarzania w usłudze Quantum, zwłaszcza w przypadku wielu qubits.  Na przykład, gdy definiujemy $ \psi $ jako wektor, nie jest wyraźnie jasne, czy $ \psi $ jest wierszem lub wektorem kolumny.  W związku z tym, jeśli $ \phi $ i $ \psi $ są wektorami, to równie niejasne, jeśli $ \phi \psi $ jest nawet zdefiniowane, ponieważ kształty $ \phi $ i $ \psi $ mogą być niejasne w kontekście.  Oprócz niejednoznaczności kształtów wektorów, wyraźne proste wektory korzystające z notacji liniowej algebraicznych wprowadzonej wcześniej mogą być bardzo uciążliwe. Jeśli na przykład chcemy opisać $ stan $n-qubit, gdy każdy qubit przyjmuje wartość $0, $ wyrażamy stan jako 

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } . $$  

Ocenianie tego produktu dwuskładnikowego jest niepraktyczne, ponieważ wektor bazuje na wykładniczo dużej przestrzeni i dlatego ten zapis jest w rzeczywistości najlepszym opisem stanu, który można podać przy użyciu poprzedniej notacji.  

[*Notacja Dirac*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) rozwiązuje te problemy poprzez przedprezentowanie nowego języka w celu dopasowania do precyzyjnej potrzeby Quantum Mechanics.  Z tego powodu zaleca się, aby czytelnik nie przeglądał przykładów w tej sekcji jako sztywna recepta opisującą sposób opisywania Stanów Quantum, ale zachęca czytelnika do wyświetlania takich rozwiązań jak sugestie, których można użyć do zwięzłego wyrażania koncepcji Quantum.

Istnieją dwa typy wektorów w notacji Dirac: wektor *bra* i wektor *KET* , tak jak w przypadku łączenia się z nimi w formie *hamulca* lub wewnętrznego produktu.  Jeśli $ \psi $ jest wektorem kolumny, możemy napisać ją w notacji Dirac jako $ \ket { \psi } $, gdzie $ \ket { \cdot $ oznacza, } że jest to wektor kolumny jednostki, czyli wektor *KET* .  Podobnie wektor wiersza $ \psi ^ \dagger $ jest wyrażony jako $ \bra { \psi } $. Innymi słowy, funkcja $ \psi ^ \dagger $ jest uzyskiwana przez zastosowanie złożonej sprzężonej wartości wejściowej do elementów transponowanych $ \psi $ . Notacja bra-KET bezpośrednio oznacza, że $ \braket { \psi | \psi } $ to wewnętrzny produkt wektora $ \psi $ , który jest z definicji $1 $ .  

Ogólnie rzecz biorąc, jeśli $ \psi $ i $ \phi $ są wektorami stanu Quantum, ich wewnętrzny produkt to $ \braket { \phi | \psi $, } co oznacza, że prawdopodobieństwo mierzenia stanu $ \ket { \psi $ to $ } \ket { \phi } $ to $ | \braket { \phi | \psi } | ^ 2 $ .  

Poniższa Konwencja służy do opisywania Stanów Quantum, które kodują wartości zero i jeden (qubit podstawowe Stany obliczeniowe):

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Przykład: reprezentacja operacji Hadamard z notacją Dirac

Poniższy zapis jest często używany do opisywania Stanów, które wynikają z zastosowania bramy Hadamard do $ \ket{0 } $ i $ \ket{1 } $ (które odpowiadają wektorom jednostek w kierunkach $ + x $ i $-x $ w sferze Bloch):

$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = \ket { -}.
$$

Te Stany można również rozszerzyć przy użyciu notacji Dirac jako kwoty $ \ket{0 } $ i $ \ket{1 } $:

$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad \ket { -} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).
$$

### <a name="computational-basis-vectors"></a>Wektory podstawy obliczeniowej
Pokazuje to, dlaczego te Stany są często nazywane *zasadami obliczeniowymi*: każdy stan Quantum może zawsze być wyrażony jako sumy wektorów obliczeniowych, a takie kwoty są łatwo wyrażone przy użyciu notacji Dirac.  Jest to również prawdą, że Stany $ \ket { +} $ i $ \ket { -} $ również tworzą podstawę dla Stanów Quantum.  Można to sprawdzić z faktu, że

$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\ket { +}-\ket { -}).
$$

Przykładem notacji Dirac jest rozważenie klasy hamulca $ \braket{0 | 1 } $, która jest wewnętrznym produktem od $0 $ do $1 $ .  Może być zapisany jako 

$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end { bmatrix } = 0. $ $

Wskazuje to, że $ \ket{0 } $ i $ \ket{1 } $ są wektorami prostopadłymi, co oznacza, że $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ .  Również według definicji $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , co oznacza, że dwa wektory obliczeniowe mogą być również wywołane *orthonormal*.
Te właściwości orthonormal będą przydatne w poniższym przykładzie. Jeśli mamy stan $ \ket { \psi } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $, ponieważ $ \braket{1 | 0 } = 0 $ prawdopodobieństwo pomiaru $1 $ jest  

$ $ \big | \braket{1 | \psi } \big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \right | ^ 2 = \frac{9 } {25 } . $ $ 

### <a name="tensor-product-notation"></a>Notacja iloczynu
Notacja Dirac obejmuje również niejawną strukturę produktu w ramach tego programu.  Jest to ważne, ponieważ w przypadku przetwarzania Quantum wektor stanu opisany przez dwa nieskorelowane rejestry Quantum jest iloczynów dwustanowych.  Zwięzłe opisywanie struktury produktu dwuczęściowego lub jego braku, jest istotne, jeśli chcesz wyjaśnić obliczenia Quantum.  Struktura iloczynu dwuetapowego oznacza, że możemy napisać $ \psi \otimes \phi $ dla wszystkich dwóch wektorów Stanów Quantum $ \phi $ i $ \psi $ jako $ \ket { \psi } \ket { \phi } $, czasami jawnie napisane jako $ \ket { \psi } \otimes \ket { \phi } $, ale $ nie jest to konieczne.  Na przykład stan z dwoma qubits zainicjowany do stanu zero jest określony przez

$ $ \begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ \end{ bmatrix } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } .
$$

Analogicznie, stan $ \ket{p } $ dla liczby całkowitej $p $ reprezentuje stan Quantum, który koduje w postaci binarnej reprezentację liczby całkowitej $p $ .  Jeśli na przykład chcemy wyrazić liczbę $5 $ przy użyciu niepodpisanego kodowania binarnego, możemy to samo wyrazić jako

$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .
$$

W tej notacji $ \ket{0 } $ nie musi odwoływać się do stanu jednego qubit, ale raczej *Rejestr qubit* przechowujący kodowanie binarne $0 $ .  Różnice między tymi dwiema notacjami są zwykle jasne w kontekście.  Ta konwencja jest przydatna do uproszczenia pierwszego przykładu, który można napisać w jeden z następujących sposobów:

$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \cdots \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Przykład: Opisywanie nadpozycji z notacją Dirac
Innym przykładem, jak można użyć notacji Dirac do opisania stanu Quantum, należy wziąć pod uwagę następujące równoważne sposoby pisania stanu Quantum, który jest równe nadpozycja dla każdego możliwego ciągu bitowego o długości $n$

$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {\otimes n } .
$$

W tym miejscu możesz zazastanawiać się, dlaczego suma $ wyniesie od $0 do $2 ^ {n } -1 $ dla $n $ bitowej.  Najpierw należy zauważyć, że istnieją co } najmniej dwie konfiguracje, które $n $ mogą wykonać usługa BITS.  Można to sprawdzić przez zanotowanie, że jeden bit może przyjmować $2 $ wartości, ale dwa bity mogą przyjmować $4 $ wartości i tak dalej. Ogólnie rzecz biorąc, oznacza to, że istnieją wartości $2 ^ n $ inne możliwe ciągi bitowe, ale największą wartość zakodowaną w dowolnym z nich $1 \cdots 1 = 2 ^ n-1 $ i tym samym jest górny limit liczby.
Jako notatka po stronie, w tym przykładzie nie użyto elementu $ \ket { +} ^ {\otimes n } = \ket { +} $ w trybie analogowym do $ \ket{0 } ^ {\otimes n } = \ket{0 } $, ponieważ ta konwencja notacji jest zwykle zarezerwowana dla stanu podstawy obliczeń z każdą qubit zainicjowaną na zero.  Chociaż taka konwencja byłaby w tym przypadku rozsądna, nie jest ona stosowana w literaturze obliczeniowej Quantum.

### <a name="expressing-linearity-with-dirac-notation"></a>Wyrażanie liniowości przy użyciu notacji Dirac
Kolejną cechą notacji Dirac jest fakt, że jest on liniowy.  Jeśli chcemy napisać w przypadku czterech wektorów stanu Quantum, 

$ $ (\Alpha \ket { \psi } + \beta \ket { \phi } ) \otimes (\gamma \ket { \chi } + \delta \ket { \omega } ) = \Alpha \gamma \ket { \psi } \ket { \chi } + \Alpha \delta \ket { \psi \ket \omega } { } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \phi \delta \ket { } \ket { \omega } . $ $

Oznacza to, że można rozpowszechnić notację iloczynu dwukierunkowego w notacji Dirac, aby zapewnić, że produkty Dwupunktowe między wektorami stanu kończą się podobnie jak zwykłe mnożenia.

Wektory bra są zgodne z podobną Konwencją do KET wektorów.  Na przykład wektor $ \bra { \psi } \bra { \phi } $ jest odpowiednikiem wektora stanu $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ . Jeśli KET Vector $ \ket { \psi } $ to $ \Alpha \ket{0 } + \beta \ket{1 } $, to bra wektorowa wersja wektora to $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra{0 \Alpha } ^ * + \bra{1 } \beta ^ *) $.

Załóżmy na przykład, że chcemy obliczyć prawdopodobieństwo mierzenia stanu $ \ket { \psi } = \frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } $ przy użyciu programu Quantum do mierzenia Stanów na wartość $ \ket { +} $ lub $ \ket { -} $. Następnie prawdopodobieństwo, że dane urządzenie będzie miało stan $ \ket { -} $ to 

$ $ | \braket { -| \psi } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \right | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \right | ^ 2 = \frac{1 } {50 } . $ $

Fakt, że znak ujemny pojawia się w obliczeniach prawdopodobieństwa, jest manifestem wpływów Quantum, który jest jednym z mechanizmów, za pomocą których przetwarzanie Quantum uzyskuje korzyści w porównaniu do klasycznego przetwarzania danych.

## <a name="ketbra-or-outer-product"></a>ketbra lub zewnętrzny produkt
Ostatni element omawiany w notacji Dirac jest produktem *ketbra* lub zewnętrznym.  Zewnętrzny produkt jest reprezentowany w notacjach Dirac jako $ \ket { \psi } \bra { \phi } $ i czasami nazywa się ketbras, ponieważ Bras i kets występuje w kolejności odwrotnej jako brakets.  Produkt zewnętrzny jest definiowany za pośrednictwem mnożenia macierzy jako $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ dla wektorów stanu Quantum $ \psi $ i $ \phi $ .  Najprostszym i raczej najbardziej typowym przykładem tego zapisu jest

$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end { bmatrix } \qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{ bmatrix } 0&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end { bmatrix } .
$$

Ketbras są często nazywane projektorami, ponieważ projektuje stan Quantum do ustalonej wartości.  Ponieważ te operacje nie są jednostkowymi jednostkami (i nie zachowują nawet normy wektora), nie powinny być niezależne, że komputer Quantum nie może w sposób jednoznaczny zastosować projektora.  Jednak projektory wykonują atrakcyjne zadanie opisujące akcję, którą mierzy w stanie Quantum.  Na przykład jeśli mierzy się stan $ \ket { \psi } $ to $0 $ , wynikowa transformacja, którą stan środowiska w wyniku pomiaru wynosi

  $ $ \ket { \psi } \rightarrow \frac { (\ket{0 } \bra{0 } ) \ket { \psi } } {| \braket{0 | \psi } |} = \ket{0 } , $ $

ponieważ jeden z nich oczekuje na zmierzenie stanu i znalezienie go jako $ \ket{0 } $.  Aby wykonać ponownie iteracje, takie projektory nie mogą być stosowane do stanu na komputerze Quantum w sposób deterministyczny.  Zamiast tego można je najlepiej zastosować losowo z wynikiem $ \ket{0 } $, który pojawia się z pewnymi stałymi prawdopodobieństwami.  Prawdopodobieństwo pomyślnego pomiaru może być zapisywane jako oczekiwana wartość rzutnika Quantum w stanie

$ $ \bra { \psi } (\ket{0 } \bra{0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2, $ $

pokazuje, że projektory po prostu zapewniają nowy sposób wyrażania procesu pomiaru.

Jeśli zamiast tego będziemy rozważyć zmierzenie pierwszego qubit stanu wieloqubitowego na $1, $ możemy również opisać ten proces wygodnie przy użyciu projektorów i notacji Dirac:

$ $ P (\Text{First qubit = 1 } ) = \bra { \psi } \left (\ket{1 } \bra{1 } \otimes \boldone ^ {\otimes n-1 } \right) \ket { \psi } .
$$

W tym miejscu macierz tożsamości może być wygodnie zapisywana w notacji Dirac jako

$ $ \boldone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \end{ bmatrix } .
$$

W przypadku gdy istnieją dwa-qubits projektora można rozwinąć jako 

$ $ \ket{1 } \bra{1 } \otimes \id = \ket{1 } \bra{1 } \otimes (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .
$$

Możemy zobaczyć, że jest to zgodne z dyskusjami dotyczącymi prawdopodobieństwa pomiaru dla Stanów multiqubit przy użyciu notacji wektorów kolumn:

$ $ P (\Text{First qubit = 1 } ) = \psi ^ \dagger (e \_ {10} e \_ {10 } ^ \dagger + e \_ {11} e \_ {11 } ^ \dagger) \psi = | e \_ {10 } ^ \dagger \psi | ^ 2 + | e \_ {11 } ^ \dagger \psi | ^ 2, $ $

który pasuje do dyskusji o pomiarach wieloqubitowych.  Uogólnienie tego wyniku w przypadku wielu qubit, jednak jest nieco bardziej bezpośrednie do wyrażania przy użyciu notacji Dirac niż notacja wektora kolumn i jest całkowicie równoważne poprzedniej obróbce.

## <a name="density-operators"></a>Operatory gęstości

Innym przydatnym operatorem, który wyraża użycie notacji Dirac, jest *operator gęstości*, czasami również znany jako *operator stanu*.
Operator gęstości dla wektora stanu Quantum przyjmuje postać $ \rho = \ket { \psi } \bra { \psi } $.
Pojęcie to przedstawiające stan jako macierz, a nie wektor, jest często wygodne, ponieważ daje wygodną metodę reprezentowania obliczeń prawdopodobieństwa, a także umożliwia jednemu opisywaniu niepewności statystycznej i niepewności w ramach tego samego formalnego charakteru.
Ogólne operatory stanu Quantum, a nie wektory, są powszechnie dostępne w niektórych obszarach przetwarzania Quantum, ale nie są niezbędne do zrozumienia podstaw tego pola.
W przypadku interesującego czytnika zalecamy odczytanie jednej z książek referencyjnych, które znajdują się w temacie, [Aby uzyskać więcej informacji](xref:microsoft.quantum.more-information).

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Sekwencje Q # bram równoważne z Stanami Quantum
Punkt końcowy, który stanowi podstawę dla notacji Quantum i języka programowania Q #: na początku tego dokumentu stwierdzamy, że jest to podstawowy obiekt informacji w ramach przetwarzania Quantum.  Może to być niespodziewane, że w Q # nie ma pojęcia dotyczącego elementu Quantum.  Zamiast tego wszystkie stany są opisane tylko przez operacje używane do ich przygotowania.  Poprzedni przykład jest doskonałym ilustracją.  Zamiast wyznaczania jednolitej nadpozycji w każdym ciągu bitowym Quantum w rejestrze, możemy przedstawić wynik jako $H ^ {\otimes n } \ket{0 } $.  Ten wykładniczy, krótszy opis stanu nie tylko ma zaletę, że możemy z niej skorzystać, ale również zwięzłie definiuje operacje, które są niezbędne do propagowania przez stos oprogramowania w celu wdrożenia algorytmu.  Z tego powodu polecenie Q # jest przeznaczone do emitowania sekwencji bram zamiast Stanów Quantum; jednak na poziomie teoretycznym dwie perspektywy są równoważne.
