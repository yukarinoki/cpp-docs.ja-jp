---
title: コンパイラ エラー C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: e854764dc3f8d3ede79965302b62055b91df0a4c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165627"
---
# <a name="compiler-error-c3808"></a>コンパイラ エラー C3808

> '*type*': comimport 属性を持つクラスはメンバー '*member*' を定義できません。 abstract 関数または dllimport 関数のみを使用できます

## <a name="remarks"></a>解説

<xref:System.Runtime.InteropServices.ComImportAttribute> から派生した型で*メンバー*を定義することはできません。

**/Clr: pure**および **/clr: safe**コンパイラオプションは visual studio 2015 で非推奨とされており、visual studio 2017 ではサポートされていません。

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
