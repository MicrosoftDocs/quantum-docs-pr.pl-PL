---
title: Specyfikacja schematu Broombridge (ver 0,2)
description: Szczegółowe informacje o specyfikacjach Broombridge Quantum chemia v 0,2 dla biblioteki chemii Microsoft Quantum.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 851d10c0137deecf8e861aad30b5e08a9ae61754
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833773"
---
# <a name="broombridge-specification-v02"></a>Specyfikacja Broombridge v 0,2 #

Kluczowe słowa "musi", "nie może być", "wymagane", ",", ",", "," powinny "," nie powinno być "," zalecane "," maj "i" opcjonalne "w tym dokumencie są interpretowane zgodnie z opisem w [dokumencie RFC 2119](https://tools.ietf.org/html/rfc2119).

Każdy pasek boczny z nagłówkami "Uwaga", "informacje" lub "ostrzeżenie" ma format.

## <a name="introduction"></a>Wprowadzenie ##

Ta sekcja jest informacyjna.

Dokumenty Broombridge są przeznaczone do przekazywania wystąpień problemów symulacji w ramach chemii Quantum do przetwarzania za pomocą symulacji Quantum i programowanie łańcuchy narzędzi.

## <a name="serialization"></a>Serializacja ##

Ta sekcja jest normatywna.

Dokument Broombridge musi być serializowany jako [dokument YAML 1,2](http://yaml.org/spec/) reprezentujący obiekt JSON, zgodnie z opisem w sekcji [RFC 4627](https://tools.ietf.org/html/rfc4627) sekcja 2,2.
Serializacja obiektu do YAML musi mieć właściwość `"$schema"` , której wartość jest `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` i musi być prawidłowa, zgodnie ze schematem JSON specyfikacji Draft-06 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

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
`version`Właściwość musi mieć wartość `"0.2"` .

### <a name="example"></a>Przykład ###

Ta sekcja jest informacyjna.

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>Sekcja opis problemu ##

Ta sekcja jest normatywna.

Obiekt Broombridge musi mieć właściwość, `problem_description` której wartość jest tablicą JSON.
Każdy element w wartości `problem_description` właściwości musi być obiektem JSON opisującym jeden zestaw całek, zgodnie z opisem w pozostałej części tej sekcji.
W pozostałej części tej sekcji termin "obiekt opisu problemu" będzie odnosić się do elementu w wartości `problem_description` właściwości obiektu Broombridge.

Każdy obiekt opisu problemu musi mieć właściwość, `metadata` której wartość jest obiektem JSON.
Wartość `metadata` może być pustym obiektem JSON (czyli `{}` ) lub może zawierać dodatkowe właściwości zdefiniowane przez implementację.

### <a name="hamiltonian-section"></a>Sekcja hamiltonian ###

#### <a name="overview"></a>Omówienie ####

Ta sekcja jest informacyjna.

`hamiltonian`Właściwość każdego obiektu opis problemu opisuje hamiltonian dla konkretnego problemu chemii Quantum przez wymienienie jednego z tych warunków i dwóch treści jako rozrzedzonych tablic liczb rzeczywistych.
Operatory hamiltonian opisane przez każdy obiekt opisu problemu przyjmują postać

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

Każdy obiekt opisu problemu musi mieć właściwość, `hamiltonian` której wartość jest obiektem JSON.
Wartość `hamiltonian` właściwości jest znana jako obiekt hamiltonian i musi mieć właściwości `one_electron_integrals` i `two_electron_integrals` zgodnie z opisem w pozostałej części tej sekcji.

Każdy obiekt opisu problemu musi mieć właściwość, `coulomb_repulsion` której wartość jest obiektem o prostej liczbie.
Każdy obiekt opisu problemu musi mieć właściwość, `energy_offet` której wartość jest obiektem o prostej liczbie.
> KORYGUJĄC Wartości `coulomb_repulsion` i `energy_offet` dodane razem przechwytują okres tożsamości hamiltonian.

##### <a name="one-electron-integrals-object"></a>Obiekt całkowity w jednym Elektronzie #####

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


##### <a name="two-electron-integrals-object"></a>Dwukolorowy obiekt całkowity #####

Ta sekcja jest normatywna.

`two_electron_integrals`Właściwość obiektu HAMILTONIAN musi być ilością tablicy rozrzedzonej z jedną dodatkową właściwością o nazwie `index_convention` .
Każdy element wartości `two_electron_integrals` musi mieć cztery indeksy.

Każda `two_electron_integrals` Właściwość musi mieć `index_convention` Właściwość.
Wartość `index_convention` właściwości musi być jedną z dozwolonych wartości wymienionych w tabeli 1.
Jeśli wartość `index_convention` jest `mulliken` , a następnie dla każdego elementu `two_electron_integrals` ilości tablicy rozrzedzonej, parser ładujący dokument Broombridge musi utworzyć wystąpienie Hamiltonianego terminu równego operatorowi dwuskładnikowego $h _ {i, j, k, l} a ^ \ dagger_i a ^ \ dagger_j a_k a_l $, gdzie $i $, $j $, $k $, i $l $ muszą być liczbami całkowitymi o wartości co najmniej 1, a gdzie $h _ {i, j, k, l} $ jest elementem `[i, j, k, l, h(i, j, k, l)]` ilości tablicy rozrzedzonej.

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

### <a name="initial-state-section"></a>Sekcja stanu początkowego ###

Ta sekcja jest normatywna.

`initial_state_suggestion`Obiekt, którego wartością jest tablica JSON, określa początkowe Stany Quantum, które są istotne dla określonego hamiltonian. Każdy element w wartości `initial_state_suggestion` właściwości musi być obiektem JSON opisującym jeden stan Quantum, zgodnie z opisem w pozostałej części tej sekcji.
W pozostałej części tej sekcji termin "obiekt stanu" będzie odwoływać się do elementu w wartości `initial_state_suggestion` właściwości obiektu Broombridge.

#### <a name="state-object"></a>Obiekt State ####

Ta sekcja jest normatywna.

Każdy obiekt stanu musi mieć `label` Właściwość zawierającą ciąg. Każdy obiekt stanu musi mieć `method` Właściwość. Wartość `method` właściwości musi być jedną z dozwolonych wartości wymienionych w tabeli 3.
Każdy obiekt stanu może mieć właściwość, `energy` której wartość musi być obiektem o prostej liczbie.

Jeśli wartość `method` właściwości jest `sparse_multi_configurational` , obiekt stanu musi mieć `superposition` Właściwość zawierającą tablicę Stanów bazowych i ich nieznormalizowane amplitudy.

Na przykład początkowy stan $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0,1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} , $ $ gdzie $ \ket{E} $ ma energię $0,987 \textrm{ha} $, są reprezentowane przez
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

