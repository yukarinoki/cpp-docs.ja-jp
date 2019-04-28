---
title: コンパイラ エラー C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: f4a17557e5e4ca1eb3f69561c964c9bbe24bb70d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303784"
---
# <a name="compiler-error-c2017"></a>コンパイラ エラー C2017

無効なエスケープ シーケンス

文字または文字列の外部で、\t など、エスケープ シーケンスが表示される定数。

次の例では、C2017 が生成されます。

```
// C2017.cpp
int main() {
   char test1='a'\n;   // C2017
   char test2='a\n';   // ok
}
```

C2017 は、エスケープ シーケンスを含む文字列を含む文字列化演算子を使用する場合に発生することができます。

次の例では、C2017 が生成されます。

```
// C2017b.cpp
#define TestDfn(x) AfxMessageBox(#x)
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017
```