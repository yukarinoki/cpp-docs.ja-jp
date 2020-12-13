---
description: '詳細情報: コンパイラの警告 (レベル 1) C4144'
title: コンパイラの警告 (レベル 1) C4144
ms.date: 11/04/2016
f1_keywords:
- C4144
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
ms.openlocfilehash: 11f276d4790c11654655fea7cf814dfb30a6787b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136306"
---
# <a name="compiler-warning-level-1-c4144"></a>コンパイラの警告 (レベル 1) C4144

' expression ': switch 式としての関係式

指定された関係式は [switch](../../cpp/switch-statement-cpp.md) ステートメントの制御式として使用されました。 関連する case ステートメントには、ブール値が提供されます。 次の例では、C4144 が生成されます。

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
