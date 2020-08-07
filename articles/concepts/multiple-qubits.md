---
title: wiele qubits opis: informacje na temat wykonywania operacji na co najmniej dwóch qubitsach.
Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. Multiple-qubits MS. Author: nawiebe@microsoft.com MS. Date: 12/11/2017 MS. temat: artykuł No-Loc:
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="multiple-qubits"></a>Wiele Qubits

Bramy pojedynczej qubit mają pewne funkcje, takie jak możliwość znajdowania się w więcej niż jednym stanie w danym czasie, jeśli wszystkie z nich znajdowały się na bramach pojedynczej qubit, firma Microsoft może mieć urządzenie z możliwością obliczeniową, które będzie dwarfed przez nawet Kalkulator postanowił tylko klasyczny nadsystemu.
Rzeczywista moc obliczeniowa Quantum jest oczywista tylko wtedy, gdy zwiększy się liczbę qubits.
Ta moc jest częścią, ponieważ wymiar przestrzeni wektorowej wektorów stanu Quantum rośnie wykładniczo z liczbą qubits.
Oznacza to, że w przypadku, gdy pojedyncze qubit można modelować, Symulacja obliczeń 50-qubit Quantum będzie raczej wypchnięcie ograniczeń istniejących komputerów.
Zwiększenie rozmiaru obliczeń przez tylko jeden dodatkowy qubit *podwaja* ilość pamięci wymaganej do przechowania stanu i wydłuża czas *doubles* obliczeniowy.
To szybkie podwojenie mocy obliczeniowej polega na tym, że komputer Quantum o stosunkowo niewielkiej liczbie qubits może znacznie przekroczyć najbardziej wydajne nadchodzące komputery dzisiejsze, jutro i więcej w przypadku niektórych zadań obliczeniowych.

Dlaczego mamy wykładniczy wzrost dla wektorów stanu Quantum?  Naszym celem w tej sekcji jest zapoznanie się z regułami używanymi do kompilowania wielu qubit Stanów z jednego qubit Stanów, a także omówienia operacji związanych z bramą, które należy uwzględnić w naszym zestawie bram w celu utworzenia uniwersalnego komputera z systemem Quantum z wieloma qubitami.
Te narzędzia są absolutnie niezbędne do zrozumienia zestawów bram, które są często używane w Q# kodzie, a także do uzyskania Intuition na temat tego, dlaczego działania Quantum, takie jak Entanglement lub zakłócenia, działają w sposób bardziej wydajny niż środowisko klasyczne.

## <a name="representing-two-qubits"></a>Reprezentuje dwa Qubits
Główną różnicą między jednym i dwuqubitowym stanem jest to, że dwa qubit Stany są cztery wymiarowe, a nie dwa wymiarowe.
Wynika to z faktu, że podstawa obliczeniowa dla dwóch qubit Stanów jest tworzona przez produkty dwustronne z qubit Stanów.  Na przykład mamy\begin{align}
00 \equiv \begin{bmatrix} 1 \\\\ 0 1 0 1 0 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} , \qquad 01 \equiv \begin{bmatrix} 1 \\\\ 0 0 0 \end{bmatrix} \otimes \begin{bmatrix} 1 0 \\\\ \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} ,\\\\
10 0 1 1 0 0 0 \equiv \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} & = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} , \qquad 11 \equiv \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} 0 0 0.
\end{align}

Łatwiej jest zobaczyć, że bardziej ogólnie jest stan Quantum dla $ n $ qubits jest reprezentowany przez wektor jednostki wymiaru $ 2 ^ n $ przy użyciu tej konstrukcji.  Wektor

$$
\begin{bmatrix}\alpha _ { 00 } 01 \\\\ 10 \alpha   _ { } \\\\ \alpha _ { 11 } \\\\ \alpha   _ { }  \end{bmatrix}
$$

reprezentuje stan Quantum dla dwóch qubits, jeśli $ | \alpha _ { 00 } | ^ 2 + | \alpha _ { 01 } | ^ 2 + | \alpha _ { 10 } | ^ 2 + | \alpha _ { 11 } | ^ 2 = 1 $ . Podobnie jak w przypadku pojedynczego qubits wektor stanu Quantum dla wielu qubits przechowuje wszystkie informacje potrzebne do opisania zachowania systemu.

Jeśli podano dwie osobne qubits, jeden w stanie $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ i drugi qubit w stanie $ \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ , odpowiadający mu stan qubit to    

