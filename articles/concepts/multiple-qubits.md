---
title: Wiele kubitów
description: Dowiedz się, jak wykonywać operacje na co najmniej dwóch qubits.
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 239073b7e7edafc49bc65cb60c9f45cf0af83dbe
ms.sourcegitcommit: a0e50c5f07841b99204c068cf5b5ec8ed087ffea
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/26/2020
ms.locfileid: "80320885"
---
# <a name="multiple-qubits"></a>Wiele Qubits

Bramy pojedynczej qubit mają pewne funkcje, takie jak możliwość znajdowania się w więcej niż jednym stanie w danym czasie, jeśli wszystkie z nich znajdowały się na bramach pojedynczej qubit, a my będziemy mieć urządzenie z mocą obliczeniową, które będzie dwarfed przez nawet Kalkulator podzieli się na to, że jest to klasyczny komputer.
Rzeczywista moc obliczeniowa Quantum jest oczywista tylko wtedy, gdy zwiększy się liczbę qubits.
Ta moc jest częścią, ponieważ wymiar przestrzeni wektorowej wektorów stanu Quantum rośnie wykładniczo z liczbą qubits.
Oznacza to, że w przypadku, gdy pojedyncze qubit można modelować, Symulacja obliczeń 50-qubit Quantum będzie raczej wypchnięcie ograniczeń istniejących komputerów.
Zwiększenie rozmiaru obliczeń przez tylko jeden dodatkowy qubit *podwaja* ilość pamięci wymaganej do przechowania stanu i wydłuża czas obliczeniowy.
To szybkie podwojenie mocy obliczeniowej polega na tym, że komputer Quantum o stosunkowo niewielkiej liczbie qubits może znacznie przekroczyć najbardziej wydajne nadchodzące komputery dzisiejsze, jutro i więcej w przypadku niektórych zadań obliczeniowych.

Dlaczego mamy wykładniczy wzrost dla wektorów stanu Quantum?  Naszym celem w tej sekcji jest zapoznanie się z regułami używanymi do kompilowania wielu qubit Stanów z jednego qubit Stanów, a także omówienia operacji związanych z bramą, które należy uwzględnić w naszym zestawie bram w celu utworzenia uniwersalnego komputera z systemem Quantum z wieloma qubitami.
Te narzędzia są absolutnie niezbędne do zrozumienia zestawów bram, które są często używane w kodzie Q #, a także w celu uzyskania Intuition na temat tego, dlaczego skutki Quantum, takie jak Entanglement lub zakłócenia, przetwarzają przetwarzanie Quantum w sposób bardziej wydajny niż środowisko klasyczne.

## <a name="representing-two-qubits"></a>Reprezentuje dwa Qubits
Główną różnicą między jednym i dwuqubitowym stanem jest to, że dwa qubit Stany są cztery wymiarowe, a nie dwa wymiarowe.
Wynika to z faktu, że podstawa obliczeniowa dla dwóch qubit Stanów jest tworzona przez produkty dwustronne z qubit Stanów.  Na przykład mamy \begin{align} 00 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}1 \\\\ 0\\\\ 0\\\\ 0 \end{bmatrix}, \qquad 01 \equiv \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 1\\\\ 0\\\\ 0 \end{bmatrix} ,\\\\ 10 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} & = \begin{bmatrix}0 \\\\ 0\\\\ 1\\\\ 0 \end{bmatrix}, \qquad 11 \equiv \begin{bmatrix}0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix}0 \\\\ 1 \end{bmatrix} = \begin{bmatrix}0 \\\\ 0\\\\ 0\\\\ 1 \end{bmatrix}.
\end{align}

Łatwiej jest zobaczyć, że bardziej ogólnie jest stan Quantum $n $ qubits jest reprezentowany przez wektor jednostki wymiaru $2 ^ n $ przy użyciu tej konstrukcji.  Wektor

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

reprezentuje stan Quantum dla dwóch qubits, jeśli $ | \ alpha_{00}| ^ 2 + | \ alpha_{01}| ^ 2 + | \ alpha_{10}| ^ 2 + | \ alpha_{11}| ^ 2 = 1 $. Podobnie jak w przypadku pojedynczego qubits wektor stanu Quantum dla wielu qubits przechowuje wszystkie informacje potrzebne do opisania zachowania systemu.

