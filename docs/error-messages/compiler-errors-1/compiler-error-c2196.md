---
description: 詳細については、「コンパイラエラー C2196」を参照してください。
title: コンパイラ エラー C2196
ms.date: 11/04/2016
f1_keywords:
- C2196
helpviewer_keywords:
- C2196
ms.assetid: fd2f6a58-48ce-4e58-96f8-e37720feb8e7
ms.openlocfilehash: 7c82cd145cff43d8773f87e65a09eee32185ffb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305470"
---
# <a name="compiler-error-c2196"></a>コンパイラ エラー C2196

case の値 'value' は既に使用されています。

switch ステートメントで、同じ case 値を複数回使用します。

次の例では C2196 が生成されます。

```cpp
// C2196.cpp
int main() {
   int i = 0;
   switch( i ) {
   case 0:
      break;
   case 0:   // C2196
   // try the following line instead
   // case 1:
      break;
   }
}
```
