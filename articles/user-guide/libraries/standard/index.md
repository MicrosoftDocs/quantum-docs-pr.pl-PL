---
title: Wprowadzenie do bibliotek standardowych języka Microsoft Q#
description: Dowiedz się więcej o bibliotekach standardowych języka Microsoft Q#, które definiują operacje, funkcje i typy danych używane w programach kwantowych.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 820ad885e7134aa723116d4c9f853d88210a5514
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273817"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Wprowadzenie do bibliotek standardowych języka Q# #

Język Q# jest obsługiwany przez szereg różnych użytecznych operacji, funkcji i typów zdefiniowanych przez użytkownika, które składają się na *standardowe biblioteki* języka Q#.
[`Microsoft.Quantum.Development.Kit`Pakiet NuGet ](https://www.nuget.org/packages/microsoft.quantum.development.kit) instalowany podczas [instalacji i walidacji](xref:microsoft.quantum.install) zawiera kompilator języka Q# i niektóre elementy standardowej biblioteki, które są wdrażane przez maszyny docelowe.
[Pakiet `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) zawiera tę część standardowych bibliotek języka Q#, którą można przenosić pomiędzy maszynami docelowymi.

Symbole zdefiniowane przez standardowe biblioteki języka Q# są opisane bardziej szczegółowo w [dokumentacji interfejsu API](xref:microsoft.quantum.standardlibsintro).

W poniższych sekcjach zostaną opisane najważniejsze funkcje każdej części standardowej biblioteki wraz z opisem kontekstu korzystania z każdej funkcji w praktyce.
