---
description: '詳細情報: コンパイラの警告 (レベル 4) C4238'
title: コンパイラの警告 (レベル 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: 8999d9ebeb4583256360f6223d4bf51a842fcb01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334869"
---
# <a name="compiler-warning-level-4-c4238"></a>コンパイラの警告 (レベル 4) C4238

非標準の拡張機能が使用されています

以前のバージョンの Visual C++ との互換性を保つために、Microsoft extensions (**/ze**) では、暗黙的または明示的にアドレスを取得するコンテキストで、クラス型を右辺値として使用できます。 次の例のような場合は、これが危険になることがあります。

## <a name="example"></a>例

```cpp
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

この使用法により、ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) でエラーが発生します。
