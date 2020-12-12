---
description: '詳細情報: コンパイラの警告 (レベル 1) C4183'
title: コンパイラの警告 (レベル 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: 1e9753637d0ee52ef40ce875e4e2d66fbdaab9db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266677"
---
# <a name="compiler-warning-level-1-c4183"></a>コンパイラの警告 (レベル 1) C4183

' identifier ': 戻り値の型がありません。' int ' を返すメンバー関数であると想定されます

クラスまたは構造体のメンバー関数のインライン定義に戻り値の型がありません。 このメンバー関数は、の既定の戻り値の型を持つと見なされ **`int`** ます。

次の例では、C4183 が生成されます。

```cpp
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```
