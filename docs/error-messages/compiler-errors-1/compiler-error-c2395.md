---
title: コンパイラ エラー C2395 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2395
dev_langs:
- C++
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 99d9a1be42a36baac2037e4289cb24db2f45b563
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050542"
---
# <a name="compiler-error-c2395"></a>コンパイラ エラー C2395

'your_type::operator'op'' : CLR または WinRT 演算子が無効です。 少なくとも 1 つのパラメーターが次の型である必要があります: 'T'、'T%'、'T&'、'T^'、'T^%'、'T^&' (T = 'your_type')。

Windows ランタイムまたはマネージド型の演算子に、演算子の戻り値の型と同じ型を持つ 1 つ以上のパラメーターがありません。

次の例では、C2395 を生成し、その修正方法を示しています。

```
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```