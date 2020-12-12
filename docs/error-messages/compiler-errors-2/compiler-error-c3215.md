---
description: 詳細については、「コンパイラエラー C3215」を参照してください。
title: コンパイラ エラー C3215
ms.date: 11/04/2016
f1_keywords:
- C3215
helpviewer_keywords:
- C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
ms.openlocfilehash: 1291f480e4f01502db4232585f7e7786fd637072
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173741"
---
# <a name="compiler-error-c3215"></a>コンパイラ エラー C3215

'type1': 'type2' によって既に制限されているジェネリック型パラメーターです

制約が複数回指定されました。

ジェネリックの詳細については、「 [Generics](../../extensions/generics-cpp-component-extensions.md)」を参照してください。

次の例では C3215 が生成されます。

```cpp
// C3215.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A,A
ref class C {};   // C3215
```

考えられる解決策:

```cpp
// C3215b.cpp
// compile with: /clr /c
interface struct A {};

generic <class T>
where T : A
ref class C {};
```
