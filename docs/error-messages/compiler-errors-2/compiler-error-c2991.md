---
title: コンパイラ エラー C2991
ms.date: 11/04/2016
f1_keywords:
- C2991
helpviewer_keywords:
- C2991
ms.assetid: a87e4404-26e8-4927-b3ee-5d02b3b8bee1
ms.openlocfilehash: bb7d709f757b6da10c8b17d5b30e2c2b86edd85e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366096"
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