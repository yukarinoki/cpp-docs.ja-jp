---
title: コンパイラの警告 (レベル 1) C4965
ms.date: 11/04/2016
f1_keywords:
- C4965
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
ms.openlocfilehash: 7d77df395d680b467d1a04a3f59c9822842f99f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653103"
---
# <a name="compiler-warning-level-1-c4965"></a>コンパイラの警告 (レベル 1) C4965

整数 0 の暗黙的なボックスです。nullptr または明示的なキャストを使用して、

Visual C には、値型の暗黙的なボックス化が機能します。 現在 c++ マネージ拡張を使用して null 代入を発生させた命令がボックス化変換された整数への代入

詳細については、「 [ボックス化](../../windows/boxing-cpp-component-extensions.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

## <a name="example"></a>例

次の例では、C4965 が生成されます。

```
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