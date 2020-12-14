---
description: '詳細情報: コンパイラの警告 (レベル 4) C4211'
title: コンパイラの警告 (レベル 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: bbd6469dc98d95342538bf3a9065b4647619d69a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314738"
---
# <a name="compiler-warning-level-4-c4211"></a>コンパイラの警告 (レベル 4) C4211

非標準の拡張が使用されています: extern を static に再定義します

既定の Microsoft 拡張機能 (/Ze) では、識別子をとして再定義でき **`extern`** **`static`** ます。

## <a name="example"></a>例

```c
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

このような再定義は ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では無効です。
