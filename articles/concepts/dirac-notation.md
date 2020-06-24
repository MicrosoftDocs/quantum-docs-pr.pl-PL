---
title: Notacja Diraca
description: Dowiedz się więcej o używaniu notacji Dirac do reprezentowania Stanów Quantum i symulowania operacji Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
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
ms.openlocfilehash: f9dddfa25e9fd1e3d8aaf92b2e3b17c96ed8b72a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269510"
---
# <a name="dirac-notation"></a><span data-ttu-id="44499-103">Notacja Dirac</span><span class="sxs-lookup"><span data-stu-id="44499-103">Dirac Notation</span></span>

<span data-ttu-id="44499-104">Podczas gdy notacja wektora kolumn jest powszechna w algebry liniowym, często jest to bardzo trudne w przypadku przetwarzania w usłudze Quantum, zwłaszcza w przypadku wielu qubits.</span><span class="sxs-lookup"><span data-stu-id="44499-104">While column vector notation is ubiquitous in linear algebra, it is often cumbersome in quantum computing especially when dealing with multiple qubits.</span></span>  <span data-ttu-id="44499-105">Na przykład, gdy definiujemy $ \psi $ jako wektor, nie jest wyraźnie jasne, czy $ \psi $ jest wierszem lub wektorem kolumny.</span><span class="sxs-lookup"><span data-stu-id="44499-105">For example, when we define $\psi$ to be a vector it is not explicitly clear whether $\psi$ is a row or a column vector.</span></span>  <span data-ttu-id="44499-106">W związku z tym, jeśli $ \phi $ i $ \psi $ są wektorami, to równie niejasne, jeśli $ \phi \psi $ jest nawet zdefiniowane, ponieważ kształty $ \phi $ i $ \psi $ mogą być niejasne w kontekście.</span><span class="sxs-lookup"><span data-stu-id="44499-106">Thus if $\phi$ and $\psi$ are vectors then it is equally unclear if $\phi \psi$ is even defined because the shapes of $\phi$ and $\psi$ may be unclear in the context.</span></span>  <span data-ttu-id="44499-107">Oprócz niejednoznaczności kształtów wektorów, wyraźne proste wektory korzystające z notacji liniowej algebraicznych wprowadzonej wcześniej mogą być bardzo uciążliwe.</span><span class="sxs-lookup"><span data-stu-id="44499-107">Beyond the ambiguity about the shapes of vectors, expressing even simple vectors using the linear algebraic notation introduced earlier can be very cumbersome.</span></span> <span data-ttu-id="44499-108">Jeśli na przykład chcemy opisać $ stan $n-qubit, gdy każdy qubit przyjmuje wartość $0, $ wyrażamy stan jako</span><span class="sxs-lookup"><span data-stu-id="44499-108">For example, if we wish to describe an $n$-qubit state where each qubit takes the value $0$ then we would formally express the state as</span></span> 

<span data-ttu-id="44499-109">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="44499-109">$$\begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix}.</span></span> $$  

<span data-ttu-id="44499-110">Ocenianie tego produktu dwuskładnikowego jest niepraktyczne, ponieważ wektor bazuje na wykładniczo dużej przestrzeni i dlatego ten zapis jest w rzeczywistości najlepszym opisem stanu, który można podać przy użyciu poprzedniej notacji.</span><span class="sxs-lookup"><span data-stu-id="44499-110">Of course evaluating this tensor product is impractical because the vector lies in an exponentially large space and so this notation is in fact the best description of the state that can be given using the previous notation.</span></span>  

<span data-ttu-id="44499-111">[*Notacja Dirac*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) rozwiązuje te problemy poprzez przedprezentowanie nowego języka w celu dopasowania do precyzyjnej potrzeby Quantum Mechanics.</span><span class="sxs-lookup"><span data-stu-id="44499-111">[*Dirac notation*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) solves these issues by presenting a new language to fit the precise needs of quantum mechanics.</span></span>  <span data-ttu-id="44499-112">Z tego powodu zaleca się, aby czytelnik nie przeglądał przykładów w tej sekcji jako sztywna recepta opisującą sposób opisywania Stanów Quantum, ale zachęca czytelnika do wyświetlania takich rozwiązań jak sugestie, których można użyć do zwięzłego wyrażania koncepcji Quantum.</span><span class="sxs-lookup"><span data-stu-id="44499-112">For this reason, we recommend the reader not view the examples in this section as a rigid prescription of how to describe quantum states, but rather encourage the reader to view these as suggestions that can be used to concisely express quantum ideas.</span></span>

