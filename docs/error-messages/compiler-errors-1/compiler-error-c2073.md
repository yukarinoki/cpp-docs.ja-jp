---
title: コンパイラ エラー C2073 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2073
dev_langs:
- C++
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 950ca9551a605da392c1f033cb1784ff43a7fefc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112370"
---
# <a name="compiler-error-c2073"></a>コンパイラ エラー C2073

'identifier': 部分的に初期化された配列の要素は、既定のコンス トラクターをいる必要があります

少なすぎます初期化子は、ユーザー定義型または定数の配列に指定されました。 配列メンバーを明示的な初期化子と、対応するコンス トラクターが指定されていない場合は、既定のコンス トラクターを指定する必要があります。

次の例では、C2073 が生成されます。

```
// C2073.cpp
class A {
public:
   A( int );   // constructor for ints only
};
A a[3] = { A(1), A(2) };   // C2073, no default constructor
```

```
// C2073b.cpp
// compile with: /c
class B {
public:
   B();   // default constructor declared
   B( int );
};
B b[3] = { B(1), B(2) };   // OK
```