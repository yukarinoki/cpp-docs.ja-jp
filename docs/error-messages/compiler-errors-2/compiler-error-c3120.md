---
description: 詳細については、「コンパイラエラー C3120」を参照してください。
title: コンパイラエラー C3120
ms.date: 11/04/2016
f1_keywords:
- C3120
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
ms.openlocfilehash: 533f0df3da392c36b07af41b9493a7c404972760
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151074"
---
# <a name="compiler-error-c3120"></a>コンパイラエラー C3120

' method_name ': インターフェイスメソッドは可変個引数リストを受け取ることができません

インターフェイスメソッドは可変個引数リストを受け取ることができません。 たとえば、次のインターフェイス定義では C3120 が生成されます。

```cpp
// C3120.cpp
__interface A {
int X(int i, ...);    // C3120
};

int main(void) { return(0); }
```
