---
<span data-ttu-id="c2c55-101">title: zaawansowane pojęcia dotyczące macierzy: informacje na temat eigenvectors, eigenvalues i wykładniczych, podstawowych narzędzi służących do opisywania i symulowania algorytmów Quantum.</span><span class="sxs-lookup"><span data-stu-id="c2c55-101">title: Advanced matrix concepts description: Learn about eigenvectors, eigenvalues, and matrix exponentials, the fundamental tools used to describe and simulate quantum algorithms.</span></span>
<span data-ttu-id="c2c55-102">Autor: QuantumWriter UID: Microsoft. Quantum. koncepcje. Matrix — Advanced MS. Author: v-benbra MS. Date: 12/11/2017 MS. temat: artykuł No-Loc:</span><span class="sxs-lookup"><span data-stu-id="c2c55-102">author: QuantumWriter uid: microsoft.quantum.concepts.matrix-advanced ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="c2c55-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="c2c55-103">"Q#"</span></span>
- <span data-ttu-id="c2c55-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="c2c55-104">"$$v"</span></span>
- <span data-ttu-id="c2c55-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-105">"$$"</span></span>
- <span data-ttu-id="c2c55-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-106">"$$"</span></span>
- <span data-ttu-id="c2c55-107">"$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-107">"$"</span></span>
- <span data-ttu-id="c2c55-108">"$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-108">"$"</span></span>
- <span data-ttu-id="c2c55-109">"$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-109">"$"</span></span>
- <span data-ttu-id="c2c55-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-110">"$$"</span></span>
- <span data-ttu-id="c2c55-111">"$$$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-111">"$$$"</span></span>
- <span data-ttu-id="c2c55-112">"$$$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-112">"$$$"</span></span>
- <span data-ttu-id="c2c55-113">"$$$"</span><span class="sxs-lookup"><span data-stu-id="c2c55-113">"$$$"</span></span>
- <span data-ttu-id="c2c55-114">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="c2c55-114">"\cdots"</span></span>
- <span data-ttu-id="c2c55-115">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="c2c55-115">"bmatrix"</span></span>
- <span data-ttu-id="c2c55-116">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="c2c55-116">"\ddots"</span></span>
- <span data-ttu-id="c2c55-117">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="c2c55-117">"\equiv"</span></span>
- <span data-ttu-id="c2c55-118">"\sum"</span><span class="sxs-lookup"><span data-stu-id="c2c55-118">"\sum"</span></span>
- <span data-ttu-id="c2c55-119">"\begin"</span><span class="sxs-lookup"><span data-stu-id="c2c55-119">"\begin"</span></span>
- <span data-ttu-id="c2c55-120">"\end"</span><span class="sxs-lookup"><span data-stu-id="c2c55-120">"\end"</span></span>
- <span data-ttu-id="c2c55-121">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="c2c55-121">"\sqrt"</span></span>
- <span data-ttu-id="c2c55-122">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="c2c55-122">"\otimes"</span></span>
- <span data-ttu-id="c2c55-123">"{"</span><span class="sxs-lookup"><span data-stu-id="c2c55-123">"{"</span></span>
- <span data-ttu-id="c2c55-124">"}"</span><span class="sxs-lookup"><span data-stu-id="c2c55-124">"}"</span></span>
- <span data-ttu-id="c2c55-125">"\text"</span><span class="sxs-lookup"><span data-stu-id="c2c55-125">"\text"</span></span>
- <span data-ttu-id="c2c55-126">"\phi"</span><span class="sxs-lookup"><span data-stu-id="c2c55-126">"\phi"</span></span>
- <span data-ttu-id="c2c55-127">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="c2c55-127">"\kappa"</span></span>
- <span data-ttu-id="c2c55-128">"\psi"</span><span class="sxs-lookup"><span data-stu-id="c2c55-128">"\psi"</span></span>
- <span data-ttu-id="c2c55-129">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="c2c55-129">"\alpha"</span></span>
- <span data-ttu-id="c2c55-130">"\beta"</span><span class="sxs-lookup"><span data-stu-id="c2c55-130">"\beta"</span></span>
- <span data-ttu-id="c2c55-131">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="c2c55-131">"\gamma"</span></span>
- <span data-ttu-id="c2c55-132">"\delta"</span><span class="sxs-lookup"><span data-stu-id="c2c55-132">"\delta"</span></span>
- <span data-ttu-id="c2c55-133">"\omega"</span><span class="sxs-lookup"><span data-stu-id="c2c55-133">"\omega"</span></span>
- <span data-ttu-id="c2c55-134">"\bra"</span><span class="sxs-lookup"><span data-stu-id="c2c55-134">"\bra"</span></span>
- <span data-ttu-id="c2c55-135">"\ket"</span><span class="sxs-lookup"><span data-stu-id="c2c55-135">"\ket"</span></span>
- <span data-ttu-id="c2c55-136">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="c2c55-136">"\boldone"</span></span>
- <span data-ttu-id="c2c55-137">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="c2c55-137">"\\\\"</span></span>
- <span data-ttu-id="c2c55-138">"\\"</span><span class="sxs-lookup"><span data-stu-id="c2c55-138">"\\"</span></span>
- <span data-ttu-id="c2c55-139">"="</span><span class="sxs-lookup"><span data-stu-id="c2c55-139">"="</span></span>
- <span data-ttu-id="c2c55-140">"\frac"</span><span class="sxs-lookup"><span data-stu-id="c2c55-140">"\frac"</span></span>
- <span data-ttu-id="c2c55-141">"\text"</span><span class="sxs-lookup"><span data-stu-id="c2c55-141">"\text"</span></span>
- <span data-ttu-id="c2c55-142">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="c2c55-142">"\mapsto"</span></span>
- <span data-ttu-id="c2c55-143">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="c2c55-143">"\dagger"</span></span>
- <span data-ttu-id="c2c55-144">"\to"</span><span class="sxs-lookup"><span data-stu-id="c2c55-144">"\to"</span></span>
- <span data-ttu-id="c2c55-145">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="c2c55-145">"\begin{cases}"</span></span>
- <span data-ttu-id="c2c55-146">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="c2c55-146">"\end{cases}"</span></span>
- <span data-ttu-id="c2c55-147">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="c2c55-147">"\operatorname"</span></span>
- <span data-ttu-id="c2c55-148">"\braket"</span><span class="sxs-lookup"><span data-stu-id="c2c55-148">"\braket"</span></span>
- <span data-ttu-id="c2c55-149">"\id"</span><span class="sxs-lookup"><span data-stu-id="c2c55-149">"\id"</span></span>
- <span data-ttu-id="c2c55-150">"\expect"</span><span class="sxs-lookup"><span data-stu-id="c2c55-150">"\expect"</span></span>
- <span data-ttu-id="c2c55-151">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="c2c55-151">"\defeq"</span></span>
- <span data-ttu-id="c2c55-152">"\variance"</span><span class="sxs-lookup"><span data-stu-id="c2c55-152">"\variance"</span></span>
- <span data-ttu-id="c2c55-153">"\dd"</span><span class="sxs-lookup"><span data-stu-id="c2c55-153">"\dd"</span></span>
- <span data-ttu-id="c2c55-154">"&"</span><span class="sxs-lookup"><span data-stu-id="c2c55-154">"&"</span></span>
- <span data-ttu-id="c2c55-155">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="c2c55-155">"\begin{align}"</span></span>
- <span data-ttu-id="c2c55-156">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="c2c55-156">"\end{align}"</span></span>
- <span data-ttu-id="c2c55-157">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="c2c55-157">"\Lambda"</span></span>
- <span data-ttu-id="c2c55-158">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="c2c55-158">"\lambda"</span></span>
- <span data-ttu-id="c2c55-159">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="c2c55-159">"\Omega"</span></span>
- <span data-ttu-id="c2c55-160">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="c2c55-160">"\mathrm"</span></span>
- <span data-ttu-id="c2c55-161">"\left"</span><span class="sxs-lookup"><span data-stu-id="c2c55-161">"\left"</span></span>
- <span data-ttu-id="c2c55-162">"\right"</span><span class="sxs-lookup"><span data-stu-id="c2c55-162">"\right"</span></span>
- <span data-ttu-id="c2c55-163">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="c2c55-163">"\qquad"</span></span>
- <span data-ttu-id="c2c55-164">"\times"</span><span class="sxs-lookup"><span data-stu-id="c2c55-164">"\times"</span></span>
- <span data-ttu-id="c2c55-165">"\big"</span><span class="sxs-lookup"><span data-stu-id="c2c55-165">"\big"</span></span>
- <span data-ttu-id="c2c55-166">"\langle"</span><span class="sxs-lookup"><span data-stu-id="c2c55-166">"\langle"</span></span>
- <span data-ttu-id="c2c55-167">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="c2c55-167">"\rangle"</span></span>
- <span data-ttu-id="c2c55-168">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="c2c55-168">"\bigg"</span></span>
- <span data-ttu-id="c2c55-169">"\Big"</span><span class="sxs-lookup"><span data-stu-id="c2c55-169">"\Big"</span></span>
- <span data-ttu-id="c2c55-170">"|"</span><span class="sxs-lookup"><span data-stu-id="c2c55-170">"|"</span></span>
- <span data-ttu-id="c2c55-171">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="c2c55-171">"\mathbb"</span></span>
- <span data-ttu-id="c2c55-172">"\vec"</span><span class="sxs-lookup"><span data-stu-id="c2c55-172">"\vec"</span></span>
- <span data-ttu-id="c2c55-173">"\in"</span><span class="sxs-lookup"><span data-stu-id="c2c55-173">"\in"</span></span>
- <span data-ttu-id="c2c55-174">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="c2c55-174">"\texttt"</span></span>
- <span data-ttu-id="c2c55-175">"\ne"</span><span class="sxs-lookup"><span data-stu-id="c2c55-175">"\ne"</span></span>
- <span data-ttu-id="c2c55-176">"<"</span><span class="sxs-lookup"><span data-stu-id="c2c55-176">"<"</span></span>
- <span data-ttu-id="c2c55-177">">"</span><span class="sxs-lookup"><span data-stu-id="c2c55-177">">"</span></span>
- <span data-ttu-id="c2c55-178">"\leq"</span><span class="sxs-lookup"><span data-stu-id="c2c55-178">"\leq"</span></span>
- <span data-ttu-id="c2c55-179">"\geq"</span><span class="sxs-lookup"><span data-stu-id="c2c55-179">"\geq"</span></span>
- <span data-ttu-id="c2c55-180">"~~"</span><span class="sxs-lookup"><span data-stu-id="c2c55-180">"~~"</span></span>
- <span data-ttu-id="c2c55-181">"~"</span><span class="sxs-lookup"><span data-stu-id="c2c55-181">"~"</span></span>
- <span data-ttu-id="c2c55-182">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c2c55-182">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="c2c55-183">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="c2c55-183">"\end{bmatrix}"</span></span>
- <span data-ttu-id="c2c55-184">"\_"</span><span class="sxs-lookup"><span data-stu-id="c2c55-184">"\_"</span></span>