Jeśli podano dwa osobne qubits, jeden w stanie $ \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} $ i drugi qubit w stanie $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $, odpowiadający mu stan dwóch qubit to

$ $ \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} = \begin{bmatrix} \Alpha \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\ \delta \end{bmatrix} \end{bmatrix} = \begin{bmatrix} \alpha\gamma \\\\ \alpha\delta \\\\ \beta\gamma \\\\ \beta\delta \end{bmatrix} , $$

gdzie operacja $ \otimes $ jest nazywana iloczynem dwukierunkowym (lub produktem Kronecker) wektorów. Należy pamiętać, że w przypadku, gdy zawsze można utworzyć dwuqubitowy iloczyn dwóch stanów, a nie wszystkie dwuqubitowe Stany Quantum można napisać jako iloczyn dwustronicowy dwóch stanów.
Na przykład nie istnieją Stany $ \psi = \begin{bmatrix} \Alpha \\\\ \beta \end{bmatrix} $ i $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ 

$ $ \psi\otimes \phi = \begin{bmatrix} 1/\ sqrt{2} \\\\ 0 \\\\ 0 \\\\ 1/\ sqrt{2} \end{bmatrix}. $ $ 

Taki stan dwuqubitowy, który nie może być zapisany jako iloczyn dwuetapowego stanu jednego qubitu, jest nazywany "Entangled State"; dwa qubits są określane jako [*Entangled*](https://en.wikipedia.org/wiki/Quantum_entanglement).  Mówiąc, że stan Quantum nie może być uważany za pojedynczy iloczyn jednego z qubit Stanów, informacje przechowywane przez stan nie są ograniczone do jednej z qubits indywidualnie.  Zamiast tego informacje są przechowywane nie lokalnie w korelacji między tymi dwoma stanami.  Taka nielokalna informacja jest jedną z głównych funkcji przetwarzania Quantum w porównaniu z klasycznym przetwarzaniem i jest istotna dla wielu protokołów Quantum, takich jak [teleporty](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) Quantum i [Korekcja błędów Quantum](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Mierzenie dwuQubitowych Stanów ##
Mierzenie dwuqubitowych Stanów jest bardzo podobne do pomiarów pojedynczej qubit. Mierzenie stanu

$ $ \begin{bmatrix} \ alpha_{00} \\\\ \ alpha_{01} \\\\ \ alpha_{10} \\\\ \ alpha_{11} \end{bmatrix} $ $

zwraca $0 $ z prawdopodobieństwem $ | \ alpha_{00}| ^ $2, $1 $ z prawdopodobieństwem $ | \ alpha_{01}| ^ $2, $10 $ z prawdopodobieństwem $ | \ alpha_{10}| ^ $2 i $11 $ z prawdopodobieństwem $ | \ alpha_{11}| ^ $2. Zmienne $ \ alpha_{00}, \ alpha_{01}, \ alpha_{10}, $ i $ \ alpha_{11}$ zostały świadomie nazwane, aby to połączenie było jasne. Po pomiarze, jeśli wynik wynosi $0 $, stan Quantum w systemie qubit jest zwinięty i jest teraz

$ $0 \equiv \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix}.
$$

Możliwe jest również zmierzenie tylko jednego qubita z dwuqubitnym stanem Quantum. W przypadkach, gdy mierzy się tylko jeden z qubits, wpływ pomiaru jest nieco różny, ponieważ cały stan nie jest zwijany do stanu podstawy, a raczej jest zwinięty tylko w jednym podsystemie.  Innymi słowy w takich przypadkach pomiary tylko jednego qubit zwija tylko jeden z podsystemów, ale nie wszystkich.  

