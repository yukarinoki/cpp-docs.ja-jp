---
description: 詳細については、「コンパイラエラー C2017」を参照してください。
title: コンパイラエラー C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: c70bd39cb15a0eff5d209a6fc76e3dc44b990d8e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220904"
---
# <a name="compiler-error-c2017"></a>コンパイラエラー C2017

無効なエスケープシーケンスです。

\T などのエスケープシーケンスは、文字または文字列定数の外側に出現します。

次の例では、C2017 が生成されます。

```cpp
// C2017.cpp
int main() {
   char test1='a'\n;   // C2017
   char test2='a\n';   // ok
}
```

C2017 は、エスケープシーケンスを含む文字列で stringize 演算子が使用されている場合に発生する可能性があります。

次の例では、C2017 が生成されます。

```cpp
// C2017b.cpp
#define TestDfn(x) AfxMessageBox(#x)
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017
```
