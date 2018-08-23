---
title: 組み込みおよびインライン アセンブリ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8affd4bb-279d-46f3-851f-8be0a9c5ed3f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff2b99eedcdd81a96dc3091046a4f62ffe002509
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572744"
---
# <a name="intrinsics-and-inline-assembly"></a>組み込みおよびインライン アセンブリ
1 つ、x64 の制約のコンパイラは、インライン アセンブラーのサポートがないようにします。 つまり、関数は、サブルーチン、またはコンパイラによってサポートされる組み込み関数として記述する必要がいずれかの C または C++ で記述することはできません。 特定の関数はパフォーマンスと小文字が区別されないものもあります。 パフォーマンスが重視される関数は、組み込み関数として実装する必要があります。  
  
 コンパイラでサポートされている組み込み関数は「[コンパイラ組み込み](../intrinsics/compiler-intrinsics.md)します。  
  
## <a name="see-also"></a>関連項目  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)