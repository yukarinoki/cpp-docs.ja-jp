---
title: コンパイラ エラー C2991 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2991
dev_langs:
- C++
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09b26d60968b9befc3bc9b027b46f09c269dd9a9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091622"
---
# <a name="compiler-error-c2991"></a>コンパイラ エラー C2991

型パラメーター 'parameter' の再定義です

ジェネリック定義またはテンプレート定義の 2 つの `parameter`で型が競合しています。 複数のジェネリックまたはテンプレートのパラメーターを定義する場合は、同等の型を使用する必要があります。

次の例では C2991 が生成されます。

```
// C2991.cpp
// compile with: /c
template<class T, class T> struct TC {};   // C2991
// try the following line instead
// template<class T, class T2> struct TC {};
```

C2991 は、ジェネリックを使用する場合にも発生することがあります。

```
// C2991b.cpp
// compile with: /clr /c
generic<class T,class T> ref struct GC {};   // C2991
// try the following line instead
// generic<class T,class T2> ref struct GC {};
```