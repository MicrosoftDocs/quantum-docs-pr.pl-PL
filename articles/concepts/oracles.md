---
title: Bazy danych Quantum Oracle | Microsoft Docs
description: Bazy danych Quantum Oracle
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 96949b371a3a5a1135d624690933a48ea0214a2e
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184716"
---
# <a name="quantum-oracles"></a><span data-ttu-id="3aade-103">Bazy danych Quantum Oracle</span><span class="sxs-lookup"><span data-stu-id="3aade-103">Quantum Oracles</span></span>

<span data-ttu-id="3aade-104">Oracle $O $ jest operacją "Black Box", która jest używana jako dane wejściowe w innym algorytmie.</span><span class="sxs-lookup"><span data-stu-id="3aade-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="3aade-105">Często takie operacje są definiowane przy użyciu klasycznej funkcji $f: \\{0, 1\\} ^ n \to \\{0, 1\\} ^ m $, które pobiera $n $-bitowy binarny dane wejściowe i tworzy $m $-bitowy binarne dane wyjściowe.</span><span class="sxs-lookup"><span data-stu-id="3aade-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="3aade-106">W tym celu należy wziąć pod uwagę określone dane wejściowe danych binarnych $x = (x_{0}, x_{1}, \dots, x_ {n-1}) $.</span><span class="sxs-lookup"><span data-stu-id="3aade-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="3aade-107">Możemy etykietować Stany qubit jako $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}} $.</span><span class="sxs-lookup"><span data-stu-id="3aade-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="3aade-108">Możemy najpierw spróbować zdefiniować $O $, aby $O \ket{x} = \ket{f (x)} $, ale ma to kilka problemów.</span><span class="sxs-lookup"><span data-stu-id="3aade-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="3aade-109">Po pierwsze, $f $ może mieć inny rozmiar danych wejściowych i wyjściowych ($n \ne m $), takie jak zastosowanie $O $ spowoduje zmianę liczby qubits w rejestrze.</span><span class="sxs-lookup"><span data-stu-id="3aade-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="3aade-110">Po drugie, nawet jeśli $n = m $, funkcja nie może być odwracalna: Jeśli $f (x) = f (y) $ dla niektórych $x \ne y $, a następnie $O \ket{x} = O\ket {y} $, ale $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $.</span><span class="sxs-lookup"><span data-stu-id="3aade-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="3aade-111">Oznacza to, że nie będzie możliwe konstruowanie sąsiedniej operacji $O ^ \dagger $, a firmy Oracle muszą mieć zdefiniowane dla nich sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="3aade-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="3aade-112">Definiowanie firmy Oracle według jej wpływu na Stany obliczeniowe</span><span class="sxs-lookup"><span data-stu-id="3aade-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="3aade-113">Firma Microsoft może obsłużyć oba te problemy, wprowadzając drugi rejestr $m $ qubits do przechowywania naszej odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="3aade-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="3aade-114">Następnie zdefiniujemy efekt działania firmy Oracle na wszystkich stanach obliczeniowych: dla wszystkich $x \In \\{0, 1\\} ^ n $ i $y \In \\{0, 1\\} ^ m $,</span><span class="sxs-lookup"><span data-stu-id="3aade-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="3aade-115">$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="3aade-115">$$ \begin{align} O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="3aade-116">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3aade-116">\end{align} $$</span></span>

