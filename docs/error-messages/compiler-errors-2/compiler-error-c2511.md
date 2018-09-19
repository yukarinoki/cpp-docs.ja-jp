---
title: コンパイラ エラー C2511 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b628adda383baee0f2ec03ace715d94c6cca764c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058147"
---
# <a name="compiler-error-c2511"></a>コンパイラ エラー C2511

'identifier': オーバー ロード メンバー関数の 'class' に見つかりませんでした

指定されたパラメーターでは、バージョンの関数は宣言されていません。  以下の原因が考えられます。

1. 不適切なパラメーターは、関数に渡されます。

1. 間違った順序でパラメーターが渡されます。

1. パラメーター名のスペルが間違っています。

次の例では、C2511 が生成されます。

```
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```