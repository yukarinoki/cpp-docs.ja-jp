---
title: コンパイラの警告 (レベル 1) C4144
ms.date: 11/04/2016
f1_keywords:
- C4144
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
ms.openlocfilehash: 99902edee371704c57a772e1b62f7ec4f41afb36
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163690"
---
# <a name="compiler-warning-level-1-c4144"></a>コンパイラの警告 (レベル 1) C4144

' expression ': switch 式としての関係式

指定された関係式は[switch](../../cpp/switch-statement-cpp.md)ステートメントの制御式として使用されました。 関連する case ステートメントには、ブール値が提供されます。 次の例では、C4144 が生成されます。

```cpp
// C4144.cpp
// compile with: /W1
int main()
{
   int i = 0;
   switch(!i) {   // C4144, remove the ! to resolve
      case 1:
         break;
      default:
         break;
   }
}
```
