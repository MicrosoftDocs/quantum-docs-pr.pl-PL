---
title: Pomiary Pauli | Microsoft Docs
description: Pomiary Pauli
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7bea821be7e26e72f2860278486d35be676ca63d
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183713"
---
# <a name="pauli-measurements"></a>Pomiary Pauli

W poprzednich dyskusjach koncentrujemy się na obliczaniu pomiarów bazowych.  W rzeczywistości istnieją inne typowe pomiary wykonywane w ramach przetwarzania Quantum, które z perspektywy notacji są wygodne do wyrażania na podstawie obliczeniowych pomiarów.  Najbardziej typowym zestawem tych pomiarów są *pomiary Pauli*.  W takich przypadkach często omawia się pomiar pomiaru operatora Pauli, w ogólności operatora, takiego jak $X, Y, Z $ lub $Z \otimes Z, X\otimes X, X\otimes Y $ i tak dalej.  Omawianie pomiaru w warunkach operatorów Pauli jest szczególnie powszechne w podpolu korekcji błędów Quantum. W Q # korzystamy z podobnej Konwencji; teraz wyjaśnimy ten alternatywny widok pomiarów.

Przed napisaniem szczegółowych informacji o tym, jak sądzisz o pomiarze Pauli, warto zastanowić się nad tym, co mierzy jeden qubit wewnątrz komputera Quantum w stanie Quantum.  Załóżmy, że mamy $n $-qubit Quantum State; następnie zmierzenie jednej qubit od razu wystawia wszystkie możliwości $2 ^ n $, które mogą być w stanie.  Innymi słowy, pomiar projektuje stan Quantum na jedną z dwóch miejsc.  Możemy uogólnić sposób, w jaki myślimy o pomiarach, aby to uwzględnić.

Aby zwięzłie zidentyfikować te podobszary, należy zapoznać się z językiem.  Jednym ze sposobów, aby to zrobić, można opisać dwa podobszary, określając je za pośrednictwem macierzy, która ma dwa unikatowe eigenvalues, podejmowane przez Konwencję jako $ \Pm $1.  Najprostszym przykładem jest:

$ $ Z = \begin{bmatrix} 1 & 0 \\\\ 0 &-1 \end{bmatrix}.
$$

Pauli-$Z $ Matrix jasno ma dwa eigenvectors $ \ket{0}$ i $ \ket{1}$ z eigenvalues $ \Pm $1.  W takim przypadku firma Microsoft mierzy qubit i uzyska $ \ket{0}$ w eigenspace $ + $1 (zestaw wszystkich wektorów, które są tworzone z sum eigenvectors z tylko dodatnimi lub tylko negatywnymi eigenvalues), i jeśli mierzę $ \ket{1}$ jesteśmy w $-$1 eigenspace $Z $.  Ten proces jest określany w języku Pauli pomiarów jako "pomiar Pauli $Z $" i jest całkowicie równoważny do wykonywania obliczeniowej miary.

Oczywiście każda $2 \ Times $2 macierz, która jest przekształceniem jednostkowym $Z $ spełnia również te kryteria.  Jest to konieczne, ponieważ możemy również rozważyć użycie macierzy $A = U ^ \dagger Z U $, dla dowolnej macierzy jednostkowej $U $, w celu uzyskania matrycy, która definiuje dwa wyniki pomiaru w jego $ \Pm $1 eigenvectors.  Notacja pomiarów Pauli odwołuje się do tego, identyfikując $X, Y, Z $ pomiarów jako równoważne pomiary, które mogą wykonać, aby uzyskać informacje z qubit.  Te pomiary są podane poniżej dla wygody.

$ $ \begin{Array}{| c | c |} \text{Pauli pomiary} & U\\\\ Z & \boldone\\\\ X & H\\\\ Y & HS ^ \dagger\\\\ \end{Array} $ $

Oznacza to, że użycie tego języka "Measure $Y $" jest równoznaczne z zastosowaniem $HS ^ \dagger $, a następnie pomiary w oparciu o obliczenia, gdzie $S $ to brama fazy o tej samej nazwie określona przez

$ $ \begin{bmatrix}1 & 0\\\\ 0 & i\end {bmatrix}.
$$

