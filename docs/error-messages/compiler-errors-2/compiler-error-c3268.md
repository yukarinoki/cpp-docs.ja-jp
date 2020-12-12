---
description: 詳細については、「コンパイラエラー C3268」を参照してください。
title: コンパイラ エラー C3268
ms.date: 11/04/2016
f1_keywords:
- C3268
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
ms.openlocfilehash: 405977afe5a58545dd5e8b0d54cb08f431935191
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223322"
---
# <a name="compiler-error-c3268"></a>コンパイラ エラー C3268

> '*function*': ジェネリッククラスのジェネリック関数またはメンバー関数に、変数パラメーターリストを指定することはできません

## <a name="remarks"></a>解説

**/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

詳細については、「 [ジェネリック](../../extensions/generics-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3268 が生成されます。

```cpp
// C3268.cpp
// compile with: /clr:pure /c
generic <class ItemType>
void Test(ItemType item, ...) {}   // C3268
// try the following line instead
// void Test(ItemType item) {}

generic <class ItemType2>
ref struct MyStruct { void Test(...){} };   // C3268
// try the following line instead
// ref struct MyStruct { void Test2(){} };   // OK
```
