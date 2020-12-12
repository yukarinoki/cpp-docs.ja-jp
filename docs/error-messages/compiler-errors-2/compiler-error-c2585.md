---
description: 詳細については、「コンパイラエラー C2585」を参照してください。
title: コンパイラ エラー C2585
ms.date: 11/04/2016
f1_keywords:
- C2585
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
ms.openlocfilehash: 568e5db1ca160b9fd13596d4f94f646cb4cf0bdd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177654"
---
# <a name="compiler-error-c2585"></a>コンパイラ エラー C2585

' type ' への明示的な変換があいまいです

型変換によって複数の結果が生成される可能性があります。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 多重継承に基づいたクラスまたは構造体型からの変換。 型が同じ基底クラスを2回以上継承する場合、変換関数または演算子は、スコープ解決 () を使用して、 `::` 変換で使用する継承クラスを指定する必要があります。

1. 変換演算子とコンストラクターが、同じ変換を行うように定義されています。
