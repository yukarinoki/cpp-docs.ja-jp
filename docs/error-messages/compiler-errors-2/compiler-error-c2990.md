---
title: コンパイラ エラー C2990 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2990
dev_langs:
- C++
helpviewer_keywords:
- C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0afceb82a58ee5c0a21e39fcaf4ba0a9ee9f2c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066974"
---
# <a name="compiler-error-c2990"></a>コンパイラ エラー C2990

'class': 非クラス型既にクラス型として宣言されています。

非ジェネリックまたはテンプレート クラスは、ジェネリックまたはテンプレート クラスを再定義します。 ヘッダー ファイルの競合を確認します。

次の例では、C2990 が生成されます。

```
// C2990.cpp
// compile with: /c
template <class T>
class C{};
class C{};   // C2990
```

C2990 は、ジェネリックを使用しているときにも発生します。

```
// C2990b.cpp
// compile with: /clr /c
generic <class T>
ref struct GC;

ref struct GC {};   // C2990
```

Visual C 2005; C2990 にも発生により、Visual C コンパイラで重大な変更コンパイラは、同じ種類の複数の宣言がテンプレートの仕様と一致させることが必要になりました。

次の例では、C2990 が生成されます。

```
// C2990c.cpp
// compile with: /c
template<class T>
class A;

template<class T>
struct A2 {
   friend class A;   // C2990
};

// OK
template<class T>
struct B {
   template<class T>
   friend class A;
};
```