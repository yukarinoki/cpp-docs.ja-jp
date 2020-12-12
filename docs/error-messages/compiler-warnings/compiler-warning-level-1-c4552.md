---
description: '詳細情報: コンパイラの警告 (レベル 1) C4552'
title: コンパイラの警告 (レベル 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 52cea1aac8b46fc5c1958bd917f6ab910ef326c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265923"
---
# <a name="compiler-warning-level-1-c4552"></a>コンパイラの警告 (レベル 1) C4552

' operator ': 演算子は無効です。副作用のある演算子が必要です

式ステートメントに、式の先頭として副作用のない演算子が含まれている場合は、間違いであると思います。

この警告をオーバーライドするには、式をかっこで囲みます。

次の例では、C4552 が生成されます。

```cpp
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```
