---
title: Specyfikacja schematu Broombridge (ver 0,1)
description: Szczegóły specyfikacji dla schematu chemii Broombridge Quantum v dla biblioteki chemii Microsoft Quantum.
author: cgranade
ms.author: chgranad
ms.date: 10/17/2018
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
no-loc:
- Q#
- $$v
ms.openlocfilehash: 0a306f59a823e76ba0518d023a41f1f9d5670e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858193"
---
# <a name="broombridge-specification-v01"></a>Specyfikacja Broombridge v 0,1 #

Kluczowe słowa "musi", "nie może być", "wymagane", ",", ",", "," powinny "," nie powinno być "," zalecane "," maj "i" opcjonalne "w tym dokumencie są interpretowane zgodnie z opisem w [dokumencie RFC 2119](https://tools.ietf.org/html/rfc2119).

Każdy pasek boczny z nagłówkami "Uwaga", "informacje" lub "ostrzeżenie" ma format.

## <a name="introduction"></a>Wprowadzenie ##

Ta sekcja jest informacyjna.

Dokumenty Broombridge są przeznaczone do przekazywania wystąpień problemów symulacji w ramach chemii Quantum do przetwarzania za pomocą symulacji Quantum i programowanie łańcuchy narzędzi.

## <a name="serialization"></a>Serializacja ##

Ta sekcja jest normatywna.

Dokument Broombridge musi być serializowany jako [dokument YAML 1,2](http://yaml.org/spec/) reprezentujący obiekt JSON, zgodnie z opisem w sekcji [RFC 4627](https://tools.ietf.org/html/rfc4627) sekcja 2,2.
Serializacja obiektu do YAML musi mieć właściwość `"$schema"` , której wartość jest `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` i musi być prawidłowa, zgodnie ze schematem JSON specyfikacji Draft-06 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Dla pozostałej części tej specyfikacji "obiekt Broombridge" odwołuje się do obiektu JSON deserializowanego z dokumentu Broombridge YAML.

O ile jawnie nie zaznaczono inaczej, obiekty nie mogą mieć dodatkowych właściwości poza tymi określonymi jawnie w tym dokumencie.

## <a name="additional-definitions"></a>Dodatkowe definicje ##

Ta sekcja jest normatywna.

### <a name="quantity-objects"></a>Obiekty ilości ###

Ta sekcja jest normatywna.

_Obiekt ilości_ jest obiektem JSON i musi mieć właściwość, `units` której wartość jest jedną z dozwolonych wartości wymienionych w tabeli 1.

Obiekt ilości jest _prostym obiektem ilości_ , jeśli zawiera on jedną właściwość `value` oprócz jej `units` właściwości.
Wartość `value` właściwości musi być liczbą.

Obiekt ilości jest _obiektem o ograniczonej_ liczbie, jeśli ma właściwości `lower` i `upper` oprócz jego `units` właściwości.
Wartości `lower` `upper` właściwości i muszą być liczbami.
Obiekt o ograniczonej ilości może mieć właściwość, `value` której wartość jest liczbą.

Obiekt ilości jest _obiektem ilości tablicy rozrzedzonej_ , jeśli ma właściwość `format` i Właściwość oprócz właściwości `values` `units` .
Wartość `format` musi być ciągiem `sparse` .
Wartość `values` właściwości musi być tablicą.
Każdy element elementu `values` musi być tablicą reprezentującą indeksy i wartość liczby tablicy rozrzedzonej.

Indeksy dla każdego elementu obiektu liczby tablic rozrzedzonych muszą być unikatowe w całym obiekcie ilości tablicy rozrzedzonej.
Jeśli indeks jest obecny z wartością `0` , Analizator musi traktować obiekt ilości tablicy rozrzedzonej identycznie do obiektu z ilością tablicy rozrzedzonej, w którym ten indeks nie jest obecny.


Obiekt ilości musi być

- prosty obiekt ilości,
- Obiekt ograniczonej ilości lub
- Obiekt ilości tablicy rozrzedzonej.


### <a name="examples"></a>Przykłady ###

Ta sekcja jest informacyjna.

Prosta ilość reprezentująca $1.9844146837 \, \mathrm{ha} $:

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Ograniczona ilość reprezentująca jednolitą dystrybucję dla interwału $ [-7,-6] \, \mathrm{ha} $:

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Poniżej znajduje się liczba tablic rozrzedzonych z elementem `[1, 2]` równym `hello` i elementem `[3, 4]` równym `world` :

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Sekcja formatu ##

Ta sekcja jest normatywna.

Obiekt Broombridge musi mieć właściwość, `format` której wartość jest obiektem JSON z jedną właściwością o nazwie `version` .
`version`Właściwość musi mieć wartość `"0.1"` .

### <a name="example"></a>Przykład ###

Ta sekcja jest informacyjna.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Sekcja zestawów całkowitych ##

Ta sekcja jest normatywna.

Obiekt Broombridge musi mieć właściwość, `integral_sets` której wartość jest tablicą JSON.
Każdy element w wartości `integral_sets` właściwości musi być obiektem JSON opisującym jeden zestaw całek, zgodnie z opisem w pozostałej części tej sekcji.
W pozostałej części tej sekcji termin "obiekt zestawu całkowitego" odwołuje się do elementu w wartości `integral_sets` właściwości obiektu Broombridge.

Każdy obiekt zestawu całkowitego musi mieć właściwość, `metadata` której wartość jest obiektem JSON.
Wartość `metadata` może być pustym obiektem JSON (czyli `{}` ) lub może zawierać dodatkowe właściwości zdefiniowane przez implementację.

### <a name="hamiltonian-section"></a>Sekcja hamiltonian ###

#### <a name="overview"></a>Omówienie ####

Ta sekcja jest informacyjna.

`hamiltonian`Właściwość każdego obiektu zestawu całkowitego opisuje hamiltonian dla konkretnego problemu chemii Quantum poprzez wymienienie jednego z tych warunków i dwóch treści jako rozrzedzonych tablic liczb rzeczywistych.
Operatory hamiltonian opisane przez każdy obiekt zestawu całkowitego przyjmują formularz

$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} godz. \_ \{ \} ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {IJKL} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} \_ \_

