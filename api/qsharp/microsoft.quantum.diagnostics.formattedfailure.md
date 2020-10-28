---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 0d7fb01ddf23cd6d79f722c8f6b691afa74a8885
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712679"
---
# <a name="formattedfailure-function"></a>FormattedFailure, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


Funkcja wewnętrzna używana do niepowodzenia z znaczącymi komunikatami o błędach.

```qsharp
function FormattedFailure<'T> (actual : 'T, expected : 'T, message : String) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="actual--t"></a>rzeczywista: 'T




### <a name="expected--t"></a>Oczekiwano: 'T




### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)





## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

Ta funkcja jest przeznaczona do emulowania przez środowiska uruchomieniowe symulacji, dlatego w celu umożliwienia przesyłania dalej sformatowanych sprzeczności.