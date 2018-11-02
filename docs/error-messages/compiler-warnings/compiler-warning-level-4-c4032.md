---
title: コンパイラの警告 (レベル 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: fa1602d63ed9822725fea8e1b842929f221d3926
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657302"
---
# <a name="compiler-warning-level-4-c4032"></a>コンパイラの警告 (レベル 4) C4032

仮パラメーター 'number' が昇格するときに別の種類

パラメーターの型が互換性のある、既定の昇格の場合、前の宣言で型を使用できません。

これは ANSI C でエラー ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) は Microsoft 拡張機能 (/Ze) 警告します。

## <a name="example"></a>例

```
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```