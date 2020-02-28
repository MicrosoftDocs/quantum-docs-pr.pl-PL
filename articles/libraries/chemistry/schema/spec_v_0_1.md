---
title: Specyfikacja schematu Broombridge (ver 0,1)
description: Szczegóły specyfikacji dla schematu chemii Broombridge Quantum v dla biblioteki chemii Microsoft Quantum.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906427"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="52216-103">Specyfikacja Broombridge v 0,1</span><span class="sxs-lookup"><span data-stu-id="52216-103">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="52216-104">Kluczowe słowa "musi", "nie może być", "wymagane", ",", ",", "," powinny "," nie powinno być "," zalecane "," maj "i" opcjonalne "w tym dokumencie są interpretowane zgodnie z opisem w [dokumencie RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="52216-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="52216-105">Każdy pasek boczny z nagłówkami "Uwaga", "informacje" lub "ostrzeżenie" ma format.</span><span class="sxs-lookup"><span data-stu-id="52216-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="52216-106">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="52216-106">Introduction</span></span> ##

<span data-ttu-id="52216-107">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="52216-107">This section is informative.</span></span>

<span data-ttu-id="52216-108">Dokumenty Broombridge są przeznaczone do przekazywania wystąpień problemów symulacji w ramach chemii Quantum do przetwarzania za pomocą symulacji Quantum i programowanie łańcuchy narzędzi.</span><span class="sxs-lookup"><span data-stu-id="52216-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="52216-109">Serializacji</span><span class="sxs-lookup"><span data-stu-id="52216-109">Serialization</span></span> ##

<span data-ttu-id="52216-110">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-110">This section is normative.</span></span>

<span data-ttu-id="52216-111">Dokument Broombridge musi być serializowany jako [dokument YAML 1,2](http://yaml.org/spec/) reprezentujący obiekt JSON, zgodnie z opisem w sekcji [RFC 4627](https://tools.ietf.org/html/rfc4627) sekcja 2,2.</span><span class="sxs-lookup"><span data-stu-id="52216-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="52216-112">Serializacja obiektu do YAML musi mieć Właściwość `"$schema"` której wartość jest `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`i musi być prawidłowa zgodnie z wersją schematu JSON — 06 specyfikacje [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="52216-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="52216-113">Dla pozostałej części tej specyfikacji "obiekt Broombridge" odwołuje się do obiektu JSON deserializowanego z dokumentu Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="52216-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="52216-114">O ile jawnie nie zaznaczono inaczej, obiekty nie mogą mieć dodatkowych właściwości poza tymi określonymi jawnie w tym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="52216-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="52216-115">Dodatkowe definicje</span><span class="sxs-lookup"><span data-stu-id="52216-115">Additional Definitions</span></span> ##

<span data-ttu-id="52216-116">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="52216-117">Obiekty ilości</span><span class="sxs-lookup"><span data-stu-id="52216-117">Quantity Objects</span></span> ###

<span data-ttu-id="52216-118">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-118">This section is normative.</span></span>

<span data-ttu-id="52216-119">_Obiekt ilości_ jest obiektem JSON i musi mieć Właściwość `units` której wartość jest jedną z dozwolonych wartości wymienionych w tabeli 1.</span><span class="sxs-lookup"><span data-stu-id="52216-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="52216-120">Obiekt ilości jest _prostym obiektem ilości_ , jeśli ma `value` pojedynczej właściwości oprócz właściwości `units`.</span><span class="sxs-lookup"><span data-stu-id="52216-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="52216-121">Wartość właściwości `value` musi być liczbą.</span><span class="sxs-lookup"><span data-stu-id="52216-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="52216-122">Obiekt ilości jest _obiektem o ograniczonej_ liczbie, jeśli ma właściwości `lower` i `upper` poza `units` właściwością.</span><span class="sxs-lookup"><span data-stu-id="52216-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="52216-123">Wartości `lower` i `upper` właściwości muszą być liczbami.</span><span class="sxs-lookup"><span data-stu-id="52216-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="52216-124">Obiekt o ograniczonej ilości może mieć Właściwość `value` której wartość jest liczbą.</span><span class="sxs-lookup"><span data-stu-id="52216-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="52216-125">Obiekt ilości jest _obiektem ilości tablicy rozrzedzonej_ , jeśli ma właściwość `format` i Właściwość `values` oprócz `units` właściwości.</span><span class="sxs-lookup"><span data-stu-id="52216-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="52216-126">Wartość `format` musi być ciągiem `sparse`.</span><span class="sxs-lookup"><span data-stu-id="52216-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="52216-127">Wartość właściwości `values` musi być tablicą.</span><span class="sxs-lookup"><span data-stu-id="52216-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="52216-128">Każdy element `values` musi być tablicą reprezentującą indeksy i wartość liczby tablicy rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="52216-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="52216-129">Indeksy dla każdego elementu obiektu liczby tablic rozrzedzonych muszą być unikatowe w całym obiekcie ilości tablicy rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="52216-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="52216-130">Jeśli indeks jest obecny z wartością `0`, Analizator musi traktować obiekt ilości tablicy rozrzedzonej identycznie do obiektu z ilością tablicy rozrzedzonej, w którym ten indeks nie jest obecny.</span><span class="sxs-lookup"><span data-stu-id="52216-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="52216-131">Obiekt ilości musi być</span><span class="sxs-lookup"><span data-stu-id="52216-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="52216-132">prosty obiekt ilości,</span><span class="sxs-lookup"><span data-stu-id="52216-132">a simple quantity object,</span></span>
- <span data-ttu-id="52216-133">Obiekt ograniczonej ilości lub</span><span class="sxs-lookup"><span data-stu-id="52216-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="52216-134">Obiekt ilości tablicy rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="52216-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="52216-135">Przykłady</span><span class="sxs-lookup"><span data-stu-id="52216-135">Examples</span></span> ###

<span data-ttu-id="52216-136">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="52216-136">This section is informative.</span></span>

<span data-ttu-id="52216-137">Prosta ilość reprezentująca $1.9844146837\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="52216-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="52216-138">Ograniczona ilość reprezentująca jednolitą dystrybucję dla interwału $ [-7,-6]\,\mathrm{Ha} $:</span><span class="sxs-lookup"><span data-stu-id="52216-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="52216-139">Poniżej znajduje się liczba tablic rozrzedzonych z elementem `[1, 2]` równe `hello` i element `[3, 4]` równy `world`:</span><span class="sxs-lookup"><span data-stu-id="52216-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="52216-140">Sekcja formatu</span><span class="sxs-lookup"><span data-stu-id="52216-140">Format Section</span></span> ##

<span data-ttu-id="52216-141">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-141">This section is normative.</span></span>

<span data-ttu-id="52216-142">Obiekt Broombridge musi mieć Właściwość `format` której wartość jest obiektem JSON z jedną właściwością o nazwie `version`.</span><span class="sxs-lookup"><span data-stu-id="52216-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="52216-143">Właściwość `version` musi mieć wartość `"0.1"`.</span><span class="sxs-lookup"><span data-stu-id="52216-143">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="52216-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="52216-144">Example</span></span> ###

<span data-ttu-id="52216-145">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="52216-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="52216-146">Sekcja zestawów całkowitych</span><span class="sxs-lookup"><span data-stu-id="52216-146">Integral Sets Section</span></span> ##

<span data-ttu-id="52216-147">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-147">This section is normative.</span></span>

<span data-ttu-id="52216-148">Obiekt Broombridge musi mieć Właściwość `integral_sets` której wartością jest tablica JSON.</span><span class="sxs-lookup"><span data-stu-id="52216-148">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="52216-149">Każdy element w wartości właściwości `integral_sets` musi być obiektem JSON opisującym jeden zestaw całek, zgodnie z opisem w pozostałej części tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="52216-149">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="52216-150">W pozostałej części tej sekcji termin "obiekt zestawu całkowitego" odwołuje się do elementu w wartości właściwości `integral_sets` obiektu Broombridge.</span><span class="sxs-lookup"><span data-stu-id="52216-150">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="52216-151">Każdy obiekt zestawu całkowitego musi mieć Właściwość `metadata` której wartość jest obiektem JSON.</span><span class="sxs-lookup"><span data-stu-id="52216-151">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="52216-152">Wartość `metadata` może być pustym obiektem JSON (czyli `{}`) lub może zawierać dodatkowe właściwości zdefiniowane przez realizatora.</span><span class="sxs-lookup"><span data-stu-id="52216-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="52216-153">Sekcja hamiltonian</span><span class="sxs-lookup"><span data-stu-id="52216-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="52216-154">Omówienie</span><span class="sxs-lookup"><span data-stu-id="52216-154">Overview</span></span> ####

<span data-ttu-id="52216-155">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="52216-155">This section is informative.</span></span>

<span data-ttu-id="52216-156">Właściwość `hamiltonian` każdego obiektu zestawu całkowitego zawiera opis hamiltonian dla konkretnego problemu chemii Quantum przez wymienienie jednego z tych warunków i dwóch treści jako rozrzedzonych tablic liczb rzeczywistych.</span><span class="sxs-lookup"><span data-stu-id="52216-156">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="52216-157">Operatory hamiltonian opisane przez każdy obiekt zestawu całkowitego przyjmują formularz</span><span class="sxs-lookup"><span data-stu-id="52216-157">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="52216-158">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{IJ\} ^\{\dagger\}\_{i, \sigma}\_{j, \sigma} \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}}\_{IJKL} a ^ \dagger\_{i , \sigma} ^ \dagger\_{k, \rho}\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="52216-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="52216-159">tutaj $h _ {IJKL} = (IJ | KL) $ w Konwencji Mulliken.</span><span class="sxs-lookup"><span data-stu-id="52216-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="52216-160">W przypadku przejrzystości okres jednorazowy to</span><span class="sxs-lookup"><span data-stu-id="52216-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="52216-161">$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="52216-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="52216-162">i dwuletni okres jest</span><span class="sxs-lookup"><span data-stu-id="52216-162">and the two-electron term is</span></span>

