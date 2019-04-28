---
title: コンパイラ エラー C3087
ms.date: 11/04/2016
f1_keywords:
- C3087
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
ms.openlocfilehash: 43044e0708ce9c30099c7d25935a8ff9605f45ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243259"
---
# <a name="compiler-error-c3087"></a>コンパイラ エラー C3087

'named_argument': 'attribute' の呼び出しは、既にこのメンバーを初期化しています

名前付き引数が、同じ値の名前なし引数と同じ属性ブロックに指定されました。 名前付引数か名前なし引数の、どちらか 1 つだけを指定します。

## <a name="example"></a>例

次の例では C3087 が生成されます。

```
// C3087.cpp
// compile with: /c
[idl_quote("quote1", text="quote2")];   // C3087
[idl_quote(text="quote3")];   // OK
[idl_quote("quote4")];   // OK
```