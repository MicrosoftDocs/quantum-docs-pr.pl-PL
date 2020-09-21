---
title: Biblioteka dla kwantowego uczenia maszynowego
description: Dowiedz się, jak uczenie maszynowe jest używane w systemach Quantum
author: alexeib2
ms.author: alexeib
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9f7f892fb2b76432942c86163497c22f0c73d51f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833799"
---
# <a name="introduction-to-quantum-machine-learning"></a>Wprowadzenie do Machine Learning Quantum

## <a name="framework-and-goals"></a>Struktura i cele

Kodowanie i przetwarzanie informacji przy użyciu Quantum jest zaawansowaną alternatywą dla klasycznego klasyfikatora funkcji uczenia maszynowego. W szczególności pozwala nam kodować dane w rejestrach Quantum, które są zwięzłe względem liczby funkcji, systematycznie wykorzystuj Entanglement Quantum jako zasób obliczeniowy i wykorzystując pomiar Quantum dla wnioskowania klas.
Klasyfikator Quantum oparty na obwodzie to stosunkowo proste rozwiązanie Quantum, które łączy dane kodowania z szybkim obwodem Quantum Entangling/disentangling, a następnie pomiarem do wywnioskowania etykiet klas próbek danych.
Celem jest zapewnienie klasycznej charakterystyki i magazynowania obwodów podmiotu, a także hybrydowego procesu Quantum/klasycznego szkolenia parametrów obwodu nawet dla bardzo dużych miejsc funkcji.

## <a name="classifier-architecture"></a>Architektura klasyfikatora

Klasyfikacja to nadzorowane zadanie uczenia maszynowego, w którym celem jest wywnioskowanie etykiet klas $ \{ y_1, y_2, \ldots, y_d \} $ niektórych próbek danych. "Zestaw danych szkoleniowych" to kolekcja przykładów $ \mathcal{D} = \{ (x, y)} $ ze znanymi wstępnie przypisanymi etykietami. Tutaj $x $ to przykład danych, a $y $ to jego znana etykieta o nazwie "etykieta szkoleniowa".
Podobnie jak w przypadku tradycyjnych metod, klasyfikacja Quantum składa się z trzech kroków:
- kodowanie danych
- Przygotowanie stanu klasyfikatora
- pomiar ze względu na probabilistyczne charakter pomiaru, te trzy kroki muszą być powtórzone wielokrotnie. Zarówno kodowanie, jak i obliczenia stanu klasyfikatora są wykonywane za pomocą *obwodów Quantum*. Gdy obwód kodowania jest zwykle oparty na danych i bez parametrów, obwód klasyfikatora zawiera wystarczającą zestaw parametrów, które można uzyskać. 

W proponowanym rozwiązaniu obwód klasyfikatora składa się z rotacji jednoqubitowych i trójwymiarowych rotacji z dwoma qubitami. W tym miejscu są to kąty obrotu. Bramy rotacji i kontrolowanej rotacji są znane jako *uniwersalne* dla obliczeń Quantum, co oznacza, że każda macierz masy jednostkowej może być rozłożone na wystarczająco długi obwód składający się z takich bram.

W proponowanej wersji obsługiwana jest tylko jedna obwód, po której następuje szacowanie o pojedynczej częstotliwości.
W takim przypadku rozwiązanie jest analogową usługą Quantum dla maszyny wektorowej pomocy technicznej z niewielką ilością jądra wielostopniowego.

![Multilayer Perceptron a klasyfikator skoncentrowany obwodu](~/media/DLvsQCC.png)

Prosty projekt klasyfikatora Quantum można porównać do tradycyjnego rozwiązania do obsługi maszyn wektorowych (SVM). Wnioskowanie dla przykładu danych $x $ w przypadku SVM jest wykonywane przy użyciu optymalnego formularza jądra $ \sum \ alpha_j k (x_j, x) $, gdzie $k $ jest pewną funkcją jądra.

Z kolei klasyfikator Quantum używa predykcyjności $p (y │ x, U (\theta)) = 〈 U (\theta) x | M | U (\theta) x 〉 $, który jest podobny w duchu, ale technicznie inny. W tym przypadku, gdy używane jest proste kodowanie amplitudy, $p (y │ x, U (\theta)) $ jest postacią kwadratową w amplitudach $x $, ale współczynniki tego formularza nie są już niezależne. Zamiast tego są one agregowane z elementów macierzy obwodu $U (\theta) $, które zwykle mają znacznie mniej bardziej poznanie parametry $ \theta $ niż wymiar wektora $x $. Stopień wielomianu $p (y │ x, U (\theta)) $ w oryginalnych funkcjach można zwiększyć do wartości $2 ^ l $ przy użyciu kodowania produktu Quantum na $l $ kopie $x $.

Nasza architektura analizuje stosunkowo płytki obwodów, co w związku z tym musi być *szybko Entangling* w celu przechwycenia wszystkich korelacji między funkcjami danych we wszystkich zakresach. Przykład najbardziej przydatnego, szybkiego składnika obwodu Entangling pokazano na poniższej ilustracji. Mimo że obwód z tą geometrią składa się tylko z bram o $3 n + 1 $, macierz wagi jednostki, która jest obliczana, zapewnia znaczącą komunikację krzyżową między funkcjami $2 ^ n $.

