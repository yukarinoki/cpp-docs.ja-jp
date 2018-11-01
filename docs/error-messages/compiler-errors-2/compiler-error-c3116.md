---
title: コンパイラ エラー C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: 3f587bc677d64bda0fb5eea0b7ebc8d5761a2e75
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612021"
---
# <a name="compiler-error-c3116"></a>コンパイラ エラー C3116

'ストレージの指定子': インターフェイス メソッドに対する無効なストレージ クラス

使用した`typedef`、 `register`、または`static`インターフェイス メソッドのストレージ クラスとして。 これらのストレージ クラスはインターフェイス メンバーに対しては許可されていません。

次の例では、C3116 が生成されます。

```
// C3116.cpp
__interface ImyInterface
{
   static void myFunc();   // C3116
};
```