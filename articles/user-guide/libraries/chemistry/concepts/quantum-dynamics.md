---
title: Dynamics Quantum
description: Poznaj podobieństwa i różnice między elementami Quantum Dynamics i klasyczną dynamiką.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4dec0ed7346cde579e5692fcf13519d4ce05cb00
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856260"
---
# <a name="quantum-dynamics"></a>Dynamics Quantum

Quantum Mechanics jest w dużym stopniu analizą bioprocesora Quantum, która dąży do zrozumienia, w jaki sposób początkowy stan Quantum $ \ket{\psi (0)} $ różni się w zależności od czasu (zobacz dokumentację [koncepcyjną](xref:microsoft.quantum.concepts.dirac) na potrzeby przetwarzania Quantum, aby uzyskać więcej informacji na temat notacji Dirac).
W odróżnieniu od tego pierwotnego warunku jest to stan Quantum, czas ewolucji i Specyfikacja dynamicznego systemu Quantum. jest to poszukiwany stan Quantum $ \ket{\psi (t)} $.
Przed kontynuowaniem wyjaśniania systemu Quantum Dynamics warto wykonać krok z powrotem i zastanowić się nad klasycznym dynamiką, ponieważ zapewnia wgląd w to, w jaki sposób Mechanics Quantum nie różni się od klasycznej usługi Dynamics.

