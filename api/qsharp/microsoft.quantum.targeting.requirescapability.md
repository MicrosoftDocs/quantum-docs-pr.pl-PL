---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231011"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. określania wartości docelowej](xref:Microsoft.Quantum.Targeting)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Atrybut rozpoznany przez kompilator używany do oznaczania możliwego do uruchomienia możliwości środowiska uruchomieniowego.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="level--string"></a>Poziom: [ciąg](xref:microsoft.quantum.lang-ref.string)

Nazwa poziomu możliwości środowiska uruchomieniowego wymaganego przez wywoływany.
### <a name="reason--string"></a>Przyczyna: [ciąg](xref:microsoft.quantum.lang-ref.string)

Opis przyczyny, dla którego możliwe jest wykonanie tej możliwości środowiska uruchomieniowego.

## <a name="remarks"></a>Uwagi

Ten atrybut jest automatycznie dodawany do żądanych przez kompilator, chyba że wystąpienie tego atrybutu już istnieje w możliwym do przeniesieniu. Nie powinno być używane z wyjątkiem rzadkich przypadków, w których kompilator nie wystawia prawidłowo wymaganej funkcji.

Poniżej znajduje się lista nazw poziomów możliwości w kolejności rosnących możliwości lub zmniejszających się ograniczeń:

## `"BasicQuantumFunctionality"`

Nie można porównać wyników pomiaru dla równości.

## `"BasicMeasurementFeedback"`

Wyniki pomiarów można porównać pod kątem równości tylko w wyrażeniach warunkowych if-Statement w operacjach. Blok instrukcji if-Statement, który zależy od wyniku nie może zawierać instrukcji Set dla zmiennych modyfikowalnych zadeklarowanych poza blokiem lub instrukcji return.

## `"FullComputation"`

Brak ograniczeń środowiska uruchomieniowego. Można wykonać dowolny program Q #.