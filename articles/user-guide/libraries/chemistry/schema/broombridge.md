---
title: Schemat chemii Quantum Broombridge
description: Przegląd schematu chemii Broombridge Quantum używany do modelowania rzeczywistych problemów biochemicznych z Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
no-loc:
- Q#
- $$v
ms.openlocfilehash: ed24fdd58dc16f97d1ba8051b1c8d0fd84ce0588
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869175"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Schemat chemii Quantum Broombridge # 

Zaawansowane, obliczeniowe oprogramowanie, takie jak [NWChem](http://www.nwchem-sw.org/) , umożliwia modelowanie szerokiego zakresu rzeczywistych problemów chemicznych. Aby można było uzyskać dostęp do modeli molekularnych NWChem za pomocą biblioteki chemii Microsoft Quantum, należy użyć schematu opartego na [YAML](https://en.wikipedia.org/wiki/YAML)o nazwie **Broombridge**. Nazwa została wybrana w odniesieniu do punktu [orientacyjnego](https://en.wikipedia.org/wiki/Broom_Bridge) , w którym niektóre okręgi są pożądane jako miejsce urodzenia Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) to projekt Open Source licencjonowany w ramach licencji programu licencjonowania Community (wyłączenie ecl) 2,0. [Schemat chemii Broombridge Quantum](https://docs.microsoft.com/quantum/libraries/chemistry/schema/spec_v_0_2)) to schemat typu "open source", który zawiera [definicję](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) z następującej [specyfikacji RFC 2119](https://tools.ietf.org/html/rfc2119) i [skryptu modułu sprawdzania poprawności](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licencjonowanego w ramach licencji MIT. 

YAML, Broombridge to strukturalna, czytelna i przez człowieka Metoda reprezentowania problemów ze strukturą elektroniczną. W szczególności można przedstawić następujące dane:
- Fermionic Hamiltonians może być reprezentowana przy użyciu DWUI dwuskładnikowych całek.
- Stany terenowe i przyjemnością mogą być prezentowane przy użyciu sekwencji tworzenia.
- Można określić górne i dolne granice poziomów energii.

Dane można generować z NWChem przy użyciu różnych metod, takich jak używanie pełnej instalacji NWChem do uruchamiania pokładów chemicznych (na przykład tych, które są dostępne w [bibliotece NWChem](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) , która wyprowadza Broombridge jako część przebiegu), lub obrazu platformy Docker NWChem, który może być również używany do generowania Broombridge z pokładów chemicznych. Aby szybko rozpocząć pracę z chemią obliczeniową bez konieczności instalowania jakichkolwiek programów chemicznych, można użyć interfejsu wizualizacji do NWChem zapewnianych przez [EMSL strzałek](https://arrows.emsl.pnnl.gov/api/qsharp_chem).

Na wysokim poziomie współpraca między NWChem i Microsoft Quantum Development Kit można wizualizować w następujący sposób: ![ stosy chemii ](~/media/broombridge.png) niebieskie pole cieniowane reprezentuje schemat Broombridge, natomiast różne szare wyszarzone pola reprezentują inne wewnętrzne reprezentacje danych, które zostały wybrane do reprezentowania i przetwarzania algorytmów Quantum dla chemii obliczeniowej na podstawie rzeczywistych problemów biochemicznych.

Folder [całkowity/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) w repozytorium "Quantum Development Kit Samples" zawiera wiele reprezentacji chemicznych zdefiniowanych przy użyciu schematu Broombridge.
