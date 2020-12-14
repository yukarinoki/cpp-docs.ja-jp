---
description: 詳細については、「コンパイラエラー C3618」を参照してください。
title: コンパイラ エラー C3618
ms.date: 11/04/2016
f1_keywords:
- C3618
helpviewer_keywords:
- C3618
ms.assetid: cacc105d-4389-4cb8-ae6c-41a3622e9a86
ms.openlocfilehash: 09e1a2a77410cc7836c00a3dd11cf5ed36553273
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223075"
---
# <a name="compiler-error-c3618"></a>コンパイラ エラー C3618

' function ': DllImport とマークされたメソッドを定義することはできません

でマークされたメソッド <xref:System.Runtime.InteropServices.DllImportAttribute> は、specified.DLL で定義されます。

## <a name="example"></a>例

次の例では、C3618 が生成されます。

```cpp
// C3618.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[ DllImport("user32.dll", EntryPoint="MessageBox", CharSet=CharSet::Ansi) ]  // CHANGED
void Func();

void Func() {}   // C3618, remove this function definition to resolve
```
