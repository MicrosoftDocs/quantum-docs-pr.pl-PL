---
title: Podstawowa Klasyfikacja z biblioteką Machine Learning Quantum
description: 'Dowiedz się, jak wykonać klasyfikator sekwencyjny Quantum zapisany w Q # przy użyciu biblioteki Quantum Machine Learning w QDK firmy Microsoft.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: f42e3e4492f934d7a8f03d4fec6fa0de765401d7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909929"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Podstawowa Klasyfikacja: klasyfikowanie danych za pomocą QDK

W tym przewodniku szybki start dowiesz się, jak wykonać klasyfikator sekwencyjny Quantum zapisany w Q # przy użyciu biblioteki Quantum Machine Learning QDK. 

W tym przewodniku użyjemy zestawu danych o połowie księżyca przy użyciu struktury klasyfikatora zdefiniowanej w Q #.

## <a name="prerequisites"></a>Wymagania wstępne

- Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- [Tworzenie projektu języka Q#](xref:microsoft.quantum.howto.createproject)

## <a name="host-program"></a>Program hosta

Program hosta składa się z trzech części:

- Załaduj zestaw danych i wybierz zestaw parametrów uruchamiania dla modelu.
- Wykonaj szkolenie, aby określić parametry i odchylenia modelu.
- Weryfikowanie modelu w celu określenia jego dokładności

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Język Python z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-python)

    Aby uruchomić, jesteś klasyfikatorem Q # z języka Python, Zapisz Poniższy kod jako `host.py`. Należy pamiętać, że w dalszej części tego samouczka potrzebne jest również `Training.qs` pliku Q #.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Język C# z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-csharp)

    Aby uruchomić, jesteś klasyfikatorem Q # C#, Zapisz Poniższy kod jako `Host.cs`. Należy pamiętać, że w dalszej części tego samouczka potrzebne jest również `Training.qs` pliku Q #.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[Język C# w programie Visual Studio 2019](#tab/tabid-vs2019)

    Aby uruchomić nowy program Q # z poziomu C# programu Visual Studio, zmodyfikuj `Host.cs`, aby uwzględnić Poniższy C# kod. Należy pamiętać, że w dalszej części tego samouczka potrzebne jest również `Training.qs` pliku Q #.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Następnie naciśnij klawisz F5. Program zacznie działać i pojawią się nowe okna z następującymi wynikami: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>Kod klasyfikatora\# Q

Teraz zobaczmy, jak operacje wywoływane przez program hosta są zdefiniowane w Q #.
Zapiszemy następujący kod w pliku o nazwie `Training.qs`.

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Najważniejsze funkcje i operacje zdefiniowane w powyższym kodzie są następujące:

- `ClassifierStructure() : ControlledRotation[]`: w tej funkcji ustawimy strukturę modelu obwodu przez dodanie warstw kontrolowanej bramy. Ten krok jest analogiczny do deklaracji warstw neurons w modelu uczenia głębokiego.
- `TrainHalfMoonModel() : TrainWineModel() : (Double[], Double)`: Ta operacja jest podstawową częścią kodu i definiuje szkolenie. Tutaj ładujemy przykłady z zestawu danych zawartego w bibliotece, ustawimy parametry funkcji Hyper-i początkowe parametry szkolenia i zaczniemy szkolenie przez wywołanie operacji `TrainSequentialClassifier` dołączonej do biblioteki. Zwraca parametry i bias określające klasyfikatora.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Ta operacja definiuje proces walidacji w celu oszacowania modelu. Tutaj ładujemy próbki do walidacji, liczbę pomiarów na próbkę i tolerancję. Zwraca liczbę błędów klasyfikacji na wybranej partii próbek do walidacji.

## <a name="next-steps"></a>Następne kroki

Najpierw można zagrać z kodem i próbować zmienić niektóre parametry, aby zobaczyć, jak ma to wpływ na szkolenie. Następnie w następnym samouczku [Zaprojektuj własny klasyfikator](xref:microsoft.quantum.libraries.machine-learning.design), dowiesz się, jak zdefiniować strukturę klasyfikatora.