<span data-ttu-id="44499-113">Istnieją dwa typy wektorów w notacji Dirac: wektor *bra* i wektor *KET* , tak jak w przypadku łączenia się z nimi w formie *hamulca* lub wewnętrznego produktu.</span><span class="sxs-lookup"><span data-stu-id="44499-113">There are two types of vectors in Dirac notation: the *bra* vector and the *ket* vector, so named because when put together they form a *braket* or inner product.</span></span>  <span data-ttu-id="44499-114">Jeśli $ \psi $ jest wektorem kolumny, możemy napisać ją w notacji Dirac jako $ \ket { \psi } $, gdzie $ \ket { \cdot $ oznacza, } że jest to wektor kolumny jednostki, czyli wektor *KET* .</span><span class="sxs-lookup"><span data-stu-id="44499-114">If $\psi$ is a column vector then we can write it in Dirac notation as $\ket{\psi}$, where the $\ket{\cdot}$ denotes that it is a unit column vector, i.e., a *ket* vector.</span></span>  <span data-ttu-id="44499-115">Podobnie wektor wiersza $ \psi ^ \dagger $ jest wyrażony jako $ \bra { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="44499-115">Similarly, the row vector $\psi^\dagger$ is expressed as $\bra{\psi}$.</span></span> <span data-ttu-id="44499-116">Innymi słowy, funkcja $ \psi ^ \dagger $ jest uzyskiwana przez zastosowanie złożonej sprzężonej wartości wejściowej do elementów transponowanych $ \psi $ .</span><span class="sxs-lookup"><span data-stu-id="44499-116">In other words, $\psi^\dagger$ is obtained by applying entry-wise complex conjugation to the elements of the transpose of $\psi$.</span></span> <span data-ttu-id="44499-117">Notacja bra-KET bezpośrednio oznacza, że $ \braket { \psi | \psi } $ to wewnętrzny produkt wektora $ \psi $ , który jest z definicji $1 $ .</span><span class="sxs-lookup"><span data-stu-id="44499-117">The bra-ket notation directly implies that $\braket{\psi|\psi}$ is the inner product of vector $\psi$ with itself, which is by definition $1$.</span></span>  

<span data-ttu-id="44499-118">Ogólnie rzecz biorąc, jeśli $ \psi $ i $ \phi $ są wektorami stanu Quantum, ich wewnętrzny produkt to $ \braket { \phi | \psi $, } co oznacza, że prawdopodobieństwo mierzenia stanu $ \ket { \psi $ to $ } \ket { \phi } $ to $ | \braket { \phi | \psi } | ^ 2 $ .</span><span class="sxs-lookup"><span data-stu-id="44499-118">More generally, if $\psi$ and $\phi$ are quantum state vectors their inner product is $\braket{\phi|\psi}$ which implies that the probability of measuring the state $\ket{\psi}$ to be $\ket{\phi}$ is $|\braket{\phi|\psi}|^2$.</span></span>  

<span data-ttu-id="44499-119">Poniższa Konwencja służy do opisywania Stanów Quantum, które kodują wartości zero i jeden (qubit podstawowe Stany obliczeniowe):</span><span class="sxs-lookup"><span data-stu-id="44499-119">The following convention is used to describe the quantum states that encode the values of zero and one (the single-qubit computational basis states):</span></span>

<span data-ttu-id="44499-120">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } , \qquad \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \ket{1 } .</span><span class="sxs-lookup"><span data-stu-id="44499-120">$$ \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0},\qquad \begin{bmatrix} 0 \\\\  1 \end{bmatrix} = \ket{1}.</span></span>
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a><span data-ttu-id="44499-121">Przykład: reprezentacja operacji Hadamard z notacją Dirac</span><span class="sxs-lookup"><span data-stu-id="44499-121">Example: representing the Hadamard operation with Dirac notation</span></span>

<span data-ttu-id="44499-122">Poniższy zapis jest często używany do opisywania Stanów, które wynikają z zastosowania bramy Hadamard do $ \ket{0 } $ i $ \ket{1 } $ (które odpowiadają wektorom jednostek w kierunkach $ + x $ i $-x $ w sferze Bloch):</span><span class="sxs-lookup"><span data-stu-id="44499-122">The following notation is often used to describe the states that result from applying the Hadamard gate to $\ket{0}$ and $\ket{1}$ (which correspond to the unit vectors in the $+x$ and $-x$ directions on the Bloch sphere):</span></span>

<span data-ttu-id="44499-123">$ $ \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ 1 \end{ bmatrix } = H \ket {0 } = \ket { +}, \qquad \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\ \\ -1 \end{ bmatrix } = H \ket {1 } = \ket { -}.</span><span class="sxs-lookup"><span data-stu-id="44499-123">$$ \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=H\ket{0} = \ket{+},\qquad \frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  -1 \end{bmatrix} =H\ket{1} = \ket{-} .</span></span>
$$

<span data-ttu-id="44499-124">Te Stany można również rozszerzyć przy użyciu notacji Dirac jako kwoty $ \ket{0 } $ i $ \ket{1 } $:</span><span class="sxs-lookup"><span data-stu-id="44499-124">These states can also be expanded using Dirac notation as sums of $\ket{0}$ and $\ket{1}$:</span></span>

<span data-ttu-id="44499-125">$ $ \ket { +} = \frac{1 } {\sqrt{2 } } (\ket{0 } + \ket{1 } ), \qquad \ket { -} = \frac{1 } {\sqrt{2 } } (\ket{0 } -\ket{1 } ).</span><span class="sxs-lookup"><span data-stu-id="44499-125">$$ \ket{+} = \frac{1}{\sqrt{2}}(\ket{0} + \ket{1}),\qquad \ket{-} = \frac{1}{\sqrt{2}}(\ket{0} - \ket{1}).</span></span>
$$

### <a name="computational-basis-vectors"></a><span data-ttu-id="44499-126">Wektory podstawy obliczeniowej</span><span class="sxs-lookup"><span data-stu-id="44499-126">Computational basis vectors</span></span>
<span data-ttu-id="44499-127">Pokazuje to, dlaczego te Stany są często nazywane *zasadami obliczeniowymi*: każdy stan Quantum może zawsze być wyrażony jako sumy wektorów obliczeniowych, a takie kwoty są łatwo wyrażone przy użyciu notacji Dirac.</span><span class="sxs-lookup"><span data-stu-id="44499-127">This demonstrates why these states are often called a *computational basis*: every quantum state can always be expressed as sums of computational basis vectors and such sums are easily expressed using Dirac notation.</span></span>  <span data-ttu-id="44499-128">Jest to również prawdą, że Stany $ \ket { +} $ i $ \ket { -} $ również tworzą podstawę dla Stanów Quantum.</span><span class="sxs-lookup"><span data-stu-id="44499-128">The converse is also true in that the states $\ket{+}$ and $\ket{-}$ also form a basis for quantum states.</span></span>  <span data-ttu-id="44499-129">Można to sprawdzić z faktu, że</span><span class="sxs-lookup"><span data-stu-id="44499-129">You can see this from the fact that</span></span>

