---
description: '詳細情報: コンパイラの警告 (レベル 2) C4094'
title: コンパイラの警告 (レベル 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: 63c554703c1eb6f7ecb831d1046641a0cde2094a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326532"
---
# <a name="compiler-warning-level-2-c4094"></a>コンパイラの警告 (レベル 2) C4094

タグなしの ' token ' はシンボルを宣言しませんでした

コンパイラは、タグなしの構造体、共用体、またはクラスを使用して空の宣言を検出しました。 宣言は無視されます。

## <a name="example"></a>例

```cpp
// C4094.cpp
// compile with: /W2
struct
{
};   // C4094

int main()
{
}
```

この条件により、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) でエラーが生成されます。
