---
description: '詳細情報: コンパイラの警告 (レベル 3) C4310'
title: コンパイラの警告 (レベル 3) C4310
ms.date: 11/04/2016
f1_keywords:
- C4310
helpviewer_keywords:
- C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
ms.openlocfilehash: 581d07005bd9932d4b0898a161a28b66e7d58b44
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344043"
---
# <a name="compiler-warning-level-3-c4310"></a>コンパイラの警告 (レベル 3) C4310

cast は定数値を切り捨てます

定数値は、より小さな型にキャストされます。 コンパイラは、データを切り捨てるキャストを実行します。 次の例では、C4310 が生成されます。

```cpp
// C4310.cpp
// compile with: /W4
int main() {
   long int a;
   a = (char) 128;   // C4310, use value 0-127 to resolve
}
```