<span data-ttu-id="44499-130">$ $ \ket{0 } = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}), \qquad \ket{1 } = \frac{1 } {\sqrt{2 } } (\ket { +}-\ket { -}).</span><span class="sxs-lookup"><span data-stu-id="44499-130">$$ \ket{0} = \frac{1}{\sqrt{2}}(\ket{+} + \ket{-}),\qquad \ket{1} = \frac{1}{\sqrt{2}}(\ket{+} - \ket{-}).</span></span>
$$

<span data-ttu-id="44499-131">Przykładem notacji Dirac jest rozważenie klasy hamulca $ \braket{0 | 1 } $, która jest wewnętrznym produktem od $0 $ do $1 $ .</span><span class="sxs-lookup"><span data-stu-id="44499-131">As an example of Dirac notation, consider the braket $\braket{0 | 1}$, which is the inner product between $0$ and $1$.</span></span>  <span data-ttu-id="44499-132">Może być zapisany jako</span><span class="sxs-lookup"><span data-stu-id="44499-132">It can be written as</span></span> 

<span data-ttu-id="44499-133">$ $ \braket{0 | 1 } = \begin{ bmatrix } 1 & 0 \end{ bmatrix } \begin{ bmatrix } 0 \\\\ 1 \end{bmatrix} = 0. $ $</span><span class="sxs-lookup"><span data-stu-id="44499-133">$$\braket{0 | 1}=\begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1\end{bmatrix}=0.$$</span></span>

<span data-ttu-id="44499-134">Wskazuje to, że $ \ket{0 } $ i $ \ket{1 } $ są wektorami prostopadłymi, co oznacza, że $ \braket{0 | 1 } = \braket{1 | 0 } = 0 $ .</span><span class="sxs-lookup"><span data-stu-id="44499-134">This says that $\ket{0}$ and $\ket{1}$ are orthogonal vectors, meaning that $\braket{0 | 1} = \braket{1 | 0} =0$.</span></span>  <span data-ttu-id="44499-135">Również według definicji $ \braket{0 | 0 } = \braket{1 | 1 } = 1 $ , co oznacza, że dwa wektory obliczeniowe mogą być również wywołane *orthonormal*.</span><span class="sxs-lookup"><span data-stu-id="44499-135">Also by definition $\braket{0 | 0} = \braket{1 | 1}=1$, which means that the two computational basis vectors can also be called *orthonormal*.</span></span>
<span data-ttu-id="44499-136">Te właściwości orthonormal będą przydatne w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="44499-136">These orthonormal properties will be useful in the following example.</span></span> <span data-ttu-id="44499-137">Jeśli mamy stan $ \ket { \psi } = {\frac{3 } {5 } } \ket{1 } + {\frac{4 } {5 } } \ket{0 } $, ponieważ $ \braket{1 | 0 } = 0 $ prawdopodobieństwo pomiaru $1 $ jest</span><span class="sxs-lookup"><span data-stu-id="44499-137">If we have a state $\ket{\psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$ then because $\braket{1 | 0} =0$ the probability of measuring $1$  is</span></span>  

<span data-ttu-id="44499-138">$ $ \big | \braket{1 | \psi } \big | ^ 2 = \left | \frac{3 } {5 } \braket{1 | 1 } + \frac{4 } {5 } \braket{1 | 0 } \right | ^ 2 = \frac{9 } {25 } . $ $</span><span class="sxs-lookup"><span data-stu-id="44499-138">$$\big|\braket{1 | \psi}\big|^2= \left|\frac{3}{5}\braket{1 | 1} +\frac{4}{5}\braket{1 | 0}\right|^2=\frac{9}{25}.$$</span></span> 

### <a name="tensor-product-notation"></a><span data-ttu-id="44499-139">Notacja iloczynu</span><span class="sxs-lookup"><span data-stu-id="44499-139">Tensor product notation</span></span>
<span data-ttu-id="44499-140">Notacja Dirac obejmuje również niejawną strukturę produktu w ramach tego programu.</span><span class="sxs-lookup"><span data-stu-id="44499-140">Dirac notation also includes an implicit tensor product structure within it.</span></span>  <span data-ttu-id="44499-141">Jest to ważne, ponieważ w przypadku przetwarzania Quantum wektor stanu opisany przez dwa nieskorelowane rejestry Quantum jest iloczynów dwustanowych.</span><span class="sxs-lookup"><span data-stu-id="44499-141">This is important because in quantum computing, the state vector described by two uncorrelated quantum registers is the tensor products of the two state vectors.</span></span>  <span data-ttu-id="44499-142">Zwięzłe opisywanie struktury produktu dwuczęściowego lub jego braku, jest istotne, jeśli chcesz wyjaśnić obliczenia Quantum.</span><span class="sxs-lookup"><span data-stu-id="44499-142">Concisely describing the tensor product structure, or lack thereof, is vital if you want to explain a quantum computation.</span></span>  <span data-ttu-id="44499-143">Struktura iloczynu dwuetapowego oznacza, że możemy napisać $ \psi \otimes \phi $ dla wszystkich dwóch wektorów Stanów Quantum $ \phi $ i $ \psi $ jako $ \ket { \psi } \ket { \phi } $, czasami jawnie napisane jako $ \ket { \psi } \otimes \ket { \phi } $, ale $ nie jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="44499-143">The tensor product structure implies that we can write $\psi \otimes \phi$ for any two quantum state vectors $\phi$ and $\psi$ as $\ket{\psi} \ket{\phi}$, sometimes explicitly written as $\ket{\psi} \otimes \ket{\phi}$, however by convention writing $\otimes$ in between the vectors is unnecessary.</span></span>  <span data-ttu-id="44499-144">Na przykład stan z dwoma qubits zainicjowany do stanu zero jest określony przez</span><span class="sxs-lookup"><span data-stu-id="44499-144">For example, the state with two qubits initialized to the zero state is given by</span></span>

<span data-ttu-id="44499-145">$ $ \begin{ bmatrix } 1 \\ \\ 0 0 \\ \\ \\ \\ \end{ bmatrix } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \ket{0 } = \ket{0 } \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="44499-145">$$ \begin{bmatrix} 1 \\\\  0 \\\\  0 \\\\  0 \end{bmatrix}= \begin{bmatrix} 1 \\\\  0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \ket{0}= \ket{0} \ket{0}.</span></span>
$$

<span data-ttu-id="44499-146">Analogicznie, stan $ \ket{p } $ dla liczby całkowitej $p $ reprezentuje stan Quantum, który koduje w postaci binarnej reprezentację liczby całkowitej $p $ .</span><span class="sxs-lookup"><span data-stu-id="44499-146">Similarly,  the state $\ket{p}$ for integer $p$ represents a quantum state that encodes in binary representation the integer $p$.</span></span>  <span data-ttu-id="44499-147">Jeśli na przykład chcemy wyrazić liczbę $5 $ przy użyciu niepodpisanego kodowania binarnego, możemy to samo wyrazić jako</span><span class="sxs-lookup"><span data-stu-id="44499-147">For example, if we wish to express the number $5$ using an unsigned binary encoding we could equally express it as</span></span>

<span data-ttu-id="44499-148">$ $ \ket{1 } \ket{0 } \ket{1 } = \ket{101 } = \ket{5 } .</span><span class="sxs-lookup"><span data-stu-id="44499-148">$$ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.</span></span>
$$

<span data-ttu-id="44499-149">W tej notacji $ \ket{0 } $ nie musi odwoływać się do stanu jednego qubit, ale raczej *Rejestr qubit* przechowujący kodowanie binarne $0 $ .</span><span class="sxs-lookup"><span data-stu-id="44499-149">Within this notation $\ket{0}$ need not refer to a single-qubit state but rather a *qubit register* storing a binary encoding of $0$.</span></span>  <span data-ttu-id="44499-150">Różnice między tymi dwiema notacjami są zwykle jasne w kontekście.</span><span class="sxs-lookup"><span data-stu-id="44499-150">The differences between these two notations is usually clear from the context.</span></span>  <span data-ttu-id="44499-151">Ta konwencja jest przydatna do uproszczenia pierwszego przykładu, który można napisać w jeden z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="44499-151">This convention is useful for simplifying the first example which can be written in any of the following ways:</span></span>

<span data-ttu-id="44499-152">$ $ \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \cdots \otimes \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } = \ket{0 } \otimes \cdots \otimes \ket{0 } = | 0 \cdots 0 \rangle = \ket{0 } ^ {\otimes n } = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="44499-152">$$ \begin{bmatrix}1 \\\\  0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\  0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= |0\cdots 0\rangle = \ket{0}^{\otimes n} = \ket{0}.</span></span>
$$

