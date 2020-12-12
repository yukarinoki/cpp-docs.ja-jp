---
description: 詳細については、「コンパイラエラー C3087」を参照してください。
title: コンパイラ エラー C3087
ms.date: 11/04/2016
f1_keywords:
- C3087
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
ms.openlocfilehash: 0700f10711610e09a797c647e0e107a3ef41f115
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116367"
---
# <a name="compiler-error-c3087"></a>コンパイラ エラー C3087

'named_argument': 'attribute' の呼び出しは、既にこのメンバーを初期化しています

名前付き引数が、同じ値の名前なし引数と同じ属性ブロックに指定されました。 名前付引数か名前なし引数の、どちらか 1 つだけを指定します。

## <a name="example"></a>例

次の例では C3087 が生成されます。

```cpp
// C3087.cpp
// compile with: /c
[idl_quote("quote1", text="quote2")];   // C3087
[idl_quote(text="quote3")];   // OK
[idl_quote("quote4")];   // OK
```
