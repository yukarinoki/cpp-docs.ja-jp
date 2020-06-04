---
title: コンパイラの警告 (レベル 4) C4032
ms.date: 11/04/2016
f1_keywords:
- C4032
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
ms.openlocfilehash: 84bfef28de2899a216616a6a5d9fb15422f2afec
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185413"
---
# <a name="compiler-warning-level-4-c4032"></a>コンパイラの警告 (レベル 4) C4032

昇格時に仮引数 ' number ' の型が異なります

パラメーターの型は、既定の昇格を通じて、前の宣言の型と互換性がありません。

これは、ANSI C ([/za](../../build/reference/za-ze-disable-language-extensions.md)) ではエラーであり、Microsoft 拡張機能 (/ze) では警告が発生します。

## <a name="example"></a>例

```c
// C4032.c
// compile with: /W4
void func();
void func(char);   // C4032, char promotes to int

int main()
{
}
```
