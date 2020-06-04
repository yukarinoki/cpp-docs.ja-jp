---
title: コンパイラの警告 (レベル 1) C4965
ms.date: 11/04/2016
f1_keywords:
- C4965
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
ms.openlocfilehash: e882cabdf38fd9bc926fbaa04352ba9d0ace90ce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174415"
---
# <a name="compiler-warning-level-1-c4965"></a>コンパイラの警告 (レベル 1) C4965

整数0の暗黙的なボックスnullptr または明示的なキャストを使用する

ビジュアルC++は、値型の暗黙的なボックス化機能を備えています。 現在、のマネージ拡張を使用して null 代入をC++行った命令は、ボックス化された int への代入になります。

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