### <a name="example-describing-superposition-with-dirac-notation"></a><span data-ttu-id="44499-153">Przykład: Opisywanie nadpozycji z notacją Dirac</span><span class="sxs-lookup"><span data-stu-id="44499-153">Example: Describing superposition with Dirac notation</span></span>
<span data-ttu-id="44499-154">Innym przykładem, jak można użyć notacji Dirac do opisania stanu Quantum, należy wziąć pod uwagę następujące równoważne sposoby pisania stanu Quantum, który jest równe nadpozycja dla każdego możliwego ciągu bitowego o długości $n$</span><span class="sxs-lookup"><span data-stu-id="44499-154">As another example of how you can use Dirac notation to describe a quantum state, consider the following equivalent ways of writing a quantum state that is an equal superposition over every possible bit string of length $n$</span></span>

<span data-ttu-id="44499-155">$ $ H ^ {\otimes n } \ket{0 } = \frac{1 } {2 ^ {n/2 } } \ sum_ {j = 0 } ^ {2 ^ n-1 } \ket{j } = \ket { +} ^ {\otimes n } .</span><span class="sxs-lookup"><span data-stu-id="44499-155">$$ H^{\otimes n} \ket{0} = \frac{1}{2^{n/2}} \sum_{j=0}^{2^n-1} \ket{j} = \ket{+}^{\otimes n}.</span></span>
$$

<span data-ttu-id="44499-156">W tym miejscu możesz zazastanawiać się, dlaczego suma $ wyniesie od $0 do $2 ^ {n } -1 $ dla $n $ bitowej.</span><span class="sxs-lookup"><span data-stu-id="44499-156">Here you may wonder why the sum goes from $0$ to $2^{n}-1$ for $n$ bits.</span></span>  <span data-ttu-id="44499-157">Najpierw należy zauważyć, że istnieją co } najmniej dwie konfiguracje, które $n $ mogą wykonać usługa BITS.</span><span class="sxs-lookup"><span data-stu-id="44499-157">First note that there are $2^{n}$ different configurations that $n$ bits can take.</span></span>  <span data-ttu-id="44499-158">Można to sprawdzić przez zanotowanie, że jeden bit może przyjmować $2 $ wartości, ale dwa bity mogą przyjmować $4 $ wartości i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="44499-158">You can see this by noting that one bit can take $2$ values but two bits can take $4$ values and so forth.</span></span> <span data-ttu-id="44499-159">Ogólnie rzecz biorąc, oznacza to, że istnieją wartości $2 ^ n $ inne możliwe ciągi bitowe, ale największą wartość zakodowaną w dowolnym z nich $1 \cdots 1 = 2 ^ n-1 $ i tym samym jest górny limit liczby.</span><span class="sxs-lookup"><span data-stu-id="44499-159">In general, this means that there are $2^n$ different possible bit strings but the largest value encoded in any of them $1\cdots 1=2^n-1$ and hence it is the upper limit for the sum.</span></span>
<span data-ttu-id="44499-160">Jako notatka po stronie, w tym przykładzie nie użyto elementu $ \ket { +} ^ {\otimes n } = \ket { +} $ w trybie analogowym do $ \ket{0 } ^ {\otimes n } = \ket{0 } $, ponieważ ta konwencja notacji jest zwykle zarezerwowana dla stanu podstawy obliczeń z każdą qubit zainicjowaną na zero.</span><span class="sxs-lookup"><span data-stu-id="44499-160">As a side note, in this example we did not use $\ket{+}^{\otimes n}=\ket{+}$ in analogy to $\ket{0}^{\otimes n} = \ket{0}$ because this notational convention is usually reserved for the computational basis state with every qubit initialized to zero.</span></span>  <span data-ttu-id="44499-161">Chociaż taka konwencja byłaby w tym przypadku rozsądna, nie jest ona stosowana w literaturze obliczeniowej Quantum.</span><span class="sxs-lookup"><span data-stu-id="44499-161">While such a convention would be sensible in this case, it is not employed in the quantum computing literature.</span></span>

