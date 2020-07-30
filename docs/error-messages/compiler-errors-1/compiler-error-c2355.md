---
title: コンパイラ エラー C2355
ms.date: 11/04/2016
f1_keywords:
- C2355
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
ms.openlocfilehash: 4e78d20fb59beead08aaddcf85138f845cfc0390
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212762"
---
# <a name="compiler-error-c2355"></a>コンパイラ エラー C2355

'this' : 静的でないメンバー関数の内部または静的でないデータ メンバー初期化子においてのみ参照できます

ポインターは、 **`this`** 非静的メンバー関数内または非静的データメンバー初期化子内でのみ有効です。 このエラーは、クラス宣言外のメンバー関数の定義のクラス スコープが適切に修飾されていないときに発生することがあります。 このエラーは、 **`this`** ポインターがクラスで宣言されていない関数で使用されている場合にも発生する可能性があります。

この問題を解決するには、メンバー関数の定義とメンバー関数の宣言がクラス内で一致していることと、メンバー関数が静的として宣言されていないことを確認します。 データ メンバー初期化子については、データ メンバーが静的として宣言されていないことを確認します。

次の例では、C2355 を生成し、その修正方法を示しています。

```cpp
// C2355.cpp
// compile with: /c
class MyClass {};
MyClass *p = this;   // C2355

// OK
class MyClass2 {
public:
   void Test() {
      MyClass2 *p = this;
   }
};
```
