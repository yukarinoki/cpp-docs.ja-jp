---
title: 非推奨のプラグマ
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.deprecated
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 6caf5283aea848186c8bd6f9dd2009bb8d8ee8b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167629"
---
# <a name="deprecated-pragma"></a>非推奨のプラグマ

**非推奨**のプラグマを使用すると、関数、型、またはその他の識別子が将来のリリースでサポートされなくなったり、使用されなくなったりすることを示すことができます。

> [!NOTE]
> C++ 14 `[[deprecated]]` 属性の詳細、および Microsoft `__declspec(deprecated)` 修飾子または**非推奨**のプラグマの代わりにその属性を使用する場合のガイダンスについては、「 [」のC++「属性](../cpp/attributes.md)」を参照してください。

## <a name="syntax"></a>構文

> **#pragma 非推奨 (** *identifier1* [ **,** *identifier2* ...] **)**

## <a name="remarks"></a>解説

コンパイラは、**非推奨**のプラグマによって指定された識別子を検出すると、コンパイラの警告[C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)を発行します。

マクロ名の使用を避けることができます。 マクロ名を引用符で囲んで配置します。そうしないと、マクロ展開が発生します。

**非推奨**のプラグマはすべての一致する識別子に対して機能し、署名は考慮されないため、オーバーロードされた関数の特定のバージョンを非推奨するのに最適な方法ではありません。 スコープ内にある一致する関数名は、警告をトリガーします。

**非推奨**のプラグマではなく、可能な場合は c++ 14 の `[[deprecated]]` 属性を使用することをお勧めします。 Microsoft 固有の[__declspec (非推奨)](../cpp/deprecated-cpp.md)宣言修飾子は、**非推奨**のプラグマよりも多くの場合に適しています。 `[[deprecated]]` 属性および `__declspec(deprecated)` 修飾子を使用すると、オーバーロードされた関数の特定の形式に非推奨の状態を指定できます。 診断の警告のみに表示されます、特定のオーバー ロードされた関数への参照属性または修飾子に適用されます。

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

## <a name="see-also"></a>参照

[プラグマディレクティブと __pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