Aby to sprawdzić, należy rozważyć zmierzenie pierwszego qubitu tego stanu, który jest tworzony przez zastosowanie przekształcenia Hadamard $H $ na dwóch qubits początkowo ustawionych jako "0": $ $ H ^ {\otimes 2} \left (\begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix}1 \\\\ 0 \end{bmatrix} \right) = \frac{1}{2}\begin{bmatrix}1 & 1 & 1 & 1 \\\\ 1 &-1 & 1 &-1 \\\\ 1 & 1 &-1 & Zakończ {bmatrix} \begin{bmatrix}1\\\\ 0\\\\ 0\\\\ 0 \ End {bmatrix} = \frac{1}{2}\begin{bmatrix}1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \mapsto \begin{Cases}\Text{Outcome} = 0 & \frac{1}{\sqrt{2}} \begin{bmatrix}1\\\\\\\\ 0\\\\ 0 \end{bmatrix}\\\\ \Text{Outcome} = 1 & \frac{1}{\sqrt{2}} \begin{bmatrix}0\\\\ 0\\\\ 1\\\\ 1 \end{bmatrix}\\\\ \end{cases}.\\\\
$ $ Oba wyniki mają 50% prawdopodobieństwa wystąpienia.  Wynik o wartości 50% prawdopodobieństwa dla obu tych możliwości można zależeć od faktu, że początkowa wektora stanu Quantum jest niezmienna w przypadku wymiany $0 $ z $1 $ na pierwszej qubit.

Reguła matematyczna służąca do mierzenia pierwszych lub sekund qubit jest prosta.  Jeśli możemy $e _k $ być $k ^ {\RM th} $ i pozwól $S $ być zestawem wszystkich $e _k $ w taki sposób, że qubit w danej sytuacji przyjmuje wartość $1 $ dla tej wartości $k $.  Na przykład jeśli interesuje Cię pomiar pierwszej qubit, $S $ będzie składać się z $e _1 \ equiv $10 i $e _3 \ equiv $11.  Podobnie, Jeśli interesuje Cię drugi qubit $S $ powinien składać się z $e _2 \ equiv $1 i $e _3 \equiv $11.  Następnie prawdopodobieństwo mierzenia wybranych qubit do $1 $ jest dla wektora stanu $ \psi $

$ $ P (\Text{Outcome} = 1) = \ sum_ {e_k \Text{w zestawie} S} \psi ^ \dagger e_k e_k ^ \dagger \psi.
$$

> [!NOTE]
> W tym dokumencie korzystamy z formatu little-endian, aby oznaczyć podstawę obliczeniową. W formacie little endian najmniej znaczące bity są pierwsze. Na przykład liczba czterech w formacie little-endian jest reprezentowana przez ciąg bitów 001.

Ponieważ każda pomiar qubit może dać jedynie $0 $ lub $1 $, prawdopodobieństwo pomiaru $0 $ jest po prostu $1-P (\Text{Outcome} = 1) $.  Dlatego tylko jawnie podajemy formułę dla prawdopodobieństwa pomiaru $1 $.

Akcja, która ma na stan, może być wyrażona Matematycznie jako

$ $ \psi \mapsto \frac{\ sum_ {e_k \Text{w zestawie} S} e_k e_k ^ \dagger \psi}{\sqrt{P (\Text{Outcome} = 1)}}.
$$

Czytnik rozwagą może martwić się o to, co się stanie, gdy prawdopodobieństwo pomiaru jest równe zero.  Chociaż wynikowy stan jest technicznie niezdefiniowany w tym przypadku, nigdy nie musimy martwić się o takie możliwości, ponieważ prawdopodobieństwo jest równe zero!


Jeśli firma Microsoft $ \psi $ będzie mieć jednolity wektor stanu podanym powyżej i chce mierzyć pierwszy qubit, 

$ $ P (\Text{Measurement pierwszej qubit} = 1) = (\psi ^ \dagger e_1) (e_1 ^ \dagger \psi) + (\psi ^ \dagger e_3) (e_3 ^ \dagger \psi) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Należy zauważyć, że jest to tylko suma dwóch prawdopodobieństw, które byłyby oczekiwane do mierzenia wyników $10 $ i $11 $, były mierzone qubits.
W naszym przykładzie jest to wynikiem

