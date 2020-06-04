---
title: コンパイラ エラー C2585
ms.date: 11/04/2016
f1_keywords:
- C2585
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
ms.openlocfilehash: 57a0cd7a200c5bbb875821eb9e10314d98e58185
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177392"
---
# <a name="compiler-error-c2585"></a>コンパイラ エラー C2585

' type ' への明示的な変換があいまいです

型変換によって複数の結果が生成される可能性があります。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 多重継承に基づいたクラスまたは構造体型からの変換。 型が同じ基底クラスを2回以上継承する場合、変換関数または演算子はスコープ解決 (`::`) を使用して、変換で使用する継承クラスを指定する必要があります。

1. 変換演算子とコンストラクターが、同じ変換を行うように定義されています。
