---
description: '詳細情報: `__uuidof` 演算子'
title: __uuidof 演算子
ms.date: 10/10/2018
f1_keywords:
- __LIBID_cpp
- __uuidof_cpp
- __uuidof
- _uuidof
helpviewer_keywords:
- __uuidof keyword [C++]
- __LIBID_ keyword [C++]
ms.assetid: badfe709-809b-4b66-ad48-ee35039d25c6
ms.openlocfilehash: e6c14ac6f00b5e6314e1e4d844aea479fa714984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116718"
---
# <a name="__uuidof-operator"></a>`__uuidof` 演算子

**Microsoft 固有の仕様**

式にアタッチされている GUID を取得します。

## <a name="syntax"></a>構文

> **`__uuidof (`***式***`)`**

## <a name="remarks"></a>解説

*式* には、型名、ポインター、参照、またはその型の配列、これらの型に特化したテンプレート、またはこれらの型の変数を指定できます。 引数は、アタッチされた GUID を見つけるためにコンパイラが使用できる限り有効です。

この組み込みの特別なケースとして、引数として **0** または NULL が指定されている場合があります。 この場合、 **`__uuidof`** はゼロで構成された GUID を返します。

このキーワードを使用すると、次のものにアタッチされている GUID を抽出できます。

- 拡張属性によってオブジェクト [`uuid`](../cpp/uuid-cpp.md) 。

- 属性を使用して作成されたライブラリブロック [`module`](../windows/attributes/module-cpp.md) 。

> [!NOTE]
> デバッグビルドでは、は **`__uuidof`** 常に (実行時に) 動的にオブジェクトを初期化します。 リリースビルドでは、は **`__uuidof`** 静的に (コンパイル時に) オブジェクトを初期化できます。

以前のバージョンとの互換性のために、 **`_uuidof`** **`__uuidof`** コンパイラオプションの [ [ `/Za` \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない場合、はのシノニムになります。

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

## <a name="comments"></a>説明

ライブラリ名がスコープ内にない場合は、の代わりにを使用でき `__LIBID_` **`__uuidof`** ます。 次に例を示します。

```cpp
StringFromCLSID(__LIBID_, &lpolestr);
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[キーワード](../cpp/keywords-cpp.md)