### <a name="expressing-linearity-with-dirac-notation"></a><span data-ttu-id="44499-162">Wyrażanie liniowości przy użyciu notacji Dirac</span><span class="sxs-lookup"><span data-stu-id="44499-162">Expressing linearity with Dirac notation</span></span>
<span data-ttu-id="44499-163">Kolejną cechą notacji Dirac jest fakt, że jest on liniowy.</span><span class="sxs-lookup"><span data-stu-id="44499-163">Another nice feature of Dirac notation is the fact that it is linear.</span></span>  <span data-ttu-id="44499-164">Jeśli chcemy napisać w przypadku czterech wektorów stanu Quantum,</span><span class="sxs-lookup"><span data-stu-id="44499-164">If we wish to write for any four quantum state vectors,</span></span> 

<span data-ttu-id="44499-165">$ $ (\Alpha \ket { \psi } + \beta \ket { \phi } ) \otimes (\gamma \ket { \chi } + \delta \ket { \omega } ) = \Alpha \gamma \ket { \psi } \ket { \chi } + \Alpha \delta \ket { \psi \ket \omega } { } + \beta \gamma \ket { \phi } \ket { \chi } + \beta \phi \delta \ket { } \ket { \omega } . $ $</span><span class="sxs-lookup"><span data-stu-id="44499-165">$$(\alpha \ket{\psi} +\beta\ket{\phi})\otimes (\gamma \ket{\chi} + \delta \ket{\omega})= \alpha\gamma \ket{\psi}\ket{\chi} + \alpha\delta \ket{\psi}\ket{\omega}+\beta\gamma\ket{\phi}\ket{\chi}+\beta\delta\ket{\phi}\ket{\omega}.$$</span></span>

<span data-ttu-id="44499-166">Oznacza to, że można rozpowszechnić notację iloczynu dwukierunkowego w notacji Dirac, aby zapewnić, że produkty Dwupunktowe między wektorami stanu kończą się podobnie jak zwykłe mnożenia.</span><span class="sxs-lookup"><span data-stu-id="44499-166">That is to say, you can distribute the tensor product notation in Dirac notation so that taking tensor products between state vectors ends up looking just like ordinary multiplication.</span></span>

<span data-ttu-id="44499-167">Wektory bra są zgodne z podobną Konwencją do KET wektorów.</span><span class="sxs-lookup"><span data-stu-id="44499-167">Bra vectors follow a similar convention to ket vectors.</span></span>  <span data-ttu-id="44499-168">Na przykład wektor $ \bra { \psi } \bra { \phi } $ jest odpowiednikiem wektora stanu $ \psi ^ \dagger \otimes \phi ^ \dagger = (\psi \otimes \phi) ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="44499-168">For example, the vector $\bra{\psi}\bra{\phi}$ is equivalent to the state vector $\psi^\dagger \otimes \phi^\dagger=(\psi\otimes \phi)^\dagger$.</span></span> <span data-ttu-id="44499-169">Jeśli KET Vector $ \ket { \psi } $ to $ \Alpha \ket{0 } + \beta \ket{1 } $, to bra wektorowa wersja wektora to $ \bra { \psi } = \ket { \psi } ^ \dagger = (\bra{0 \Alpha } ^ \* + \bra{1 } \beta ^ \*) $.</span><span class="sxs-lookup"><span data-stu-id="44499-169">If the ket vector $\ket{\psi}$ is $\alpha \ket{0} + \beta \ket{1}$ then the bra vector version of the vector is $\bra{\psi}=\ket{\psi}^\dagger = (\bra{0}\alpha^\* +\bra{1}\beta^\*)$.</span></span>

