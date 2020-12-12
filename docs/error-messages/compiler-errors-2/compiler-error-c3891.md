---
description: 詳細については、「コンパイラエラー C3891」を参照してください。
title: コンパイラ エラー C3891
ms.date: 11/04/2016
f1_keywords:
- C3891
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
ms.openlocfilehash: df853f3ed0a163b48e75d54561d00298edd215b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144301"
---
# <a name="compiler-error-c3891"></a>コンパイラ エラー C3891

' var ': リテラルデータメンバーを左辺値として使用することはできません。

[リテラル](../../extensions/literal-cpp-component-extensions.md)変数は定数であり、宣言で初期化された後に値を変更することはできません。

次の例では、C3891 が生成されます。

```cpp
// C3891.cpp
// compile with: /clr
ref struct Y1 {
   literal int staticConst = 9;
};

int main() {
   Y1::staticConst = 0;   // C3891
}
```
