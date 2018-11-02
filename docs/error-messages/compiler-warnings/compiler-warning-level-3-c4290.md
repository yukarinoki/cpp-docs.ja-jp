---
title: コンパイラの警告 (レベル 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: c585294686298a1197d437d41a0d541f1268985f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512737"
---
# <a name="compiler-warning-level-3-c4290"></a>コンパイラの警告 (レベル 3) C4290

関数の指定以外 C++ 例外の指定は無視されます。

関数は、Visual C を受け入れますが、実装していない例外指定を使用して宣言されます。 コードでは、例外は、コンパイル時に無視される仕様は、再コンパイルする必要があります、リンクを再利用後で例外の仕様をサポートしているバージョン。

詳細については、次を参照してください。[例外の仕様 (スロー)](../../cpp/exception-specifications-throw-cpp.md)します。

使用してこの警告を回避することができます、[警告](../../preprocessor/warning.md)プラグマ。

```
#pragma warning( disable : 4290 )
```

次のコード サンプルでは、C4290 が生成されます。

```
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```