---
title: コンパイラの警告 (レベル 2) C4309
ms.date: 11/04/2016
f1_keywords:
- C4309
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
ms.openlocfilehash: a307d941f6225c9e431ad71a6385229bd01957f9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161868"
---
# <a name="compiler-warning-level-2-c4309"></a>コンパイラの警告 (レベル 2) C4309

' conversion ': 定数値の切り捨て

型変換によって、定数が割り当てられた領域を超えています。 定数には、より大きな型を使用することが必要になる場合があります。

次の例では、C4309 が生成されます。

```cpp
// C4309.cpp
// compile with: /W2
int main()
{
   char c = 128;   // C4309
}
```
