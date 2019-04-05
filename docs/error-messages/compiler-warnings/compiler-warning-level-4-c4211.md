---
title: コンパイラの警告 (レベル 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: cc80ddc459193c2e8fe5ca0b37d28d53d346fc53
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038110"
---
# <a name="compiler-warning-level-4-c4211"></a>コンパイラの警告 (レベル 4) C4211

使用される標準の拡張機能: extern が static に再定義されました

既定の Microsoft 拡張 (/Ze) で再定義できます、`extern`識別子として**静的**します。

## <a name="example"></a>例

```
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

このような再定義は ANSI 互換では無効です ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。

## <a name="see-also"></a>関連項目

