---
title: Projektowanie własnego klasyfikatora przy użyciu QDK
description: Zapoznaj się z podstawowymi pojęciami dotyczącymi projektowania modeli obwodów dla klasyfikatora zorientowanego obwodu Quantum.
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2100fe120ba3b5fce5d06e77d7f3f5174bc04adb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858812"
---
# <a name="design-your-own-classifier"></a>Projektowanie własnego klasyfikatora

W tym przewodniku przedstawiono podstawowe pojęcia związane z projektowaniem modeli obwodów dla klasyfikatora zorientowanego obwodu Quantum.

Podobnie jak w przypadku klasycznej uczenia głębokiego, nie ma żadnej ogólnej reguły wyboru określonej architektury. W zależności od problemu niektóre architektury będą działać lepiej niż inne. Ale istnieją pewne koncepcje, które mogą być przydatne podczas projektowania obwodu:

- Duża liczba parametrów implikuje bardziej elastyczny model, który może być odpowiedni do rysowania złożonych granic klasyfikacji, ale może być również bardziej podatny na zamontowanie.

- Bramy Entangling między qubitsami są niezbędne do przechwytywania korelacji między funkcjami Quantum.

## <a name="how-to-build-a-classifier-with-q"></a>Jak utworzyć klasyfikator przy użyciu Q\#

Aby skompilować klasyfikator, zamierzamy połączyć kontrolowane rotacje w modelu obwodu. Aby to zrobić, można użyć typu [`ControlledRotation`](xref:Microsoft.Quantum.MachineLearning.ControlledRotation) zdefiniowanego w bibliotece Quantum Machine Learning. Ten typ akceptuje cztery argumenty, które określają: indeks elementu docelowego qubit, tablicę indeksów qubits kontrolki, oś obrotu i indeks skojarzonego parametru w tablicy parametrów definiujących model.

Zobaczmy przykład klasyfikatora. W [przykładzie Half księżyca](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)możemy znaleźć następujący klasyfikator zdefiniowany w pliku `Training.qs` .

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

To, co definiujemy w tym miejscu, jest funkcja, która zwraca tablicę `ControlledRotation` elementów, która razem z tablicą parametrów i odchylenia będzie definiować nasze [`SequentialModel`](xref:Microsoft.Quantum.MachineLearning.SequentialModel) . Ten typ jest fundamentalny w bibliotece Machine Learning Quantum i definiuje klasyfikatora. Obwód zdefiniowany w funkcji powyżej jest częścią klasyfikatora, w którym każda próbka zestawu danych zawiera dwie funkcje. W związku z tym potrzebujemy tylko dwóch qubits. Graficzna reprezentacja obwodu to:

 ![Przykład modelu obwodu](~/media/circuit_model_1.PNG)

Należy zauważyć, że domyślnie operacje biblioteki Quantum Machine Learning mierzą ostatni qubit rejestru w celu oszacowania prawdopodobieństwa klasyfikacji. Należy pamiętać o tym fakcie podczas projektowania obwodu.

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Używanie funkcji biblioteki do zapisywania warstw bram

Załóżmy, że mamy zestaw danych o 784 funkcjach na wystąpienie, np. obrazy 28 × 28 pikseli, takie jak zestaw danych MNIST ręcznie. W takim przypadku szerokość obwodu jest wystarczająco duża, aby można było pisać każdą bramę indywidualnie, ale niepraktyczne zadanie. Dlatego Biblioteka Quantum Machine Learning udostępnia zestaw narzędzi do automatycznego generowania warstw z parametrami. Na przykład funkcja [`LocalRotationsLayer`](xref:Microsoft.Quantum.MachineLearning.LocalRotationsLayer) zwraca tablicę niekontrolowanych rotacji qubit na daną oś, z jednym obrotem dla każdego qubit w rejestrze, z których każdy jest określany przez inny parametr modelu. Na przykład `LocalRotationsLayer(4, X)` zwraca następujący zestaw bram:

 ![Warstwa obrotów lokalnych](~/media/local_rotations_layer.PNG)

Zalecamy zapoznanie się z [biblioteką interfejsów API Machine Learning Quantum](xref:Microsoft.Quantum.MachineLearning) , aby poznać wszystkie narzędzia dostępne do usprawnienia projektowania obwodu.

## <a name="next-steps"></a>Następne kroki

 Wypróbuj różne struktury w przykładach dostarczonych przez przykłady. Czy widzisz zmiany w wydajności modelu? W następnym samouczku [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) dowiesz się, jak ładować zestawy danych, aby próbować i eksplorować nowe architektury klasyfikatorów.