---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="c2c55-185">Zaawansowane koncepcje macierzy</span><span class="sxs-lookup"><span data-stu-id="c2c55-185">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="c2c55-186">Teraz rozszerzamy manipulowanie macierzami na [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) i [*wykładnicze*](https://en.wikipedia.org/wiki/Matrix_exponential) , które tworzą podstawowy zestaw narzędzi potrzebnych do opisywania i implementowania algorytmów Quantum.</span><span class="sxs-lookup"><span data-stu-id="c2c55-186">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="c2c55-187">Eigenvalues i Eigenvectors</span><span class="sxs-lookup"><span data-stu-id="c2c55-187">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="c2c55-188">Przypuśćmy, $ $ że jest to macierz kwadratowa, a funkcja $ v to $ wektor, który nie jest wektorem "All Zeros" (tj. wektor ze wszystkimi wpisami równą $ 0 $ ).</span><span class="sxs-lookup"><span data-stu-id="c2c55-188">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="c2c55-189">Załóżmy $ $ , że v to [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors)  $ M, $ Jeśli $ = OKS $ dla pewnej liczby $ c $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-189">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="c2c55-190">Załóżmy $ $ , że c jest [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) odpowiadający eigenvector $ v $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-190">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="c2c55-191">Ogólnie rzecz biorąc $ , macierz M $ może przekształcić wektor w dowolne inne wektory, ale eigenvector jest specjalny, ponieważ pozostaje niezmieniony, z wyjątkiem tego, że jest mnożony przez liczbę.</span><span class="sxs-lookup"><span data-stu-id="c2c55-191">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="c2c55-192">Należy pamiętać, że jeśli $ v $ jest eigenvector z eigenvalue $ c $ , to $ AV $ jest również eigenvector (dla dowolnej niezerowej $ a $ ) z tym samym eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="c2c55-192">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="c2c55-193">Na przykład w przypadku macierzy tożsamości każdy wektor $ v $ jest eigenvector z eigenvalue $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-193">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="c2c55-194">Innym przykładem jest rozważenie [*przekątnej matrycy*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D, $ która ma tylko niezerowe wpisy na przekątnej:</span><span class="sxs-lookup"><span data-stu-id="c2c55-194">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

$$
\begin{bmatrix}
<span data-ttu-id="c2c55-195">wartość d_1 & 0 & 0 0 \\\\ & d_2 & 0 0 0 \\\\ & & D_3 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="c2c55-195">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="c2c55-196">Wektory</span><span class="sxs-lookup"><span data-stu-id="c2c55-196">The vectors</span></span>

<span data-ttu-id="c2c55-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ \end{bmatrix} , 0 \begin{bmatrix} \\\\ 1 \\\\ \end{bmatrix} i \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="c2c55-197">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="c2c55-198">są eigenvectors tej macierzy odpowiednio z eigenvalues  $ D_1 $ , $ d_2 $ i $ D_3 $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-198">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="c2c55-199">Jeśli $ D_1 $ , $ d_2 $ i $ D_3 $ są liczbami odrębnymi, wówczas te wektory (i ich wielokrotność) są jedyną eigenvectorsą macierzy $ d $ . Ogólnie rzecz biorąc, w przypadku matrycy ukośnej można łatwo odczytywać eigenvalues i eigenvectors.</span><span class="sxs-lookup"><span data-stu-id="c2c55-199">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$. In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="c2c55-200">Eigenvalues są wszystkie liczby wyświetlane na przekątnej, a ich odpowiednie eigenvectors to wektory jednostek z jednym wpisem równym 1, $ $ a pozostałe wpisy są równe $ 0 $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-200">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="c2c55-201">Zwróć uwagę, że w powyższym przykładzie eigenvectors z $ D jest $ podstawą dla $ $ wektorów trójwymiarowych.</span><span class="sxs-lookup"><span data-stu-id="c2c55-201">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="c2c55-202">Podstawą jest zestaw wektorów, tak że każdy wektor może być zapisany jako liniowa kombinacja.</span><span class="sxs-lookup"><span data-stu-id="c2c55-202">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="c2c55-203">Bardziej jawnie, $ v_1 $ , $ v_2 $ i $ v_3 $ stanowią podstawę, jeśli dowolny wektor $ v $ może być zapisany jako $ v = A_1 v_1 + a_2 v_2 + a_3 v_3 $ dla niektórych liczb $ A_1 $ , $ a_2 $ i $ a_3 $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-203">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="c2c55-204">Odwołaj, że macierz hermitian (nazywana również własnym) to złożona macierz kwadratowa równa własnej złożonej funkcji sprzężonej, a macierz jednostkowa to złożona macierz kwadratowa, której odwrotność jest równa jego przylegającej lub złożonej funkcji sprzężonej.</span><span class="sxs-lookup"><span data-stu-id="c2c55-204">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate transpose, while a unitary matrix is a complex square matrix whose inverse is equal to its adjoint or complex conjugate transpose.</span></span>
<span data-ttu-id="c2c55-205">W przypadku hermitian i macierzy jednostkowych, które zasadniczo są jedynymi macierzami wykrytymi w ramach obliczeń opartych na usłudze Quantum, istnieje ogólny wynik, który jest znany jako [*widmo theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), które potwierdzają następujące kwestie: dla każdej Hermitianej lub macierzy jednostkowej $ M $ , istnieje jednostka a, $ $ która oznacza, że $ M = u w \dagger $ przypadku niektórych przekątnych macierzy $ D $ . Ponadto, ukośne wpisy $ D $ będą eigenvalues $ M $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-205">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$. Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="c2c55-206">Wiemy już, jak obliczyć eigenvalues i eigenvectorse dla macierzy ukośnych $ D $ . Korzystając z tej theorem, wiemy, że jeśli $ v $ jest eigenvectorem $ D $ z eigenvalue $ c $ , tj. $ cyfrowa = CV $ , a następnie $ U ^ \dagger v $ będzie eigenvector $ M $ z eigenvalue $ c $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-206">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$. Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="c2c55-207">Dzieje się tak, ponieważ</span><span class="sxs-lookup"><span data-stu-id="c2c55-207">This is because</span></span>

<span data-ttu-id="c2c55-208">$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (U u ^ \dagger ) v = u ^ \dagger d v = c u ^ \dagger v.$$</span><span class="sxs-lookup"><span data-stu-id="c2c55-208">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="c2c55-209">Wykładnicze macierze</span><span class="sxs-lookup"><span data-stu-id="c2c55-209">Matrix Exponentials</span></span>
<span data-ttu-id="c2c55-210">W przypadku funkcji wykładniczej można również zdefiniować wartość [*wykładniczą macierzy*](https://en.wikipedia.org/wiki/Matrix_exponential) .</span><span class="sxs-lookup"><span data-stu-id="c2c55-210">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="c2c55-211">Wartość wykładnicza macierzy macierzy $ a $ może być wyrażona jako</span><span class="sxs-lookup"><span data-stu-id="c2c55-211">The matrix exponential of a matrix $A$ can be expressed as</span></span>

$$
<span data-ttu-id="c2c55-212">e ^ A = \boldone + a + \frac { a ^ 2 } { ! } + \frac { ^ 3 } { 3!}+\cdots</span><span class="sxs-lookup"><span data-stu-id="c2c55-212">e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots</span></span>
$$

<span data-ttu-id="c2c55-213">Jest to ważne, ponieważ zmiana czasu mechanicznego Quantum jest opisana przez macierz jednostkową formularza $ e ^ { IB } $ dla hermitian macierzy $ B $ .  Z tego powodu wykonywanie wartości wykładniczych macierzy jest podstawową częścią obliczeniowych procesów Quantum, a jako takie Q# oferują procedury wewnętrzne umożliwiające opisywanie tych operacji.</span><span class="sxs-lookup"><span data-stu-id="c2c55-213">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.  For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="c2c55-214">Istnieje wiele sposobów na rozliczenie matrycy wykładniczej na klasycznym komputerze i ogólnie numeryczne przybliżenie takiej wartości wykładniczej to fraught z Peril.</span><span class="sxs-lookup"><span data-stu-id="c2c55-214">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="c2c55-215">Zobacz [*Cleve Moler i Charles van. "Nineteen podejrzanych metody obliczeń wykładniczych macierzy". SIAM przegląd 20,4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) , aby uzyskać więcej informacji na temat wyzwań.</span><span class="sxs-lookup"><span data-stu-id="c2c55-215">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="c2c55-216">Najprostszym sposobem, aby zrozumieć, jak obliczyć wartość wykładniczą macierzy, za pomocą eigenvalues i eigenvectors tej macierzy.</span><span class="sxs-lookup"><span data-stu-id="c2c55-216">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="c2c55-217">W odniesieniu do theorem widma omówione powyżej mówi, że dla każdej hermitian lub macierzy jednostkowej $ $ istnieje macierz jednostkowa $ u $ i $ wielowarstwowa macierz D, $ taka jak $ = u \dagger $ .  Ze względu na właściwości unitarity mamy, że $ ^ 2 = u ^ \dagger d ^ 2 u $ i podobne dla każdej potęgi $ p $ $ ^ p = ^ \dagger d ^ p $ .  Jeśli ta funkcja zostanie zastąpiona definicją operatora operatora wykładniczego, uzyskujemy:</span><span class="sxs-lookup"><span data-stu-id="c2c55-217">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

$$
<span data-ttu-id="c2c55-218">e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (D_ { 11 } ) & 0 & \cdots & 0 \\\\ & \exp (D_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (D_ { NN } ) \end{bmatrix} U.$$</span><span class="sxs-lookup"><span data-stu-id="c2c55-218">e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="c2c55-219">Innymi słowy, jeśli przekształcasz na eigenbasis macierzy a, a $ $ następnie obliczamy wartość wykładniczą macierzy, jest równoważne obliczaniu zwykłej wartości wykładniczej eigenvalues macierzy.</span><span class="sxs-lookup"><span data-stu-id="c2c55-219">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="c2c55-220">Ponieważ wiele operacji obliczeniowych opartych na infrastrukturze opartej na protokole Quantum obejmuje wykonywanie wartości wykładniczych macierzy, to ta część transformacji w eigenbasis macierzy, która upraszcza wykonywanie operatora wykładniczego, i jest podstawą za wiele algorytmów Quantum, takich jak Trotter – Suzuki-style metody symulacji w dalszej części tego przewodnika.</span><span class="sxs-lookup"><span data-stu-id="c2c55-220">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="c2c55-221">Inną przydatną właściwością jest to, że $ b $ jest zarówno jednostką, jak i hermitian, czyli $ b = b ^ { -1 } = b ^, \dagger $ a następnie $ b ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="c2c55-221">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="c2c55-222">Stosując tę regułę do powyższego rozwinięcia macierzy wykładniczej i grupując $ \boldone $ $ warunki i B $ razem, można zobaczyć, że dla dowolnych wartości rzeczywistych $ x $ tożsamość</span><span class="sxs-lookup"><span data-stu-id="c2c55-222">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="c2c55-223">$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$</span><span class="sxs-lookup"><span data-stu-id="c2c55-223">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="c2c55-224">przechowywane.</span><span class="sxs-lookup"><span data-stu-id="c2c55-224">holds.</span></span> <span data-ttu-id="c2c55-225">Ta lewę jest szczególnie przydatna, ponieważ umożliwia jej przyczynę o wartościach wykładniczych macierzy akcji, nawet jeśli wymiar $ b $ jest duży, w przypadku sytuacji, gdy $ b $ jest to jednostka jednostkowa i hermitian.</span><span class="sxs-lookup"><span data-stu-id="c2c55-225">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
