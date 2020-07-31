---
title: コンパイラ エラー C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: cfb89c79534318ab1fbcaa06667d594bfe2f1157
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214595"
---
# <a name="compiler-error-c2801"></a>コンパイラ エラー C2801

' operator operator ' は静的でないメンバーでなければなりません

次の演算子は、非静的メンバーとしてのみオーバーロードできます。

- 割り当て`=`

- クラスメンバーアクセス`->`

- 時`[]`

- 関数呼び出し`()`

考えられる C2801 原因:

- オーバーロードされた演算子は、クラス、構造体、または共用体のメンバーではありません。

- オーバーロードされた演算子が宣言されて **`static`** います。

- 次の例では、C2801 が生成されます。

```cpp
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```
