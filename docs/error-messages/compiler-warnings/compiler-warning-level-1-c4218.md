---
title: コンパイラの警告 (レベル 1) C4218
ms.date: 11/04/2016
f1_keywords:
- C4218
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
ms.openlocfilehash: 226bc91c272ff62ebe127aa190384d30a214b05d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223253"
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
