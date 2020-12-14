---
description: 詳細については、「コンパイラエラー C3737」を参照してください。
title: コンパイラ エラー C3737
ms.date: 11/04/2016
f1_keywords:
- C3737
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
ms.openlocfilehash: 0b7c604f49c710334eb9ddfafa253df90c72103c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244979"
---
# <a name="compiler-error-c3737"></a>コンパイラ エラー C3737

' delegate ': デリゲートに明示的な呼び出し規約を含めることはできません

の [呼び出し規約](../../cpp/calling-conventions.md) を指定することはできません **`delegate`** 。

## <a name="example"></a>例

次の例では、C3737 が生成されます。

```cpp
// C3737a.cpp
// compile with: /clr
delegate void __stdcall MyFunc();   // C3737
// Try the following line instead.
// delegate void MyFunc();

int main() {
}
```
