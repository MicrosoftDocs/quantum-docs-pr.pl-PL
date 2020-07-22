---
title: Wprowadzenie do bibliotek standardowych języka Microsoft Q#
description: Dowiedz się więcej o bibliotekach standardowych języka Microsoft Q#, które definiują operacje, funkcje i typy danych używane w programach kwantowych.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: ab069c496d89a57f979732da6ccdfbe673b79726
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2020
ms.locfileid: "86870587"
---
# <a name="introduction-to-the-q-standard-libraries"></a>Wprowadzenie do bibliotek standardowych języka Q#

Język Q# jest obsługiwany przez szereg różnych użytecznych operacji, funkcji i typów zdefiniowanych przez użytkownika, które składają się na *standardowe biblioteki* języka Q#.
[`Microsoft.Quantum.Development.Kit`Pakiet NuGet ](https://www.nuget.org/packages/microsoft.quantum.development.kit) instalowany podczas [instalacji i walidacji](xref:microsoft.quantum.install) zawiera kompilator języka Q# i niektóre elementy standardowej biblioteki, które są wdrażane przez maszyny docelowe.
[Pakiet `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) zawiera tę część standardowych bibliotek języka Q#, którą można przenosić pomiędzy maszynami docelowymi.

Symbole zdefiniowane przez standardowe biblioteki języka Q# są opisane bardziej szczegółowo w [dokumentacji interfejsu API](xref:microsoft.quantum.standardlibsintro).

W poniższych sekcjach zostaną opisane najważniejsze funkcje każdej części standardowej biblioteki wraz z opisem kontekstu korzystania z każdej funkcji w praktyce.