$$
\begin{bmatrix} \alpha \\\\  \beta \end{bmatrix} \otimes \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} 
=\begin{bmatrix} \alpha \begin{bmatrix} \gamma \\\\  \delta \end{bmatrix} \\\\ \beta \begin{bmatrix}\gamma \\\\  \delta \end{bmatrix} \end{bmatrix}
= \begin{bmatrix} \alpha\gamma \\\\  \alpha\delta \\\\  \beta\gamma \\\\  \beta\delta \end{bmatrix}, $$

gdzie operacja $ \otimes $ jest nazywana iloczynem dwukierunkowym (lub Kronecker produktu) wektorów. Należy pamiętać, że w przypadku, gdy zawsze można utworzyć dwuqubitowy iloczyn dwóch stanów, a nie wszystkie dwuqubitowe Stany Quantum można napisać jako iloczyn dwustronicowy dwóch stanów.
Na przykład nie ma żadnych Stanów $ \psi = \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ i $ \phi = \begin{bmatrix} \gamma \\\\ \delta \end{bmatrix} $ że ich iloczyn na siebie jest stanem     

$$\psi\otimes\phi = \begin{bmatrix} 1/ \sqrt { 2 } \\\\ 0 \\\\ 0 \\\\ / \sqrt { 2 } \end{bmatrix} .$$ 

Taki stan dwuqubitowy, który nie może być zapisany jako iloczyn dwuetapowego stanu jednego qubitu, jest nazywany "Entangled State"; dwa qubits są określane jako [*Entangled*](https://en.wikipedia.org/wiki/Quantum_entanglement).  Mówiąc, że stan Quantum nie może być uważany za pojedynczy iloczyn jednego z qubit Stanów, informacje przechowywane przez stan nie są ograniczone do jednej z qubits indywidualnie.  Zamiast tego informacje są przechowywane nie lokalnie w korelacji między tymi dwoma stanami.  Taka nielokalna informacja jest jedną z głównych funkcji przetwarzania Quantum w porównaniu z klasycznym przetwarzaniem i jest istotna dla wielu protokołów Quantum, takich jak [teleporty](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) Quantum i [Korekcja błędów Quantum](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Mierzenie dwuQubitowych Stanów ##
Mierzenie dwuqubitowych Stanów jest bardzo podobne do pomiarów pojedynczej qubit. Mierzenie stanu

$$
    \begin{bmatrix}
        \alpha_ { 00 } 01 \\\\ \alpha _ { }\\\\ 
        \alpha_ { 10 } 11 \\\\ \alpha _ {}
    \end{bmatrix}
$$

zwraca $ 00 $ z prawdopodobieństwem $ | \alpha _ { 00 } | ^ 2 $ , $ 01 $ $ | z \alpha prawdopodobieństwem _ { 01 } | ^ 2 $ , $ 10 $ z prawdopodobieństwem $ | \alpha _ { 10 } | ^ 2 $ i $ 11 $ z $ prawdopodobieństwem | 11 \alpha _ { } | ^ 2 $ . Zmienne $ \alpha _ { 00 } , \alpha _ { 01 } , \alpha _ { 10 } $ i $ 11 \alpha _ { } $ zostały świadomie nazwane, aby to połączenie było jasne. Po pomiarze, jeśli wynik wynosi $ 00, $ stan Quantum dla systemu dwuqubitowego został zwinięty i jest teraz

$$
    1,00\equiv
    \begin{bmatrix}
        jedno\\\\ 
        2,0\\\\ 
        2,0\\\\ 
        0 \end{bmatrix} .
$$

Możliwe jest również zmierzenie tylko jednego qubita z dwuqubitnym stanem Quantum. W przypadkach, gdy mierzy się tylko jeden z qubits, wpływ pomiaru jest nieco różny, ponieważ cały stan nie jest zwijany do stanu podstawy, a raczej jest zwinięty tylko w jednym podsystemie.  Innymi słowy w takich przypadkach pomiary tylko jednego qubit zwija tylko jeden z podsystemów, ale nie wszystkich.  

Aby to sprawdzić, rozważ zmierzenie pierwszego qubitu następującego stanu, który jest tworzony przez zastosowanie Hadamard przekształcenia $ H $ na dwóch qubits początkowo ustawionych jako "0":$$
H ^ { \otimes 2 (1 0 1 0) 1 2 1 1 1 1 1 – 1 1-1-1-1,0 1-1-1-1-1,0% 0 1 1 } \left \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \right = \frac { } { } \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} = \frac { } { } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \mapsto \begin{cases} \text { } = . wynik 0 1 2% 1 & \frac { } { \sqrt { } } \begin{bmatrix} \\\\ \\\\ 0 \\\\ 0 \end{bmatrix} \\\\ \text { wynik } = 1 & \frac { 1 } { \sqrt { } } \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \\\\ \end{cases} 0 0 1.  
$$
Oba wyniki mają 50% prawdopodobieństwa wystąpienia.  Wynik o wartości 50% prawdopodobieństwa dla obu tych możliwości można zależeć od faktu, że początkowa wektor stanu Quantum jest niezmienny w przypadku wymiany $ 0 $ z $ 1 $ w pierwszej qubit.

