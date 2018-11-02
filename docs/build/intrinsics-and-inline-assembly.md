---
title: 組み込みおよびインライン アセンブリ
ms.date: 11/04/2016
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
ms.openlocfilehash: 033225259c0a33414fe45eba313bb1f1c94eb379
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515103"
---
# <a name="intrinsics-and-inline-assembly"></a>組み込みおよびインライン アセンブリ

1 つ、x64 の制約のコンパイラは、インライン アセンブラーのサポートがないようにします。 つまり、関数は、サブルーチン、またはコンパイラによってサポートされる組み込み関数として記述する必要がいずれかの C または C++ で記述することはできません。 特定の関数はパフォーマンスと小文字が区別されないものもあります。 パフォーマンスが重視される関数は、組み込み関数として実装する必要があります。

コンパイラでサポートされている組み込み関数は「[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)します。

## <a name="see-also"></a>関連項目

[x64 ソフトウェア規約](../build/x64-software-conventions.md)