W klasycznej usłudze Dynamics wiemy, że firma Microsoft wie od firmy Kowalski, że pozycja cząsteczek powstała w oparciu o $F (x, t) = No= m\frac {\ DD ^ 2} {\dd t ^ 2} {x} (t) $, gdzie $F (x, t) $ to siła, $m $ jest masą, a $a $ to przyspieszenie.
Następnie, uwzględniając początkową pozycję $x (0) $, czas ewolucji $t $, i opis sił, które działają na cząsteczek, możemy znaleźć $x (t) $, rozwiązując równanie różnicowe określone przez równania Kowalski dla $x (t) $.
Określenie sił w ten sposób jest nieco bólu.
Dlatego często wyrażamy siły pod względem potencjalnej energii systemu, która daje nam $-\ partial_x V (x, t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $.
W tym przypadku, w przypadku cząsteczek, dynamika systemu jest określana tylko przez potencjalną funkcję energetyczną, masę cząsteczek i czas ewolucji.

Szerszy język jest często wprowadzany dla klasycznej usługi Dynamics, która wykracza poza $F = ma $.
Jednym sformułowaniem, który jest szczególnie przydatny w Mechanics Quantum, jest hamiltonian Mechanics.
W hamiltonian Mechanics, całkowita energia systemu i (uogólnione) pozycje i momentu, dają wszystkie informacje, które są konieczne do opisania ruchu dowolnego klasycznego obiektu.
W celu $f (x, p, t) $ to niektóre funkcje uogólnionych pozycji $x $ i $p $ w systemie i let $H (x, p, t) $ to funkcja hamiltonian.
Na przykład, jeśli przyjmujemy $f (x, p, t) = x (t) $ i $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $, odzyskamy powyższe przypadki newtonian Dynamics.
Ogólnie rzecz biorąc, \begin{align} \frac{d}{DT} f &= \ partial_t f-(\ partial_x H \ partial_p f + \ partial_p H \ partial_x f) \\ \\ & \defeq \ partial_t f + \\ {f, H \\ }.
\end{align} tutaj $ \\ {f, H \\ } $ jest nazywana [nawiasem Poissona](https://en.wikipedia.org/wiki/Poisson_bracket) i pojawia się ogólnie w klasycznej usłudze Dynamics z powodu centralnej roli, która jest odtwarzana w ramach definiowania dynamiki.

Dynamics Quantum można opisać przy użyciu dokładnie tego samego języka.
Hamiltonian, lub całkowita energia, całkowicie określa dynamikę wszystkich zamkniętych systemów Quantum.
Istnieją jednak pewne istotne różnice między tymi dwoma teorie.
W klasycznym Mechanics $x $ i $p $ są tylko liczbami, natomiast w Quantum Mechanics nie są.
Rzeczywiście nie są one jeszcze takie: $xp \ne px $.

Prawidłowym pojęciem matematycznym opisującym te obiekty inne niż podróży jest operator, który w przypadkach, gdy $x $ i $p $ mogą pobrać tylko dyskretny zestaw wartości, jest zgodny z koncepcją macierzy.
W związku z tym dla uproszczenia przyjęto, że nasz system Quantum jest skończona, aby można go było opisać przy użyciu [wektorów i macierzy](xref:microsoft.quantum.concepts.vectors).
Firma Microsoft zaleca, aby te macierze były hermitian (co oznacza, że transpozycja sprzężenia jest taka sama jak w przypadku oryginalnej macierzy).
Gwarantuje to, że eigenvalues macierzy są prawdziwe; warunek, który nakładamy, aby zapewnić, że podczas mierzenia ilości, takiej jak pozycja, że nie powrócisz liczby urojonej.

Podobnie jak analogiczne pozycje i pędu w Mechanics Quantum muszą zostać zastąpione przez operatory, funkcja hamiltonian musi być w podobny sposób zastępowana przez operator.
Na przykład w przypadku cząstki w wolnym miejscu mamy $H (x, p) = p ^ 2/2 mln $ w ramach Quantum Mechanics operator hamiltonian $ \hat{H} $ to $ \hat{H} = \hat{p} ^ 2/2 mln $, gdzie $ \hat{p} $ jest operatorem h.
Z tej perspektywy przechodzenie z klasycznego do Quantum Dynamics tylko obejmuje zastąpienie zmiennych używanych w zwykłych Dynamics z operatorami.
Po zbudowaniu operatora hamiltonian przez przetłumaczenie zwykłej klasycznej hamiltonian na język Quantum, możemy przedstawić dynamikę dowolnej ilości mechanicznej jednostki Quantum (tj. operatorów mechanicznych Quantum) $ \hat{f} (t) $ przez \begin{align} \frac{d}{DT} \hat{f} = \ partial_t \hat{f} + [\hat{f}, \hat{H}], \end{align} gdzie $ [f, H] = fH-HF $ jest znany jako commutator.
To wyrażenie jest takie samo jak w przypadku klasycznego wyrażenia podanego powyżej z różnicą, że nawias Poissona $ \\ {f, H \\ } $ jest zastępowany przez commutator między $f $ i $H $.
Ten proces wykonywania klasycznej hamiltonian i używania go do znajdowania hamiltonian Quantum jest znany w Quantum żargon jako podziału kanoniczny.

Jakie operatory $f $ są najbardziej interesujące?  Odpowiedź na ten temat zależy od problemu, który ma zostać rozwiązany.
Prawdopodobnie najbardziej przydatną ilością do znalezienia jest operator stanu Quantum, który został omówiony w poprzedniej dokumentacji koncepcyjnej, można użyć do wyodrębnienia wszystkich informacji o usłudze Dynamics.
Po wykonaniu tej czynności (i uproszczeniu wyniku w przypadku, gdy ma on czysty stan), znaleziono Schrödinger równanie dla stanu Quantum \begin{align} i \ partial_t \ket{\psi (t)} = \hat{H} (t) \ket{\psi (t)}.
\end{align}

To równanie, ale być może mniej intuicyjne niż powyższy, daje, że najprostsze wyrażenie dla zrozumienie, jak symulować dynamikę Quantum na komputerze Quantum lub klasycznym.
Wynika to z faktu, że rozwiązanie do równania różnicowego może być wyrażone w następującej postaci (w przypadku, gdy hamiltonian jest stałą w $t $) \begin{align} \ket{\psi (t)} = e ^ {-iHt} \ket{\psi (0)}.
\end{align} tutaj $e ^ {-iHt} $ jest macierzą jednostkową.
Oznacza to, że istnieje obwód Quantum, który może zostać zaprojektowany w celu jego wykonania, ponieważ komputery Quantum mogą dokładnie przybliżać każdą macierz jednostkową.
Ten etap znajdowania obwodu Quantum w celu zaimplementowania operatora ewolucji czasu Quantum $e ^ {-iHt} $ jest często nazywany symulacją Quantum lub w szczególności z symulacją dynamiczną Quantum.
