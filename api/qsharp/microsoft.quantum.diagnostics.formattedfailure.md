---
uid: Microsoft.Quantum.Diagnostics.FormattedFailure
title: FormattedFailure, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: FormattedFailure
qsharp.summary: Internal function used to fail with meaningful error messages.
ms.openlocfilehash: 6b1202c8897d67e3089a88a0855c8008b3a8c2ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828273"
---
# <a name="formattedfailure-function"></a>FormattedFailure, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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