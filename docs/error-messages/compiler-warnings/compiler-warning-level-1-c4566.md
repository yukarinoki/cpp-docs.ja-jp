---
title: コンパイラの警告 (レベル 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: c864feb2478e9f99ad6e4c0087dcef72b55de601
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397265"
---
# <a name="compiler-warning-level-1-c4566"></a>コンパイラの警告 (レベル 1) C4566

ユニバーサル文字名 'char' で表される文字は、現在のコード ページ (ページ) で表すことができません。

現在の ANSI コード ページではないすべての Unicode 文字を表現できます。

ナロー文字列 (1 バイト文字) は、ワイド文字列 (2 バイト文字) はないマルチバイト文字に変換されます。

次の例では、C4566 が生成されます。

```
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```