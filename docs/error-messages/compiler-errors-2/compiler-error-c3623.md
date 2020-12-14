---
description: 詳細については、「コンパイラエラー C3623」を参照してください。
title: コンパイラ エラー C3623
ms.date: 11/04/2016
f1_keywords:
- C3623
helpviewer_keywords:
- C3623
ms.assetid: a0341b45-062a-4f67-beb9-ba74201ed1ed
ms.openlocfilehash: 042e530dc1529307c90b05771d662aaed4b60775
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222984"
---
# <a name="compiler-error-c3623"></a>コンパイラ エラー C3623

'variable': ビット フィールドは、マネージド型または WinRT 型ではサポートされていません。

マネージド クラスまたは WinRT クラスの変数に対して、ビット フィールドは使用できません。

次の例では C3623 が生成されます。

```cpp
// C3623.cpp
// compile with: /clr
using namespace System;
ref class CMyClass {
public:
   int i : 1;   // C3623
};

int main() {
   CMyClass^ pMyClass = gcnew CMyClass();
   pMyClass->i = 3;
   Console::Out->WriteLine(pMyClass->i);
}
```