<span data-ttu-id="52216-163">$ $ h\_\{IJKL\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i (x\_1) \psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\psi\_k ^\{\*\}(x\_2) \psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="52216-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="52216-164">Jak wspomniano w opisie [właściwości`basis_set`](#basis-set-object) każdego elementu właściwości `integral_sets`, zdecydowanie jawnie założono, że używane funkcje podstawowe są wartościami rzeczywistymi.</span><span class="sxs-lookup"><span data-stu-id="52216-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="52216-165">Pozwala to na użycie następujących symmetries między postanowieniami w celu skompresowania reprezentacji hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="52216-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="52216-166">$ $ h_ {IJKL} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = H_ {klji} = h_ {lkij} = h_ {LKJI}.</span><span class="sxs-lookup"><span data-stu-id="52216-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="52216-167">Zawartość</span><span class="sxs-lookup"><span data-stu-id="52216-167">Contents</span></span> ####

<span data-ttu-id="52216-168">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-168">This section is normative.</span></span>

<span data-ttu-id="52216-169">Każdy zestaw całkowity musi mieć Właściwość `hamiltonian` której wartość jest obiektem JSON.</span><span class="sxs-lookup"><span data-stu-id="52216-169">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="52216-170">Wartość właściwości `hamiltonian` jest znana jako obiekt hamiltonian i musi mieć właściwości `one_electron_integrals` i `two_electron_integrals` zgodnie z opisem w pozostałej części tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="52216-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="52216-171">Obiekt hamiltonian może mieć również właściwość `particle_hole_representation`.</span><span class="sxs-lookup"><span data-stu-id="52216-171">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="52216-172">Jeśli jest obecny, wartość `particle_hole_representation` musi być zgodna z formatem opisanym w pozostałej części tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="52216-172">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="52216-173">Obiekt całkowity w jednym Elektronzie</span><span class="sxs-lookup"><span data-stu-id="52216-173">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="52216-174">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-174">This section is normative.</span></span>

<span data-ttu-id="52216-175">Właściwość `one_electron_integrals` obiektu hamiltonian musi być liczbą tablicy rozrzedzonej, której indeksy są dwoma liczbami całkowitymi i których wartości są liczbami.</span><span class="sxs-lookup"><span data-stu-id="52216-175">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="52216-176">Każdy termin musi mieć indeksy `[i, j]` gdzie `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="52216-176">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="52216-177">KORYGUJĄC Odzwierciedla to symetrię, która $h _ {IJ} = h_ {ji} $, która jest konsekwencją faktu, że hamiltonian to hermitian.</span><span class="sxs-lookup"><span data-stu-id="52216-177">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="52216-178">Przykład</span><span class="sxs-lookup"><span data-stu-id="52216-178">Example</span></span> ######

<span data-ttu-id="52216-179">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="52216-179">This section is informative.</span></span>

<span data-ttu-id="52216-180">Następująca liczba macierzy rozrzedzonych reprezentuje hamiltonian $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow}\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1, \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow}\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow}\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="52216-180">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="52216-181">Broombridge używa indeksowania opartego na 1.</span><span class="sxs-lookup"><span data-stu-id="52216-181">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="52216-182">Dwukolorowy obiekt całkowity</span><span class="sxs-lookup"><span data-stu-id="52216-182">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="52216-183">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-183">This section is normative.</span></span>

<span data-ttu-id="52216-184">Właściwość `two_electron_integrals` obiektu hamiltonian musi być ilością tablicy rozrzedzonej z jedną dodatkową właściwością o nazwie `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="52216-184">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="52216-185">Każdy element wartości `two_electron_integrals` musi mieć cztery indeksy.</span><span class="sxs-lookup"><span data-stu-id="52216-185">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="52216-186">Każda właściwość `two_electron_integrals` musi mieć Właściwość `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="52216-186">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="52216-187">Wartość właściwości `index_convention` musi być jedną z dozwolonych wartości wymienionych w tabeli 1.</span><span class="sxs-lookup"><span data-stu-id="52216-187">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="52216-188">Jeśli wartość `index_convention` jest `mulliken`, a następnie dla każdego elementu `two_electron_integrals` liczby macierzy rozrzedzonych, parser ładujący dokument Broombridge musi utworzyć wystąpienie hamiltonian terminu równego operatorowi dwuskładnikowego, $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, gdzie $i $, $j $, $k $, i $l $ muszą być liczbami całkowitymi w łącznym zakresie od 1 do liczby Electrons określonych przez właściwość `n_electrons` obiektu zestawu całkowitego i gdzie $h _ {i, j , k, l} $ jest elementem `[i, j, k, l, h(i, j, k, l)]` ilości tablicy rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="52216-188">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="52216-189">Symmetries</span><span class="sxs-lookup"><span data-stu-id="52216-189">Symmetries</span></span> ######

<span data-ttu-id="52216-190">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-190">This section is normative.</span></span>

<span data-ttu-id="52216-191">Jeśli właściwość `index_convention` obiektu `two_electron_integrals` jest równa `mulliken`, a następnie Jeśli element z indeksami `[i, j, k, l]` jest obecny, następujące indeksy nie mogą być obecne, chyba że są równe `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="52216-191">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="52216-192">Ponieważ właściwość `index_convention` jest obiektem z ilością rozrzedzoną, nie można powtarzać indeksów w różnych elementach.</span><span class="sxs-lookup"><span data-stu-id="52216-192">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="52216-193">W szczególności jeśli element z indeksami `[i, j, k, l]` jest obecny, żaden inny element nie może mieć takich indeksów.</span><span class="sxs-lookup"><span data-stu-id="52216-193">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="52216-194">Przykład</span><span class="sxs-lookup"><span data-stu-id="52216-194">Example</span></span> #######

<span data-ttu-id="52216-195">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="52216-195">This section is informative.</span></span>

<span data-ttu-id="52216-196">Poniższy obiekt Określa hamiltonian</span><span class="sxs-lookup"><span data-stu-id="52216-196">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="52216-197">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} ^ {\dagger}\_{1, \rho}\_{1, \rho}\_{1, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} \rho}\_{3, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} ^ {\dagger}\_{6, \rho} a\_{2, \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho}\_{1, \sigma}-0,1 a ^ {\dagger}\_{3 , \sigma} ^ {\dagger}\_{2, \rho}\_{1, \rho}\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho}\_{1, \rho}\_{6, \sigma}\Biggr)\\, \textrm{Ha}.\_\_</span><span class="sxs-lookup"><span data-stu-id="52216-197">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

