---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: c3e48cb5dde36b694a5b16f25333cf0dad6c0f61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713897"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a><span data-ttu-id="26458-102">OptimizedBlockEncodingGeneratorSystem, funkcja</span><span class="sxs-lookup"><span data-stu-id="26458-102">OptimizedBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="26458-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="26458-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="26458-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26458-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26458-105">Konwertuje hamiltonian opisane przez `JWOptimizedHTerms` do a `GeneratorSystem` wyrażone w warunkach Pauli `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="26458-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="26458-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="26458-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="26458-107">dane: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="26458-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="26458-108">Opis elementu hamiltonian w `JWOptimizedHTerms` formacie.</span><span class="sxs-lookup"><span data-stu-id="26458-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--optimizedbegeneratorsystem"></a><span data-ttu-id="26458-109">Wynik: [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="26458-109">Output : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>

<span data-ttu-id="26458-110">Reprezentacja hamiltonian jako `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="26458-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>