Reguła matematyczna służąca do mierzenia pierwszych lub sekund qubit jest prosta.  Jeśli postanowimy $ $ , e_k być $ k ^ { \rma } $ wektora obliczeń i niech $ S $ będzie zestawem wszystkich $ e_k $ w taki sposób, że qubit w danym przypadku Pobiera wartość $ 1 $ dla tej wartości $ k $ .  Na przykład, Jeśli interesuje Cię pomiar pierwszej qubit, $ S $ będzie zawierać $ e_1 \equiv 10 $ i $ e_3 \equiv 11 $ .  Podobnie, jeśli chcemy, aby druga qubit $ S $ obejmowała $ e_2 \equiv 01 $ i $ e_3 \equiv 11 $ .  Prawdopodobieństwo mierzenia wybranych qubit na $ 1 $ jest dla wektora stanu$\psi$

$$
P ( \text { wynik } = 1) = \sum _ { e_k \text { w zestawie } S } \psi ^ \dagger e_k e_k ^ \dagger \psi .
$$

> [!NOTE]
>W tym dokumencie korzystamy z formatu little-endian, aby oznaczyć podstawę obliczeniową. W formacie little endian najmniej znaczące bity są pierwsze. Na przykład liczba czterech w formacie little-endian jest reprezentowana przez ciąg bitów 001.

Ponieważ każda pomiar qubit może dać jedynie $ wartość 0 $ lub $ 1 $ , prawdopodobieństwo pomiaru $ 0 $ jest po prostu $ 1-P ( \text { wynik } = 1) $ .  Dlatego tylko jawnie dajemy formułę dla prawdopodobieństwa pomiaru $ 1 $ .

Akcja, która ma na stan, może być wyrażona Matematycznie jako

$$
\psi\mapsto \frac{\sum _ { e_k \text { w e_k zestawu } S } e_k ^ \dagger \psi } { \sqrt { P ( \text { wynik } = 1) } } .
$$

Czytnik rozwagą może martwić się o to, co się stanie, gdy prawdopodobieństwo pomiaru jest równe zero.  Chociaż wynikowy stan jest technicznie niezdefiniowany w tym przypadku, nigdy nie musimy martwić się o takie możliwości, ponieważ prawdopodobieństwo jest równe zero!


Jeśli zajmiemy $ \psi $ się jednolitym wektorem stanu podanym powyżej i są zainteresowani pomiarem pierwszego qubit 

$$
P ( \text { pomiary pierwszego qubit } = 1) = ( \psi ^ \dagger e_1) (e_1 ^ \dagger \psi ) + ( \psi ^ \dagger e_3) (e_3 ^ \dagger \psi ) = | e_1 ^ \dagger \psi | ^ 2 + | e_3 ^ \dagger \psi | ^ 2.
$$

Należy zauważyć, że jest to tylko suma dwóch prawdopodobieństw, które byłyby oczekiwane do mierzenia wyników $ 10 $ i $ 11 $ były mierzone qubits.
W naszym przykładzie jest to wynikiem

$$
\frac{1 4 0 0 1 0 1% 1 } { } \left | \begin{bmatrix} & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | ^ 2 + \frac { 1 } { 4 } \left | \begin{bmatrix} 0 & & & \end{bmatrix} \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} \right | = \frac { } { } 0 0 1 1 1% 2.
$$

który idealnie pasuje do tego, co nasz Intuition informuje nas o prawdopodobieństwie.  Podobnie stan można napisać jako

$$
\frac{\frac{e_1 } { 2 } + \frac { e_3 } { 2 } } { \sqrt { \frac { 1 2 } { } } } = \frac { 1 2 } { \sqrt { } } \begin{bmatrix} 0 \\\\ 0 \\\\ \\\\ 1\end{bmatrix}
$$

