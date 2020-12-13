---
description: '詳細情報: コンパイラの警告 (レベル 4) C4255'
title: コンパイラの警告 (レベル 4) C4255
ms.date: 11/04/2016
f1_keywords:
- C4255
helpviewer_keywords:
- C4255
ms.assetid: 2087b635-4b4c-4182-8a01-c26770d2bb88
ms.openlocfilehash: 31c5a121c944a65a0a5c3cd13d3e6201c3ad43a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339159"
---
# <a name="compiler-warning-level-4-c4255"></a>コンパイラの警告 (レベル 4) C4255

' function ': 関数プロトタイプが指定されていません: ' () ' を ' (void) ' に変換しています

コンパイラは、関数に対する引数の明示的なリストを見つけることができませんでした。 この警告は、C コンパイラでのみ使用されます。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4255 が生成されます。

```c
// C4255.c
// compile with: /W4 /WX
#pragma warning (default : 4255)

void f()  { // C4255
// try the following line instead
//void f(void) {
}

int main(int argc, char *argv[]) {
   f();
}
```
