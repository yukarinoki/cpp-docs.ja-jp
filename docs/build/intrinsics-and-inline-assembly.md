---
title: 組み込みおよびインライン アセンブリ |Microsoft ドキュメント
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
ms.openlocfilehash: 5b8651bea0b1ee9f54ec0af704d92feef0722368
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367980"
---
# <a name="intrinsics-and-inline-assembly"></a>組み込みおよびインライン アセンブリ
制約の 1 つ、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]コンパイラではインライン アセンブラーのサポートがありません。 関数をすることを意味は、サブルーチン、またはコンパイラによってサポートされる組み込み関数として記述する必要がいずれかの C または C++ で記述することはできません。 特定の関数は、他のユーザーがないときに、パフォーマンスの機密性の高いです。 パフォーマンスが重視される関数は、組み込み関数として実装する必要があります。  
  
 コンパイラでサポートされている組み込み関数は「[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)です。  
  
## <a name="see-also"></a>関連項目  
 [x64 ソフトウェア規約](../build/x64-software-conventions.md)