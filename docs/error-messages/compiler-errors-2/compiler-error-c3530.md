---
title: コンパイラ エラー C3530
ms.date: 11/04/2016
f1_keywords:
- C3530
helpviewer_keywords:
- C3530
ms.assetid: 21be81ce-b699-4c74-81bc-80a0c34d2d5a
ms.openlocfilehash: 90f6000c7d4c4bfa0d610bd5942df0b958e47c60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643628"
---
# <a name="compiler-error-c3530"></a>コンパイラ エラー C3530

'auto' は、他の型指定子と組み合わせることはできません。

型指定子を併用、`auto`キーワード。

### <a name="to-correct-this-error"></a>このエラーを解決するには

1. 使用する変数宣言で型指定子を使用しないでください、`auto`キーワード。

## <a name="example"></a>例

次の例では C3530 のため変数`x`が両方で宣言されて、`auto`キーワードと型`int`、例をコンパイルしたので **/Zc:auto**します。

```
// C3530.cpp
// Compile with /Zc:auto
int main()
{
   auto int x;   // C3530
   return 0;
}
```

## <a name="see-also"></a>関連項目

[auto キーワード](../../cpp/auto-keyword.md)