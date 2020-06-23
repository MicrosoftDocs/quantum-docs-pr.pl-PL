---
title: Instalowanie zestawu Microsoft Quantum Development Kit (QDK)
description: Sposób instalowania zestawu Microsoft Quantum Development Kit dla różnych środowisk.
author: bradben
ms.author: bradben
ms.date: 5/8/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 6a52eb0a9cdf699e8bb37578ffa3d73fe96a990e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85273748"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Instalowanie zestawu Microsoft Quantum Development Kit (QDK)

Dowiedz się, jak zainstalować zestaw Microsoft Quantum Development Kit (QDK), aby rozpocząć pracę z programowaniem kwantowym. Zestaw QDK składa się z:

- Języka programowania Q#
- Zestaw bibliotek, które reprezentują jako abstrakcje złożone funkcje w języku Q#
- Interfejsy API dla języków Python i .NET (C#, F# i VB.NET) do uruchamiania programów kwantowych pisanych w języku Q#
- Narzędzia ułatwiające programowanie

Programy w języku Q# mogą działać jako aplikacje autonomiczne przy użyciu programu Visual Studio Code lub Visual Studio albo za pośrednictwem notesów Jupyter za pomocą jądra Jupyter IQ#.

Mogą być również sparowane z programem hosta napisanym w języku .NET (zazwyczaj C#) lub Python, umożliwiając wywoływanie operacji kwantowych z poziomu klasycznego programu.

Zestaw QDK jest dostępny dla wielu środowisk projektowych. Wybierz preferowaną konfigurację:

[Twórz przy użyciu aplikacji wiersza polecenia dla języka Q#](xref:microsoft.quantum.install.standalone) — wybierz tę metodę, aby korzystać z języka Q# za pomocą wiersza polecenia. W przeciwieństwie do opcji znajdujących się niżej nie wymaga to sterownika ani programu hosta.

[Twórz przy użyciu notesów Jupyter dla języka Q#](xref:microsoft.quantum.install.jupyter) — wybierz to środowisko, aby uruchamiać kod Q# w komórkach z osadzonym tekstem lub tworzyć interaktywne samouczki z zakresu obliczeń kwantowych. 

[Twórz aplikacje za pomocą języków Q# i Python](xref:microsoft.quantum.install.python) — umożliwia połączenie języków Python i Q# w celu utworzenia programu hosta w języku Python, który wywołuje operacje w języku Q#.

[Twórz aplikacje za pomocą języków Q# i .NET](xref:microsoft.quantum.install.cs) — połącz języki C#, F# lub VB.NET z językiem Q# w celu utworzenia programu hosta platformy .NET, który wywołuje operacje w języku Q#.
