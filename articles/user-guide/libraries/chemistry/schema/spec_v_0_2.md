---
title: Specyfikacja schematu Broombridge (ver 0,2)
description: Szczegółowe informacje o specyfikacjach Broombridge Quantum chemia v 0,2 dla biblioteki chemii Microsoft Quantum.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275856"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="78428-103">Specyfikacja Broombridge v 0,2</span><span class="sxs-lookup"><span data-stu-id="78428-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="78428-104">Kluczowe słowa "musi", "nie może być", "wymagane", ",", ",", "," powinny "," nie powinno być "," zalecane "," maj "i" opcjonalne "w tym dokumencie są interpretowane zgodnie z opisem w [dokumencie RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="78428-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="78428-105">Każdy pasek boczny z nagłówkami "Uwaga", "informacje" lub "ostrzeżenie" ma format.</span><span class="sxs-lookup"><span data-stu-id="78428-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="78428-106">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="78428-106">Introduction</span></span> ##

<span data-ttu-id="78428-107">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-107">This section is informative.</span></span>

<span data-ttu-id="78428-108">Dokumenty Broombridge są przeznaczone do przekazywania wystąpień problemów symulacji w ramach chemii Quantum do przetwarzania za pomocą symulacji Quantum i programowanie łańcuchy narzędzi.</span><span class="sxs-lookup"><span data-stu-id="78428-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="78428-109">Serializacja</span><span class="sxs-lookup"><span data-stu-id="78428-109">Serialization</span></span> ##

<span data-ttu-id="78428-110">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-110">This section is normative.</span></span>

