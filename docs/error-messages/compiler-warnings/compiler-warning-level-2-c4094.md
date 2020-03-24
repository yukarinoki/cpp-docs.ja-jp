---
title: コンパイラの警告 (レベル 2) C4094
ms.date: 11/04/2016
f1_keywords:
- C4094
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
ms.openlocfilehash: c90ad202e193f21955d396dd2aff6b39d3a968c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174337"
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
