---
description: '詳細情報: コンパイラの警告 (レベル 1) C4965'
title: コンパイラの警告 (レベル 1) C4965
ms.date: 11/04/2016
f1_keywords:
- C4965
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
ms.openlocfilehash: a3e20fa7007daac6f9a1c6f4761e222d5ab1e86c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344277"
---
# <a name="compiler-warning-level-1-c4965"></a>コンパイラの警告 (レベル 1) C4965

整数0の暗黙的なボックスnullptr または明示的なキャストを使用する

Visual C++ は、値型の暗黙的なボックス化機能を備えています。 Managed Extensions for C++ を使用して null の割り当てが発生した命令が、ボックス化された int に割り当てられるようになりました。

詳細については、「 [ボックス化](../../extensions/boxing-cpp-component-extensions.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

## <a name="example"></a>例

次の例では、C4965 が生成されます。

```cpp
// C4965.cpp
// compile with: /clr /W1
int main() {
   System::Object ^o = 0;   // C4965

   // the previous line is the same as the following line
   // using Managed Extensions for C++
   // System::Object *o = __box(0);

   // OK
   System::Object ^o2 = nullptr;
   System::Object ^o3 = safe_cast<System::Object^>(0);
}
```
