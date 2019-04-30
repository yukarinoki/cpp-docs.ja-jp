---
title: コンパイラ エラー C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: 18d8f7130c34f5e1e33bc7aa9b9463f50c243045
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386942"
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