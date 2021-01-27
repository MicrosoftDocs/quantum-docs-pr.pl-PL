---
<span data-ttu-id="8dbce-101">title: wektory i macierze w opisie przetwarzania Quantum: Poznaj podstawy pracy z wektorami i macierzami.</span><span class="sxs-lookup"><span data-stu-id="8dbce-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="8dbce-102">Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. Vectors MS. Author: v-benbra MS. Date: 12/11/2017 MS. temat: koncepcyjne No-Loc:</span><span class="sxs-lookup"><span data-stu-id="8dbce-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: v-benbra ms.date: 12/11/2017 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="8dbce-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="8dbce-103">"Q#"</span></span>
- <span data-ttu-id="8dbce-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="8dbce-104">"$$v"</span></span>
- <span data-ttu-id="8dbce-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="8dbce-105">"$$"</span></span>
- <span data-ttu-id="8dbce-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="8dbce-106">"$$"</span></span>
- <span data-ttu-id="8dbce-107">"$"</span><span class="sxs-lookup"><span data-stu-id="8dbce-107">"$"</span></span>
- <span data-ttu-id="8dbce-108">"$"</span><span class="sxs-lookup"><span data-stu-id="8dbce-108">"$"</span></span>
- <span data-ttu-id="8dbce-109">"$"</span><span class="sxs-lookup"><span data-stu-id="8dbce-109">"$"</span></span>
- <span data-ttu-id="8dbce-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="8dbce-110">"$$"</span></span>
- <span data-ttu-id="8dbce-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="8dbce-111">"\cdots"</span></span>
- <span data-ttu-id="8dbce-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="8dbce-112">"bmatrix"</span></span>
- <span data-ttu-id="8dbce-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="8dbce-113">"\ddots"</span></span>
- <span data-ttu-id="8dbce-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="8dbce-114">"\equiv"</span></span>
- <span data-ttu-id="8dbce-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="8dbce-115">"\sum"</span></span>
- <span data-ttu-id="8dbce-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="8dbce-116">"\begin"</span></span>
- <span data-ttu-id="8dbce-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="8dbce-117">"\end"</span></span>
- <span data-ttu-id="8dbce-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="8dbce-118">"\sqrt"</span></span>
- <span data-ttu-id="8dbce-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="8dbce-119">"\otimes"</span></span>
- <span data-ttu-id="8dbce-120">"{"</span><span class="sxs-lookup"><span data-stu-id="8dbce-120">"{"</span></span>
- <span data-ttu-id="8dbce-121">"}"</span><span class="sxs-lookup"><span data-stu-id="8dbce-121">"}"</span></span>
- <span data-ttu-id="8dbce-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="8dbce-122">"\text"</span></span>
- <span data-ttu-id="8dbce-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="8dbce-123">"\phi"</span></span>
- <span data-ttu-id="8dbce-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="8dbce-124">"\kappa"</span></span>
- <span data-ttu-id="8dbce-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="8dbce-125">"\psi"</span></span>
- <span data-ttu-id="8dbce-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="8dbce-126">"\alpha"</span></span>
- <span data-ttu-id="8dbce-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="8dbce-127">"\beta"</span></span>
- <span data-ttu-id="8dbce-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="8dbce-128">"\gamma"</span></span>
- <span data-ttu-id="8dbce-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="8dbce-129">"\delta"</span></span>
- <span data-ttu-id="8dbce-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="8dbce-130">"\omega"</span></span>
- <span data-ttu-id="8dbce-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="8dbce-131">"\bra"</span></span>
- <span data-ttu-id="8dbce-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="8dbce-132">"\ket"</span></span>
- <span data-ttu-id="8dbce-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="8dbce-133">"\boldone"</span></span>
- <span data-ttu-id="8dbce-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="8dbce-134">"\\\\"</span></span>
- <span data-ttu-id="8dbce-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="8dbce-135">"\\"</span></span>
- <span data-ttu-id="8dbce-136">"="</span><span class="sxs-lookup"><span data-stu-id="8dbce-136">"="</span></span>
- <span data-ttu-id="8dbce-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="8dbce-137">"\frac"</span></span>
- <span data-ttu-id="8dbce-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="8dbce-138">"\text"</span></span>
- <span data-ttu-id="8dbce-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="8dbce-139">"\mapsto"</span></span>
- <span data-ttu-id="8dbce-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="8dbce-140">"\dagger"</span></span>
- <span data-ttu-id="8dbce-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="8dbce-141">"\to"</span></span>
- <span data-ttu-id="8dbce-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="8dbce-142">"\begin{cases}"</span></span>
- <span data-ttu-id="8dbce-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="8dbce-143">"\end{cases}"</span></span>
- <span data-ttu-id="8dbce-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="8dbce-144">"\operatorname"</span></span>
- <span data-ttu-id="8dbce-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="8dbce-145">"\braket"</span></span>
- <span data-ttu-id="8dbce-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="8dbce-146">"\id"</span></span>
- <span data-ttu-id="8dbce-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="8dbce-147">"\expect"</span></span>
- <span data-ttu-id="8dbce-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="8dbce-148">"\defeq"</span></span>
- <span data-ttu-id="8dbce-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="8dbce-149">"\variance"</span></span>
- <span data-ttu-id="8dbce-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="8dbce-150">"\dd"</span></span>
- <span data-ttu-id="8dbce-151">"&"</span><span class="sxs-lookup"><span data-stu-id="8dbce-151">"&"</span></span>
- <span data-ttu-id="8dbce-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="8dbce-152">"\begin{align}"</span></span>
- <span data-ttu-id="8dbce-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="8dbce-153">"\end{align}"</span></span>
- <span data-ttu-id="8dbce-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="8dbce-154">"\Lambda"</span></span>
- <span data-ttu-id="8dbce-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="8dbce-155">"\lambda"</span></span>
- <span data-ttu-id="8dbce-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="8dbce-156">"\Omega"</span></span>
- <span data-ttu-id="8dbce-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="8dbce-157">"\mathrm"</span></span>
- <span data-ttu-id="8dbce-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="8dbce-158">"\left"</span></span>
- <span data-ttu-id="8dbce-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="8dbce-159">"\right"</span></span>
- <span data-ttu-id="8dbce-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="8dbce-160">"\qquad"</span></span>
- <span data-ttu-id="8dbce-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="8dbce-161">"\times"</span></span>
- <span data-ttu-id="8dbce-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="8dbce-162">"\big"</span></span>
- <span data-ttu-id="8dbce-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="8dbce-163">"\langle"</span></span>
- <span data-ttu-id="8dbce-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="8dbce-164">"\rangle"</span></span>
- <span data-ttu-id="8dbce-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="8dbce-165">"\bigg"</span></span>
- <span data-ttu-id="8dbce-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="8dbce-166">"\Big"</span></span>
- <span data-ttu-id="8dbce-167">"|"</span><span class="sxs-lookup"><span data-stu-id="8dbce-167">"|"</span></span>
- <span data-ttu-id="8dbce-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="8dbce-168">"\mathbb"</span></span>
- <span data-ttu-id="8dbce-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="8dbce-169">"\vec"</span></span>
- <span data-ttu-id="8dbce-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="8dbce-170">"\in"</span></span>
- <span data-ttu-id="8dbce-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="8dbce-171">"\texttt"</span></span>
- <span data-ttu-id="8dbce-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="8dbce-172">"\ne"</span></span>
- <span data-ttu-id="8dbce-173">"<"</span><span class="sxs-lookup"><span data-stu-id="8dbce-173">"<"</span></span>
- <span data-ttu-id="8dbce-174">">"</span><span class="sxs-lookup"><span data-stu-id="8dbce-174">">"</span></span>
- <span data-ttu-id="8dbce-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="8dbce-175">"\leq"</span></span>
- <span data-ttu-id="8dbce-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="8dbce-176">"\geq"</span></span>
- <span data-ttu-id="8dbce-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="8dbce-177">"~~"</span></span>
- <span data-ttu-id="8dbce-178">"~"</span><span class="sxs-lookup"><span data-stu-id="8dbce-178">"~"</span></span>
- <span data-ttu-id="8dbce-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="8dbce-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="8dbce-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="8dbce-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="8dbce-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="8dbce-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="8dbce-182">Wektory i macierze</span><span class="sxs-lookup"><span data-stu-id="8dbce-182">Vectors and Matrices</span></span>