tutaj $h _ {IJKL} = (IJ | KL) $ w Konwencji Mulliken.

W przypadku przejrzystości okres jednorazowy to

$ $ h_ {IJ} = \int {\mathrm d} x \psi ^ * \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ a} {| x-x \_ A |}  \right) \psi \_ j (x), $ $

i dwuletni okres jest

$ $ h \_ \{ IJKL \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2).
$$

Jak wspomniano w opisie [ `basis_set` Właściwości](#basis-set-object) każdego elementu `integral_sets` właściwości, wyraźnie zakładamy, że używane funkcje podstawowe są wartościami rzeczywistymi.
Pozwala to na użycie następujących symmetries między postanowieniami w celu skompresowania reprezentacji hamiltonian.

$ $ h_ {IJKL} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = H_ {klji} = h_ {lkij} = h_ {LKJI}.
$$


#### <a name="contents"></a>Zawartość ####

Ta sekcja jest normatywna.

Każdy zestaw całkowity musi mieć właściwość, `hamiltonian` której wartość jest obiektem JSON.
Wartość `hamiltonian` właściwości jest znana jako obiekt hamiltonian i musi mieć właściwości `one_electron_integrals` i `two_electron_integrals` zgodnie z opisem w pozostałej części tej sekcji.
Obiekt hamiltonian może również mieć właściwość `particle_hole_representation` .
Jeśli jest obecny, wartość `particle_hole_representation` musi być zgodna z formatem opisanym w pozostałej części tej sekcji.

##### <a name="one-electron-integrals-object"></a>Obiekt całkowity One-Electron #####

Ta sekcja jest normatywna.

`one_electron_integrals`Właściwość obiektu HAMILTONIAN musi być liczbą tablicy rozrzedzonej, której indeksy są dwoma liczbami całkowitymi i których wartości są liczbami.
Każdy termin musi mieć indeksy, `[i, j]` gdzie `i >= j` .

> KORYGUJĄC Odzwierciedla to symetrię, która $h _ {IJ} = h_ {ji} $, która jest konsekwencją faktu, że hamiltonian to hermitian.


###### <a name="example"></a>Przykład ######

Ta sekcja jest informacyjna.

Następująca liczba macierzy rozrzedzonych reprezentuje hamiltonian $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {2, \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.
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
> Broombridge używa indeksowania opartego na 1.


##### <a name="two-electron-integrals-object"></a>Obiekt całkowity Two-Electron #####

Ta sekcja jest normatywna.

`two_electron_integrals`Właściwość obiektu HAMILTONIAN musi być ilością tablicy rozrzedzonej z jedną dodatkową właściwością o nazwie `index_convention` .
Każdy element wartości `two_electron_integrals` musi mieć cztery indeksy.

Każda `two_electron_integrals` Właściwość musi mieć `index_convention` Właściwość.
Wartość `index_convention` właściwości musi być jedną z dozwolonych wartości wymienionych w tabeli 1.
Jeśli wartość `index_convention` jest `mulliken` , a następnie dla każdego elementu w `two_electron_integrals` tablicy rozrzedzonej, parser ładujący dokument Broombridge musi utworzyć wystąpienie hamiltonian terminu równego operatorowi dwuskładnikowego, $h _ {i, j, k, l} a ^ \ dagger_i ^ \ dagger_j a_k a_l $, gdzie $i $, $j $, $k $, i $l $ muszą być liczbami całkowitymi w łącznym zakresie od 1 do liczby Electrons określonych przez `n_electrons` właściwość obiektu zestawu całkowitego, a gdzie $h _ {i, j, k, l} $ jest elementem `[i, j, k, l, h(i, j, k, l)]` ilości tablicy rozrzedzonej.

###### <a name="symmetries"></a>Symmetries ######

Ta sekcja jest normatywna.

Jeśli `index_convention` Właściwość `two_electron_integrals` obiektu jest równa `mulliken` , wtedy, gdy element z indeksami `[i, j, k, l]` jest obecny, następujące indeksy nie mogą być obecne, chyba że są równe `[i, j, k, l]` :

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Ponieważ `index_convention` Właściwość jest obiektem z ilością rozrzedzoną, nie można powtarzać indeksów w różnych elementach.
> W szczególności, jeśli element z indeksami `[i, j, k, l]` jest obecny, żaden inny element nie może mieć takich indeksów.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Przykład #######

Ta sekcja jest informacyjna.

Poniższy obiekt Określa hamiltonian

$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} {1, \_ \rho} a \_ {2, \rho} a \_ {3, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} \_ {3, \rho} { \_ 2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.
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

##### <a name="particlehole-representation-object"></a>Obiekt reprezentacji cząsteczek #####

Ta sekcja jest normatywna.

Obiekt reprezentacji cząsteczek jest określany, że całkowite składowane są zdefiniowane w odniesieniu do reprezentacji w postaci cząsteczek, przez co operatory tworzenia i Annihilation opisują excitations poza używanym stanem odwołania, takim jak stan Hartree-Fock.
Obiekt jest opcjonalny.
Jeśli obiekt nie jest określony, hamiltonian ma być interpretowany jako nieokreślony w reprezentacji z dziurą cząstkową.
Jeśli jest obecny, wartość `particle_hole_representation` musi być obiektem ilości tablicy rozrzedzonej, którego indeksy są czterema liczbami całkowitymi, a których wartości to liczba i ciąg.
Część ciągu wartości każdego elementu musi zawierać tylko znaki `'+'` i `'-'` określać, czy dany czynnik w danym okresie jest operatorem tworzenia lub Annihilation w reprezentacji cząstek.  Na przykład `"-+++"` reaguje na otwór, który jest tworzony w lokacji $i $ i cząsteczek tworzonych w lokacjach $j, k $ i $l $.

> [!NOTE]
> Ponieważ wartość `particle_hole_representation` jest obiektem ilości tablicy rozrzedzonej, `unit` `format` należy określić właściwości i.
> W tabeli 1 są wymienione akceptowalne jednostki.
> `format`Właściwość jest wymagana i wskazuje, czy współczynniki hamiltonian są określone jako tablica o gęstej lub rozrzedzonej.
> W bieżącej wersji obsługiwane są tylko tablice rozrzedzone z interpretacją, że wszystkie nieokreślone elementy są $0 $, ale przyszłe wersje mogą dodać obsługę dodatkowych wartości `format` właściwości.

### <a name="initial-state-section"></a>Sekcja stanu początkowego ###

Obiekt initial_state_suggestion określa początkowe Stany Quantum, które są istotne dla określonego hamiltonian. Ten obiekt musi być tablicą obiektów JSON `state` .

#### <a name="state-object"></a>Obiekt State ####

Każdy stan reprezentuje pozycję zajętej orbitals. Każdy obiekt stanu musi mieć `label` Właściwość zawierającą ciąg. Każdy obiekt stanu musi mieć `superposition` Właściwość zawierającą tablicę Stanów bazowych i ich nieznormalizowane amplitudy.

Na przykład początkowy stan $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} $ $ są reprezentowane przez
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

#### <a name="basis-set-object"></a>Obiekt zestawu podstawy ####

Ta sekcja jest normatywna.

Każdy obiekt zestawu całkowitego może mieć `basis_set` Właściwość.
Jeśli jest obecny, wartość `basis_set` właściwości musi być obiektem z dwiema właściwościami `type` i `name` .

Funkcje podstawowe identyfikowane przez wartość `basis_set` właściwości muszą być wartościami rzeczywistymi.

> [!NOTE]
> Założenie, że wszystkie funkcje podstawowe są prawdziwe w przyszłych wersjach tej specyfikacji.

## <a name="tables-and-lists"></a>Tabele i listy ##

### <a name="table-1-allowed-physical-units"></a>Tabela 1. Dozwolone jednostki fizyczne ###

Ta sekcja jest normatywna.

Dowolny ciąg określający jednostkę musi mieć jedną z następujących wartości:

- `hartree`
- `ev`

Analizatory i producenci muszą traktować następujące proste ilości obiektów jako równoważne:

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tabela 2. Dozwolone konwencje indeksów ###

Ta sekcja jest normatywna.

Dowolny ciąg określający Konwencję indeksu musi mieć jedną z następujących wartości:

- `mulliken`

Ta sekcja jest informacyjna.

Dodatkowe konwencje indeksów można wprowadzać w przyszłych wersjach tej specyfikacji.

#### <a name="interpretation-of-index-conventions"></a>Interpretacja Konwencji indeksów ####

Ta sekcja jest informacyjna.
