---
title: コンパイラ エラー C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: d7163cf07a440a0afd1216b3e5cf665326ffb963
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386604"
---
# <a name="compiler-error-c3920"></a>コンパイラ エラー C3920

' operator ': 後置インクリメント/デクリメントの WinRT または CLR 演算子の後置の呼び出しを定義することはできません WinRT または CLR 演算子は、対応するプレフィックスを呼び出します後置形式のセマンティクスを持つ WinRT または CLR 演算子 (op_Increment/op_Decrement) が

Windows Runtime および CLR は後置演算子をサポートしておらず、ユーザー定義後置演算子は許可されていません。  前置演算子は定義でき、プレ インクリメント演算でもポスト インクリメント演算でも前置演算子が使用されます。

次の例では、C3920 を生成し、その修正方法を示しています。

```
// C3920.cpp
// compile with: /clr /LD
public value struct V {
   static V operator ++(V me, int)
   // try the following line instead
   // static V operator ++(V me)
   {   // C3920
      me.m_i++;
      return me;
   }

   int m_i;
};
```