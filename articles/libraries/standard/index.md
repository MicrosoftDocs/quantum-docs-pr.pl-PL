---
title: Wprowadzenie do bibliotek standardowych języka Q# | Microsoft Docs
description: Wprowadzenie do bibliotek standardowych języka Q#
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.intro
ms.openlocfilehash: 547f4f6066e3ead627cd2a5970b1555999e988bb
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "73056379"
---
# <a name="introduction-to-the-q-standard-libraries"></a><span data-ttu-id="3151e-103">Wprowadzenie do bibliotek standardowych języka Q#</span><span class="sxs-lookup"><span data-stu-id="3151e-103">Introduction to the Q# Standard Libraries</span></span> #

<span data-ttu-id="3151e-104">Język Q# jest obsługiwany przez szereg różnych użytecznych operacji, funkcji i typów zdefiniowanych przez użytkownika, które składają się na *standardowe biblioteki* języka Q#.</span><span class="sxs-lookup"><span data-stu-id="3151e-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard libraries*.</span></span>
<span data-ttu-id="3151e-105">[`Microsoft.Quantum.Development.Kit`Pakiet NuGet ](https://www.nuget.org/packages/microsoft.quantum.development.kit) instalowany podczas [instalacji i walidacji](xref:microsoft.quantum.install) zawiera kompilator języka Q# i niektóre elementy standardowej biblioteki, które są wdrażane przez maszyny docelowe.</span><span class="sxs-lookup"><span data-stu-id="3151e-105">The [`Microsoft.Quantum.Development.Kit` NuGet package](https://www.nuget.org/packages/microsoft.quantum.development.kit) installed during [installation and validation](xref:microsoft.quantum.install) provides the Q# compiler, and parts of the standard library that are implemented by the target machines.</span></span>
<span data-ttu-id="3151e-106">[Pakiet `Microsoft.Quantum.Standard`](https://www.nuget.org/packages/microsoft.quantum.standard) zawiera tę część standardowych bibliotek języka Q#, którą można przenosić pomiędzy maszynami docelowymi.</span><span class="sxs-lookup"><span data-stu-id="3151e-106">The [`Microsoft.Quantum.Standard` package](https://www.nuget.org/packages/microsoft.quantum.standard) provides the portion of the Q# standard libraries that are portable across target machines.</span></span>

<span data-ttu-id="3151e-107">Symbole zdefiniowane przez standardowe biblioteki języka Q# są opisane bardziej szczegółowo w [dokumentacji interfejsu API](xref:microsoft.quantum.standardlibsintro).</span><span class="sxs-lookup"><span data-stu-id="3151e-107">The symbols defined by the Q# standard libraries are defined in much greater and more exhaustive detail in the [API documentation](xref:microsoft.quantum.standardlibsintro).</span></span>

<span data-ttu-id="3151e-108">W poniższych sekcjach zostaną opisane najważniejsze funkcje każdej części standardowej biblioteki wraz z opisem kontekstu korzystania z każdej funkcji w praktyce.</span><span class="sxs-lookup"><span data-stu-id="3151e-108">In the following sections, we will outline the most salient features of each part of the standard library and provide some context about how each feature might be used in practice.</span></span>
