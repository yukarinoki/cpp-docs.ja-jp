---
title: コンパイラ エラー C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 59ceea942d9165f6f7c6161032e96404bc0dcba7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547252"
---
# <a name="compiler-error-c3533"></a>コンパイラ エラー C3533

'type': パラメーターは 'auto' を含む型を含めることはできません

メソッドまたはテンプレートのパラメーターを宣言することはできません、`auto`キーワード場合、既定[/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md)コンパイラ オプションが有効にします。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 削除、`auto`パラメーター宣言からキーワード。

## <a name="example"></a>例

関数パラメーターを宣言しているために、次の例で C3533、`auto`キーワードとそれをコンパイルした **/Zc:auto**します。

```
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

## <a name="example"></a>例

テンプレート パラメーターを宣言しているために、次の例が c++ 14 モードで C3533 を生成、`auto`キーワードとそれをコンパイルした **/Zc:auto**します。(C++ 17 でこれは 1 つの非型テンプレート パラメーターが推測される型を持つクラス テンプレートの有効な定義)。

```
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (変数の型の推測)](../../build/reference/zc-auto-deduce-variable-type.md)