ponownie zgodnie z naszymi Intuition.

## <a name="two-qubit-operations"></a>Dwie qubit operacje
Podobnie jak w przypadku pojedynczej qubit, każda transformacja jednostkowa jest prawidłową operacją na qubits. Ogólnie rzecz biorąc, przekształcenie jednostkowe na $ n $ qubits jest macierzą $ $ o rozmiarze $ 2 ^ n \times 2 ^ n $ (tak, aby działała na wektorach o rozmiarze $ 2 ^ n $ ), takich jak $ u ^ { -1 } = U ^ \dagger $ .
Na przykład brama CNOT (sterowana bez) jest powszechnie wykorzystywaną bramą dwuqubitową i jest reprezentowana przez następującą macierz jednostkową:

$$
\operatorname{CNOT } = \begin{bmatrix} 1 \ 0 \ 0 \ 0 \\\\ 0 \ 1 \ 0 \ 0 0 \ 0 \ 0 \ \\\\ 1 \\\\ 0 \ 0 \ 1 \ 0\end{bmatrix}
$$

Możemy również utworzyć bramy dwuqubitowe, stosując bramy jednoqubitowe na obu qubits. Na przykład jeśli stosujemy bramy 

$$
\begin{bmatrix}
a \ b \\\\ c \ d\end{bmatrix}
$$

oraz

$$\begin{bmatrix}
e \ f \\\\ g \ h\end{bmatrix}
$$

odpowiednio do pierwszej i drugiej qubits jest to równoznaczne z zastosowaniem jednostki dwuqubitowej dostarczonej przez jej iloczyn dwuskładnikowy:$$\begin{bmatrix}
a \ b \\\\ c \ d\end{bmatrix}
\otimes 
\begin{bmatrix}
e \ f \\\\ g \ h\end{bmatrix}=
    \begin{bmatrix}
    AE \ AF \ nie należy\\\\
    AG \ Ah \ BG \ BH\\\\
    ce \ CF \ de \ DF\\\\
    CG \ ch \ DG \ DH \end{bmatrix} .$$
W ten sposób możemy tworzyć bramy dwuqubitowe, pobierając iloczyn dwustronnych bram o pojedynczej qubit. Niektóre przykłady bram z dwoma qubitami obejmują $ h \otimes h $ , $ x \otimes \boldone $ i $ x \otimes Z $ .

Należy pamiętać, że chociaż dwie bramy pojedynczej qubit definiują bramę dwuqubitową przez przejmowanie jej iloczynu, to nie jest spełniony. Nie wszystkie bramy dwuqubitowe mogą być napisywane jako iloczyn dwuskładnikowego bram pojedynczej qubit.  Taka Brama jest nazywana bramą *Entangling* . Przykładem bramy Entangling jest brama CNOT.

Intuition za bramą typu kontrolowanego nie można uogólnionie do dowolnych bram.  Kontrolowana Brama ogólnie jest bramą, która działa jako tożsamość (IE nie ma żadnej akcji), chyba że określony qubit to $ 1 $ .  Oznacza to, że sterowane jednostki są kontrolowane w tym przypadku na qubit z etykietą $ x $ $ \Lambda \_ (U) $ .  Przykładowo $ \Lambda _0 (u) e 1 \_ { } \otimes { \psi } = e \_ { 1 } \otimes U { \psi } $ i $ \Lambda \_ 0 (u) e \_ { 0 } \otimes { \psi } = e \_ { 0 } \otimes { \psi } $ , gdzie $ e \_ 0 $ i $ e \_ 1 $ są wektorami obliczanymi na podstawie wartości $ 0 $ i $ 1 $ .  Rozważmy na przykład następującą sterowaną $ bramą-Z, $ a następnie możemy to zrobić jako$$
\Lambda\_0 (Z) 1 0 1,0 0 0 1,0 0 0 0 1 0 0 0 = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & -1 \end{bmatrix} = ( \boldone \otimes h) \operatorname { CNOT } ( \boldone \otimes h).
$$

Kompilowanie kontrolowanej unitaries w efektywny sposób jest ważnym wyzwaniem.  Najprostszym sposobem wdrożenia tego wymagania jest tworzenie bazy danych z kontrolowanymi wersjami bram i zastępowanie każdej bramy podstawowej w pierwotnej operacji jednostkowej z kontrolowanym odpowiednikiem.  Jest to często dość wasteful i sprytne Insights często można użyć do zastępowania kilku bram z kontrolowanymi wersjami, aby osiągnąć ten sam wpływ.  Z tego powodu firma Microsoft udostępnia w naszym środowisku algorytmie metodę kontroli lub zezwala użytkownikowi na definiowanie kontrolowanej wersji jednostki, jeśli znana jest zoptymalizowana wersja.