![Szybko Entangling obwód Quantum na 5 qubits (z dwiema warstwami cyklicznymi).](~/media/5-qubit-qccc.png)

Obwód w powyższym przykładzie składa się z 6 G_1 bram qubit, \ldots, G_5; G_ {16} ) $ i 10 2-qubits bramy $ (G_6, \ldots, G_ {15} ) $. Przy założeniu, że każda Brama jest zdefiniowana za pomocą jednego z parametrów, który ma 16 parametrów, podczas gdy wymiar 5-qubit Hilbert jest 32. Taka geometria obwodu może być w łatwy sposób uogólniony do dowolnego $ngo rejestru $-qubit, gdy $n $ jest nieparzysta, co generuje obwody z $3 n + 1 $ parametrów dla przestrzeni funkcji $2 ^ n $-wymiarową.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Szkolenie klasyfikatora jako nadzorowane zadanie uczenia się

Szkolenie modelu klasyfikatora polega na znalezieniu optymalnych wartości parametrów operacyjnych, takich jak maksymalizacja średniego prawdopodobieństwa wywnioskowania prawidłowych etykiet szkoleniowych na przykładach szkoleniowych.
W tym scenariuszu dotyczymy tylko wypróbujemy z klasyfikacją dwóch poziomów, np. $d = $2 i tylko dwie klasy z etykietami $y _1, y_2 $.

> [!NOTE]
> Zasadnym sposobem uogólniania metod do dowolnej liczby klas jest zamienienie qubits z qudits, tj. jednostkami Quantum z $d $, i pomiaru dwukierunkowego z $dnym pomiarem.

### <a name="likelihood-as-the-training-goal"></a>Prawdopodobieństwo, że cel szkolenia

Uwzględniając $Uy obwód Quantum, gdzie $ \theta $ jest wektorem parametrów, i wskazując końcowy pomiar przez $M $, średnie prawdopodobieństwo poprawnego wnioskowania etykiety to $ $ \begin{align} \mathcal{L} (\theta) = \frac {1} {| \mathcal{D} |} \left (\ sum_ {(x, y_1) \In\mathcal{D}} P (M = y_1 | U (\theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\theta) x) \right) \end{align} $ $, gdzie $P (M = y | z) $ jest prawdopodobieństwem mierzenia $y $ w stanie Quantum $z $.
W tym miejscu wystarczy zrozumieć, że funkcja prawdopodobieństwo $ \mathcal{L} (\theta) $ jest gładka w $ \theta $, a jej pochodna w dowolnym $ \ theta_j $ może zostać obliczona w ramach tego samego protokołu Quantum, co jest używane do obliczania prawdopodobieństwa samego działania. Pozwala to na optymalizację $ \mathcal{L} (\theta) $ według gradientu.

### <a name="classifier-bias-and-training-score"></a>Ocena odchylenia i szkolenia klasyfikatora

Uwzględniając pewne pośrednie (lub końcowe) wartości parametrów w $ \theta $, musimy zidentyfikować jedną rzeczywistą wartość $b $ wie jako *bias klasyfikatora* , aby wykonać wnioskowanie. Reguła wnioskowania o etykiecie działa w następujący sposób: 
- Przykładem $x $ jest przypisana etykieta $y _2 $ if i tylko wtedy, gdy $P (M = y_2 | U (\theta) x) + b > $0,5 (RULE1) (w przeciwnym razie jest przypisana etykieta $y _1 $)

Jasno $b $ musi znajdować się w interwale $ (-0,5, + 0,5) $, aby mieć znaczenie.

Przypadek szkoleniowy $ (x, y) \In \mathcal{D} $ jest uznawany za nieprawidłową *klasyfikację* na podstawie odchylenia $b $, jeśli etykieta wnioskowana dla $x $ AS na RULE1 jest w rzeczywistości różna od $y $. Ogólna liczba *nieocenionych klasyfikacji to wynik szkoleniowy* klasyfikatora z uwzględnieniem odchylenia $b $. *Optymalna* wartość klasyfikatora $b $ minimalizuje wynik szkolenia. Jest to łatwe do sprawdzenia, czy z góry obliczone oszacowania prawdopodobieństwa $ \{ P (M = y_2 | U (\theta) x) | (x, *) \in\mathcal{D} \} $, optymalna wartość klasyfikatora może być znaleziona przez wyszukiwanie binarne w interwale $ (-0,5, + 0,5) $ przez utworzenie maksymalnie $ \ Log_2 (| \mathcal{D} |) $ kroki.

### <a name="reference"></a>Dokumentacja

Te informacje powinny być wystarczające, aby rozpocząć odtwarzanie kodu. Jeśli jednak chcesz dowiedzieć się więcej na temat tego modelu, zapoznaj się z oryginalną propozycją: [ *"skoncentrowane na obwodach klasyfikatory Quantum", Maria Schuld, Alex Bocharov, krysta Svore i Nathana Wiebe*](https://arxiv.org/abs/1804.00633)

Oprócz przykładu kodu, który będzie widoczny w następnych krokach, można również rozpocząć Eksplorowanie klasyfikacji Quantum w [tym samouczku](https://github.com/microsoft/QuantumKatas/tree/main/tutorials/QuantumClassification) 
