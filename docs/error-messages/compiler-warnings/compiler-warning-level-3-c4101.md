---
title: コンパイラの警告 (レベル 3) C4101 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1549a327329d438cb30bd6908e07419eb1b6bc1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060838"
---
# <a name="compiler-warning-level-3-c4101"></a>コンパイラの警告 (レベル 3) C4101

'identifier': 参照されていないローカル変数

ローカル変数は使用されません。 この警告は、明確な状況で発生します。

```
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

呼び出すときに、この警告が発生も、**静的**メンバー関数は、クラスのインスタンスを使用します。

```
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

コンパイラはこのような状況で、に関する情報を使用して`si`にアクセスする、**静的**関数がクラスのインスタンスを呼び出すには必要ありません、**静的**関数です。 そのため、警告。 この警告を解決するのには、次のことができます。

- インスタンス、コンパイラが使用して、コンス トラクターを追加`si`への呼び出しで`func`します。

- 削除、**静的**キーワードの定義から`func`します。

- 呼び出す、**静的**関数を明示的に:`int y = S::func();`します。