$ $ \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 1 & 0 \ End {bmatrix} \ BEGIN {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \right | ^ 2 + \frac{1}{4}\left | \begin{bmatrix}0 & 0 & 0 & 1 \ End {bmatrix} \ BEGIN {bmatrix} 1\\\\ 1\\\\ 1\\\\ 1 \ End {bmatrix} \right | ^ 2 = \frac{1}{2}.
$$

który idealnie pasuje do tego, co nasz Intuition informuje nas o prawdopodobieństwie.  Podobnie stan można napisać jako

$ $ \frac{\frac{e_1}{2}+ \frac{e_3}{2}} {\sqrt{\frac{1}{2}}} = \frac{1}{\sqrt{2}} \begin{bmatrix} 0\\\\ 0\\\\ 1\\\\ 1 \ End {bmatrix} $ $

ponownie zgodnie z naszymi Intuition.

## <a name="two-qubit-operations"></a>Dwie qubit operacje
Podobnie jak w przypadku pojedynczej qubit, każda transformacja jednostkowa jest prawidłową operacją na qubits. Ogólnie przekształcenie jednostkowe na $n $ qubits jest macierzą $U $ o rozmiarze $2 ^ n \times 2 ^ n $ (tak, aby działała w wektorach o rozmiarze $2 ^ n $), takich jak $U ^{-1} = U ^ \dagger $.
Na przykład brama CNOT (sterowana bez) jest powszechnie wykorzystywaną bramą dwuqubitową i jest reprezentowana przez następującą macierz jednostkową:

$ $ \operatorname{CNOT} = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 \\\\ 0 \ 0 \ 0 \ 1 \\\\ 0 \ 0 \ 1 \ 0 \end{bmatrix} $ $

Możemy również utworzyć bramy dwuqubitowe, stosując bramy jednoqubitowe na obu qubits. Na przykład jeśli stosujemy bramy 

$ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} $ $

i

$ $ \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} $ $

odpowiednio do pierwszej i drugiej qubits jest to równoznaczne z zastosowaniem jednostki dwuqubitowej dostarczonej przez jej iloczyn dwuskładnikowy: $ $ \begin{bmatrix} a \ b\\\\ c \ d \end{bmatrix} \otimes \begin{bmatrix} e \ f\\\\ g \ h \end{bmatrix} = \begin{bmatrix} AE \ AF \ to \ \\\\ ce \ CF \ de \ DF \\\\ CG \ ch \ DG \ DH \end{bmatrix}. $ $, dzięki czemu możemy utworzyć bramę z dwoma qubitami, pobierając iloczyn dwukrotnego z bram o pojedynczej qubit.\\\\ Niektóre przykłady bram z dwoma qubitmi obejmują $H \otimes H $, $X \otimes \boldone $ i $X \otimes Z $.

Należy pamiętać, że chociaż dwie bramy pojedynczej qubit definiują bramę dwuqubitową przez przejmowanie jej iloczynu, to nie jest spełniony. Nie wszystkie bramy dwuqubitowe mogą być napisywane jako iloczyn dwuskładnikowego bram pojedynczej qubit.  Taka Brama jest nazywana bramą *Entangling* . Przykładem bramy Entangling jest brama CNOT.

Intuition za bramą typu kontrolowanego nie można uogólnionie do dowolnych bram.  Kontrolowana Brama ogólnie jest bramą, która działa jako tożsamość (IE nie ma żadnej akcji), chyba że określony qubit to $1 $.  Należy zauważyć, że kontrolowane jednostki są kontrolowane w tym przypadku na qubit z $x etykietą $ \Lambda\_x (U) $.  Przykładowo $ \ Lambda_0 (U) e\_{1}\otimes {\psi} = e\_{1}\otimes U {\psi} $ i $ \Lambda\_0 (U) e\_{0}\otimes {\psi} = e\_{0}\otimes{\psi} $, gdzie $e\_$0 i $e\_$1 to wektory obliczeniowe dla pojedynczego qubit odpowiadające wartościom $0 $ i $1 $.  Rozważmy na przykład następujące kontrolowane $Z $ bramę, a następnie można to wyrazić jako $ $ \Lambda\_0 (Z) = \begin{bmatrix}1 & 0 & 0 & 0\\\\0 & 1 & 0 & 0\\\\0 & 0 & 1 \operatorname{CNOT} (\boldone\otimes h).\\\\
$$

Kompilowanie kontrolowanej unitaries w efektywny sposób jest ważnym wyzwaniem.  Najprostszym sposobem wdrożenia tego wymagania jest tworzenie bazy danych z kontrolowanymi wersjami bram i zastępowanie każdej bramy podstawowej w pierwotnej operacji jednostkowej z kontrolowanym odpowiednikiem.  Jest to często dość wasteful i sprytne Insights często można użyć do zastępowania kilku bram z kontrolowanymi wersjami, aby osiągnąć ten sam wpływ.  Z tego powodu firma Microsoft udostępnia w naszym środowisku algorytmie metodę kontroli lub zezwala użytkownikowi na definiowanie kontrolowanej wersji jednostki, jeśli znana jest zoptymalizowana wersja.

