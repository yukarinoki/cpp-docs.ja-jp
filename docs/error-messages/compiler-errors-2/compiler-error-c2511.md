---
title: コンパイラ エラー C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: 9d9ba48b0607e7a30b8748d4e9ae4f7025f11dea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165022"
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