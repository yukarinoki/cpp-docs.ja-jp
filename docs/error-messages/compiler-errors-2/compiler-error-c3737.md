---
title: コンパイラ エラー C3737
ms.date: 11/04/2016
f1_keywords:
- C3737
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
ms.openlocfilehash: b6c2a85556e96ff6176e158b7d75a844bb5710d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327887"
---
# <a name="compiler-error-c3737"></a>コンパイラ エラー C3737

'delegate': デリゲートは、明示的な呼び出し規則がありません

指定することはできません、[呼び出し規約](../../cpp/calling-conventions.md)の`delegate`します。

## <a name="example"></a>例

次の例では、C3737 が生成されます。

```
// C3737a.cpp
// compile with: /clr
delegate void __stdcall MyFunc();   // C3737
// Try the following line instead.
// delegate void MyFunc();

int main() {
}
```