Bramy można również kontrolować przy użyciu informacji klasycznych.  Klasyczno sterowane niebrama, na przykład jest tylko zwykłą niebramą, ale jest stosowane tylko wtedy, gdy klasyczny bit ma wartość $ 1, a nie $ bit Quantum.  W tym sensie kontrolowana Brama może być uważana za instrukcję if w kodzie Quantum, w którym Brama jest stosowana tylko w jednej gałęzi kodu.


Tak jak w przypadku pojedynczej qubit, Brama dwuqubitowa jest uniwersalna, jeśli dowolna wartość $ \times $ macierzy jednostkowej 4 4 może być przybliżona przez iloczyn bram z tego zestawu do dowolnej precyzji.
Przykładem uniwersalnego zestawu bram jest brama Hadamard, Brama T i bramę CNOT. Pobierając produkty z tych bram, możemy przybliżyć każdą macierz jednostkową na dwóch qubits.

## <a name="many-qubit-systems"></a>Wiele systemów qubit
Obserwujemy dokładnie te same wzorce, które zostały zbadane w przypadku dwóch qubitów, aby skompilować Stany Quantum qubit z mniejszych systemów.  Takie Stany są tworzone przez tworzenie iloczynów części mniejszych Stanów.  Rozważmy na przykład kodowanie ciągu bitowego $ 1011001 $ na komputerze Quantum.  Możemy kodować ten

$$
1011001 0 1 1 0 0 1 0 1 1 \equiv \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} 0 0 1.
$$

Bramy Quantum działają w taki sam sposób.  Na przykład jeśli chcemy zastosować $ $ bramę X do pierwszego qubit, a następnie wykonać CNOT między drugim i trzecim qubits, możemy wyrazić tę transformację jako

\begin{align}
&(X \otimes \operatorname { CNOT } _ { 12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone ) \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 0 \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 \end{bmatrix} \otimes \begin{bmatrix} 0 \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ \end{bmatrix} \otimes \begin{bmatrix} \\\\ 1 1 0 0 0\end{bmatrix}\\\\
&\qquad\qquad\equiv0011001.\end{align}

W wielu systemach qubit często istnieje potrzeba alokacji i alokacji qubits, które pełnią rolę pamięci tymczasowej dla komputera Quantum.  Taka qubit jest nazywana Ancilla.  Domyślnie przyjęto, że stan qubit jest inicjowany $ e_0 $ po przydzieleniu.  Ponadto założono, że jest on ponownie zwracany do $ e_0 $ przed cofnięciem alokacji.  To założenie jest ważne, ponieważ jeśli Ancilla qubit będzie Entangled z innym rejestrem qubit, gdy zostanie cofnięta alokacja, proces cofania alokacji spowoduje szkody dla Ancilla.  Z tego powodu zawsze zakładamy, że takie qubits są przywracane do stanu początkowego przed jego udostępnieniem.

Na koniec, chociaż nowe bramy, które trzeba dodać do naszego zestawu bram w celu osiągnięcia uniwersalnego przetwarzania Quantum dla dwóch qubitych komputerów z systemem Quantum, nie trzeba wprowadzać nowych bram w przypadku wieloqubitowego przypadku.  Bramy $ H $ , $ T $ i CNOT tworzą uniwersalną bramę w wielu qubitsach, ponieważ wszelka ogólna transformacja jednostkowa może być dzielona na serię dwóch rotacji qubit.  Następnie możemy wykorzystać teorię opracowaną w przypadku dwóch qubitów i użyć jej ponownie w przypadku wielu qubits.

Chociaż liniowa notacja algebraicznych, z której korzystamy z tego względu, może być używana do opisywania Stanów wieloqubitowych, gdy zwiększamy rozmiar Stanów.  Wynikowa kolumna-wektor dla ciągu o długości 7 bitów, na przykład, jest $ 128 $ , co sprawia, że jest to wyrażenie opisane wcześniej przy użyciu notacji opisanej w przeszłości.  Z tego powodu następnym zaprezentować wspólną notację w ramach przetwarzania Quantum, która pozwala nam na zwięzłe opisywanie tych wektorów wielowymiarowych.
