---
title: Wprowadzenie do bibliotek standardowych języka Microsoft Q#
description: Dowiedz się więcej o bibliotekach standardowych języka Microsoft Q#, które definiują operacje, funkcje i typy danych używane w programach kwantowych.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 63709015a12a7f972a676018970143ca163e92d0
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90836016"
---
# <a name="introduction-to-the-no-locq-standard-libraries"></a><span data-ttu-id="25717-103">Wprowadzenie do bibliotek standardowych języka Q#</span><span class="sxs-lookup"><span data-stu-id="25717-103">Introduction to the Q# Standard Libraries</span></span>

<span data-ttu-id="25717-104">Język Q# jest obsługiwany przez szereg różnych użytecznych operacji, funkcji i typów zdefiniowanych przez użytkownika, które składają się na *biblioteki standardowe* języka Q#.</span><span class="sxs-lookup"><span data-stu-id="25717-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="25717-105">[Pakiet NuGet `Microsoft.Quantum.Development.Kit`](https://www.nuget.org/packages/microsoft.quantum.development.kit) instalowany podczas [instalacji i walidacji](xref:microsoft.quantum.install) zawiera kompilator języka Q# i niektóre elementy biblioteki standardowej, które są implementowane przez maszyny docelowe.</span><span class="sxs-lookup"><span data-stu-id="25717-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="25717-106">[Pakiet `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) zawiera tę część bibliotek standardowych języka Q#, którą można przenosić między maszynami docelowymi.</span><span class="sxs-lookup"><span data-stu-id="25717-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="25717-107">Symbole zdefiniowane przez biblioteki standardowe języka Q# są opisane bardziej szczegółowo w [dokumentacji interfejsu API](xref:microsoft.quantum.apiref-intro).</span><span class="sxs-lookup"><span data-stu-id="25717-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.apiref-intro).</span></span>

<span data-ttu-id="25717-108">W poniższych sekcjach zostaną opisane najważniejsze funkcje każdej części standardowej biblioteki wraz z opisem kontekstu korzystania z każdej funkcji w praktyce.</span><span class="sxs-lookup"><span data-stu-id="25717-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