<span data-ttu-id="78428-111">Dokument Broombridge musi być serializowany jako [dokument YAML 1,2](http://yaml.org/spec/) reprezentujący obiekt JSON, zgodnie z opisem w sekcji [RFC 4627](https://tools.ietf.org/html/rfc4627) sekcja 2,2.</span><span class="sxs-lookup"><span data-stu-id="78428-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="78428-112">Serializacja obiektu do YAML musi mieć właściwość `"$schema"` , której wartość jest `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` i musi być prawidłowa, zgodnie ze schematem JSON specyfikacji Draft-06 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="78428-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="78428-113">Dla pozostałej części tej specyfikacji "obiekt Broombridge" odwołuje się do obiektu JSON deserializowanego z dokumentu Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="78428-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="78428-114">O ile jawnie nie zaznaczono inaczej, obiekty nie mogą mieć dodatkowych właściwości poza tymi określonymi jawnie w tym dokumencie.</span><span class="sxs-lookup"><span data-stu-id="78428-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="78428-115">Dodatkowe definicje</span><span class="sxs-lookup"><span data-stu-id="78428-115">Additional Definitions</span></span> ##

<span data-ttu-id="78428-116">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="78428-117">Obiekty ilości</span><span class="sxs-lookup"><span data-stu-id="78428-117">Quantity Objects</span></span> ###

<span data-ttu-id="78428-118">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-118">This section is normative.</span></span>

<span data-ttu-id="78428-119">_Obiekt ilości_ jest obiektem JSON i musi mieć właściwość, `units` której wartość jest jedną z dozwolonych wartości wymienionych w tabeli 1.</span><span class="sxs-lookup"><span data-stu-id="78428-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="78428-120">Obiekt ilości jest _prostym obiektem ilości_ , jeśli zawiera on jedną właściwość `value` oprócz jej `units` właściwości.</span><span class="sxs-lookup"><span data-stu-id="78428-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="78428-121">Wartość `value` właściwości musi być liczbą.</span><span class="sxs-lookup"><span data-stu-id="78428-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="78428-122">Obiekt ilości jest _obiektem o ograniczonej_ liczbie, jeśli ma właściwości `lower` i `upper` oprócz jego `units` właściwości.</span><span class="sxs-lookup"><span data-stu-id="78428-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="78428-123">Wartości `lower` `upper` właściwości i muszą być liczbami.</span><span class="sxs-lookup"><span data-stu-id="78428-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="78428-124">Obiekt o ograniczonej ilości może mieć właściwość, `value` której wartość jest liczbą.</span><span class="sxs-lookup"><span data-stu-id="78428-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="78428-125">Obiekt ilości jest _obiektem ilości tablicy rozrzedzonej_ , jeśli ma właściwość `format` i Właściwość oprócz właściwości `values` `units` .</span><span class="sxs-lookup"><span data-stu-id="78428-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="78428-126">Wartość `format` musi być ciągiem `sparse` .</span><span class="sxs-lookup"><span data-stu-id="78428-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="78428-127">Wartość `values` właściwości musi być tablicą.</span><span class="sxs-lookup"><span data-stu-id="78428-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="78428-128">Każdy element elementu `values` musi być tablicą reprezentującą indeksy i wartość liczby tablicy rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="78428-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="78428-129">Indeksy dla każdego elementu obiektu liczby tablic rozrzedzonych muszą być unikatowe w całym obiekcie ilości tablicy rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="78428-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="78428-130">Jeśli indeks jest obecny z wartością `0` , Analizator musi traktować obiekt ilości tablicy rozrzedzonej identycznie do obiektu z ilością tablicy rozrzedzonej, w którym ten indeks nie jest obecny.</span><span class="sxs-lookup"><span data-stu-id="78428-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="78428-131">Obiekt ilości musi być</span><span class="sxs-lookup"><span data-stu-id="78428-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="78428-132">prosty obiekt ilości,</span><span class="sxs-lookup"><span data-stu-id="78428-132">a simple quantity object,</span></span>
- <span data-ttu-id="78428-133">Obiekt ograniczonej ilości lub</span><span class="sxs-lookup"><span data-stu-id="78428-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="78428-134">Obiekt ilości tablicy rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="78428-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="78428-135">Przykłady</span><span class="sxs-lookup"><span data-stu-id="78428-135">Examples</span></span> ###

<span data-ttu-id="78428-136">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-136">This section is informative.</span></span>

<span data-ttu-id="78428-137">Prosta ilość reprezentująca $1.9844146837 \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="78428-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="78428-138">Ograniczona ilość reprezentująca jednolitą dystrybucję dla interwału $ [-7,-6] \, \mathrm{ha} $:</span><span class="sxs-lookup"><span data-stu-id="78428-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="78428-139">Poniżej znajduje się liczba tablic rozrzedzonych z elementem `[1, 2]` równym `hello` i elementem `[3, 4]` równym `world` :</span><span class="sxs-lookup"><span data-stu-id="78428-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="78428-140">Sekcja formatu</span><span class="sxs-lookup"><span data-stu-id="78428-140">Format Section</span></span> ##

<span data-ttu-id="78428-141">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-141">This section is normative.</span></span>

<span data-ttu-id="78428-142">Obiekt Broombridge musi mieć właściwość, `format` której wartość jest obiektem JSON z jedną właściwością o nazwie `version` .</span><span class="sxs-lookup"><span data-stu-id="78428-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="78428-143">`version`Właściwość musi mieć wartość `"0.2"` .</span><span class="sxs-lookup"><span data-stu-id="78428-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="78428-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="78428-144">Example</span></span> ###

<span data-ttu-id="78428-145">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="78428-146">Sekcja opis problemu</span><span class="sxs-lookup"><span data-stu-id="78428-146">Problem Description Section</span></span> ##

<span data-ttu-id="78428-147">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-147">This section is normative.</span></span>

<span data-ttu-id="78428-148">Obiekt Broombridge musi mieć właściwość, `problem_description` której wartość jest tablicą JSON.</span><span class="sxs-lookup"><span data-stu-id="78428-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="78428-149">Każdy element w wartości `problem_description` właściwości musi być obiektem JSON opisującym jeden zestaw całek, zgodnie z opisem w pozostałej części tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="78428-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="78428-150">W pozostałej części tej sekcji termin "obiekt opisu problemu" będzie odnosić się do elementu w wartości `problem_description` właściwości obiektu Broombridge.</span><span class="sxs-lookup"><span data-stu-id="78428-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="78428-151">Każdy obiekt opisu problemu musi mieć właściwość, `metadata` której wartość jest obiektem JSON.</span><span class="sxs-lookup"><span data-stu-id="78428-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="78428-152">Wartość `metadata` może być pustym obiektem JSON (czyli `{}` ) lub może zawierać dodatkowe właściwości zdefiniowane przez implementację.</span><span class="sxs-lookup"><span data-stu-id="78428-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="78428-153">Sekcja hamiltonian</span><span class="sxs-lookup"><span data-stu-id="78428-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="78428-154">Omówienie</span><span class="sxs-lookup"><span data-stu-id="78428-154">Overview</span></span> ####

<span data-ttu-id="78428-155">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-155">This section is informative.</span></span>

<span data-ttu-id="78428-156">`hamiltonian`Właściwość każdego obiektu opis problemu opisuje hamiltonian dla konkretnego problemu chemii Quantum przez wymienienie jednego z tych warunków i dwóch treści jako rozrzedzonych tablic liczb rzeczywistych.</span><span class="sxs-lookup"><span data-stu-id="78428-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="78428-157">Operatory hamiltonian opisane przez każdy obiekt opisu problemu przyjmują postać</span><span class="sxs-lookup"><span data-stu-id="78428-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="78428-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} godz. \_ \{ \} ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {IJKL} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} \_ \_</span><span class="sxs-lookup"><span data-stu-id="78428-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="78428-159">tutaj $h _ {IJKL} = (IJ | KL) $ w Konwencji Mulliken.</span><span class="sxs-lookup"><span data-stu-id="78428-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="78428-160">W przypadku przejrzystości okres jednorazowy to</span><span class="sxs-lookup"><span data-stu-id="78428-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="78428-161">$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ a} {| x-x \_ A |}  \right) \psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="78428-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="78428-162">i dwuletni okres jest</span><span class="sxs-lookup"><span data-stu-id="78428-162">and the two-electron term is</span></span>

