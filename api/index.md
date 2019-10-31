---
uid: microsoft.quantum.standardlibsintro
title: Standardowa biblioteka Q# dla rozwiązania Microsoft Quantum
description: Dokumentacja referencyjna standardowej biblioteki języka Q# dla rozwiązania Microsoft Quantum
author: natke
ms.author: nakersha
ms.date: 09/04/2019
ms.topic: landing-page
ms.openlocfilehash: 25a53e1cb8577761ef89cdcf2cfcddc509093f86
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2019
ms.locfileid: "72999096"
---
# <a name="q-standard-libraries"></a><span data-ttu-id="f8d10-103">Standardowe biblioteki języka Q#</span><span class="sxs-lookup"><span data-stu-id="f8d10-103">Q# standard libraries</span></span> #

<span data-ttu-id="f8d10-104">Język Q# jest obsługiwany przez szereg różnych użytecznych operacji, funkcji i typów zdefiniowanych przez użytkownika, które składają się na *standardową bibliotekę* języka Q#.</span><span class="sxs-lookup"><span data-stu-id="f8d10-104">Q# is supported by a range of different useful operations, functions, and user-defined types that comprise the Q# *standard library*.</span></span>
<span data-ttu-id="f8d10-105">Standardowa biblioteka języka Q# jest podzielona na dwie główne części:</span><span class="sxs-lookup"><span data-stu-id="f8d10-105">The Q# standard library is split into two main parts:</span></span>

- <span data-ttu-id="f8d10-106">**Preludium**: operacje i funkcje zdefiniowane jako część maszyny docelowej i kompilatora, zwykle w klasycznym natywnym kodzie platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="f8d10-106">**The prelude**: operations and functions defined as a part of the target machine and compiler, typically in classical native .NET code.</span></span>
  <span data-ttu-id="f8d10-107">Ogólnie rzecz biorąc, różne maszyny docelowe mogą mieć różne implementacje preludium odpowiednie dla systemu.</span><span class="sxs-lookup"><span data-stu-id="f8d10-107">In general, different target machines may have different implementations of the prelude appropriate to each system.</span></span>
- <span data-ttu-id="f8d10-108">**Kanon**: operacje i funkcje zdefiniowane w języku Q# oparte na logice zdefiniowanej w preludium.</span><span class="sxs-lookup"><span data-stu-id="f8d10-108">**The canon**: operations and functions defined in Q# building on the logic defined in the prelude.</span></span>
  <span data-ttu-id="f8d10-109">Implementacja kanonu jest niezależna od maszyn docelowych.</span><span class="sxs-lookup"><span data-stu-id="f8d10-109">The canon implementation is agnostic with respect to target machines.</span></span>
<span data-ttu-id="f8d10-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span><span class="sxs-lookup"><span data-stu-id="f8d10-110">&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</span></span>