---
description: 詳細については、「コンパイラエラー C3920」を参照してください。
title: コンパイラ エラー C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: b4cb793744126ee7bc91d18692d25439880fc672
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326574"
---
# <a name="compiler-error-c3920"></a>コンパイラ エラー C3920

' operator ' ': 後置形式で winrt またはデクリメント演算子を定義できません。後置形式の winrt または clr 演算子は、対応するプレフィックス WinRT または CLR 演算子 (op_Increment/op_Decrement) を呼び出しますが、後置形式のセマンティクスで呼び出されます

Windows Runtime および CLR は後置演算子をサポートしておらず、ユーザー定義後置演算子は許可されていません。  前置演算子は定義でき、プレ インクリメント演算でもポスト インクリメント演算でも前置演算子が使用されます。

次の例では、C3920 を生成し、その修正方法を示しています。

```cpp
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