<span data-ttu-id="44499-170">Załóżmy na przykład, że chcemy obliczyć prawdopodobieństwo mierzenia stanu $ \ket { \psi } = \frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } $ przy użyciu programu Quantum do mierzenia Stanów na wartość $ \ket { +} $ lub $ \ket { -} $.</span><span class="sxs-lookup"><span data-stu-id="44499-170">As an example, imagine that we wish to calculate the probability of measuring the state $\ket{\psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ using a quantum program for measuring states to be either $\ket{+}$ or $\ket{-}$.</span></span> <span data-ttu-id="44499-171">Następnie prawdopodobieństwo, że dane urządzenie będzie miało stan $ \ket { -} $ to</span><span class="sxs-lookup"><span data-stu-id="44499-171">Then the probability that the device would output that the state is $\ket{-}$ is</span></span> 

<span data-ttu-id="44499-172">$ $ | \braket { -| \psi } | ^ 2 = \left | \frac{1 } {\sqrt{2 } } (\bra{0 } -\bra{1 } ) (\frac{3 } {5 } \ket{1 } + \frac{4 } {5 } \ket{0 } ) \right | ^ 2 = \left | -\frac{3 } {5 \sqrt {2 } } + \frac{4 } {5 \sqrt {2 } } \right | ^ 2 = \frac{1 } {50 } . $ $</span><span class="sxs-lookup"><span data-stu-id="44499-172">$$|\braket{- | \psi}|^2= \left|\frac{1}{\sqrt{2}}(\bra{0} - \bra{1})(\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right|^2=\left|-\frac{3}{5\sqrt{2}} + \frac{4}{5\sqrt{2}}\right|^2=\frac{1}{50}.$$</span></span>

<span data-ttu-id="44499-173">Fakt, że znak ujemny pojawia się w obliczeniach prawdopodobieństwa, jest manifestem wpływów Quantum, który jest jednym z mechanizmów, za pomocą których przetwarzanie Quantum uzyskuje korzyści w porównaniu do klasycznego przetwarzania danych.</span><span class="sxs-lookup"><span data-stu-id="44499-173">The fact that the negative sign appears in the calculation of the probability is a manifestation of quantum interference, which is one of the mechanisms by which quantum computing gains advantages over classical computing.</span></span>

## <a name="ketbra-or-outer-product"></a><span data-ttu-id="44499-174">ketbra lub zewnętrzny produkt</span><span class="sxs-lookup"><span data-stu-id="44499-174">ketbra or outer product</span></span>
<span data-ttu-id="44499-175">Ostatni element omawiany w notacji Dirac jest produktem *ketbra* lub zewnętrznym.</span><span class="sxs-lookup"><span data-stu-id="44499-175">The final item worth discussing in Dirac notation is the *ketbra* or outer product.</span></span>  <span data-ttu-id="44499-176">Zewnętrzny produkt jest reprezentowany w notacjach Dirac jako $ \ket { \psi } \bra { \phi } $ i czasami nazywa się ketbras, ponieważ Bras i kets występuje w kolejności odwrotnej jako brakets.</span><span class="sxs-lookup"><span data-stu-id="44499-176">The outer product is represented within Dirac notations as $\ket{\psi} \bra{\phi}$, and sometimes called ketbras because the bras and kets occur in the opposite order as brakets.</span></span>  <span data-ttu-id="44499-177">Produkt zewnętrzny jest definiowany za pośrednictwem mnożenia macierzy jako $ \ket { \psi } \bra { \phi } = \psi \phi ^ \dagger $ dla wektorów stanu Quantum $ \psi $ i $ \phi $ .</span><span class="sxs-lookup"><span data-stu-id="44499-177">The outer product is defined via matrix multiplication as $\ket{\psi} \bra{\phi} = \psi \phi^\dagger$ for quantum state vectors $\psi$ and $\phi$.</span></span>  <span data-ttu-id="44499-178">Najprostszym i raczej najbardziej typowym przykładem tego zapisu jest</span><span class="sxs-lookup"><span data-stu-id="44499-178">The simplest, and arguably most common example of this notation, is</span></span>

<span data-ttu-id="44499-179">$ $ \ket{0 } \bra{0 } = \begin{ bmatrix } 1 \\\\ 0 \end{ bmatrix } \begin{ bmatrix } 1&0 \end{ bmatrix } = \begin{ bmatrix } 1 &0 \\\\ 0 &0 \end{bmatrix} \qquad \ket{1 } \bra{1 } = \begin{ bmatrix } 0 \\\\ 1 \end{ bmatrix } \begin{ bmatrix } 0&1 \end{ bmatrix } = \begin{ bmatrix } 0 &0 \\\\ 0 &1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="44499-179">$$ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1&0 \end{bmatrix}= \begin{bmatrix}1 &0\\\\ 0 &0\end{bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0&1 \end{bmatrix}= \begin{bmatrix}0 &0\\\\ 0 &1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="44499-180">Ketbras są często nazywane projektorami, ponieważ projektuje stan Quantum do ustalonej wartości.</span><span class="sxs-lookup"><span data-stu-id="44499-180">Ketbras are often called projectors because they project a quantum state onto a fixed value.</span></span>  <span data-ttu-id="44499-181">Ponieważ te operacje nie są jednostkowymi jednostkami (i nie zachowują nawet normy wektora), nie powinny być niezależne, że komputer Quantum nie może w sposób jednoznaczny zastosować projektora.</span><span class="sxs-lookup"><span data-stu-id="44499-181">Since these operations are not unitary (and do not even preserve the norm of a vector), it should come as no surprise that a quantum computer cannot deterministically apply a projector.</span></span>  <span data-ttu-id="44499-182">Jednak projektory wykonują atrakcyjne zadanie opisujące akcję, którą mierzy w stanie Quantum.</span><span class="sxs-lookup"><span data-stu-id="44499-182">However projectors do a beautiful job of describing the action that measurement has on a quantum state.</span></span>  <span data-ttu-id="44499-183">Na przykład jeśli mierzy się stan $ \ket { \psi } $ to $0 $ , wynikowa transformacja, którą stan środowiska w wyniku pomiaru wynosi</span><span class="sxs-lookup"><span data-stu-id="44499-183">For example, if we measure a state $\ket{\psi}$ to be $0$ then the resulting transformation that the state experiences as a result of the measurement is</span></span>

  <span data-ttu-id="44499-184">$ $ \ket { \psi } \rightarrow \frac { (\ket{0 } \bra{0 } ) \ket { \psi } } {| \braket{0 | \psi } |} = \ket{0 } , $ $</span><span class="sxs-lookup"><span data-stu-id="44499-184">$$\ket{\psi} \rightarrow \frac{(\ket{0} \bra{0})\ket{\psi}}{|\braket{0 | \psi}|}= \ket{0},$$</span></span>

<span data-ttu-id="44499-185">ponieważ jeden z nich oczekuje na zmierzenie stanu i znalezienie go jako $ \ket{0 } $.</span><span class="sxs-lookup"><span data-stu-id="44499-185">as one expects if you were to measure the state and find it to be $\ket{0}$.</span></span>  <span data-ttu-id="44499-186">Aby wykonać ponownie iteracje, takie projektory nie mogą być stosowane do stanu na komputerze Quantum w sposób deterministyczny.</span><span class="sxs-lookup"><span data-stu-id="44499-186">To reiterate, such projectors cannot be applied on a state in a quantum computer deterministically.</span></span>  <span data-ttu-id="44499-187">Zamiast tego można je najlepiej zastosować losowo z wynikiem $ \ket{0 } $, który pojawia się z pewnymi stałymi prawdopodobieństwami.</span><span class="sxs-lookup"><span data-stu-id="44499-187">Instead, they can at best be applied randomly with the result $\ket{0}$ appearing with some fixed probability.</span></span>  <span data-ttu-id="44499-188">Prawdopodobieństwo pomyślnego pomiaru może być zapisywane jako oczekiwana wartość rzutnika Quantum w stanie</span><span class="sxs-lookup"><span data-stu-id="44499-188">The probability of such a measurement succeeding can be written as the expectation value of the quantum projector in the state</span></span>

<span data-ttu-id="44499-189">$ $ \bra { \psi } (\ket{0 } \bra{0 } ) \ket { \psi } = | \braket { \psi | 0 } | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="44499-189">$$ \bra{\psi} (\ket{0} \bra{0})\ket{\psi} = |\braket{\psi | 0}|^2, $$</span></span>

<span data-ttu-id="44499-190">pokazuje, że projektory po prostu zapewniają nowy sposób wyrażania procesu pomiaru.</span><span class="sxs-lookup"><span data-stu-id="44499-190">which illustrates that projectors simply give a new way of expressing the measurement process.</span></span>

<span data-ttu-id="44499-191">Jeśli zamiast tego będziemy rozważyć zmierzenie pierwszego qubit stanu wieloqubitowego na $1, $ możemy również opisać ten proces wygodnie przy użyciu projektorów i notacji Dirac:</span><span class="sxs-lookup"><span data-stu-id="44499-191">If instead we consider measuring the first qubit of a multi-qubit state to be $1$ then we can also describe this process conveniently using projectors and Dirac notation:</span></span>

<span data-ttu-id="44499-192">$ $ P (\Text{First qubit = 1 } ) = \bra { \psi } \left (\ket{1 } \bra{1 } \otimes \boldone ^ {\otimes n-1 } \right) \ket { \psi } .</span><span class="sxs-lookup"><span data-stu-id="44499-192">$$ P(\text{first qubit = 1})= \bra{\psi}\left(\ket{1}\bra{1}\otimes \boldone^{\otimes n-1}\right) \ket{\psi}.</span></span>
$$

<span data-ttu-id="44499-193">W tym miejscu macierz tożsamości może być wygodnie zapisywana w notacji Dirac jako</span><span class="sxs-lookup"><span data-stu-id="44499-193">Here the identity matrix can be conveniently written in Dirac notation as</span></span>

<span data-ttu-id="44499-194">$ $ \boldone = \ket{0 } \bra{0 } + \ket{1 } \bra{1 } = \begin{ bmatrix } 1&0 \\\\ 0&1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="44499-194">$$ \boldone = \ket{0} \bra{0}+\ket{1} \bra{1}= \begin{bmatrix}1&0\\\\ 0&1 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="44499-195">W przypadku gdy istnieją dwa-qubits projektora można rozwinąć jako</span><span class="sxs-lookup"><span data-stu-id="44499-195">For the case where there are two-qubits the projector can be expanded as</span></span> 

<span data-ttu-id="44499-196">$ $ \ket{1 } \bra{1 } \otimes \id = \ket{1 } \bra{1 } \otimes (\ket{0 } \bra{0 } + \ket{1 } \bra{1 } ) = \ket{10 } \bra{10 } + \ket{11 } \bra{11 } .</span><span class="sxs-lookup"><span data-stu-id="44499-196">$$ \ket{1} \bra{1} \otimes \id = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+\ket{1} \bra{1})= \ket{10}\bra{10} + \ket{11}\bra{11}.</span></span>
$$

<span data-ttu-id="44499-197">Możemy zobaczyć, że jest to zgodne z dyskusjami dotyczącymi prawdopodobieństwa pomiaru dla Stanów multiqubit przy użyciu notacji wektorów kolumn:</span><span class="sxs-lookup"><span data-stu-id="44499-197">We can then see that this is consistent with the discussion about measurement likelihoods for multiqubit states using column-vector notation:</span></span>

<span data-ttu-id="44499-198">$ $ P (\Text{First qubit = 1 } ) = \psi ^ \dagger (e \_ {10} e \_ {10 } ^ \dagger + e \_ {11} e \_ {11 } ^ \dagger) \psi = | e \_ {10 } ^ \dagger \psi | ^ 2 + | e \_ {11 } ^ \dagger \psi | ^ 2, $ $</span><span class="sxs-lookup"><span data-stu-id="44499-198">$$ P(\text{first qubit = 1})= \psi^\dagger (e\_{10}e\_{10}^\dagger + e\_{11}e\_{11}^\dagger)\psi = |e\_{10}^\dagger \psi|^2 + |e\_{11}^\dagger \psi|^2, $$</span></span>

<span data-ttu-id="44499-199">który pasuje do dyskusji o pomiarach wieloqubitowych.</span><span class="sxs-lookup"><span data-stu-id="44499-199">which matches the multi-qubit measurement discussion.</span></span>  <span data-ttu-id="44499-200">Uogólnienie tego wyniku w przypadku wielu qubit, jednak jest nieco bardziej bezpośrednie do wyrażania przy użyciu notacji Dirac niż notacja wektora kolumn i jest całkowicie równoważne poprzedniej obróbce.</span><span class="sxs-lookup"><span data-stu-id="44499-200">The generalization of this result to the multi-qubit case, however, is slightly more straightforward to express using Dirac notation than column-vector notation, and is entirely equivalent to the previous treatment.</span></span>

## <a name="density-operators"></a><span data-ttu-id="44499-201">Operatory gęstości</span><span class="sxs-lookup"><span data-stu-id="44499-201">Density operators</span></span>

<span data-ttu-id="44499-202">Innym przydatnym operatorem, który wyraża użycie notacji Dirac, jest *operator gęstości*, czasami również znany jako *operator stanu*.</span><span class="sxs-lookup"><span data-stu-id="44499-202">Another useful operator to express using Dirac notation is a *density operator*, sometimes also known as a *state operator*.</span></span>
<span data-ttu-id="44499-203">Operator gęstości dla wektora stanu Quantum przyjmuje postać $ \rho = \ket { \psi } \bra { \psi } $.</span><span class="sxs-lookup"><span data-stu-id="44499-203">A density operator for a quantum state vector takes the form $\rho = \ket{\psi} \bra{\psi}$.</span></span>
<span data-ttu-id="44499-204">Pojęcie to przedstawiające stan jako macierz, a nie wektor, jest często wygodne, ponieważ daje wygodną metodę reprezentowania obliczeń prawdopodobieństwa, a także umożliwia jednemu opisywaniu niepewności statystycznej i niepewności w ramach tego samego formalnego charakteru.</span><span class="sxs-lookup"><span data-stu-id="44499-204">This concept of representing the state as a matrix, rather than a vector, is often convenient because it gives a convenient way of representing probability calculations, and also allows one to describe both statistical uncertainty as well as quantum uncertainty within the same formalism.</span></span>
<span data-ttu-id="44499-205">Ogólne operatory stanu Quantum, a nie wektory, są powszechnie dostępne w niektórych obszarach przetwarzania Quantum, ale nie są niezbędne do zrozumienia podstaw tego pola.</span><span class="sxs-lookup"><span data-stu-id="44499-205">General quantum state operators, rather than vectors, are ubiquitous in some areas of quantum computing but are not necessary to understand the basics of the field.</span></span>
<span data-ttu-id="44499-206">W przypadku interesującego czytnika zalecamy odczytanie jednej z książek referencyjnych, które znajdują się w temacie, [Aby uzyskać więcej informacji](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="44499-206">For the interested reader, we recommend reading one of the reference books provided in [For more information](xref:microsoft.quantum.more-information).</span></span>

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a><span data-ttu-id="44499-207">Sekwencje Q # bram równoważne z Stanami Quantum</span><span class="sxs-lookup"><span data-stu-id="44499-207">Q# gate sequences equivalent to quantum states</span></span>
<span data-ttu-id="44499-208">Punkt końcowy, który stanowi podstawę dla notacji Quantum i języka programowania Q #: na początku tego dokumentu stwierdzamy, że jest to podstawowy obiekt informacji w ramach przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="44499-208">A final point worth raising about quantum notation and the Q# programming language: at the onset of this document we mentioned that the quantum state is the fundamental object of information in quantum computing.</span></span>  <span data-ttu-id="44499-209">Może to być niespodziewane, że w Q # nie ma pojęcia dotyczącego elementu Quantum.</span><span class="sxs-lookup"><span data-stu-id="44499-209">It may then come as a surprise that in Q# there is no notion of a quantum state.</span></span>  <span data-ttu-id="44499-210">Zamiast tego wszystkie stany są opisane tylko przez operacje używane do ich przygotowania.</span><span class="sxs-lookup"><span data-stu-id="44499-210">Instead, all states are described only by the operations used to prepare them.</span></span>  <span data-ttu-id="44499-211">Poprzedni przykład jest doskonałym ilustracją.</span><span class="sxs-lookup"><span data-stu-id="44499-211">The previous example is an excellent illustration of this.</span></span>  <span data-ttu-id="44499-212">Zamiast wyznaczania jednolitej nadpozycji w każdym ciągu bitowym Quantum w rejestrze, możemy przedstawić wynik jako $H ^ {\otimes n } \ket{0 } $.</span><span class="sxs-lookup"><span data-stu-id="44499-212">Rather than expressing a uniform superposition over every quantum bit string in a register, we can represent the result as $H^{\otimes n} \ket{0}$.</span></span>  <span data-ttu-id="44499-213">Ten wykładniczy, krótszy opis stanu nie tylko ma zaletę, że możemy z niej skorzystać, ale również zwięzłie definiuje operacje, które są niezbędne do propagowania przez stos oprogramowania w celu wdrożenia algorytmu.</span><span class="sxs-lookup"><span data-stu-id="44499-213">This exponentially shorter description of the state not only has the advantage that we can classically reason about it, but it also concisely defines the operations needed to be propagated through the software stack to implement the algorithm.</span></span>  <span data-ttu-id="44499-214">Z tego powodu polecenie Q # jest przeznaczone do emitowania sekwencji bram zamiast Stanów Quantum; jednak na poziomie teoretycznym dwie perspektywy są równoważne.</span><span class="sxs-lookup"><span data-stu-id="44499-214">For this reason, Q# is designed to emit gate sequences rather than quantum states; however, at a theoretical level the two perspectives are equivalent.</span></span>
