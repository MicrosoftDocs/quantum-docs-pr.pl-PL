---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712334"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>FiveQubitCodeEncoderImpl, operacja

Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Package [](https://nuget.org/packages/)


Operacja prywatna używana do implementowania zarówno kodera qubit, jak i dekodera.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="data--qubit"></a>dane: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Tablica zawierająca 1 qubit, która jest wejściowym qubit.


### <a name="scratch--qubit"></a>Scratch: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Tablica zawierająca 4 qubits, która umożliwia dodawanie nadmiarowości.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Wybrany koder został pobrany z papieru V. Kliuchnikov i D. Maslov, "Optymalizacja obwodów Clifford," Bio. Rev. cz. Rev. A 88, 052307 (2013); https://arxiv.org/abs/1305.0810, Rysunek 4b) i wymaga łącznie 11 bram.