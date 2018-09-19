---
title: コンパイラ エラー C2589 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2db5dde898a3e5918eed62b2b32231b5d7ed014f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046057"
---
# <a name="compiler-error-c2589"></a>コンパイラ エラー C2589

'identifier': 無効なトークンの右側にある ':: '

クラス、構造体または共用体の名前が、スコープ解決演算子 (2 つのコロン) の左側に表示された場合、右側のトークンは、クラス、構造体または共用体のメンバーにある必要があります。 それ以外の場合、任意のグローバル識別子が右側に表示できます。

スコープ解決演算子をオーバー ロードできません。

次の例では、C2589 が生成されます。

```
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```