##### <a name="particlehole-representation-object"></a><span data-ttu-id="52216-198">Obiekt reprezentacji cząsteczek</span><span class="sxs-lookup"><span data-stu-id="52216-198">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="52216-199">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-199">This section is normative.</span></span>

<span data-ttu-id="52216-200">Obiekt reprezentacji cząsteczek jest określany, że całkowite składowane są zdefiniowane w odniesieniu do reprezentacji w postaci cząsteczek, w wyniku których operatory tworzenia i Annihilation opisują excitations poza używanym stanem odwołania, takim jak Hartree — Stan Fock.</span><span class="sxs-lookup"><span data-stu-id="52216-200">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="52216-201">Obiekt jest opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="52216-201">The object is OPTIONAL.</span></span>
<span data-ttu-id="52216-202">Jeśli obiekt nie jest określony, hamiltonian ma być interpretowany jako nieokreślony w reprezentacji z dziurą cząstkową.</span><span class="sxs-lookup"><span data-stu-id="52216-202">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="52216-203">Jeśli jest obecny, wartość `particle_hole_representation` musi być obiektem ilości tablicy rozrzedzonej, którego indeksy są czterema liczbami całkowitymi, a których wartości to liczba i ciąg.</span><span class="sxs-lookup"><span data-stu-id="52216-203">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="52216-204">Część ciągu wartości każdego elementu musi zawierać tylko znaki `'+'` i `'-'`, które określają, czy dany czynnik w danym okresie jest operatorem tworzenia lub Annihilation w reprezentacji cząstek.</span><span class="sxs-lookup"><span data-stu-id="52216-204">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="52216-205">Na przykład `"-+++"` reaguje na otwór, który jest tworzony w lokacji $i $ i cząsteczek tworzonych w lokacjach $j, k $ i $l $.</span><span class="sxs-lookup"><span data-stu-id="52216-205">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="52216-206">Ponieważ wartość `particle_hole_representation` jest obiektem ilości tablicy rozrzedzonej, należy określić właściwości `unit` i `format`.</span><span class="sxs-lookup"><span data-stu-id="52216-206">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="52216-207">W tabeli 1 są wymienione akceptowalne jednostki.</span><span class="sxs-lookup"><span data-stu-id="52216-207">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="52216-208">Właściwość `format` jest wymagana i wskazuje, czy współczynniki hamiltonian są określone jako tablica o gęstej lub rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="52216-208">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="52216-209">W bieżącej wersji obsługiwane są tylko tablice rozrzedzone z interpretacją, że wszystkie nieokreślone elementy są $0 $, ale przyszłe wersje mogą dodać obsługę dodatkowych wartości właściwości `format`.</span><span class="sxs-lookup"><span data-stu-id="52216-209">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="52216-210">Sekcja stanu początkowego</span><span class="sxs-lookup"><span data-stu-id="52216-210">Initial State Section</span></span> ###

