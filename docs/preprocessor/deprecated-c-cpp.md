---
description: '詳細情報: 非推奨のプラグマ'
title: 非推奨のプラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.deprecated
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: b3f7e8bf17e98f6e6f57511f3c0c9a94a9388bf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300776"
---
# <a name="deprecated-pragma"></a>非推奨のプラグマ

プラグマでは、 **`deprecated`** 関数、型、またはその他の識別子が将来のリリースでサポートされなくなったり、使用されなくなったりすることを示すことができます。

> [!NOTE]
> C++ 14 属性の詳細 `[[deprecated]]` と、Microsoft 修飾子またはプラグマではなくこの属性を使用する場合のガイダンスについ `__declspec(deprecated)` ては **`deprecated`** 、「 [c++ の属性](../cpp/attributes.md)」を参照してください。

## <a name="syntax"></a>構文

> **#pragma 非推奨 (** *identifier1* [ **,** *identifier2* ...] **)**

## <a name="remarks"></a>解説

コンパイラは、プラグマによって指定された識別子を検出すると **`deprecated`** 、コンパイラの警告 [C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)を発行します。

マクロ名の使用を避けることができます。 マクロ名を引用符で囲んで配置します。そうしないと、マクロ展開が発生します。

**`deprecated`** プラグマはすべての一致する識別子に対して機能し、署名は考慮されないため、オーバーロードされた関数の特定のバージョンを非推奨するのに最適な方法ではありません。 スコープ内にある一致する関数名は、警告をトリガーします。

可能であれば、プラグマではなく C++ 14 属性を使用することをお勧めし `[[deprecated]]` **`deprecated`** ます。 Microsoft 固有の [__declspec (非推奨)](../cpp/deprecated-cpp.md) 宣言修飾子も、多くの場合、プラグマよりも適してい **`deprecated`** ます。 `[[deprecated]]`属性と修飾子を使用すると、オーバーロードされた `__declspec(deprecated)` 関数の特定の形式に非推奨の状態を指定できます。 診断警告は、属性または修飾子が適用される特定のオーバーロードされた関数への参照にのみ表示されます。

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

[プラグマ ディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
