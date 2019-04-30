---
title: コンパイラの警告 (レベル 1) C4144
ms.date: 11/04/2016
f1_keywords:
- C4144
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
ms.openlocfilehash: b2406357baf70e45566f2d2f25839d151bac4186
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352950"
---
# <a name="compiler-warning-level-1-c4144"></a>コンパイラの警告 (レベル 1) C4144

'expression' : relational expression as switch expression

指定した関係式は、の制御式として使用された、[切り替える](../../cpp/switch-statement-cpp.md)ステートメント。 関連付けられた case ステートメントには、ブール値が提供されます。 次の例では、C4144 が生成されます。

```
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