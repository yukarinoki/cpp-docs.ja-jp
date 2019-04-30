---
title: コンパイラ エラー C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 44f7988f9fedb882972b2823f2fe70d9512d4e87
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408681"
---
# <a name="compiler-error-c2801"></a>コンパイラ エラー C2801

'operator 演算子' は非静的メンバーである必要があります。

非静的メンバーとしてのみ、次の演算子をオーバー ロードできます。

- 割り当て `=`

- クラス メンバーへのアクセス `->`

- 添字演算子 `[]`

- 関数呼び出し `()`

C2801 の考えられる原因:

- オーバー ロードされた演算子は、クラス、構造体または共用体のメンバーではありません。

- オーバー ロードされた演算子が宣言されて`static`します。

- 次の例では、C2801 が生成されます。

```
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```