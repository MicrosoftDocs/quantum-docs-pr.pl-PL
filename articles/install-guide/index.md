---
title: Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK)
description: Jak zainstalować zestaw Microsoft Quantum Development Kit dla środowisk C#, Python i Jupyter Notebook.
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: bca700660094b91f1c0dfa03f9bce1336073ca51
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680195"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym. Zestaw QDK składa się z:

- języka programowania Q#
- zestawu bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#
- Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#
- narzędzia ułatwiające programowanie

Programy Q# są często parowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python. Pozwala to na wywoływanie operacji kwantowych z poziomu klasycznego programu.
Ponadto zestaw QDK zapewnia obsługę języka Q# przez notesy Jupyter przy użyciu jądra Jupyter IQ#.

Zestaw QDK jest dostępny dla wielu środowisk projektowych. Wybierz preferowaną konfigurację z poniższych sekcji:

- [Aplikacja wiersza polecenia dla języka Q#:](xref:microsoft.quantum.install.standalone) wybierz tę metodę, jeśli chcesz korzystać z języka Q# za pomocą wiersza polecenia. W przeciwieństwie do opcji znajdujących się niżej nie wymaga to sterownika ani programu hosta.
- [Zainstaluj język Q# dla notesów Jupyter:](xref:microsoft.quantum.install.jupyter) wybierz to środowisko, aby wykonywać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych. 
- [Twórz aplikacje za pomocą języków Q# i Python:](xref:microsoft.quantum.install.python) wybierz tę metodę, jeśli chcesz połączyć języki Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.
- [Twórz aplikacje za pomocą języków Q# i C# lub F#:](xref:microsoft.quantum.install.cs) wybierz tę metodę, jeśli chcesz połączyć języki C# lub F# i Q# w celu utworzenia programu hosta platformy .NET, który wywołuje operacje w języku Q#.