Jest to również równoznaczne z zastosowaniem $HS ^ \dagger $ do wektora stanu Quantum, a następnie zmierzenie $Z $.  Prawidłowy stan można znaleźć, przenosząc z powrotem do podstawy obliczeniowej, które dotyczą zastosowania $SH $ do wektora stanu Quantum.

## <a name="q-outcome-classical-information-obtained-from-quantum-state"></a>Informacje o wynikach pytań i odpowiedzi klasycznej uzyskane z stanu Quantum
W odpowiedzi na pytanie o wyniki, tj. klasyczne informacje wyodrębnione z tego stanu, to $j $, który znajduje się w zestawie $\{0, 1\}$, jeśli wynik znajduje się w $ (-1) ^ j $ eigenspace operatora Pauli.

Pomiary operatorów Pauli wieloqubitowych są zdefiniowane w podobny sposób, jak pokazano w:

$ $ Z\otimes Z = \begin{bmatrix}1 & 0 & 0 & 0\\\\ 0 &-1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 & 1 \ End {bmatrix}.
$$

W tym celu dwa operatory Pauli-$Z $ tworzą tablicę składającą się z dwóch spacji składających się z $ + $1 i $-$1 eigenvalues.  Podobnie jak w przypadku pojedynczej qubit, oba stanowią pół miejsca, że połowa dostępnego miejsca wektorowego należy do $ + $1 eigenspace i pozostała połowa do eigenspace $-$1.  Ogólnie rzecz biorąc, łatwo jest zapoznać się z definicją iloczynu dwuczęściowego, że każdy dwuczęściowy produkt Pauli-$Z $ operatory i tożsamość również przestrzega tego.  Na przykład

$ $ Z\otimes\boldone = \begin{bmatrix} 1 & 0 & 0 & 0\\\\ 0 & 1 & 0 & 0\\\\ 0 & 0 &-1 & 0\\\\ 0 & 0 & 0 &-1 \ End {bmatrix}.
$$

Tak jak wcześniej, każda jednostkowa transformacja takich macierzy również zawiera opis dwóch miejsc z etykietą $ \Pm $1 eigenvalues.  Na przykład $X \otimes X = H\otimes H (Z\otimes Z) H\otimes H $ od tożsamości, która $Z = HXH $.  Podobnie jak w przypadku qubit, wszystkie dwie qubit Pauli-pomiary mogą być zapisywane jako $U ^ \dagger (Z\otimes \id) U $ dla $4 \ Times $4 macierze jednostkowe $U $.  Wyliczamy przekształcenia w poniższej tabeli, w której wprowadzamy dla wygody usługi wymiany, która zamienia qubits $0 $ i $1 $: $ \operatorname{SWAP} = \operatorname{CNOT}\_{01}\operatorname{CNOT}\_{10}\operatorname{CNOT}\_{01}$:

