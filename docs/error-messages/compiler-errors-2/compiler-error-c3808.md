---
description: 詳細については、「コンパイラエラー C3808」を参照してください。
title: コンパイラ エラー C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: e5d31e884de0b04caba7c52e8d6abc01b3d21a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315154"
---
# <a name="compiler-error-c3808"></a>コンパイラ エラー C3808

> '*type*': comimport 属性を持つクラスはメンバー '*member*' を定義できません。 abstract 関数または dllimport 関数のみを使用できます

## <a name="remarks"></a>解説

から派生した型で <xref:System.Runtime.InteropServices.ComImportAttribute> は、 *メンバー* を定義できません。

**/Clr: pure** および **/clr: safe** コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

## <a name="example"></a>例

次の例では、C3808 が生成されます。

```cpp
// C3808.cpp
// compile with: /c /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 {
   int f() {}   // C3808
   virtual int g() abstract;   // OK

   [DllImport("msvcrt.dll")]
   int printf(System::String ^, int i);   // OK
};
```
