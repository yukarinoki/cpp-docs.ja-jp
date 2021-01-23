---
description: pragmaMicrosoft C/c + + で非推奨とされるディレクティブの詳細について説明します。
title: れ pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.deprecated
helpviewer_keywords:
- deprecated pragma
- pragma, deprecated
no-loc:
- pragma
ms.openlocfilehash: 47e049f415b243a4c9959c7adc789f32f91de7ba
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712909"
---
# <a name="deprecated-no-locpragma"></a>`deprecated` pragma

では、 **`deprecated`** pragma 関数、型、またはその他の識別子が将来のリリースでサポートされなくなったり、使用されなくなったりすることを示すことができます。

> [!NOTE]
> C++ 14 属性の詳細 `[[deprecated]]` と、Microsoft 修飾子またはの代わりにその属性を使用する場合のガイダンスについて `__declspec(deprecated)` は **`deprecated`** pragma 、「 [c++ の属性](../cpp/attributes.md)」を参照してください。

## <a name="syntax"></a>構文

> **`#pragma deprecated(`***identifier1* [ **`,`** *identifier2* ...]**`)`**

## <a name="remarks"></a>解説

コンパイラは、によって指定された識別子を検出すると **`deprecated`** pragma 、コンパイラの警告 [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)を発行します。

マクロ名の使用を避けることができます。 マクロ名を引用符で囲んで配置します。そうしないと、マクロ展開が発生します。

は **`deprecated`** pragma すべての一致する識別子に対して機能し、署名を考慮しないため、オーバーロードされた関数の特定のバージョンを非推奨するのに最適な方法ではありません。 スコープ内にある一致する関数名は、警告をトリガーします。

ではなく、可能な場合は C++ 14 属性を使用することをお勧めし `[[deprecated]]` **`deprecated`** pragma ます。 また、Microsoft 固有の [`__declspec(deprecated)`](../cpp/deprecated-cpp.md) 宣言修飾子は、よりも多くの場合に適して **`deprecated`** pragma います。 `[[deprecated]]`属性と修飾子を使用すると、オーバーロードされた `__declspec(deprecated)` 関数の特定の形式に非推奨の状態を指定できます。 診断警告は、属性または修飾子が適用される特定のオーバーロードされた関数への参照にのみ表示されます。

## <a name="example"></a>例

```cpp
// pragma_directive_deprecated.cpp
// compile with: /W3
#include <stdio.h>
void func1(void) {
}

void func2(void) {
}

int main() {
   func1();
   func2();
   #pragma deprecated(func1, func2)
   func1();   // C4995
   func2();   // C4995
}
```

次のサンプルでは、クラスの使用を避ける方法を示します。

```cpp
// pragma_directive_deprecated2.cpp
// compile with: /W3
#pragma deprecated(X)
class X {  // C4995
public:
   void f(){}
};

int main() {
   X x;   // C4995
}
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
