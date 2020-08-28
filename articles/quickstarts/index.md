---
title: Instalowanie zestawu Microsoft Quantum Development Kit (QDK)
description: Sposób instalowania zestawu Microsoft Quantum Development Kit dla różnych środowisk.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3aafe78d5910027e2836f7dce72c064e75fc4436
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863710"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym. Zestaw QDK składa się z:

- Język programowania Q#
- Zestaw bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#
- Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#
- Narzędzia ułatwiające programowanie

Programy w języku Q# mogą działać jako aplikacje autonomiczne przy użyciu programu Visual Studio Code lub Visual Studio albo za pośrednictwem notesów Jupyter za pomocą jądra Jupyter IQ#.
Mogą być również sparowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python, umożliwiając wywoływanie operacji kwantowych z poziomu klasycznego programu.

Przepływy pracy dla każdej z tych konfiguracji są opisane i porównane w sekcji [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs).

Aby kontynuować instalowanie zestawu QDK i tworzenie projektów języka Q#, wybierz preferowaną konfigurację:

[Twórz przy użyciu aplikacji języka Q#](xref:microsoft.quantum.install.standalone) — wybierz tę metodę, aby korzystać z języka Q# za pomocą wiersza polecenia. W przeciwieństwie do opcji znajdujących się niżej nie wymaga to sterownika ani programu hosta.

[Twórz przy użyciu notesów Jupyter dla języka Q#](xref:microsoft.quantum.install.jupyter) — wybierz to środowisko, aby uruchamiać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych. 

[Twórz aplikacje za pomocą języków Q# i Python](xref:microsoft.quantum.install.python) — umożliwia połączenie języków Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.

[Twórz aplikacje za pomocą języków Q# i .NET](xref:microsoft.quantum.install.cs) — połącz języki C#, F# lub VB.NET z językiem Q# w celu utworzenia programu hosta platformy .NET, który wywołuje operacje w języku Q#.
