---
title: Podstawowa Klasyfikacja z biblioteką Machine Learning Quantum
description: 'Dowiedz się, jak wykonać klasyfikator sekwencyjny Quantum zapisany w Q # przy użyciu biblioteki Quantum Machine Learning w QDK firmy Microsoft.'
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
ms.openlocfilehash: 1d2538fd164c4c61c2712978d3b5c57b0eb766e6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275786"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a>Podstawowa Klasyfikacja: klasyfikowanie danych za pomocą QDK

W tym przewodniku szybki start dowiesz się, jak wykonać klasyfikator sekwencyjny Quantum zapisany w Q # przy użyciu biblioteki Quantum Machine Learning QDK. 

W tym przewodniku użyjemy zestawu danych o połowie księżyca przy użyciu struktury klasyfikatora zdefiniowanej w Q #.

## <a name="prerequisites"></a>Wymagania wstępne

- Zestaw Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).
- Utwórz projekt Q # dla [programu hosta Python](xref:microsoft.quantum.install.python) lub [programu hosta języka C#](xref:microsoft.quantum.install.cs).

## <a name="host-program"></a>Program hosta

Program hosta składa się z trzech części:

- Załaduj zestaw danych i wybierz zestaw parametrów uruchamiania dla modelu.
- Wykonaj szkolenie, aby określić parametry i odchylenia modelu.
- Weryfikowanie modelu w celu określenia jego dokładności

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[Język Python z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-python)

    Aby uruchomić, jesteś klasyfikatorem Q # z języka Python, Zapisz Poniższy kod jako `host.py` . Należy pamiętać, że wymagany jest również plik Q # `Training.qs` opisany w dalszej części tego samouczka.

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    Następnie możesz uruchomić program hosta języka Python z poziomu wiersza polecenia:

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[Język C# z programem Visual Studio Code lub wierszem polecenia](#tab/tabid-csharp)

    Aby uruchomić, jesteś klasyfikatorem Q # z C#, Zapisz Poniższy kod jako `Host.cs` . Należy pamiętać, że wymagany jest również plik Q # `Training.qs` opisany w dalszej części tego samouczka.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Następnie możesz uruchomić program hosta języka C# z poziomu wiersza polecenia:

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[Język C# w programie Visual Studio 2019](#tab/tabid-vs2019)

    Aby uruchomić nowy program Q # z poziomu języka C# w programie Visual Studio, należy zmodyfikować, `Host.cs` Aby uwzględnić Poniższy kod w języku C#. Należy pamiętać, że wymagany jest również plik Q # `Training.qs` opisany w dalszej części tego samouczka.

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    Następnie naciśnij klawisz F5. Program zacznie działać i pojawią się nowe okna z następującymi wynikami: 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a>\#Kod klasyfikatora Q

Teraz zobaczmy, jak operacje wywoływane przez program hosta są zdefiniowane w Q #.
Zapiszemy następujący kod w pliku o nazwie `Training.qs` .

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

Najważniejsze funkcje i operacje zdefiniowane w powyższym kodzie są następujące:

- `ClassifierStructure() : ControlledRotation[]`: w tej funkcji ustawimy strukturę modelu obwodu przez dodanie warstw kontrolowanej bramy. Ten krok jest analogiczny do deklaracji warstw neurons w modelu uczenia głębokiego.
- `TrainHalfMoonModel() : (Double[], Double)`: Ta operacja jest podstawową częścią kodu i definiuje szkolenie. Tutaj ładujemy przykłady z zestawu danych zawartego w bibliotece, ustawimy parametry funkcji Hyper-i początkowe parametry szkolenia i zaczniemy szkolenie przez wywołanie operacji `TrainSequentialClassifier` zawartej w bibliotece. Zwraca parametry i bias określające klasyfikatora.
- `ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: Ta operacja definiuje proces walidacji w celu oszacowania modelu. Tutaj ładujemy próbki do walidacji, liczbę pomiarów na próbkę i tolerancję. Zwraca liczbę błędów klasyfikacji na wybranej partii próbek do walidacji.

## <a name="next-steps"></a>Następne kroki

Najpierw można zagrać z kodem i próbować zmienić niektóre parametry, aby zobaczyć, jak ma to wpływ na szkolenie. Następnie w następnym samouczku [Zaprojektuj własny klasyfikator](xref:microsoft.quantum.libraries.machine-learning.design), dowiesz się, jak zdefiniować strukturę klasyfikatora.