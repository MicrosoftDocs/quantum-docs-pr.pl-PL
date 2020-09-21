---
title: Modele Quantum dla systemów elektronicznych
description: Dowiedz się, jak systemy elektroniczne molekularne są symulowane przy użyciu modelowania Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4ff3d11bfd4dae5489fc4b7efe4da4ccda00882f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833925"
---
# <a name="quantum-models-for-electronic-systems"></a>Modele Quantum dla systemów elektronicznych

Aby symulować systemy elektroniczne, musimy najpierw zacząć od określenia hamiltonian, które można znaleźć w postaci kanonicznej procedury podziału opisanej powyżej.
W odniesieniu do $N _e $ Electrons z chwilą $p _i $ (w trzech wymiarach) i mas $m _e $ i położenia wektorów $x _i $ wraz z jądrem z opłatami $Z _k e $ w pozycjach $y _k $, operator hamiltonian odczytuje \begin{Equation} \hat{H} = \sum \_ {i = 1} ^ {N \_ e} \frac{\hat{p} \_ i ^ 2} {2 mln \_ e} + \frac {1} {2} \sum \_ {i\ne j} \frac{e ^ 2} {| \hat{x} \_ i-\hat{x} \_ j |}-\sum \_ {i, k} \frac{Z \_ KE ^ 2} {| \hat{x} \_ i-{y} \_ k |} + \frac {1} {2} \ sum_ {k\ne k '} \frac{Z \_ kZ \_ {k '} e ^ 2} {| y \_ k-t \_ k ' |}. \label{EQ: Ham} \end{Equation} operatory czasu $ \hat{p} \_ i ^ 2 $ można wyświetlić w realnym miejscu jako operatorzy Laplacian, tj. $ \hat{p} \_ i ^ 2 =-\partial \_ {x \_ i} ^ 2-\partial \_ {y \_ i} ^ 2-\partial \_ {z \_ i} ^ 2 $.
Tutaj wprowadziliśmy uproszczenie, że jądro jest w stanie spoczynku dla cząsteczki.
Jest to znane jako przybliżenie Oppenheimer i ma być ważne dla spektrum energii niskiego poziomu dla elementu $ \hat{H} $, ponieważ masa elektronów wynosi około $1/1836 $ masy Proton.
Ten operator hamiltonian można łatwo znaleźć, pisząc energię dla systemu $N \_ e $ Electrons i stosując proces kanoniczny podziału opisany w temacie [Quantum Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics).

Aby utworzyć reprezentację macierzy jednostkowej dla $e ^ {-i\hat {H} t} $, musimy reprezentować operator $ \hat{H} $ jako macierz.
W tym celu należy wybrać system współrzędnych lub podstawę do reprezentowania problemu w programie.
Na przykład jeśli $ \ psi_j $ to zestaw funkcji ortogonalnych podstaw dla $N _e $ Electrons, możemy zdefiniować macierz

\begin{Equation} H \_ {i, j} = \int \_ {-\infty} ^ \infty\int \_ {-\infty} ^ \infty \psi ^ { \* } \_ i (x \_ 1) \hat{H} \psi \_ j (x \_ 2) \dd ^ 3: \_ 1 \Dd ^ 3 \_ . \ Label {EQ: discreteHam} \end{Equation}

Chociaż w zasadzie operator $ \hat{H} $ nie jest powiązany i nie działa na skończonej przestrzeni wymiarowej, macierz z elementami $H \_ \{ i, j \} $ powyżej.
Oznacza to, że błędy są naliczane przez wybranie zbyt małego zestawu podstaw; jednak wybranie dużej podstawy może spowodować niepraktyczne symulowanie dynamiki biochemii.
Z tego powodu wybór podstawy, który może zwięzłie reprezentować problem, jest istotny dla rozwiązania problemu ze strukturą elektroniczną.

Istnieje wiele odpowiednich podstaw, których można użyć, i wybór odpowiedniej podstawy, aby dopasować problem, jest znaczną częścią chemii Quantum.
Prawdopodobnie najprostszymi takimi zestawami są Slater-Type-Orbitals (konie), które są (ortogonalne) rozwiązania do równania Schrödinger (tj. eigenfunctions of $ \hat{H} $) dla atomów, takich jak.
Inne zestawy podstawowe, takie jak orbitalsy płaszczyzny lub rzeczywiste miejsce, mogą być używane i aby uzyskać bardziej szczegółowe informacje, odwołując się do czytnika chcesz wiedzieć do standardowego tekstu ["Teoria struktury elektronicznej molekularnej"](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) przez Helgaker.

Chociaż Stany używane w powyższym modelu mogą wydawać się dowolne, Mechanics Quantum nakłada ograniczenia dotyczące stanów, które można znaleźć w charakterze.
W szczególności wszystkie prawidłowe elektroniczne Stany Quantum muszą mieć zabezpieczenia symetryczne w ramach wymiany etykiet elektronów.
Oznacza to, że jeśli $ \psi (x_1, x_2) $ była funkcją Wave dla wspólnego stanu Quantum dwóch Electrons, musimy mieć wartość $ $ \psi (x_1, x_2) =-\psi (x_2, x_1).
$ $ Zasada wykluczenia Pauli, która zakazuje, aby dwa electronsy były w tym samym stanie Quantum to, fascinatingly, bezpośrednią konsekwencją tego prawa, tak jak w przypadku wymiany dwóch Electrons znajdujących się w tej samej pozycji $ \psi (x_1, x_1) \mapsto \psi (x_1 x_1) \ne-\psi (x_1, x_1) $ chyba $ \psi (x_1 , x_1) = 0 $.
Z tego względu Stany początkowe muszą zostać wybrane do przestrzegania tej właściwości antysymetrii i z kolei nigdy nie mają dwóch Electrons w tym samym stanie.
Jest to kluczowa struktura elektroniczna, ponieważ zabrania wielu electronsów w tym samym stanie, a z kolei umożliwia komputerom Quantum użycie jednego bitu Quantum do przechowywania liczby Electrons w danym stanie Quantum.

Mimo że Quantum Mechanics może być symulowany na komputerze Quantum przez dyskretyzowanie atrybutu te Stany, większość pracy w polu ma eschewed to podejście, ponieważ wymaga wielu qubits do przechowywania stanów i wymaga skomplikowanej procedury przygotowania stanu do przygotowania stanu początkowego antysymetrycznego.
Na szczęście te problemy można sidestepped, wyświetlając problem z symulacją z innej perspektywy.
