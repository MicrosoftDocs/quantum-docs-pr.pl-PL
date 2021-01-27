---
uid: Microsoft.Quantum.Arrays.EmptyArray
title: EmptyArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EmptyArray
qsharp.summary: Returns the empty array of a given type.
ms.openlocfilehash: cf15e61862bb64fb3408db2318fafb56d532b365
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846178"
---
# <a name="emptyarray-function"></a>EmptyArray, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zwraca pustą tablicę danego typu.

```qsharp
function EmptyArray<'TElement> () : 'TElement[]
```


## <a name="output--telement"></a>Dane wyjściowe: "TEle []

Pusta tablica.

## <a name="type-parameters"></a>Parametry typu

### <a name="telement"></a>"TEle

Typ elementów tablicy.

## <a name="example"></a>Przykład

```qsharp
let empty = EmptyArray<Int>();
```