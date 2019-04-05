---
title: deprecated (C/C++)
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.deprecated
- deprecated_CPP
helpviewer_keywords:
- deprecated pragma
- pragmas, deprecated
ms.assetid: 9c046f12-7875-499a-8d5d-12f8642fed2d
ms.openlocfilehash: 262b23e6e4813a5e22bc3f4e7c9a18efb9988a7c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023315"
---
# <a name="deprecated-cc"></a>deprecated (C/C++)

**deprecated**プラグマを使用すると、関数、型、またはその他の識別子が将来のリリースでサポートされなくなる可能性があるか、使用できなくなることを示すことができます。

> [!NOTE]
> C++ 14 について`[[deprecated]]`属性、およびそれを使用するタイミングに関するガイダンスは、vs を Microsoft declspec または pragma 属性を参照してください[C++ の標準属性](../cpp/attributes.md)属性。

## <a name="syntax"></a>構文

```
#pragma deprecated( identifier1 [,identifier2, ...] )
```

## <a name="remarks"></a>Remarks

コンパイラがで指定された識別子を検出した場合、**deprecated**プラグマ、コンパイラの警告を発行[C4995](../error-messages/compiler-warnings/compiler-warning-level-3-c4995.md)します。

マクロ名の使用を避けることができます。 マクロ名を引用符で囲んで配置します。そうしないと、マクロ展開が発生します。

**deprecated**プラグマは、すべての一致する識別子で機能し、アカウントに署名を受け取らない、オーバー ロードされた関数の特定のバージョンを非推奨の最適なオプションではありません。 スコープに取り込まれるすべての一致する関数名は、警告をトリガーします。

C++ 14 を使用することをお勧めします。`[[deprecated]]`属性は、可能であれば、の代わりに、**deprecated**プラグマ。 Microsoft 固有[__declspec(deprecated)](../cpp/deprecated-cpp.md)宣言修飾子はより多くの場合の方が適切でも、**deprecated**プラグマ。 `[[deprecated]]`属性と`__declspec(deprecated)`修飾子を使用すると、オーバー ロードされた関数の特定のフォームの非推奨のステータスを指定できます。 診断の警告のみに表示されます、特定のオーバー ロードされた関数への参照属性または修飾子に適用されます。

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

[プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
