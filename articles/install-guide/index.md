---
title: Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK)
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: b209f0b600d973c3870c66060e1b484ec519322f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820712"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym. Zestaw QDK składa się z:

- języka programowania Q#
- zestawu bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#
- interfejsów API dla języków Python i .NET (tj. C#, F# i VB.NET) umożliwiających uruchamianie programów kwantowych napisanych w języku Q#
- narzędzia ułatwiające programowanie

Programy Q# są często parowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python. Pozwala to na wywoływanie operacji kwantowych z poziomu klasycznego programu.
Ponadto zestaw QDK zapewnia obsługę języka Q# przez notesy Jupyter przy użyciu jądra Jupyter IQ#.

Zestaw QDK jest dostępny dla wielu środowisk projektowych. Wybierz preferowaną konfigurację z poniższych sekcji:

- [Zainstaluj język Q# dla języka C#:](xref:microsoft.quantum.install.cs) wybierz to środowisko, jeśli chcesz połączyć języki C# i Q# w celu utworzenia programu hosta w języku C#, który wywołuje operacje w języku Q#.
- [Zainstaluj język Q# dla języka Python:](xref:microsoft.quantum.install.python) wybierz to środowisko, jeśli chcesz połączyć języki Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.
- [Zainstaluj język Q# dla notesów Jupyter:](xref:microsoft.quantum.install.jupyter) wybierz to środowisko, aby wykonywać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych. Nie wybieraj tego środowiska, jeśli chcesz połączyć język Q# z zewnętrznym klasycznym programem hosta.