$ $ \begin{Array}{| c | c |} \text{Paulie} & U\\\\ \hline Z\otimes \boldone & \boldone\otimes \boldone\\\\ X\otimes \boldone & H\otimes \boldone\\\\ Y\otimes \boldone &\\\dagger\otimes \boldone \boldone \\ & \otimes \operatorname{swap} Z\\\\ & \boldone \otimes X\\operatorname {SWAP}\\\\ Z\otimes Z & \operatorname{CNOT}\_{10}\\\\ X\otimes Z & \operatorname{CNOT}\_{10}(H\otimes \boldone)\\\\ Y\otimes Z & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes \boldone)\\\\ Z\otimes X & \operatorname{CNOT}\_{10}(\boldone\otimes H)\\\\ X\otimes X & \operatorname{CNOT}\_{10}(H \ otimes H)\\\\ Y\otimes X & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes H)\\\\ Z\otimes Y & \operatorname{CNOT}\_{10}(\boldone \otimes HS ^ \dagger)\\\\ X\otimes Y & \operatorname{CNOT}\_{10}(H\otimes HS ^ \dagger)\\\\ Y\otimes Y & \operatorname{CNOT}\_{10}(HS ^ \dagger\otimes\\\\\\

Tutaj Brama $ \operatorname{CNOT}\_{10}$ pojawia się z następującej przyczyny.  Każda miara Pauli, która nie obejmuje macierzy $ \boldone $, jest równoważna do jednostki do $Z \otimes Z $ według powyższego powodu.  Eigenvalues $Z \otimes Z $ zależą od parzystości qubits, która składa się z poszczególnych wektorów obliczeniowych, a operacje kontrolowane przez nie są wyświetlane na tej liście, służą do obliczenia tej parzystości i zapisania jej w pierwszym bitach.  Następnie po przemierzeniu pierwszego bitu można odzyskać tożsamość wynikowego miejsca, które jest równoważne pomiarowi operatora Pauli.

Jedna dodatkowa Uwaga, chociaż może być skłonny do założenia, że pomiary $Z \otimes Z $ są takie same jak pomiary $Z \otimes \id $, a następnie $ \id \otimes Z $, to założenie miałoby wartość false.  Powodem jest to, że pomiar $Z \otimes Z $ projektów w stanie Quantum do wartości $ + $1 lub $-$1 eigenstate tych operatorów.  Pomiar $Z \otimes \id $, a następnie $ \id \otimes Z $ projects Vector State w pierwszej kolejności do pół miejsca na $Z \otimes \id $, a następnie do połowy miejsca z $ \id \otimes Z $.  Ponieważ istnieją cztery wektory obliczeniowe, przeprowadzenie obydwu pomiarów zmniejsza stan do kwartału, a tym samym redukuje go do jednego wektora obliczanego na podstawie.


## <a name="correlations-between-qubits"></a>Korelacje między qubits
Innym sposobem na poszukiwanie produktów dwuskładnikowych Pauly, takich jak $X \otimes X $ lub $Z \otimes Z $, jest to, że pomiary umożliwiają przeszukanie informacji przechowywanych w korelacji między tymi dwoma qubits.  Pomiar $X \otimes \id $ umożliwia przeglądanie informacji przechowywanych lokalnie w pierwszej qubit.  Mimo że oba typy pomiarów są równie cenne w przypadku obliczeń opartych na usługach Quantum Wykaże, że w ramach przetwarzania Quantum często informacje, które chcesz poznać, nie są przechowywane w żadnym z pojedynczych qubit, ale raczej są przechowywane nielokalnie we wszystkich qubitsach i tylko przez przechodzenie przez wspólne pomiary z $Z \otimes Z $ czy te informacje stają się manifestu.

Można również mierzyć dowolne operatory Pauli, takie jak $X \otimes Y \otimes Z \otimes \boldone $.  Wszystkie te produkty dwuskładnikowe operatorów Pauli mają tylko dwa eigenvalues $ \Pm $1, a oba eigenspaces stanowią pół miejsca całego obszaru wektora.  W ten sposób są one zgodne z wymaganiami określonymi powyżej.

W Q #, takie pomiary zwracają $j $, jeśli pomiar daje wynik w eigenspace znak $ (-1) ^ j $.  To jak wbudowana funkcja w funkcji Q # jest przydatna, ponieważ pomiar takich operatorów wymaga długich łańcuchów z kontrolowanymi bramami i transformacjami bazowymi, aby opisać diagonalizing $U $Z $  Po prostu można określić, że chcesz wykonać jedną z tych wstępnie zdefiniowanych pomiarów, nie musisz martwić się o to, jak przekształcić swoją podstawę, tak aby pomiar bazowy obliczał informacje.  W programie Q # wszystkie wymagane przekształcenia podstawowe są obsługiwane automatycznie. Zobacz [Informacje o bibliotece Q # dla pomiarów Pauli](/qsharp/api/canon/microsoft.quantum.canon.measurepaulis)

## <a name="the-no-cloning-theorem"></a>Theorem bez klonowania
Informacje o Quantum są zaawansowane.  Umożliwia nam wykonywanie niezwykłych rzeczy, takich jak liczba czynników, które są wykładniczo szybsze niż najlepsze znane klasyczne algorytmy, lub efektywnie symuluje skorelowane systemy elektronów, które w sposób klasyczny wymagają wykładniczego kosztu, aby symulować dokładne symulacje.  Istnieją jednak ograniczenia dotyczące mocy obliczeniowej Quantum.  Takie ograniczenie jest określone przez *theorem bez klonowania*.

Theorem No-kloning ma nazwę aptly.
Nie zezwala na klonowanie ogólnych Stanów Quantum przez komputer Quantum.
Potwierdzenie theorem jest niezwykle proste.
Mimo że pełne potwierdzenie theorem nie jest w stanie nieco zbyt technicznym w naszej dyskusji, dowód theorem w przypadku, gdy dany komputer Quantum nie ma dodatkowej Ancilla qubits, jest w naszym zakresie (Ancilla qubits jest używany do wyznaczania miejsca podczas obliczeń i jest łatwo używany i zarządzany w usłudze Q #), zobacz <xref:microsoft.quantum.techniques.qubits>).
W przypadku takiego komputera z systemem Quantum Operacja klonowania musi być macierzą jednostkową. Nie można wymusić pomiaru, ponieważ spowodowałoby to uszkodzenie stanu Quantum, który próbujemy sklonować. Potrzebna macierz jednostkowa musi mieć Właściwość $ $ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}, $ $ dla dowolnego stanu $ \ket{\psi} $.
Właściwość liniowości mnożenia macierzy wskazuje, że dla każdego drugiego stanu Quantum $ \ket{\phi} $,

\begin{align} & U\left [\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right] \ket{0}= \frac{1}{\sqrt{2}} U\ket {\ Fi} \ KET{0}+ \frac{1}{\sqrt{2}} U\ket {\ psi} \ KET{0}\\\\ & \qquad\qquad = \frac{1}{\sqrt{2}} \left (\ket{\phi}\ket{\phi} + \ket{\psi}\ket{\psi}\right)\\\\ & \qquad\qquad\ne \left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \ Right) \right) \otimes\left (\frac{1}{\sqrt{2}} \left (\ket{\phi} + \ket{\psi} \right) \right).
\end{align}