<span data-ttu-id="78428-163">$ $ h \_ \{ IJKL \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="78428-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="78428-164">Jak wspomniano w opisie [ `basis_set` Właściwości](#basis-set-object) każdego elementu `integral_sets` właściwości, wyraźnie zakładamy, że używane funkcje podstawowe są wartościami rzeczywistymi.</span><span class="sxs-lookup"><span data-stu-id="78428-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="78428-165">Pozwala to na użycie następujących symmetries między postanowieniami w celu skompresowania reprezentacji hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="78428-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="78428-166">$ $ h_ {IJKL} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = H_ {klji} = h_ {lkij} = h_ {LKJI}.</span><span class="sxs-lookup"><span data-stu-id="78428-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="78428-167">Zawartość</span><span class="sxs-lookup"><span data-stu-id="78428-167">Contents</span></span> ####

<span data-ttu-id="78428-168">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-168">This section is normative.</span></span>

<span data-ttu-id="78428-169">Każdy obiekt opisu problemu musi mieć właściwość, `hamiltonian` której wartość jest obiektem JSON.</span><span class="sxs-lookup"><span data-stu-id="78428-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="78428-170">Wartość `hamiltonian` właściwości jest znana jako obiekt hamiltonian i musi mieć właściwości `one_electron_integrals` i `two_electron_integrals` zgodnie z opisem w pozostałej części tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="78428-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="78428-171">Każdy obiekt opisu problemu musi mieć właściwość, `coulomb_repulsion` której wartość jest obiektem o prostej liczbie.</span><span class="sxs-lookup"><span data-stu-id="78428-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="78428-172">Każdy obiekt opisu problemu musi mieć właściwość, `energy_offet` której wartość jest obiektem o prostej liczbie.</span><span class="sxs-lookup"><span data-stu-id="78428-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="78428-173">KORYGUJĄC Wartości `coulomb_repulsion` i `energy_offet` dodane razem przechwytują okres tożsamości hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="78428-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="78428-174">Obiekt całkowity w jednym Elektronzie</span><span class="sxs-lookup"><span data-stu-id="78428-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="78428-175">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-175">This section is normative.</span></span>

<span data-ttu-id="78428-176">`one_electron_integrals`Właściwość obiektu HAMILTONIAN musi być liczbą tablicy rozrzedzonej, której indeksy są dwoma liczbami całkowitymi i których wartości są liczbami.</span><span class="sxs-lookup"><span data-stu-id="78428-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="78428-177">Każdy termin musi mieć indeksy, `[i, j]` gdzie `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="78428-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="78428-178">KORYGUJĄC Odzwierciedla to symetrię, która $h _ {IJ} = h_ {ji} $, która jest konsekwencją faktu, że hamiltonian to hermitian.</span><span class="sxs-lookup"><span data-stu-id="78428-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="78428-179">Przykład</span><span class="sxs-lookup"><span data-stu-id="78428-179">Example</span></span> ######

<span data-ttu-id="78428-180">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-180">This section is informative.</span></span>

<span data-ttu-id="78428-181">Następująca liczba macierzy rozrzedzonych reprezentuje hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="78428-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="78428-182">Broombridge używa indeksowania opartego na 1.</span><span class="sxs-lookup"><span data-stu-id="78428-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="78428-183">Dwukolorowy obiekt całkowity</span><span class="sxs-lookup"><span data-stu-id="78428-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="78428-184">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-184">This section is normative.</span></span>

<span data-ttu-id="78428-185">`two_electron_integrals`Właściwość obiektu HAMILTONIAN musi być ilością tablicy rozrzedzonej z jedną dodatkową właściwością o nazwie `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="78428-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="78428-186">Każdy element wartości `two_electron_integrals` musi mieć cztery indeksy.</span><span class="sxs-lookup"><span data-stu-id="78428-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="78428-187">Każda `two_electron_integrals` Właściwość musi mieć `index_convention` Właściwość.</span><span class="sxs-lookup"><span data-stu-id="78428-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="78428-188">Wartość `index_convention` właściwości musi być jedną z dozwolonych wartości wymienionych w tabeli 1.</span><span class="sxs-lookup"><span data-stu-id="78428-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="78428-189">Jeśli wartość `index_convention` jest `mulliken` , a następnie dla każdego elementu `two_electron_integrals` ilości tablicy rozrzedzonej, parser ładujący dokument Broombridge musi utworzyć wystąpienie Hamiltonianego terminu równego operatorowi dwuskładnikowego $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, gdzie $i $, $j $, $k $, i $l $ muszą być liczbami całkowitymi o wartości co najmniej 1, a gdzie $h _ {i, j, k, l} $ jest elementem `[i, j, k, l, h(i, j, k, l)]` ilości tablicy rozrzedzonej.</span><span class="sxs-lookup"><span data-stu-id="78428-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="78428-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="78428-190">Symmetries</span></span> ######

<span data-ttu-id="78428-191">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-191">This section is normative.</span></span>

<span data-ttu-id="78428-192">Jeśli `index_convention` Właściwość `two_electron_integrals` obiektu jest równa `mulliken` , wtedy, gdy element z indeksami `[i, j, k, l]` jest obecny, następujące indeksy nie mogą być obecne, chyba że są równe `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="78428-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="78428-193">Ponieważ `index_convention` Właściwość jest obiektem z ilością rozrzedzoną, nie można powtarzać indeksów w różnych elementach.</span><span class="sxs-lookup"><span data-stu-id="78428-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="78428-194">W szczególności, jeśli element z indeksami `[i, j, k, l]` jest obecny, żaden inny element nie może mieć takich indeksów.</span><span class="sxs-lookup"><span data-stu-id="78428-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="78428-195">Przykład</span><span class="sxs-lookup"><span data-stu-id="78428-195">Example</span></span> #######

<span data-ttu-id="78428-196">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-196">This section is informative.</span></span>

<span data-ttu-id="78428-197">Poniższy obiekt Określa hamiltonian</span><span class="sxs-lookup"><span data-stu-id="78428-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="78428-198">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} {1, \_ \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} \_ {3, \rho} { \_ 2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="78428-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

### <a name="initial-state-section"></a><span data-ttu-id="78428-199">Sekcja stanu początkowego</span><span class="sxs-lookup"><span data-stu-id="78428-199">Initial State Section</span></span> ###

<span data-ttu-id="78428-200">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-200">This section is normative.</span></span>

<span data-ttu-id="78428-201">`initial_state_suggestion`Obiekt, którego wartością jest tablica JSON, określa początkowe Stany Quantum, które są istotne dla określonego hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="78428-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="78428-202">Każdy element w wartości `initial_state_suggestion` właściwości musi być obiektem JSON opisującym jeden stan Quantum, zgodnie z opisem w pozostałej części tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="78428-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="78428-203">W pozostałej części tej sekcji termin "obiekt stanu" będzie odwoływać się do elementu w wartości `initial_state_suggestion` właściwości obiektu Broombridge.</span><span class="sxs-lookup"><span data-stu-id="78428-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="78428-204">Obiekt State</span><span class="sxs-lookup"><span data-stu-id="78428-204">State object</span></span> ####

<span data-ttu-id="78428-205">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-205">This section is normative.</span></span>

<span data-ttu-id="78428-206">Każdy obiekt stanu musi mieć `label` Właściwość zawierającą ciąg.</span><span class="sxs-lookup"><span data-stu-id="78428-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="78428-207">Każdy obiekt stanu musi mieć `method` Właściwość.</span><span class="sxs-lookup"><span data-stu-id="78428-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="78428-208">Wartość `method` właściwości musi być jedną z dozwolonych wartości wymienionych w tabeli 3.</span><span class="sxs-lookup"><span data-stu-id="78428-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="78428-209">Każdy obiekt stanu może mieć właściwość, `energy` której wartość musi być obiektem o prostej liczbie.</span><span class="sxs-lookup"><span data-stu-id="78428-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="78428-210">Jeśli wartość `method` właściwości jest `sparse_multi_configurational` , obiekt stanu musi mieć `superposition` Właściwość zawierającą tablicę Stanów bazowych i ich nieznormalizowane amplitudy.</span><span class="sxs-lookup"><span data-stu-id="78428-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="78428-211">Na przykład początkowy stan $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} , $ $ gdzie $ \ket{E} $ ma energię $0,987 \textrm{ha} $, są reprezentowane przez</span><span class="sxs-lookup"><span data-stu-id="78428-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="78428-212">Jeśli wartość `method` właściwości jest `unitary_coupled_cluster` , obiekt stanu musi mieć `cluster_operator` Właściwość, której wartość jest obiektem JSON.</span><span class="sxs-lookup"><span data-stu-id="78428-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="78428-213">Obiekt JSON musi mieć właściwość, `reference_state` której wartość jest stanem bazowym.</span><span class="sxs-lookup"><span data-stu-id="78428-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="78428-214">Obiekt JSON może mieć właściwość, `one_body_amplitudes` której wartość jest tablicą operatorów klastrów jednociałowych i ich amplitud.</span><span class="sxs-lookup"><span data-stu-id="78428-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="78428-215">Obiekt JSON może mieć właściwość, `two_body_amplitudes` której wartość jest tablicą dwóch operatorów klastra i ich amplitud.</span><span class="sxs-lookup"><span data-stu-id="78428-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="78428-216">zawierający tablicę Stanów bazowych i ich nieznormalizowane amplitudy.</span><span class="sxs-lookup"><span data-stu-id="78428-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="78428-217">Na przykład stan $ $ \ket{\Text{Reference}} = (^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="78428-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="78428-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="78428-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="78428-219">$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \downarrow}a \_ {3, \uparrow}a \_ {2, \downarrow} $ $ jest reprezentowane przez</span><span class="sxs-lookup"><span data-stu-id="78428-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="78428-220">Obiekt zestawu podstawy</span><span class="sxs-lookup"><span data-stu-id="78428-220">Basis Set Object</span></span> ####

