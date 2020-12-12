---
description: '詳細情報: コンパイラの警告 (レベル 1) C4566'
title: コンパイラの警告 (レベル 1) C4566
ms.date: 11/04/2016
f1_keywords:
- C4566
helpviewer_keywords:
- C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
ms.openlocfilehash: 2e0d1f5b80a42d58f2866109957e466d3ab36cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332237"
---
# <a name="compiler-warning-level-1-c4566"></a>コンパイラの警告 (レベル 1) C4566

ユニバーサル文字名 ' char ' で表される文字は、現在のコードページ (ページ) では表現できません

現在の ANSI コードページですべての Unicode 文字を表すことはできません。

ナロー文字列 (1 バイト文字) はマルチバイト文字に変換されますが、ワイド文字列 (2 バイト文字) は変換されません。

次の例では、C4566 が生成されます。

```cpp
// C4566.cpp
// compile with: /W1
int main() {
   char c1 = '\u03a0';   // C4566
   char c2 = '\u0642';   // C4566

   wchar_t c3 = L'\u03a0';   // OK
   wchar_t c4 = L'\u0642';   // OK
}
```