Bramy można również kontrolować przy użyciu informacji klasycznych.  Klasyczno sterowaną niebramą, na przykład jest tylko zwykłą niebramą, ale jest stosowany tylko wtedy, gdy klasyczny bit to $1 $, a nie bit Quantum.  W tym sensie kontrolowana Brama może być uważana za instrukcję if w kodzie Quantum, w którym Brama jest stosowana tylko w jednej gałęzi kodu.


Podobnie jak w przypadku pojedynczej qubit, zestaw bram z dwoma qubitami jest uniwersalny, jeśli dowolna precyzja macierzy $4 \ Times $4 może być przybliżona przez iloczyn bram z tego zestawu do dowolnej dokładności.
Przykładem uniwersalnego zestawu bram jest brama Hadamard, Brama T i bramę CNOT. Pobierając produkty z tych bram, możemy przybliżyć każdą macierz jednostkową na dwóch qubits.

## <a name="many-qubit-systems"></a>Wiele systemów qubit
Obserwujemy dokładnie te same wzorce, które zostały zbadane w przypadku dwóch qubitów, aby skompilować Stany Quantum qubit z mniejszych systemów.  Takie Stany są tworzone przez tworzenie iloczynów części mniejszych Stanów.  Rozważmy na przykład kodowanie ciągu bitowego $1011001 $ na komputerze Quantum.  Możemy kodować ten

$ $1011001 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}.
$$

Bramy Quantum działają w taki sam sposób.  Na przykład jeśli chcemy zastosować bramę $X $ do pierwszego qubit, a następnie wykonać CNOT między drugim i trzecim qubits, możemy wyrazić tę transformację jako

\begin{align} & (X \otimes \operatorname{CNOT}_{12}\otimes \boldone\otimes \boldone \otimes \boldone \otimes \boldone) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}\otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix}\\\\ & \qquad\qquad\equiv 0011001.
\end{align}

W wielu systemach qubit często istnieje potrzeba przydzielenia i cofnięcia przydziału qubits, które pełnią rolę pamięci tymczasowej dla komputera Quantum.  Taka qubit jest nazywana Ancilla.  Domyślnie przyjęto, że stan qubit jest inicjowany $e _0 $ po przydzieleniu.  Ponadto założono, że jest on ponownie zwracany do $e _0 $ przed cofnięciem przydziału.  To założenie jest ważne, ponieważ jeśli Ancilla qubit będzie Entangled z innym rejestrem qubit, gdy zostanie wycofany, proces cofania przydziału spowoduje szkody dla Ancilla.  Z tego powodu zawsze zakładamy, że takie qubits są przywracane do stanu początkowego przed jego udostępnieniem.

Na koniec, chociaż nowe bramy, które trzeba dodać do naszego zestawu bram w celu osiągnięcia uniwersalnego przetwarzania Quantum dla dwóch qubitych komputerów z systemem Quantum, nie trzeba wprowadzać nowych bram w przypadku wieloqubitowego przypadku.  Bramy $H $, $T $ i CNOT tworzą uniwersalną bramę w wielu qubitsach, ponieważ wszelka ogólna transformacja jednostkowa może zostać podzielona na serię dwóch rotacji qubit.  Następnie możemy wykorzystać teorię opracowaną w przypadku dwóch qubitów i użyć jej ponownie w przypadku wielu qubits.

Chociaż liniowa notacja algebraicznych, z której korzystamy z tego względu, może być używana do opisywania Stanów wieloqubitowych, gdy zwiększamy rozmiar Stanów.  Wynikowa kolumna-wektor dla ciągu o długości 7 bitów, na przykład, to $128 $, co sprawia, że jest to wyrażenie opisane wcześniej przy użyciu notacji, która była często bardzo skomplikowana.  Z tego powodu następnym zaprezentować wspólną notację w ramach przetwarzania Quantum, która pozwala nam na zwięzłe opisywanie tych wektorów wielowymiarowych.
