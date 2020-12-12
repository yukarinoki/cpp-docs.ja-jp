---
description: 詳細については、「コンパイラエラー C3252」を参照してください。
title: コンパイラ エラー C3252
ms.date: 11/04/2016
f1_keywords:
- C3252
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
ms.openlocfilehash: 59b5a0073d3dc8147b2e89d637fd98ba7339f6b8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194307"
---
# <a name="compiler-error-c3252"></a>コンパイラ エラー C3252

'method': マネージド型または WinRT 型で、仮想メソッドのアクセシビリティを制限することはできません。

基底クラスの仮想メソッドまたはインターフェイスのいずれかのメソッドを実装するクラスは、そのメソッドのアクセスを制限することはできません。

インターフェイスのすべてのメソッドはパブリックです。

次の例では、C3252 を生成し、その修正方法を示しています。

```cpp
// C3252.cpp
// compile with: /clr /c
ref class A {
public:
   virtual void f1() {}
};

ref class B : public A {
// To fix, uncomment the following line:
// public:
   virtual void f1() override sealed {}   // C3252, make this method public
};
```