Zapewnia to podstawowe Intuition za theorem bez klonowania: każde urządzenie, które kopiuje nieznany stan Quantum, musi powodować błędy w co najmniej niektórych stanach, które kopiuje.  Podczas gdy klucz założono, że Cloner działa w sposób liniowy w stanie wprowadzania, może zostać naruszony przez dodanie Ancilla i pomiaru Ancilla qubits, takie interakcje także przecieki informacji o systemie za pomocą statystyk pomiarów i zapobiegania również dokładne klonowanie w takich przypadkach.  Aby uzyskać bardziej szczegółowe informacje, zobacz theorem No-kloning, [Aby uzyskać więcej informacji](xref:microsoft.quantum.more-information).

Theorema bez klonowania jest ważna w przypadku jakościowej interpretacji obliczeń opartych na usłudze Quantum, ponieważ w przypadku niedrogiego klonowania Stanów Quantum można udzielić prawie magicalej możliwości uczenia się od Stanów Quantum.  Rzeczywiście można naruszyć zasadę niepewności vaunted Heisenberg.  Alternatywnie można użyć optymalnej Cloner do pobrania pojedynczego przykładu ze złożonej dystrybucji Quantum i dowiedzieć się wszystkiego, co może być możliwe, aby poznać tę dystrybucję z zaledwie jednego przykładu.  Przypomina to Przerzucanie monet i obserwowanie głowic, a następnie na poinformowanie przyjaciela o tym, że reagują na "Ah" dystrybucja tej monety musi być Bernoulliego z $p = 0.512643 \ ldots $! "  Taka instrukcja byłaby niesensicala, ponieważ jeden bit informacji (wynik Head) po prostu nie może udostępnić wielu bitów informacji potrzebnych do zakodowania dystrybucji bez poważnych informacji.  Podobnie, bez wcześniejszej informacji, nie możemy idealnie sklonować stanu Quantum, tak samo, jak nie można przygotować kompletu takich monet bez znajomości $p $.

Informacje nie są bezpłatne w obliczeniach Quantum.  Każda qubit mierzona w postaci pojedynczej informacji, a theorem bez klonowania nie wykazuje, że nie ma tylne wejście, które mogą być wykorzystywane w celu założenia zasadniczego kompromisu między informacjami uzyskanymi na temat systemu a zaistniałymi zakłóceniami.

