---
title: コンパイラ エラー C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: c77c5c0fff8f8d9c1c64ba11773503b197006b67
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91510107"
---
# <a name="compiler-error-c3533"></a>コンパイラ エラー C3533

' type ': パラメーターに ' auto ' を含む型を指定することはできません

**`auto`** 既定の[/zc: auto](../../build/reference/zc-auto-deduce-variable-type.md)コンパイラオプションが有効になっている場合、メソッドまたはテンプレートパラメーターをキーワードで宣言することはできません。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. **`auto`** パラメーター宣言からキーワードを削除します。

## <a name="examples"></a>例

次の例では、キーワードを使用して関数パラメーターを宣言 **`auto`** し、 **/zc: auto**を指定してコンパイルするため、C3533 が生成されます。

```cpp
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

次の例では、C3533 を C++ 14 モードで生成します。これは、キーワードを使用してテンプレートパラメーターを宣言 **`auto`** し、 **/zc: auto**を指定してコンパイルするためです。(C++ 17 では、これは、型が推測される単一の非型テンプレートパラメーターを持つクラステンプレートの有効な定義です)。

```cpp
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-cpp.md)<br/>
[/Zc: auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)