<span data-ttu-id="3aade-117">Teraz $O = O ^ \dagger $ według konstrukcji, dlatego zostały rozwiązane oba poprzednie problemy.</span><span class="sxs-lookup"><span data-stu-id="3aade-117">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="3aade-118">Aby zobaczyć, że $O = O ^ {\dagger} $, należy pamiętać, że $O ^ 2 = \boldone $, $a \oplus b \oplus b = a $ dla wszystkich $a, b \In \{0, 1\}$.</span><span class="sxs-lookup"><span data-stu-id="3aade-118">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="3aade-119">W związku z tym $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.</span><span class="sxs-lookup"><span data-stu-id="3aade-119">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="3aade-120">Ważne jest, aby w ten sposób definiować Oracle w ten sposób dla każdego stanu podstawy obliczeniowej $ \ket{x}\ket{y} $, a także definiować, jak $O $ działa w przypadku każdego innego stanu.</span><span class="sxs-lookup"><span data-stu-id="3aade-120">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="3aade-121">Następuje to bezpośrednio od faktu, że $O $, podobnie jak wszystkie operacje Quantum, jest liniowy w stanie, w którym działa.</span><span class="sxs-lookup"><span data-stu-id="3aade-121">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="3aade-122">Rozważmy operację Hadamard, na przykład, która jest definiowana przez $H \ket{0} = \ket{+} $ i $H \ket{1} = \ket{-}$.</span><span class="sxs-lookup"><span data-stu-id="3aade-122">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="3aade-123">Jeśli chcielibyśmy dowiedzieć się, jak $H $ działa na $ \ket{+} $, możemy użyć tego $H $ jest liniowy,</span><span class="sxs-lookup"><span data-stu-id="3aade-123">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="3aade-124">$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ KET {+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.</span><span class="sxs-lookup"><span data-stu-id="3aade-124">$$ \begin{align} H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="3aade-125">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3aade-125">\end{align} $$</span></span>

<span data-ttu-id="3aade-126">W przypadku definiowania naszej bazy danych Oracle $O $ można w podobny sposób użyć, aby wszystkie Stany $ \ket{\psi} $ w $n + m $ qubits mogły być zapisywane jako</span><span class="sxs-lookup"><span data-stu-id="3aade-126">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="3aade-127">$ $ \begin{align} \ket{\psi} & = \sum_{x \In \\{0, 1\\} ^ n, y \In \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3aade-127">$$ \begin{align} \ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \end{align} $$</span></span>

<span data-ttu-id="3aade-128">gdzie $ \Alpha: \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \to \mathbb{C} $ reprezentuje współczynniki stanu $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="3aade-128">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="3aade-129">Dział</span><span class="sxs-lookup"><span data-stu-id="3aade-129">Thus,</span></span>

<span data-ttu-id="3aade-130">$ $ \begin{align} O \ket{\psi} & = O \sum_{x \In \\{0, 1\\} ^ n, y \In \\{0, 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \In \\{0 , 1\\} ^ n, t \In \\{0, 1\\} ^ m} \Alpha (x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \In \\{0, 1\\} ^ n, y \In \\{0 , 1\\} ^ m} \Alpha (x, y) \ket{x} \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="3aade-130">$$ \begin{align} O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="3aade-131">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3aade-131">\end{align} $$</span></span>

## <a name="phase-oracles"></a><span data-ttu-id="3aade-132">Fazy Oracle</span><span class="sxs-lookup"><span data-stu-id="3aade-132">Phase oracles</span></span>
<span data-ttu-id="3aade-133">Alternatywnie możemy kodować $f $ do $O Oracle $ przez zastosowanie _fazy_ w oparciu o dane wejściowe $O $.</span><span class="sxs-lookup"><span data-stu-id="3aade-133">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="3aade-134">Na przykład możemy zdefiniować $O $ w taki sposób, aby $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.</span><span class="sxs-lookup"><span data-stu-id="3aade-134">For instance, we might define $O$ such that $$ \begin{align} O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="3aade-135">\end{align} $ $ Jeśli faza Oracle działa na bieżąco z rejestrem w stanie wyliczenia $ \ket{x} $, to faza jest globalnym etapem i dlatego nie jest zauważalna.</span><span class="sxs-lookup"><span data-stu-id="3aade-135">\end{align} $$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="3aade-136">Jednak taka Oracle może być bardzo wydajnym zasobem, jeśli jest stosowana do nadpozycji lub jako kontrolowanej operacji.</span><span class="sxs-lookup"><span data-stu-id="3aade-136">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="3aade-137">Rozważmy na przykład fazę orcale $O _F $ dla funkcji Single-qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="3aade-137">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="3aade-138">Następnie $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f ( 0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.</span><span class="sxs-lookup"><span data-stu-id="3aade-138">Then, $$ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="3aade-139">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="3aade-139">\end{align} $$</span></span>

<span data-ttu-id="3aade-140">Ogólnie rzecz biorąc, oba widoki rozwiązań firmy Oracle można rozszerzyć, aby reprezentować funkcje klasyczne, które zwracają liczby rzeczywiste, a nie tylko jeden bit.</span><span class="sxs-lookup"><span data-stu-id="3aade-140">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="3aade-141">Wybór najlepszego sposobu implementacji Oracle zależy od tego, jak ta Oracle będzie używana w danym algorytmie.</span><span class="sxs-lookup"><span data-stu-id="3aade-141">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="3aade-142">Na przykład [algorytm Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) opiera się na bazie danych Oracle zaimplementowane w pierwszej kolejności, natomiast [algorytm Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) opiera się na platformie Oracle zaimplementowane w drugi sposób.</span><span class="sxs-lookup"><span data-stu-id="3aade-142">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="3aade-143">Aby uzyskać więcej informacji, zalecamy dyskusję w [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="3aade-143">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>