---
title: break ステートメント (C)
ms.date: 11/04/2016
f1_keywords:
- break
helpviewer_keywords:
- break keyword [C]
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
ms.openlocfilehash: c46173ceebd7291336c18d36203d1e4dc59ce46d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222005"
---
# <a name="break-statement-c"></a>break ステートメント (C)

**`break`** ステートメントでは、それを囲む最も近い **`do`** 、 **`for`** 、 **`switch`** 、または **`while`** の各ステートメントの実行が終了されます。 制御は、終了したステートメントの後に続くステートメントに移動します。

## <a name="syntax"></a>構文

*jump-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**break ;**

**`break`** ステートメントは、 **`switch`** ステートメント内の特定ので case の処理を終了するためによく使用されます。 囲む反復ステートメントまたは **`switch`** ステートメントがない場合、エラーが生成されます。

入れ子になったステートメント内では、 **`break`** ステートメントにより、それを直接囲む **`do`** 、 **`for`** 、 **`switch`** 、または **`while`** の各ステートメントだけが終了されます。 **`return`** ステートメントまたは **`goto`** ステートメントを使用して、入れ子構造から別の場所に制御を移すことができます。

**`break`** ステートメントの例を次に示します。

```
#include <stdio.h>
int main() {
   char c;
   for(;;) {
      printf_s( "\nPress any key, Q to quit: " );

      // Convert to character value
      scanf_s("%c", &c);
      if (c == 'Q')
          break;
   }
} // Loop exits only when 'Q' is pressed
```

## <a name="see-also"></a>関連項目

[break ステートメント](../cpp/break-statement-cpp.md)