<span data-ttu-id="52216-211">Obiekt initial_state_suggestion określa początkowe Stany Quantum, które są istotne dla określonego hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="52216-211">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="52216-212">Ten obiekt musi być tablicą obiektów `state` JSON.</span><span class="sxs-lookup"><span data-stu-id="52216-212">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="52216-213">Obiekt State</span><span class="sxs-lookup"><span data-stu-id="52216-213">State object</span></span> ####

<span data-ttu-id="52216-214">Każdy stan reprezentuje pozycję zajętej orbitals.</span><span class="sxs-lookup"><span data-stu-id="52216-214">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="52216-215">Każdy obiekt stanu musi mieć Właściwość `label` zawierającą ciąg.</span><span class="sxs-lookup"><span data-stu-id="52216-215">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="52216-216">Każdy obiekt stanu musi mieć Właściwość `superposition` zawierającą tablicę Stanów bazowych i ich nieznormalizowane amplitudy.</span><span class="sxs-lookup"><span data-stu-id="52216-216">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="52216-217">Na przykład początkowy stan $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket{0} $ $ są reprezentowane naciskając</span><span class="sxs-lookup"><span data-stu-id="52216-217">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="52216-218">Obiekt zestawu podstawy</span><span class="sxs-lookup"><span data-stu-id="52216-218">Basis Set Object</span></span> ####

