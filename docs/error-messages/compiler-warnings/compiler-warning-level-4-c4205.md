---
title: コンパイラの警告 (レベル 4) C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: 7b6e273de196f6708b92774ce5b436dc810ad3a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161440"
---
# <a name="compiler-warning-level-4-c4205"></a>コンパイラの警告 (レベル 4) C4205

非標準の拡張機能が使用されています: 関数スコープの静的関数宣言

Microsoft 拡張機能 (/Ze) では、**静的**関数を別の関数内で宣言できます。 関数にはグローバルスコープが指定されています。

## <a name="example"></a>例

```c
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

このような初期化は、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では無効です。