<span data-ttu-id="8dbce-183">Znajomość wektorów i macierzy jest niezbędna do zrozumienia przetwarzania Quantum.</span><span class="sxs-lookup"><span data-stu-id="8dbce-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="8dbce-184">Udostępniamy krótkie wprowadzenie poniżej, a zainteresowani czytelnicy są zalecani do odczytania standardowego odwołania do algebry liniowego *, takiego jak Strang, G. (1993). Wprowadzenie do liniowej algebry (obj. 3). Wellesley, MA: Wellesley-Cambridge naciśnij* lub odwołanie online, takie jak [algebry liniowe](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="8dbce-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="8dbce-185">Wektor kolumny (lub po prostu [*wektor*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ wymiaru (lub rozmiaru) $ n $ jest kolekcją $ n $ liczb zespolonych $ (v_1, v_2, \ldots, v_n) $ uporządkowanych jako kolumna:</span><span class="sxs-lookup"><span data-stu-id="8dbce-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="8dbce-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="8dbce-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-187">v_1\\\\</span></span>
<span data-ttu-id="8dbce-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-188">v_2\\\\</span></span>
<span data-ttu-id="8dbce-189">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-189">\vdots\\\\</span></span>
<span data-ttu-id="8dbce-190">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="8dbce-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="8dbce-191">Norma wektora $ v $ jest definiowana jako $ \sqrt { \sum \_ i | v \_ i | ^ 2 } $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="8dbce-192">Wektor jest określany jako wartość normy jednostkowej (lub alternatywnie jest nazywany [*wektorem jednostki*](https://en.wikipedia.org/wiki/Unit_vector)), jeśli jej normą $ jest $ 1.</span><span class="sxs-lookup"><span data-stu-id="8dbce-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="8dbce-193">[*Sąsiadująca wektora*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ jest oznaczona jako $ \dagger $ wektora v ^ i jest definiowana jako następująca Vector, gdzie $ \* $ wskazuje złożona sprzężona,</span><span class="sxs-lookup"><span data-stu-id="8dbce-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="8dbce-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix} ^ \dagger = \begin{bmatrix} v_1 ^ \* & \cdots & v_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="8dbce-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="8dbce-195">Najbardziej typowym sposobem mnożenia dwóch wektorów jest użycie [*wewnętrznego produktu*](https://en.wikipedia.org/wiki/Inner_product_space), znanego również jako iloczyn kropki.</span><span class="sxs-lookup"><span data-stu-id="8dbce-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="8dbce-196">Wewnętrzny produkt daje rzutowanie jednego wektora na inny i jest niecenny w opisie, jak wyznaczać jeden wektor jako sumę innych łatwiejszych wektorów.</span><span class="sxs-lookup"><span data-stu-id="8dbce-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="8dbce-197">Wewnętrzny produkt między $ u $ i $ v $ , oznaczany $ \left \langle u, v \right \rangle $ jest zdefiniowany jako</span><span class="sxs-lookup"><span data-stu-id="8dbce-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="8dbce-198">\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } v_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="8dbce-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="8dbce-199">Ten zapis umożliwia także zapisanie normy wektora $ v $ jako $ \sqrt { \langle v, v \rangle } $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="8dbce-200">Możemy pomnożyć wektor z liczbą c, $ $ Aby utworzyć nowy wektor, którego wpisy są mnożone przez $ c $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="8dbce-201">Możemy również dodać dwa wektory $ u $ i $ v $ w celu utworzenia nowego wektora, którego wpisy są sumą wpisów $ u $ i $ v $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="8dbce-202">Poniżej przedstawiono następujące operacje:</span><span class="sxs-lookup"><span data-stu-id="8dbce-202">These operations are depicted below:</span></span>

<span data-ttu-id="8dbce-203">$$\mathrm{Jeśli } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="8dbce-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-204">u_1\\\\</span></span>
<span data-ttu-id="8dbce-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-205">u_2\\\\</span></span>
<span data-ttu-id="8dbce-206">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-206">\vdots\\\\</span></span>
<span data-ttu-id="8dbce-207">u_n \end{bmatrix} ~ \mathrm { i}~</span><span class="sxs-lookup"><span data-stu-id="8dbce-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="8dbce-208">v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="8dbce-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-209">v_1\\\\</span></span>
    <span data-ttu-id="8dbce-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-210">v_2\\\\</span></span>
    <span data-ttu-id="8dbce-211">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-211">\vdots\\\\</span></span>
    <span data-ttu-id="8dbce-212">v_n \end{bmatrix} , ~ \mathrm { następnie}~</span><span class="sxs-lookup"><span data-stu-id="8dbce-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="8dbce-213">Au + BV =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="8dbce-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="8dbce-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="8dbce-216">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-216">\vdots\\\\</span></span>
<span data-ttu-id="8dbce-217">au_n i bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="8dbce-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="8dbce-218">[*Macierz*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) o rozmiarze $ m \times n $ to zbiór $ $ liczb zespolonych MN uporządkowanych w $ $ wierszach m i $ n $ kolumn, jak pokazano poniżej:</span><span class="sxs-lookup"><span data-stu-id="8dbce-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="8dbce-219">$$Mol =</span><span class="sxs-lookup"><span data-stu-id="8dbce-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="8dbce-220">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="8dbce-221">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="8dbce-222">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="8dbce-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="8dbce-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="8dbce-224">Należy zauważyć, że wektor wymiaru $ n $ jest po prostu macierzą o rozmiarze $ n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="8dbce-225">Podobnie jak w przypadku wektorów, możemy pomnożyć macierz o liczbie $ c $ , aby uzyskać nową macierz, w której każdy wpis jest mnożony przez $ c $ , i można dodać dwie macierze o tym samym rozmiarze, aby utworzyć nową macierz, której wpisy są sumą odpowiednich wpisów dwóch macierzy.</span><span class="sxs-lookup"><span data-stu-id="8dbce-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="8dbce-226">Iloczyny i wielokrotność macierzy</span><span class="sxs-lookup"><span data-stu-id="8dbce-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="8dbce-227">Możemy również pomnożyć dwie macierze $ m $ wymiaru $ m \times n $ i $ n $ wymiaru $ n \times p, $ Aby uzyskać nową macierz $ p $ o wymiarze $ m \times p $ w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8dbce-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="8dbce-228">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="8dbce-229">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="8dbce-230">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { MN}</span><span class="sxs-lookup"><span data-stu-id="8dbce-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="8dbce-231">N_ { 11 } ~~ N_ { 12 } ~~ \cdots ~~ N_ { 1p}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="8dbce-232">N_ { 21 } ~~ N_ { 22 } ~~ \cdots ~~ N_ {}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="8dbce-233">N_ { N1 } ~~ N_ { N2 } ~~ \cdots ~~ N_ { np}</span><span class="sxs-lookup"><span data-stu-id="8dbce-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="8dbce-234">P_ { 11 } ~~ p_ { 12 } ~~ \cdots ~~ p_ { 1p}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="8dbce-235">P_ { 21 } ~~ p_ { 22 } ~~ \cdots ~~ p_ {}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="8dbce-236">P_ { M1 } ~~ p_ { m2 } ~~ \cdots ~~ p_ { MP}</span><span class="sxs-lookup"><span data-stu-id="8dbce-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="8dbce-237">miejsce, w którym wpisy $ P $ są $ p_ { IK } = \sum _j M_ { IJ } N_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="8dbce-238">Na przykład wpis $ p_ { 11 } $ jest wewnętrznym produktem pierwszego wiersza $ M $ z pierwszą kolumną $ N $ . Należy zauważyć, że ponieważ wektor jest po prostu szczególnym przypadkiem macierzy, ta definicja rozciąga się na liczebność wektora.</span><span class="sxs-lookup"><span data-stu-id="8dbce-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="8dbce-239">Wszystkie używane macierze będą macierzami kwadratowymi, gdzie liczba wierszy i kolumn jest równa lub wektorów, które odnoszą się tylko do $ 1 $ kolumny.</span><span class="sxs-lookup"><span data-stu-id="8dbce-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="8dbce-240">Jedna specjalna macierz kwadratowa to [*macierz tożsamości*](https://en.wikipedia.org/wiki/Identity_matrix), oznaczona $ \boldone $ , która ma wszystkie elementy ukośne równe $ 1 $ i pozostałe elementy równe $ 0 $ :</span><span class="sxs-lookup"><span data-stu-id="8dbce-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="8dbce-241">1 ~~ 0 ~~ 0 \cdots ~~\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="8dbce-242">0 ~~ 1 ~~ \cdots ~~\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="8dbce-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="8dbce-244">0 ~~ 0 ~~ \cdots ~~ \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="8dbce-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="8dbce-245">W przypadku macierzy kwadratowej $ a firma $ Microsoft zaleca, $ Aby macierz B $ była [*odwrócona*](https://en.wikipedia.org/wiki/Invertible_matrix) , jeśli $ AB = ba = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="8dbce-246">Odwrotność macierzy nie może istnieć, ale gdy istnieje, jest unikatowa i oznacza to $ ^ { -1 } $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="8dbce-247">Dla każdej macierzy $ m $ , sąsiadujące lub sprzężone przestawianie $ m $ to macierz N, $ $ która $ N_ { IJ } = m_ { ji } ^ \* $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="8dbce-248">Sąsiadująco $ m $ jest zwykle oznaczona symbolem $ m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="8dbce-249">Załóżmy, że macierz $ u $ jest [*jednostką*](https://en.wikipedia.org/wiki/Unitary_matrix) $ , jeśli uu ^ \dagger = u ^ \dagger u = \boldone $ lub równoważne, $ U ^ { -1 } = U ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="8dbce-250">Być może najważniejszym właściwością macierzy jednostkowych jest zachowanie normy wektora.</span><span class="sxs-lookup"><span data-stu-id="8dbce-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="8dbce-251">Dzieje się tak, ponieważ</span><span class="sxs-lookup"><span data-stu-id="8dbce-251">This happens because</span></span> 

<span data-ttu-id="8dbce-252">$$\langlev, v v \rangle = ^ \dagger v = ^ \dagger u ^ { -1 } u v v = ^ \dagger u ^ u \dagger v = \langle , u v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="8dbce-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="8dbce-253">Macierz $ m $ jest określana jako [*hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) , jeśli $ m = m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="8dbce-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="8dbce-254">Na koniec, [*produkt*](https://en.wikipedia.org/wiki/Tensor_product) (lub produkt Kronecker) dwóch macierzy $ m $ o rozmiarze $ m \times $ i $ n $ rozmiaru $ p \times q $ to większa macierz $ p = M \otimes $ o rozmiarze $ MP \times NQ i $ jest uzyskiwana z $ M $ i $ n $ w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8dbce-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="8dbce-255">M \otimes N &=</span><span class="sxs-lookup"><span data-stu-id="8dbce-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="8dbce-256">M_ { 11 } ~~ \cdots ~~ m_ { 1N }\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="8dbce-257">M_ { M1 } ~~ \cdots ~~ m_ { MN  }</span><span class="sxs-lookup"><span data-stu-id="8dbce-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="8dbce-258">N_ { 11 } ~~ \cdots ~~ N_ { 1Q  }\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="8dbce-259">N_ { P1 } ~~ \cdots ~~ N_ { pq}</span><span class="sxs-lookup"><span data-stu-id="8dbce-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="8dbce-260">M_ { 11 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="8dbce-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="8dbce-261">M_ { 1N } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="8dbce-262">M_ { M1 } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="8dbce-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="8dbce-263">M_ { MN } \begin{bmatrix} N_ { 11 } ~~ \cdots ~~ N_ { 1Q } \\\\ \ddots \\\\ N_ { P1 } ~~ \cdots ~~ N_ { pq }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="8dbce-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="8dbce-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="8dbce-265">Jest to lepsza Prezentacja z kilkoma przykładami:</span><span class="sxs-lookup"><span data-stu-id="8dbce-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="8dbce-266">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="8dbce-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="8dbce-267">\begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="8dbce-268">\\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="8dbce-269">=a \begin{bmatrix} c a \\\\ d a \\\\ e \\\\ b c b \\\\ d \\\\\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="8dbce-270">oraz</span><span class="sxs-lookup"><span data-stu-id="8dbce-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="8dbce-271">a \ b \\\\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="8dbce-272">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="8dbce-273">z\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="8dbce-274">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="8dbce-275">b\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="8dbce-276">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="8dbce-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="8dbce-278">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="8dbce-279">Wykres\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="8dbce-280">e \ f \\\\ g \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="8dbce-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="8dbce-281">AE \ AF \ nie należy \\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="8dbce-282">AG \ Ah \ BG \ BH \\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="8dbce-283">ce \ CF \ de \ DF \\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="8dbce-284">CG \ ch \ DG \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="8dbce-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="8dbce-285">Ostateczną, użyteczną Konwencją notacji otaczającą produkty na siebie, jest to, że dla dowolnego wektora $ v $ lub macierz $ m $ , $ v ^ { \otimes n } $ lub $ m ^ { \otimes n } $ jest krótkie dla jednostronicowego $ $ produktu dwuetapowego.</span><span class="sxs-lookup"><span data-stu-id="8dbce-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="8dbce-286">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="8dbce-286">For example:</span></span>

\begin{align}
<span data-ttu-id="8dbce-287">&\begin{bmatrix}1 0 1 0, 1 0 1, 0 0 \\\\ \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \end{bmatrix} \qquad \begin{bmatrix} \\\\ \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} -1-1-1,\\\\</span><span class="sxs-lookup"><span data-stu-id="8dbce-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="8dbce-288">&\begin{bmatrix}0 1 1 0 1,0 1 0 & \\\\ & \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & \\\\ & \end{bmatrix} , \qquad \begin{bmatrix} 0 1 1,0 & \\\\ & 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 1,0 0 0 0 0 0 1 0 0 0</span><span class="sxs-lookup"><span data-stu-id="8dbce-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
