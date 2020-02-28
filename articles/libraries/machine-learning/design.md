---
title: Projektowanie własnego klasyfikatora przy użyciu QDK
description: Zapoznaj się z podstawowymi pojęciami dotyczącymi projektowania modeli obwodów dla klasyfikatora zorientowanego obwodu Quantum.
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: 4899336f437c1b7712a7831b97fd6ec1431b59a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909725"
---
# <a name="design-your-own-classifier"></a>Projektowanie własnego klasyfikatora

W tym przewodniku przedstawiono podstawowe pojęcia związane z projektowaniem modeli obwodów dla klasyfikatora zorientowanego obwodu Quantum.

Podobnie jak w przypadku klasycznej uczenia głębokiego, nie ma żadnej ogólnej reguły wyboru określonej architektury. W zależności od problemu niektóre architektury będą działać lepiej niż inne. Ale istnieją pewne koncepcje, które mogą być przydatne podczas projektowania obwodu:

- Duża liczba parametrów implikuje bardziej elastyczny model, który może być odpowiedni do rysowania złożonych granic klasyfikacji, ale może być również bardziej podatny na zamontowanie.

- Bramy Entangling między qubitsami są niezbędne do przechwytywania korelacji między funkcjami Quantum.

## <a name="how-to-build-a-classifier-with-q"></a>Jak utworzyć klasyfikator przy użyciu Q\#

Aby skompilować klasyfikator, zamierzamy połączyć kontrolowane rotacje w modelu obwodu. Aby to zrobić, można użyć typu [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) zdefiniowanego w bibliotece Machine Learning Quantum. Ten typ akceptuje cztery argumenty, które określają: indeks elementu docelowego qubit, tablicę indeksów qubits kontrolki, oś obrotu i indeks skojarzonego parametru w tablicy parametrów definiujących model.

Zobaczmy przykład klasyfikatora. W [przykładzie Half księżyca](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)możemy znaleźć następujący klasyfikator zdefiniowany w pliku `Training.qs`.

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

Co definiujemy w tym miejscu jest funkcja, która zwraca tablicę elementów `ControlledRotation`, które razem z tablicą parametrów i bias definiują nasze [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel). Ten typ jest fundamentalny w bibliotece Machine Learning Quantum i definiuje klasyfikatora. Obwód zdefiniowany w funkcji powyżej jest częścią klasyfikatora, w którym każda próbka zestawu danych zawiera dwie funkcje. W związku z tym potrzebujemy tylko dwóch qubits. Graficzna reprezentacja obwodu to:

 ![Przykład modelu obwodu](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>Używanie funkcji biblioteki do zapisywania warstw bram

Załóżmy, że mamy zestaw danych o 784 funkcjach na wystąpienie, np. obrazy 28 × 28 pikseli, takie jak zestaw danych MNIST ręcznie. W takim przypadku szerokość obwodu jest wystarczająco duża, aby można było pisać każdą bramę indywidualnie, ale niepraktyczne zadanie. Dlatego Biblioteka Quantum Machine Learning udostępnia zestaw narzędzi do automatycznego generowania warstw z parametrami. Na przykład funkcja [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) zwraca tablicę niekontrolowanych rotacji qubit na daną oś, z jednym obrotem dla każdego qubit w rejestrze, z których każdy jest określany przez inny parametr modelu. Na przykład `LocalRotationsLayer(4, X)` zwraca następujący zestaw bram:

 ![Warstwa obrotów lokalnych](~/media/local_rotations_layer.PNG)

Zalecamy zapoznanie się z [interfejsem API referenece biblioteki Quantum Machine Learning](xref:microsoft.quantum.machinelearning) , aby odnaleźć wszystkie narzędzia dostępne do usprawnienia projektowania obwodu.

## <a name="next-steps"></a>Następne kroki

 Wypróbuj różne struktury w przykładach dostarczonych przez przykłady. Czy widzisz zmiany w wydajności modelu? W następnym samouczku [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load)dowiesz się, jak ładować zestawy danych, aby próbować i eksplorować nowe architektury klasyfikatorów.
