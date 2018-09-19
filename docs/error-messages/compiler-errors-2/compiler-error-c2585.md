---
title: コンパイラ エラー C2585 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ec7b1e9c1e5e7894740cc80f9c030fa1ee26ec0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028845"
---
# <a name="compiler-error-c2585"></a>コンパイラ エラー C2585

'type' に明示的な変換があいまいです。

型変換では、1 つ以上の結果を生成できます。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには

1. 多重継承に基づく、クラスまたは構造体の型から変換します。 変換関数または演算子がスコープ解決演算子を使用する必要があります型は複数回、同じ基本クラスを継承している場合 (`::`) の変換に使用する継承されたクラスを指定します。

1. 同じ変換を行う変換演算子およびコンス トラクターを定義されています。