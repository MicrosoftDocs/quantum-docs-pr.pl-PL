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
ms.openlocfilehash: 31e43940fc0607b15ccefcfae6be7122227b3d64
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630320"
---
# <a name="quantum-oracles"></a><span data-ttu-id="e4779-103">Bazy danych Quantum Oracle</span><span class="sxs-lookup"><span data-stu-id="e4779-103">Quantum Oracles</span></span>

<span data-ttu-id="e4779-104">Oracle $O $ jest operacją "czarna Box", która jest używana jako dane wejściowe w innym algorytmie.</span><span class="sxs-lookup"><span data-stu-id="e4779-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="e4779-105">Często takie operacje są definiowane przy użyciu klasycznej funkcji $f: \\ {0, 1 \\ } ^ n \to \\ {0, 1 \\ } ^ m $ , która pobiera $ binarne dane wejściowe $n-bitowe i tworzy $m $ bitowe dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="e4779-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="e4779-106">W tym celu należy wziąć pod uwagę określone dane wejściowe binarne $x = (x_ {0 } , x_ {1 } , \dots, x_ {n-1 } ) $.</span><span class="sxs-lookup"><span data-stu-id="e4779-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="e4779-107">Możemy oznaczyć oznaczenie qubit States jako $ \ket { \vec{x } } = \ket{x_ {0 } } \otimes \ket{x_ {1 } } \otimes \cdots \otimes \ket{x_ {n-1 } } $.</span><span class="sxs-lookup"><span data-stu-id="e4779-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="e4779-108">Możemy najpierw spróbować zdefiniować $O $ tak, aby $O \ket {x } = \ket{f (x)} $, ale ma to kilka problemów.</span><span class="sxs-lookup"><span data-stu-id="e4779-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="e4779-109">Po pierwsze $f $ może mieć inny rozmiar danych wejściowych i wyjściowych ($n \ne m $ ), takie jak zastosowanie $O $ spowoduje zmianę liczby qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="e4779-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="e4779-110">Sekunda, nawet jeśli $n = m $ , funkcja nie może być odwracalna: jeśli $f (x) = f (y) $ dla niektórych $x \ne y $ , następnie $O \ket {x } = O \ket {y } $, ale $O ^ \dagger o \ket {x } \ne O ^ \dagger o \ket {y } $.</span><span class="sxs-lookup"><span data-stu-id="e4779-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="e4779-111">Oznacza to, że nie będzie możliwe konstruowanie sąsiedniej operacji $O ^ \dagger $ , a firmy Oracle muszą mieć zdefiniowane dla nich sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="e4779-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="e4779-112">Definiowanie firmy Oracle według jej wpływu na Stany obliczeniowe</span><span class="sxs-lookup"><span data-stu-id="e4779-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="e4779-113">Firma Microsoft może zająć się obydwoma problemami, wprowadzając drugi rejestr $m $ qubits do przechowywania naszej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="e4779-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="e4779-114">Następnie zdefiniujemy efekt działania firmy Oracle na wszystkich stanach obliczeniowych: dla wszystkich $x \In \\ {0, 1 \\ } ^ n $ i $y \In \\ {0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="e4779-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="e4779-115">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-115">$$ \begin{align}</span></span>
    <span data-ttu-id="e4779-116">O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="e4779-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="e4779-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-117">\end{align}</span></span>
$$

<span data-ttu-id="e4779-118">Teraz $O = O ^ \dagger $ przez konstrukcję, dlatego zostały rozwiązane oba poprzednie problemy.</span><span class="sxs-lookup"><span data-stu-id="e4779-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="e4779-119">Aby zobaczyć, że $O = O ^ {\dagger } $, należy pamiętać, że $O ^ 2 = \boldone $ od $a \oplus b \oplus b = a $ dla wszystkich $a, b \In \{ 0, 1 \} $.</span><span class="sxs-lookup"><span data-stu-id="e4779-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="e4779-120">W związku z tym $O \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y } $.</span><span class="sxs-lookup"><span data-stu-id="e4779-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="e4779-121">Ważne jest, aby w ten sposób definiować Oracle w taki sposób, że w przypadku każdego stanu podstawy obliczeniowej $ \ket{x } \ket{y } $ definiuje również sposób $ działania $O w przypadku każdego innego stanu.</span><span class="sxs-lookup"><span data-stu-id="e4779-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="e4779-122">Następuje to bezpośrednio od faktu, że $O $ , podobnie jak wszystkie operacje Quantum, są liniowe w stanie, w którym działa.</span><span class="sxs-lookup"><span data-stu-id="e4779-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="e4779-123">Rozważmy operację Hadamard, na przykład, która jest definiowana przez $H \ket{0 } = \ket { +} $ i $H \ket{1 } = \ket { -} $.</span><span class="sxs-lookup"><span data-stu-id="e4779-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="e4779-124">Jeśli chcemy wiedzieć, jak $H $ działa na serwerze $ \ket { +} $, możemy użyć tej $H $ jest liniowy,</span><span class="sxs-lookup"><span data-stu-id="e4779-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="e4779-125">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-125">$$ \begin{align}</span></span>
<span data-ttu-id="e4779-126">H \ket { +} & = \frac{1 } {\sqrt{2 } } H (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (H \ket {0 } + H \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="e4779-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="e4779-127">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-127">\end{align}</span></span>
$$

<span data-ttu-id="e4779-128">W przypadku definiowania naszej $O firmy Oracle $ można w podobny sposób użyć, aby wszystkie Stany $ \ket { \psi } $ na $n + m $ qubits mogły być zapisywane jako</span><span class="sxs-lookup"><span data-stu-id="e4779-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="e4779-129">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-129">$$ \begin{align}</span></span>
<span data-ttu-id="e4779-130">\ket { \psi } & = \ sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="e4779-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="e4779-131">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-131">\end{align}</span></span>
$$

<span data-ttu-id="e4779-132">gdzie $ \Alpha: \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ m \to \mathbb{C } $ reprezentuje współczynniki stanu $ \ket { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="e4779-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="e4779-133">Tak więc,</span><span class="sxs-lookup"><span data-stu-id="e4779-133">Thus,</span></span>

<span data-ttu-id="e4779-134">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-134">$$ \begin{align}</span></span>
<span data-ttu-id="e4779-135">O \ket { \psi } & = O \ sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, t) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \In \\ {0, 1 \\ } ^ n, y \In \\ {0, 1 \\ } ^ m } \Alpha (x, y) \ket{x } \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="e4779-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="e4779-136">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="e4779-137">Fazy Oracle</span><span class="sxs-lookup"><span data-stu-id="e4779-137">Phase oracles</span></span>
<span data-ttu-id="e4779-138">Alternatywnie możemy kodować $f $ do $O Oracle $ poprzez zastosowanie _fazy_ w oparciu o dane wejściowe do $O $ .</span><span class="sxs-lookup"><span data-stu-id="e4779-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="e4779-139">Na przykład możemy zdefiniować $O w $ taki sposób, że $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="e4779-140">O \ket{x } = (-1) ^ {f (x)} \ket{x } .</span><span class="sxs-lookup"><span data-stu-id="e4779-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="e4779-141">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-141">\end{align}</span></span>
<span data-ttu-id="e4779-142">$ $ Jeśli faza Oracle działa na rejestrze początkowo w stanie bazowym $ \ket{x } $, wówczas ta faza jest globalnym etapem i dlatego nie jest zauważalna.</span><span class="sxs-lookup"><span data-stu-id="e4779-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="e4779-143">Jednak taka Oracle może być bardzo wydajnym zasobem, jeśli jest stosowana do nadpozycji lub jako kontrolowanej operacji.</span><span class="sxs-lookup"><span data-stu-id="e4779-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="e4779-144">Rozważmy na przykład fazę orcale $O _f $ dla funkcji pojedynczej qubit $f $ .</span><span class="sxs-lookup"><span data-stu-id="e4779-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="e4779-145">Następnie $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="e4779-146">O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}.</span><span class="sxs-lookup"><span data-stu-id="e4779-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="e4779-147">\end{align}</span><span class="sxs-lookup"><span data-stu-id="e4779-147">\end{align}</span></span>
$$

<span data-ttu-id="e4779-148">Ogólnie rzecz biorąc, oba widoki rozwiązań firmy Oracle można rozszerzyć, aby reprezentować funkcje klasyczne, które zwracają liczby rzeczywiste, a nie tylko jeden bit.</span><span class="sxs-lookup"><span data-stu-id="e4779-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="e4779-149">Wybór najlepszego sposobu implementacji Oracle zależy od tego, jak ta Oracle będzie używana w danym algorytmie.</span><span class="sxs-lookup"><span data-stu-id="e4779-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="e4779-150">Na przykład [algorytm Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) opiera się na bazie danych Oracle zaimplementowane w pierwszej kolejności, natomiast [algorytm Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) opiera się na platformie Oracle zaimplementowane w drugi sposób.</span><span class="sxs-lookup"><span data-stu-id="e4779-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="e4779-151">Aby uzyskać więcej informacji, zalecamy dyskusję w [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="e4779-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
