---
title: コンパイラ エラー C3268
ms.date: 11/04/2016
f1_keywords:
- C3268
helpviewer_keywords:
- C3268
ms.assetid: d74a630c-daea-4e29-9759-83efef7fb184
ms.openlocfilehash: d9954c12fb1065a4aa5e7afbdecd1f96758acaf9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "58778009"
---
# <a name="compiler-error-c3268"></a>コンパイラ エラー C3268

> '*関数*': ジェネリック関数またはジェネリック クラスのメンバー関数は、変数パラメーター リストを含めることはできません

## <a name="remarks"></a>Remarks

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

参照してください[ジェネリック](../../extensions/generics-cpp-component-extensions.md)詳細についてはします。

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