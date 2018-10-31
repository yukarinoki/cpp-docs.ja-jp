---
title: _ _uuidof 演算子 |Microsoft Docs
ms.custom: ''
ms.date: 10/10/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
- __uuidof
- _uuidof
dev_langs:
- C++
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c75e33dd7aab1e96a1d2d3464e974a7095f83f3f
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163856"
---
# <a name="uuidof-operator"></a>__uuidof 演算子

**Microsoft 固有の仕様**

式にアタッチされている GUID を取得します。

## <a name="syntax"></a>構文

```
__uuidof (expression)
```

## <a name="remarks"></a>Remarks

*式*型名、ポインター、参照、またはその型の配列にすることができます、これらの型、またはこれらの型の変数に特化したテンプレートです。 引数は、アタッチされた GUID を見つけるためにコンパイラが使用できる限り有効です。

この組み込みの特殊なケースはいつか**0**か、引数として NULL が指定されています。 この場合、 **_ _uuidof**はゼロで構成された GUID を返します。

このキーワードを使用すると、次のものにアタッチされている GUID を抽出できます。

- オブジェクトによって、 [uuid](../cpp/uuid-cpp.md)拡張属性。

- 作成されたライブラリ ブロック、[モジュール](../windows/module-cpp.md)属性。

> [!NOTE]
> デバッグ ビルドで **_ _uuidof**常に動的に (実行時) にオブジェクトを初期化します。 リリース ビルドで **_ _uuidof**静的 (コンパイル時) にオブジェクトを初期化できます。

以前のバージョンとの互換性のため **_uuidof**のシノニムです **_ _uuidof**しない限り、コンパイラ オプション[/Za\(言語拡張機能を無効にする)](../build/reference/za-ze-disable-language-extensions.md)は指定します。

## <a name="example"></a>例

次のコード (ole32.lib でコンパイル) は、module 属性で作成されたライブラリ ブロックの uuid を表示します。

```cpp
// expre_uuidof.cpp
// compile with: ole32.lib
#include "stdio.h"
#include "windows.h"

[emitidl];
[module(name="MyLib")];
[export]
struct stuff {
   int i;
};

int main() {
   LPOLESTR lpolestr;
   StringFromCLSID(__uuidof(MyLib), &lpolestr);
   wprintf_s(L"%s", lpolestr);
   CoTaskMemFree(lpolestr);
}
```

## <a name="comments"></a>コメント

ライブラリ名が不要になったスコープ内の場合、使用することができます`__LIBID_`の代わりに **_ _uuidof**します。 例えば:

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)