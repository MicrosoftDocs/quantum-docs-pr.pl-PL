---
title: Instalowanie zestawu Microsoft Quantum Development Kit (QDK)
description: Sposób instalowania zestawu Microsoft Quantum Development Kit dla różnych środowisk.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: ee8d210d67a20cfea3bdc36162efc47f021a6dc6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885465"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym. Zestaw QDK składa się z:

- Języka programowania Q#
- Zestaw bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#
- Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#
- Narzędzia ułatwiające programowanie

Programy w języku Q# mogą działać jako aplikacje autonomiczne przy użyciu programu Visual Studio Code lub Visual Studio albo za pośrednictwem notesów Jupyter za pomocą jądra Jupyter IQ#.
Mogą być również sparowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python, umożliwiając wywoływanie operacji kwantowych z poziomu klasycznego programu.

Przepływy pracy dla każdej z tych konfiguracji są opisane i porównane w sekcji [Sposoby uruchamiania programu w języku Q#](xref:microsoft.quantum.guide.host-programs).

Aby kontynuować instalowanie zestawu QDK i tworzenie projektów języka Q#, wybierz preferowaną konfigurację:

[Twórz przy użyciu aplikacji wiersza polecenia dla języka Q#](xref:microsoft.quantum.install.standalone) — wybierz tę metodę, aby korzystać z języka Q# za pomocą wiersza polecenia. W przeciwieństwie do opcji znajdujących się niżej nie wymaga to sterownika ani programu hosta.

[Twórz przy użyciu notesów Jupyter dla języka Q#](xref:microsoft.quantum.install.jupyter) — wybierz to środowisko, aby uruchamiać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych. 

[Twórz aplikacje za pomocą języków Q# i Python](xref:microsoft.quantum.install.python) — umożliwia połączenie języków Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.

[Twórz aplikacje za pomocą języków Q# i .NET](xref:microsoft.quantum.install.cs) — połącz języki C#, F# lub VB.NET z językiem Q# w celu utworzenia programu hosta platformy .NET, który wywołuje operacje w języku Q#.
