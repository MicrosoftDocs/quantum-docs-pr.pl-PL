---
title: Wyrocznie kwantowe
description: Dowiedz się, jak korzystać z i definiować bazy danych Quantum Oracle, czarne pola, które są używane jako dane wejściowe w innym algorytmie.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904931"
---
# <a name="quantum-oracles"></a>Bazy danych Quantum Oracle

Oracle $O $ jest operacją "Black Box", która jest używana jako dane wejściowe w innym algorytmie.
Często takie operacje są definiowane przy użyciu klasycznej funkcji $f: \\{0, 1\\} ^ n \to \\{0, 1\\} ^ m $, które pobiera $n $-bitowy binarny dane wejściowe i tworzy $m $-bitowy binarne dane wyjściowe.
W tym celu należy wziąć pod uwagę określone dane wejściowe danych binarnych $x = (x_{0}, x_{1}, \dots, x_ {n-1}) $.
Możemy etykietować Stany qubit jako $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_ {n-1}} $.

Możemy najpierw spróbować zdefiniować $O $, aby $O \ket{x} = \ket{f (x)} $, ale ma to kilka problemów.
Po pierwsze, $f $ może mieć inny rozmiar danych wejściowych i wyjściowych ($n \ne m $), takie jak zastosowanie $O $ spowoduje zmianę liczby qubits w rejestrze.
Po drugie, nawet jeśli $n = m $, funkcja nie może być odwracalna: Jeśli $f (x) = f (y) $ dla niektórych $x \ne y $, a następnie $O \ket{x} = O\ket {y} $, ale $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $.
Oznacza to, że nie będzie możliwe konstruowanie sąsiedniej operacji $O ^ \dagger $, a firmy Oracle muszą mieć zdefiniowane dla nich sąsiadujące.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definiowanie firmy Oracle według jej wpływu na Stany obliczeniowe
Firma Microsoft może obsłużyć oba te problemy, wprowadzając drugi rejestr $m $ qubits do przechowywania naszej odpowiedzi.
Następnie zdefiniujemy efekt działania firmy Oracle na wszystkich stanach obliczeniowych: dla wszystkich $x \In \\{0, 1\\} ^ n $ i $y \In \\{0, 1\\} ^ m $,

$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.
\end{align} $ $

Teraz $O = O ^ \dagger $ według konstrukcji, dlatego zostały rozwiązane oba poprzednie problemy.

> [!TIP]
> Aby zobaczyć, że $O = O ^ {\dagger} $, należy pamiętać, że $O ^ 2 = \boldone $, $a \oplus b \oplus b = a $ dla wszystkich $a, b \In \{0, 1\}$.
> W związku z tym $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.

Ważne jest, aby w ten sposób definiować Oracle w ten sposób dla każdego stanu podstawy obliczeniowej $ \ket{x}\ket{y} $, a także definiować, jak $O $ działa w przypadku każdego innego stanu.
Następuje to bezpośrednio od faktu, że $O $, podobnie jak wszystkie operacje Quantum, jest liniowy w stanie, w którym działa.
Rozważmy operację Hadamard, na przykład, która jest definiowana przez $H \ket{0} = \ket{+} $ i $H \ket{1} = \ket{-}$.
Jeśli chcielibyśmy dowiedzieć się, jak $H $ działa na $ \ket{+} $, możemy użyć tego $H $ jest liniowy,

$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.
\end{align} $ $

W przypadku definiowania naszej bazy danych Oracle $O $ można w podobny sposób użyć, aby wszystkie Stany $ \ket{\psi} $ w $n + m $ qubits mogły być zapisywane jako

$ $ \begin{align} \ket{\psi} & = \ sum_ {x \In \\{0, 1\\} ^ n, y \In \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y} \end{align} $ $

gdzie $ \Alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \to \mathbb{C} $ reprezentuje współczynniki stanu $ \ket{\psi} $. Dział

$ $ \begin{align} O \ket{\psi} & = O \ sum_ {x \In \\{0, 1\\} ^ n, y \In \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y} \\\\ & = \ sum_ {x \In \\{0, 1\\} ^ n, y \In \\{0, 1\\} ^ m} \Alpha (x, y) O \ket{x} \ket{y} \\\\ & = \ sum_ {x \In \\{0, 1\\} ^ n , y \In \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y \oplus f (x)}.
\end{align} $ $

## <a name="phase-oracles"></a>Fazy Oracle
Alternatywnie możemy kodować $f $ do $O Oracle $ przez zastosowanie _fazy_ w oparciu o dane wejściowe $O $.
Na przykład możemy zdefiniować $O $ w taki sposób, aby $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.
\end{align} $ $ Jeśli faza Oracle działa na bieżąco z rejestrem w stanie wyliczenia $ \ket{x} $, to faza jest globalnym etapem i dlatego nie jest zauważalna.
Jednak taka Oracle może być bardzo wydajnym zasobem, jeśli jest stosowana do nadpozycji lub jako kontrolowanej operacji.
Rozważmy na przykład fazę orcale $O _f $ dla funkcji pojedynczej qubit $f $.
Następnie $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.
\end{align} $ $

Ogólnie rzecz biorąc, oba widoki rozwiązań firmy Oracle można rozszerzyć, aby reprezentować funkcje klasyczne, które zwracają liczby rzeczywiste, a nie tylko jeden bit.

Wybór najlepszego sposobu implementacji Oracle zależy od tego, jak ta Oracle będzie używana w danym algorytmie.
Na przykład [algorytm Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) opiera się na bazie danych Oracle zaimplementowane w pierwszej kolejności, natomiast [algorytm Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) opiera się na platformie Oracle zaimplementowane w drugi sposób.


Aby uzyskać więcej informacji, zalecamy dyskusję w [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
