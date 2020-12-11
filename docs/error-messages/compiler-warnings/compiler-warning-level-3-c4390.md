---
description: '詳細情報: コンパイラの警告 (レベル 3) C4390'
title: コンパイラの警告 (レベル 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 8067d4beae44e098085122968a227f6ff8bc8b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160442"
---
# <a name="compiler-warning-level-3-c4390"></a>コンパイラの警告 (レベル 3) C4390

'; ': 空の制御されたステートメントが見つかりました。これは目的ですか。

命令を含まない制御ステートメントの後にセミコロンが見つかりました。

マクロが原因で C4390 を取得した場合は、 [警告](../../preprocessor/warning.md) プラグマを使用して、マクロを含むモジュールの C4390 を無効にする必要があります。

次の例では、C4390 が生成されます。

```cpp
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```