<span data-ttu-id="52216-219">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-219">This section is normative.</span></span>

<span data-ttu-id="52216-220">Każdy obiekt zestawu całkowitego może mieć Właściwość `basis_set`.</span><span class="sxs-lookup"><span data-stu-id="52216-220">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="52216-221">Jeśli jest obecny, wartość właściwości `basis_set` musi być obiektem z dwiema właściwościami, `type` i `name`.</span><span class="sxs-lookup"><span data-stu-id="52216-221">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="52216-222">Funkcje podstawowe identyfikowane przez wartość właściwości `basis_set` muszą być wartościami rzeczywistymi.</span><span class="sxs-lookup"><span data-stu-id="52216-222">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="52216-223">Założenie, że wszystkie funkcje podstawowe są prawdziwe w przyszłych wersjach tej specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="52216-223">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="52216-224">Tabele i listy</span><span class="sxs-lookup"><span data-stu-id="52216-224">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="52216-225">Tabela 1.</span><span class="sxs-lookup"><span data-stu-id="52216-225">Table 1.</span></span> <span data-ttu-id="52216-226">Dozwolone jednostki fizyczne</span><span class="sxs-lookup"><span data-stu-id="52216-226">Allowed Physical Units</span></span> ###

<span data-ttu-id="52216-227">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-227">This section is normative.</span></span>

<span data-ttu-id="52216-228">Dowolny ciąg określający jednostkę musi mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="52216-228">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="52216-229">Analizatory i producenci muszą traktować następujące proste ilości obiektów jako równoważne:</span><span class="sxs-lookup"><span data-stu-id="52216-229">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="52216-230">Tabela 2.</span><span class="sxs-lookup"><span data-stu-id="52216-230">Table 2.</span></span> <span data-ttu-id="52216-231">Dozwolone konwencje indeksów</span><span class="sxs-lookup"><span data-stu-id="52216-231">Allowed Index Conventions</span></span> ###

<span data-ttu-id="52216-232">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="52216-232">This section is normative.</span></span>

<span data-ttu-id="52216-233">Dowolny ciąg określający Konwencję indeksu musi mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="52216-233">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="52216-234">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="52216-234">This section is informative.</span></span>

<span data-ttu-id="52216-235">Dodatkowe konwencje indeksów można wprowadzać w przyszłych wersjach tej specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="52216-235">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="52216-236">Interpretacja Konwencji indeksów</span><span class="sxs-lookup"><span data-stu-id="52216-236">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="52216-237">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="52216-237">This section is informative.</span></span>
