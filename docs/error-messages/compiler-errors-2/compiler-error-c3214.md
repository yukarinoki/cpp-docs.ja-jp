---
description: 詳細については、「コンパイラエラー C3214」を参照してください。
title: コンパイラ エラー C3214
ms.date: 11/04/2016
f1_keywords:
- C3214
helpviewer_keywords:
- C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
ms.openlocfilehash: 8f1b558b37e3a9f4daa08ecdd2f90b0f7a74a2a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173819"
---
# <a name="compiler-error-c3214"></a>コンパイラ エラー C3214

'type': ジェネリック 'generic_type' のジェネリック パラメーター 'param' の型引数が無効です。制約 'constraint' を満たしていません

ジェネリック クラスの制約を満たしていないジェネリック クラスをインスタンス化するために型を指定しました。

次の例では C3214 が生成されます。

```cpp
// C3214.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A
ref class C {};

ref class X : public A {};

int main() {
   C<int>^ c = new C<int>;   // C3214
   C<X ^> ^ c2 = new C<X^>;   // OK
}
```
