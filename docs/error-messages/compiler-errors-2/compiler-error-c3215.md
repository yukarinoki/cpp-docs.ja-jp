---
title: コンパイラ エラー C3215
ms.date: 11/04/2016
f1_keywords:
- C3215
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
ms.openlocfilehash: 24f17d2990c9258168a6d37fef101c21f62cb08d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778723"
---
# <a name="compiler-error-c3215"></a>コンパイラ エラー C3215

'type1': 'type2' によって既に制限されているジェネリック型パラメーターです

制約が複数回指定されました。

ジェネリックの詳細については、「 [Generics](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

次の例では C3215 が生成されます。

```
// C3215.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A,A
ref class C {};   // C3215
```

考えられる解決方法:

```
// C3215b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```