---
title: Wprowadzenie do bibliotek standardowych języka Microsoft Q#
description: Dowiedz się więcej o bibliotekach standardowych języka Microsoft Q#, które definiują operacje, funkcje i typy danych używane w programach kwantowych.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4db227fcf159331f9f8456c474ce6d64111c21df
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868478"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a>Wprowadzenie do bibliotek standardowych języka Q#

Język Q# jest obsługiwany przez szereg różnych użytecznych operacji, funkcji i typów zdefiniowanych przez użytkownika, które składają się na *biblioteki standardowe* języka Q#.
[Pakiet NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) instalowany podczas [instalacji i walidacji](xref:microsoft.quantum.install) zawiera kompilator języka Q# i niektóre elementy biblioteki standardowej, które są implementowane przez maszyny docelowe.
[Pakiet `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) zawiera tę część bibliotek standardowych języka Q#, którą można przenosić między maszynami docelowymi.

Symbole zdefiniowane przez biblioteki standardowe języka Q# są opisane bardziej szczegółowo w [dokumentacji interfejsu API](xref:microsoft.quantum.standardlibsintro).

W poniższych sekcjach zostaną opisane najważniejsze funkcje każdej części standardowej biblioteki wraz z opisem kontekstu korzystania z każdej funkcji w praktyce.
