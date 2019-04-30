---
title: コンパイラ エラー C3417
ms.date: 11/04/2016
f1_keywords:
- C3417
helpviewer_keywords:
- C3417
ms.assetid: 3e7869ea-8948-42fb-ba30-6ccafe499c35
ms.openlocfilehash: 574af940f17c1a79472d6d20d63c9ff74d4c411e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367669"
---
# <a name="compiler-error-c3417"></a>コンパイラ エラー C3417

'member': 値型は、特殊なメンバーのユーザー定義関数を含めることはできません

値型では、既定のインスタンス コンス トラクター、デストラクター、またはコピー コンス トラクターなどの関数を含めることはできません。

次の例では、c3517 エラーが生成されます。

```
// C3417.cpp
// compile with: /clr /c
value class VC {
   VC(){}   // C3417

   // OK
   static VC(){}
   VC(int i){}
};
```