---
description: '詳細情報: コンパイラの警告 (レベル 4) C4289'
title: コンパイラの警告 (レベル 4) C4289
ms.date: 11/04/2016
f1_keywords:
- C4289
helpviewer_keywords:
- C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
ms.openlocfilehash: c0b82702195aa7f5dcd88cd4e9bffbc1bbd1769f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294614"
---
# <a name="compiler-warning-level-4-c4289"></a>コンパイラの警告 (レベル 4) C4289

非標準の拡張が使用されています : 'var' : for ループで宣言したループ コントロール変数が for ループ スコープの外側で使用されています。

[/Ze](../../build/reference/za-ze-disable-language-extensions.md)および **/zc: forScope-** を使用してコンパイルする場合、 [for](../../cpp/for-statement-cpp.md)ループで宣言された変数は、-ループスコープの後に使用されていました **`for`** 。

/Ze を使用したループで標準動作を指定する方法については、「 [/zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) 」を参照してください **`for`** 。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4289 が生成されます。

```cpp
// C4289.cpp
// compile with: /W4 /Zc:forScope-
#pragma warning(default:4289)
int main() {
   for (int i = 0 ; ; )   // C4289
      break;
   i++;
}
```
