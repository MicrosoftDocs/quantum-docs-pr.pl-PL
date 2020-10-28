---
uid: Microsoft.Quantum.AmplitudeAmplification
title: Przestrzeń nazw Microsoft. Quantum. AmplitudeAmplification
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: namespace
qsharp.name: Microsoft.Quantum.AmplitudeAmplification
qsharp.summary: This namespace contains functions and operations for performing amplitude amplification.
ms.openlocfilehash: 09c29bd9d0648bb8652051ad97ceca6ef6557df3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721844"
---
# <a name="microsoftquantumamplitudeamplification-namespace"></a>Przestrzeń nazw Microsoft. Quantum. AmplitudeAmplification

Ta przestrzeń nazw zawiera funkcje i operacje do wykonywania wzmocnienia amplitudy.



## <a name="description"></a>Opis

Wzmocnienie amplitudy Oblivious z częściowym odbiciem stanowi najbardziej ogólną formę wzmocnienia amplitudy wdrożonego w tym miejscu.

Jest to wywoływane przez operację AmpAmpObliviousByReflectionPhases.

Ma dwa rejestry: `ancillaRegister` i `systemRegister` .

Akceptuje to dwie Oracle dla tych odniesień typu `ReflectionOracle` , które działają tylko w `ancillaRegister` rejestrze.

Jest to akceptowane przez firmę Oracle specjalna do Oblivious wzmocnienia amplitudy typu `ObliviousOracle` , który działa wspólnie w obu rejestrach.

Przyjęto, że stan wejściowy `ancillaRegister` jest unikatowy eigenstate $-$1 pierwszego operatora odbicia $I-2 \ KET {s} \ bra {s} $.

Odbicia w docelowym stanie Quantum są często implementowane przez założenie dostępu do bazy danych Oracle, która przygotowuje ten stan od podstaw obliczeniowej $ \ket{0\cdots 0} $.

Nasza Konwencja dla tych systemów Oracle wymaga dwóch rejestrów: rejestracji jednoqubitowej `flagQubit` i rejestru dla wszystkiego innego w rejestrze ancillaRegister.

Oracle typu `StateOracle` działa wspólnie z obydwoma rejestrami, aby utworzyć stan docelowy oflagowany przez $ \ket {1} $ w `flagQubit` rejestrze z rzeczywistą amplitudą.

Odbicie `ReflectionOracle` dotyczące tego stanu flagi jest generowane przez operację `TargetStateReflectionOracle` .

Odbicie `ReflectionOracle` stanu danych wejściowych `ancillaRegister` jest generowane przez odwrócone StateOracle, a następnie odzwierciedlające około $ \ket{0\cdots 0} $ with ReflectionStart ().

Oracle typu `DeterministicStateOracle` działa w `qubitState` rejestrach, aby utworzyć stan docelowy dokładnie bez flagi.

`AmpAmpObliviousByOraclePhases` jest wersją wzmocnienia amplitudy Oblivious, która akceptuje firmy Oracle `StateOracle` , a `ObliviousOracle` nie odbicia.

Należy zauważyć, że wzmocnienie amplitudy jest szczególnym przypadkiem wzmocnienia amplitudy Oblivious `ObliviousOracle` , gdzie jest operatorem tożsamości i nie istnieje system qubits, który `systemRegister` jest pusty.

Jest to wywoływane przez operację `AmpAmByReflectionPhases` i `AmpAmpByOraclePhases` .

Fazy dla częściowego odbicia w standardowym przypadku wyszukiwania Grover są dostarczane przez funkcję AmpAmpPhasesStandard.

Na przykład mamy następujące zależności: AmpAmpByOracle-> AmpAmpByOraclePhases-> AmpAmpObliviousByOraclePhases-> AmpAmpObliviousByReflectionPhases.