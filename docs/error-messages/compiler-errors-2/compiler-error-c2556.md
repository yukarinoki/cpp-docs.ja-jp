---
title: コンパイラ エラー C2556 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2556
dev_langs:
- C++
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 880234d1d11556b8882bfd564fdf64bc587d56ae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107798"
---
# <a name="compiler-error-c2556"></a>コンパイラ エラー C2556

'identifier': オーバー ロードされた関数は、戻り値の型のみが異なる

オーバー ロードされた関数では、同じパラメーター リストが異なる戻り値の型があります。 各オーバー ロードされた関数は、個別の仮パラメーター リストにあります。

次の例では、C2556 が生成されます。

```
// C2556.cpp
// compile with: /c
class C {
   int func();
   double func();   // C2556
   int func(int i);   // ok parameter lists differ
};
```