---
title: コンパイラの警告 C4972
ms.date: 11/04/2016
f1_keywords:
- C4972
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
ms.openlocfilehash: dcf08f26809c7c61e3e00c41c555416c95f4a0e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598836"
---
# <a name="compiler-warning-c4972"></a>コンパイラの警告 C4972

アンボックス操作の結果を左辺の値として扱う、または直接変更することは検証可能ではありません

ハンドルの値型への逆参照 (ボックス化解除) およびその後の割り当てを検証できません。

詳細については、「 [ボックス化](../../windows/boxing-cpp-component-extensions.md)で定義されているインターフェイスのプライベート C++ 固有の実装です。

## <a name="example"></a>例

次の例では C4972 警告が生成されます。

```
// C4972.cpp
// compile with: /clr:safe
using namespace System;
ref struct R {
   int ^ p;   // a value type
};

int main() {
   R ^ r = gcnew R;
   *(r->p) = 10;   // C4972

   // OK
   r->p = 10;
   Console::WriteLine( r->p );
   Console::WriteLine( *(r->p) );
}
```