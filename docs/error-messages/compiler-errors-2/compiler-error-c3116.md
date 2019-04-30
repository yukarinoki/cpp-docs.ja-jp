---
title: コンパイラ エラー C3116
ms.date: 11/04/2016
f1_keywords:
- C3116
helpviewer_keywords:
- C3116
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
ms.openlocfilehash: 3f587bc677d64bda0fb5eea0b7ebc8d5761a2e75
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376069"
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