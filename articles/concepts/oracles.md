---
title: Wyrocznie kwantowe
description: Dowiedz się, jak korzystać z i definiować bazy danych Quantum Oracle, czarne pola, które są używane jako dane wejściowe w innym algorytmie.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 747c08df110f1f10efe552628d15e3500509b690
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269562"
---
# <a name="quantum-oracles"></a>Bazy danych Quantum Oracle

Oracle $O $ jest operacją "czarna Box", która jest używana jako dane wejściowe w innym algorytmie.
Często takie operacje są definiowane przy użyciu klasycznej funkcji $f: \\ {0, 1 \\ } ^ n \to \\ {0, 1 \\ } ^ m $ , która pobiera $ binarne dane wejściowe $n-bitowe i tworzy $m $ bitowe dane wyjściowe.
W tym celu należy wziąć pod uwagę określone dane wejściowe binarne $x = (x_ {0 } , x_ {1 } , \dots, x_ {n-1 } ) $.
Możemy oznaczyć oznaczenie qubit States jako $ \ket { \vec{x } } = \ket{x_ {0 } } \otimes \ket{x_ {1 } } \otimes \cdots \otimes \ket{x_ {n-1 } } $.

Możemy najpierw spróbować zdefiniować $O $ tak, aby $O \ket {x } = \ket{f (x)} $, ale ma to kilka problemów.
Po pierwsze $f $ może mieć inny rozmiar danych wejściowych i wyjściowych ($n \ne m $ ), takie jak zastosowanie $O $ spowoduje zmianę liczby qubits w rejestrze.
Sekunda, nawet jeśli $n = m $ , funkcja nie może być odwracalna: jeśli $f (x) = f (y) $ dla niektórych $x \ne y $ , następnie $O \ket {x } = O \ket {y } $, ale $O ^ \dagger o \ket {x } \ne O ^ \dagger o \ket {y } $.
Oznacza to, że nie będzie możliwe konstruowanie sąsiedniej operacji $O ^ \dagger $ , a firmy Oracle muszą mieć zdefiniowane dla nich sąsiadujące.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Definiowanie firmy Oracle według jej wpływu na Stany obliczeniowe
Firma Microsoft może zająć się obydwoma problemami, wprowadzając drugi rejestr $m $ qubits do przechowywania naszej odpowiedzi.
Następnie zdefiniujemy efekt działania firmy Oracle na wszystkich stanach obliczeniowych: dla wszystkich $x \In \\ {0, 1 \\ } ^ n $ i $y \In \\ {0, 1 \\ } ^ m $ ,

$ $ \begin{align}
    O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.
\end{align}
$$

Teraz $O = O ^ \dagger $ przez konstrukcję, dlatego zostały rozwiązane oba poprzednie problemy.

> [!TIP]
> Aby zobaczyć, że $O = O ^ {\dagger } $, należy pamiętać, że $O ^ 2 = \boldone $ od $a \oplus b \oplus b = a $ dla wszystkich $a, b \In \{ 0, 1 \} $.
> W związku z tym $O \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y } $.

Ważne jest, aby w ten sposób definiować Oracle w taki sposób, że w przypadku każdego stanu podstawy obliczeniowej $ \ket{x } \ket{y } $ definiuje również sposób $ działania $O w przypadku każdego innego stanu.
Następuje to bezpośrednio od faktu, że $O $ , podobnie jak wszystkie operacje Quantum, są liniowe w stanie, w którym działa.
Rozważmy operację Hadamard, na przykład, która jest definiowana przez $H \ket{0 } = \ket { +} $ i $H \ket{1 } = \ket { -} $.
Jeśli chcemy wiedzieć, jak $H $ działa na serwerze $ \ket { +} $, możemy użyć tej $H $ jest liniowy,

$ $ \begin{align}
H \ket { +} & = \frac{1 } {\sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (H \ket {0 } + H \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .
\end{align}
$$

W przypadku definiowania naszej $O firmy Oracle $ można w podobny sposób użyć, aby wszystkie Stany $ \ket { \psi } $ na $n + m $ qubits mogły być zapisywane jako

$ $ \begin{align}
\ket { \psi } & = \ sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y}
\end{align}
$$

gdzie $ \Alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ m \to \mathbb{C } $ reprezentuje współczynniki stanu $ \ket { \psi } $. Tak więc,

$ $ \begin{align}
O \ket { \psi } & = O \ sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, t) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y \oplus f (x)}.
\end{align}
$$

## <a name="phase-oracles"></a>Fazy Oracle
Alternatywnie możemy kodować $f $ do $O Oracle $ poprzez zastosowanie _fazy_ w oparciu o dane wejściowe do $O $ .
Na przykład możemy zdefiniować $O w $ taki sposób, że $ $ \begin{align}
    O \ket{x } = (-1) ^ {f (x)} \ket{x } .
\end{align}
$ $ Jeśli faza Oracle działa na rejestrze początkowo w stanie bazowym $ \ket{x } $, wówczas ta faza jest globalnym etapem i dlatego nie jest zauważalna.
Jednak taka Oracle może być bardzo wydajnym zasobem, jeśli jest stosowana do nadpozycji lub jako kontrolowanej operacji.
Rozważmy na przykład fazę orcale $O _f $ dla funkcji pojedynczej qubit $f $ .
Następnie $ $ \begin{align}
    O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}.
\end{align}
$$

Ogólnie rzecz biorąc, oba widoki rozwiązań firmy Oracle można rozszerzyć, aby reprezentować funkcje klasyczne, które zwracają liczby rzeczywiste, a nie tylko jeden bit.

Wybór najlepszego sposobu implementacji Oracle zależy od tego, jak ta Oracle będzie używana w danym algorytmie.
Na przykład [algorytm Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) opiera się na bazie danych Oracle zaimplementowane w pierwszej kolejności, natomiast [algorytm Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) opiera się na platformie Oracle zaimplementowane w drugi sposób.


Aby uzyskać więcej informacji, zalecamy dyskusję w [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