<span data-ttu-id="78428-221">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-221">This section is normative.</span></span>

<span data-ttu-id="78428-222">Każdy obiekt opisu problemu może mieć `basis_set` Właściwość.</span><span class="sxs-lookup"><span data-stu-id="78428-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="78428-223">Jeśli jest obecny, wartość `basis_set` właściwości musi być obiektem z dwiema właściwościami `type` i `name` .</span><span class="sxs-lookup"><span data-stu-id="78428-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="78428-224">Funkcje podstawowe identyfikowane przez wartość `basis_set` właściwości muszą być wartościami rzeczywistymi.</span><span class="sxs-lookup"><span data-stu-id="78428-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="78428-225">Założenie, że wszystkie funkcje podstawowe są prawdziwe w przyszłych wersjach tej specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="78428-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="78428-226">Tabele i listy</span><span class="sxs-lookup"><span data-stu-id="78428-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="78428-227">Tabela 1.</span><span class="sxs-lookup"><span data-stu-id="78428-227">Table 1.</span></span> <span data-ttu-id="78428-228">Dozwolone jednostki fizyczne</span><span class="sxs-lookup"><span data-stu-id="78428-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="78428-229">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-229">This section is normative.</span></span>

<span data-ttu-id="78428-230">Dowolny ciąg określający jednostkę musi mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="78428-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="78428-231">Analizatory i producenci muszą traktować następujące proste ilości obiektów jako równoważne:</span><span class="sxs-lookup"><span data-stu-id="78428-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="78428-232">Tabela 2.</span><span class="sxs-lookup"><span data-stu-id="78428-232">Table 2.</span></span> <span data-ttu-id="78428-233">Dozwolone konwencje indeksów</span><span class="sxs-lookup"><span data-stu-id="78428-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="78428-234">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-234">This section is normative.</span></span>

