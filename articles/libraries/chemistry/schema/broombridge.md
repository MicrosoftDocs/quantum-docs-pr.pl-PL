---
title: Broombridge — schemat chemii Quantum
description: Przegląd schematu chemii Broombridge Quantum używany do modelowania rzeczywistych problemów biochemicznych z Microsoft Quantum Development Kit.
author: martinro
ms.author: martinro@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.broombridge
ms.openlocfilehash: a746b63055bb1b2c1168b89993a7459ca9597f86
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907821"
---
# <a name="broombridge-quantum-chemistry-schema"></a>Schemat chemii Quantum Broombridge # 

Zaawansowane, obliczeniowe oprogramowanie, takie jak [NWChem](http://www.nwchem-sw.org/) , umożliwia modelowanie szerokiego zakresu rzeczywistych problemów chemicznych. Aby uzyskać dostęp do modeli molekularnych NWChem za pomocą biblioteki chemii Microsoft Quantum, używamy schematu opartego na [YAML](https://en.wikipedia.org/wiki/YAML), który jest wywoływany **Broombridge**. Nazwa została wybrana w odniesieniu do punktu [orientacyjnego](https://en.wikipedia.org/wiki/Broom_Bridge) , w którym niektóre okręgi są pożądane jako miejsce urodzenia Hamiltonians. 

[NWChem](https://github.com/nwchemgit/nwchem) to projekt Open Source licencjonowany w ramach licencji programu licencjonowania Community (wyłączenie ecl) 2,0. Broombridge to schemat typu "open source", który jest określony w [tym miejscu](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) i zawiera [definicję](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/broombridge-0.1.schema.json) następującej po [dokumencie RFC 2119](https://tools.ietf.org/html/rfc2119) i [skryptu modułu sprawdzania poprawności](https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/validator.py) licencjonowanego w ramach licencji MIT. 

YAML, Broombridge to strukturalna, czytelna i przez człowieka Metoda reprezentowania problemów ze strukturą elektroniczną. W szczególności można przedstawić następujące dane: 
- Fermionic Hamiltonians może być reprezentowana przy użyciu DWUI dwuskładnikowych całek. 
- Stany terenowe i przyjemnością mogą być prezentowane przy użyciu sekwencji tworzenia.
- Można określić górne i dolne granice poziomów energii.

Format danych może być generowany z NWChem z bezproblemową prostotą: różne metody są dostępne w zakresie od pełnej instalacji NWChem do uruchamiania pokładów chemii, takich jak podane [tutaj](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests) i wyjściowe Broombridge w ramach przebiegu, na podstawie obrazu platformy Docker NWChem, który może być również używany do generowania Broombridge z pokładów chemicznych. Na koniec Metoda wizualizacji, która pozwala szybko rozpocząć pracę z chemią obliczeniową bez konieczności instalowania jakiegokolwiek oprogramowania chemicznego, jest dostarczany przez interfejs [strzałek EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) do NWChem. 

Na wysokim poziomie współpraca między NWChem i Microsoft Quantum Development Kit mogą być wizualizowane w następujący sposób: ![stos chemii](~/media/broombridge.png) niebiesko cieniowane pole reprezentuje schemat Broombridge, różne wyszarzone pola reprezentują inne wewnętrzne reprezentacje danych, które zostały wybrane do reprezentowania i przetwarzania algorytmów Quantum dla chemii obliczeniowej na podstawie rzeczywistych problemów chemicznych. 

W [tym miejscu](https://github.com/microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML)są podane liczne reprezentacje chemiczne zdefiniowane przy użyciu schematu Broombridge.
