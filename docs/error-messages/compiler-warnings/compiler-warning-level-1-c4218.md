---
title: コンパイラの警告 (レベル 1) C4218 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4218
dev_langs:
- C++
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1970dd1bd231716f59508a7cca9f82d3e13151ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074048"
---
# <a name="compiler-warning-level-1-c4218"></a>コンパイラの警告 (レベル 1) C4218

使用される標準の拡張機能: ストレージ クラスまたは型を指定する必要があります

既定の Microsoft 拡張 (/Ze) で型またはストレージ クラスを指定することがなく変数を宣言することができます。 既定の型は `int` です。

## <a name="example"></a>例

```
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

このような宣言が ANSI 互換では無効です ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。