<span data-ttu-id="78428-235">Dowolny ciąg określający Konwencję indeksu musi mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="78428-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="78428-236">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-236">This section is informative.</span></span>

<span data-ttu-id="78428-237">Dodatkowe konwencje indeksów można wprowadzać w przyszłych wersjach tej specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="78428-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="78428-238">Interpretacja Konwencji indeksów</span><span class="sxs-lookup"><span data-stu-id="78428-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="78428-239">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="78428-240">Tabela 3.</span><span class="sxs-lookup"><span data-stu-id="78428-240">Table 3.</span></span> <span data-ttu-id="78428-241">Dozwolone metody stanu</span><span class="sxs-lookup"><span data-stu-id="78428-241">Allowed State methods</span></span> ###

<span data-ttu-id="78428-242">Ta sekcja jest normatywna.</span><span class="sxs-lookup"><span data-stu-id="78428-242">This section is normative.</span></span>

<span data-ttu-id="78428-243">Dowolny ciąg określający metodę State musi mieć jedną z następujących wartości:</span><span class="sxs-lookup"><span data-stu-id="78428-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="78428-244">Ta sekcja jest informacyjna.</span><span class="sxs-lookup"><span data-stu-id="78428-244">This section is informative.</span></span>

<span data-ttu-id="78428-245">Dodatkowe metody stanu można wprowadzać w przyszłych wersjach tej specyfikacji.</span><span class="sxs-lookup"><span data-stu-id="78428-245">Additional state methods may be introduced in future versions of this specification.</span></span>
