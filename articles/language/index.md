---
title: Język programowania Q# | Microsoft Docs
description: Język programowania Q#
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: 560926f6f3e05c32a935f01ca5107a614e743ee2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442469"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="733ed-103">Język programowania Q#</span><span class="sxs-lookup"><span data-stu-id="733ed-103">The Q# Programming Language</span></span>

## <a name="introduction"></a><span data-ttu-id="733ed-104">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="733ed-104">Introduction</span></span>

<span data-ttu-id="733ed-105">Naturalnym modelem obliczeń kwantowych jest traktowanie komputera kwantowego jako koprocesora, podobnego do używanego dla procesorów GPU, FPGA i innych procesorów pomocniczych.</span><span class="sxs-lookup"><span data-stu-id="733ed-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="733ed-106">Podstawowa logika sterowania uruchamia klasyczny kod na klasycznym komputerze hosta.</span><span class="sxs-lookup"><span data-stu-id="733ed-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="733ed-107">W razie potrzeby program hosta może wywołać podprocedurę, która jest uruchamiana na procesorze pomocniczym.</span><span class="sxs-lookup"><span data-stu-id="733ed-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="733ed-108">Po zakończeniu podprocedury program hosta uzyskuje dostęp do wyników podprocedury.</span><span class="sxs-lookup"><span data-stu-id="733ed-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="733ed-109">Język Q# (Q-sharp) to język programowania specyficzny dla domeny używany do wyrażania algorytmów kwantowych.</span><span class="sxs-lookup"><span data-stu-id="733ed-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="733ed-110">Jest przeznaczony do pisania podprocedur, które są wykonywane na pomocniczym procesorze kwantowym, pod kontrolą klasycznego programu i komputera hosta.</span><span class="sxs-lookup"><span data-stu-id="733ed-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="733ed-111">Dopóki procesory kwantowe nie będą szeroko dostępne, procedury języka Q# będą wykonywane w symulatorze.</span><span class="sxs-lookup"><span data-stu-id="733ed-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="733ed-112">Język Q# udostępnia niewielki zestaw typów pierwotnych, a także dwa sposoby (tablice i krotki) tworzenia nowych typów strukturalnych.</span><span class="sxs-lookup"><span data-stu-id="733ed-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="733ed-113">Obsługuje podstawowy model proceduralny pisania programów, z pętlami i instrukcjami if/then.</span><span class="sxs-lookup"><span data-stu-id="733ed-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="733ed-114">Konstrukcje najwyższego poziomu w języku Q# są typami zdefiniowanymi przez użytkownika, operacjami i funkcjami.</span><span class="sxs-lookup"><span data-stu-id="733ed-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="733ed-115">W poniższych sekcjach szczegółowo opisano:</span><span class="sxs-lookup"><span data-stu-id="733ed-115">The following sections detail:</span></span>
- [<span data-ttu-id="733ed-116">Model typu</span><span class="sxs-lookup"><span data-stu-id="733ed-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="733ed-117">Wyrażenia</span><span class="sxs-lookup"><span data-stu-id="733ed-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="733ed-118">Instrukcje</span><span class="sxs-lookup"><span data-stu-id="733ed-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="733ed-119">Struktura plików</span><span class="sxs-lookup"><span data-stu-id="733ed-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

## <a name="conventions"></a><span data-ttu-id="733ed-120">Konwencja</span><span class="sxs-lookup"><span data-stu-id="733ed-120">Conventions</span></span>

<span data-ttu-id="733ed-121">Pracujemy nad zapewnieniem spójnego stosowania typowych znaków interpunkcyjnych we wszystkich sytuacjach.</span><span class="sxs-lookup"><span data-stu-id="733ed-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="733ed-122">Oczekujemy, że ułatwi to naukę i czytanie języka Q#, ponieważ te znaki zawsze oznaczają to samo, a te same pojęcia są zawsze reprezentowane w ten sam sposób.</span><span class="sxs-lookup"><span data-stu-id="733ed-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="733ed-123">Są to:</span><span class="sxs-lookup"><span data-stu-id="733ed-123">Specifically:</span></span>

- <span data-ttu-id="733ed-124">Średnik (`;`) służy do zakończenia instrukcji lub jednowierszowej dyrektywy.</span><span class="sxs-lookup"><span data-stu-id="733ed-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="733ed-125">Nie jest używany do żadnego innego celu.</span><span class="sxs-lookup"><span data-stu-id="733ed-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="733ed-126">Przecinek (`,`) służy do oddzielania elementów sekwencji.</span><span class="sxs-lookup"><span data-stu-id="733ed-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="733ed-127">Jest on używany dla literałów krotek, literałów tablic, list argumentów, definicji krotek i list typów.</span><span class="sxs-lookup"><span data-stu-id="733ed-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="733ed-128">**Po zmianie z wcześniejszych wersji znak `;` nie jest już obsługiwany jako separator literałów tablicy.**</span><span class="sxs-lookup"><span data-stu-id="733ed-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="733ed-129">Dwukropek (`:`) służy do wprowadzania adnotacji typu.</span><span class="sxs-lookup"><span data-stu-id="733ed-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="733ed-130">Jest używany głównie w sygnaturach wywołania.</span><span class="sxs-lookup"><span data-stu-id="733ed-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="733ed-131">Ze względu na to, że dwukropek zawsze wprowadza sygnaturę typu, trójstanowy operator warunkowy wprowadzony w wersji 0.3 używa pionowego paska, `|`, aby oddzielić wartości prawdziwe i fałszywe; w tym celu język Q# używa `cond ? tval | fval` zamiast dwukropka jako separatora, jak w języku C.</span><span class="sxs-lookup"><span data-stu-id="733ed-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
