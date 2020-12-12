---
description: 詳細については、「コンパイラエラー C2563」を参照してください。
title: コンパイラ エラー C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 2243e0820b2e69d6bc05351fdba4600188a3ac08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209153"
---
# <a name="compiler-error-c2563"></a>コンパイラ エラー C2563

仮パラメーターリストが一致しません

関数 (または関数へのポインター) の仮パラメーターリストが、別の関数 (またはメンバー関数へのポインター) の仮パラメーターリストと一致しません。 その結果、関数またはポインターの割り当てを行うことはできません。

次の例では、C2563 が生成されます。

```cpp
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```
