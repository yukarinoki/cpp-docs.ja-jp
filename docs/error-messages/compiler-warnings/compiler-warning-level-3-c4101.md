---
description: '詳細情報: コンパイラの警告 (レベル 3) C4101'
title: コンパイラの警告 (レベル 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: c5e358bea4e9a584242376ed86d1bb5af2deb734
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150632"
---
# <a name="compiler-warning-level-3-c4101"></a>コンパイラの警告 (レベル 3) C4101

' identifier ': 参照できないローカル変数です

ローカル変数は使用されません。 この警告は、明らかに次のような状況で発生します。

```cpp
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

ただし、この警告は、 **`static`** クラスのインスタンスを使用してメンバー関数を呼び出す場合にも発生します。

```cpp
// C4101b.cpp
// compile with:  /W3
struct S {
   static int func()
   {
      return 1;
   }
};

int main() {
   S si;   // C4101, si is never used
   int y = si.func();
   return y;
}
```

この場合、コンパイラはに関する情報を使用して関数にアクセスします `si` **`static`** が、関数を呼び出すためにクラスのインスタンスは必要ありません。したがって、警告が表示され **`static`** ます。 この警告を解決するには、次のようにします。

- コンストラクターを追加します。コンパイラは、の呼び出しでのインスタンスを使用し `si` `func` ます。

- **`static`** の定義からキーワードを削除 `func` します。

- 関数を **`static`** 明示的に呼び出し `int y = S::func();` ます。
