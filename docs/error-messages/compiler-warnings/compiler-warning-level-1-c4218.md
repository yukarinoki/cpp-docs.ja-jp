---
description: '詳細情報: コンパイラの警告 (レベル 1) C4218'
title: コンパイラの警告 (レベル 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 76fc53a5b290a55c73fe036e2fc02b7a1afedd23
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266417"
---
# <a name="compiler-warning-level-1-c4218"></a>コンパイラの警告 (レベル 1) C4218

非標準の拡張機能が使用されています: 少なくともストレージクラスまたは型を指定する必要があります

既定の Microsoft 拡張機能 (/Ze) では、型またはストレージクラスを指定せずに変数を宣言できます。 既定の型は **`int`** です。

## <a name="example"></a>例

```cpp
// C4218.c
// compile with: /W4
i;  // C4218

int main()
{
}
```

このような宣言は、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では無効です。
