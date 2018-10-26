---
title: コンパイラの警告 (レベル 4) C4211 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4211
dev_langs:
- C++
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e38764970b8afde477c4f627e5cd3e5874d3b129
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50054536"
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

