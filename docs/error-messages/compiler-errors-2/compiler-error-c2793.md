---
title: コンパイラ エラー C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: 5533a0e8f75a1a513fbabe451fb41629a4595382
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360152"
---
# <a name="compiler-error-c2793"></a>コンパイラ エラー C2793

'token': 予期しないトークン次 ':: '、識別子またはキーワード 'operator' が必要です

後に使用できる唯一のトークン`__super::`識別子かキーワード`operator`します。

次のサンプルの生成 C2793

```
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```