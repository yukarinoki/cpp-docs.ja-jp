---
description: '詳細情報: コンパイラの警告 (レベル 1) C4010'
title: コンパイラの警告 (レベル 1) C4010
ms.date: 11/04/2016
f1_keywords:
- C4010
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
ms.openlocfilehash: 899e34e0835cce02ab5d11b6c64ae604369f93d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241587"
---
# <a name="compiler-warning-level-1-c4010"></a>コンパイラの警告 (レベル 1) C4010

単一行コメントには、行連結文字が含まれます

//によって導入される1行のコメントには、 \\ 行連結文字として機能する円記号 () が含まれています。 コンパイラは次の行を継続と見なし、それをコメントとして扱います。

一部の構文指向エディターは、継続文字の後の行をコメントとして示していません。 この警告の原因となった行の構文の色分けを無視します。

次の例では、C4010 が生成されます。

```cpp
// C4010.cpp
// compile with: /WX
int main() {
   // the next line is also a comment because of the backslash \
   int a = 3; // C4010
   a++;
}
```
