---
title: コンパイラの警告 (レベル 1) C4397
ms.date: 11/04/2016
f1_keywords:
- C4397
helpviewer_keywords:
- C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
ms.openlocfilehash: 7f0a3c31f460a66523ed1c327cee097dc890bbeb
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447675"
---
# <a name="compiler-warning-level-1-c4397"></a>コンパイラの警告 (レベル 1) C4397

DefaultCharSetAttribute は無視されます。

<xref:System.Runtime.InteropServices.DefaultCharSetAttribute> Microsoft では無視されますC++コンパイラ。 DLL の文字セットを指定するには、DllImport の CharSet オプションを使用します。 詳細については、次を参照してください。[を使用して C++ Interop (暗黙の PInvoke)](../../dotnet/using-cpp-interop-implicit-pinvoke.md)します。

## <a name="example"></a>例

次の例では、C4397 が生成されます。

```
// C4397.cpp
// compile with: /W1 /c /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[module:DefaultCharSetAttribute(CharSet::Unicode)];   // C4397

[DllImport("kernel32", EntryPoint="CloseHandle", CharSet=CharSet::Unicode)]   // OK
extern "C" bool ImportDefault(IntPtr hObject);

public ref class MySettingVC {
public:
   void method() {
      ImportDefault(IntPtr::Zero);
   }
};

[StructLayout(LayoutKind::Explicit)]
public ref struct StructDefault1{};

public ref class ClassDefault1{};
```