---
title: コンパイラの警告 (レベル 1) C4393
ms.date: 11/04/2016
f1_keywords:
- C4393
helpviewer_keywords:
- C4393
ms.assetid: 353a0539-d1ea-4c1b-8849-c9b321ec9842
ms.openlocfilehash: 4226c8ecd41e890d70fa5741decae605d45b620f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777043"
---
# <a name="compiler-warning-level-1-c4393"></a>コンパイラの警告 (レベル 1) C4393

'var': const リテラル データ メンバーに影響を与えません無視されます。

A[リテラル](../../extensions/literal-cpp-component-extensions.md)データ メンバーを定数としても指定されました。  リテラル データ メンバーには、const からわかるように、ためする必要はありませんを追加する宣言に定数。

次の例では、C4393 が生成されます。

```
// C4393.cpp
// compile with: /clr /W1 /c
ref struct Y1 {
   literal const int staticConst = 10;   // C4393
   literal int staticConst2 = 10;   // OK
};
```