Jeśli wartość `method` właściwości jest `unitary_coupled_cluster` , obiekt stanu musi mieć `cluster_operator` Właściwość, której wartość jest obiektem JSON.
Obiekt JSON musi mieć właściwość, `reference_state` której wartość jest stanem bazowym.
Obiekt JSON może mieć właściwość, `one_body_amplitudes` której wartość jest tablicą operatorów klastrów jednociałowych i ich amplitud.
Obiekt JSON może mieć właściwość, `two_body_amplitudes` której wartość jest tablicą dwóch operatorów klastra i ich amplitud.
zawierający tablicę Stanów bazowych i ich nieznormalizowane amplitudy.

Na przykład stan $ $ \ket{\Text{Reference}} = (^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\Text{Reference}}, $ $

$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \downarrow}a \_ {3, \uparrow}a \_ {2, \downarrow} $ $ jest reprezentowane przez
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

#### <a name="basis-set-object"></a>Obiekt zestawu podstawy ####

Ta sekcja jest normatywna.

Każdy obiekt opisu problemu może mieć `basis_set` Właściwość.
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

### <a name="table-3-allowed-state-methods"></a>Tabela 3. Dozwolone metody stanu ###

Ta sekcja jest normatywna.

Dowolny ciąg określający metodę State musi mieć jedną z następujących wartości:

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

Ta sekcja jest informacyjna.

Dodatkowe metody stanu można wprowadzać w przyszłych wersjach tej specyfikacji.
