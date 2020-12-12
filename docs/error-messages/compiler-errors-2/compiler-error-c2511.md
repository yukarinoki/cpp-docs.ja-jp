---
description: 詳細については、「コンパイラエラー C2511」を参照してください。
title: コンパイラ エラー C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: 846173cc887fd09b564d18e063820bc0e0d5b184
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212923"
---
# <a name="compiler-error-c2511"></a>コンパイラ エラー C2511

' identifier ': オーバーロードされたメンバー関数が ' class ' に見つかりませんでした

指定されたパラメーターを使用して関数のバージョンが宣言されていません。  次の原因が考えられます。

1. 関数に渡されたパラメーターが正しくありません。

1. 間違った順序で渡されたパラメーター。

1. パラメーター名のスペルが正しくありません。

次の例では、C2511 が生成されます。

```cpp
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
