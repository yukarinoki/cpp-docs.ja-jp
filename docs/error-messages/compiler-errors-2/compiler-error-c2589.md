---
description: 詳細については、「コンパイラエラー C2589」を参照してください。
title: コンパイラ エラー C2589
ms.date: 11/04/2016
f1_keywords:
- C2589
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
ms.openlocfilehash: b874988f65ef41a9cde19e4c0229a6cb54859b28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177498"
---
# <a name="compiler-error-c2589"></a>コンパイラ エラー C2589

' identifier ': ':: ' の右側に無効なトークンがあります

クラス、構造体、または共用体の名前がスコープ解決演算子 (2 つのコロン) の左側に表示される場合、右側のトークンはクラス、構造体、または共用体のメンバーである必要があります。 それ以外の場合は、任意のグローバル識別子を右側に表示できます。

スコープ解決演算子をオーバーロードすることはできません。

次の例では、C2589 が生成されます。

```cpp
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```
