---
description: '詳細情報: コンパイラの警告 (レベル 1) C4397'
title: コンパイラの警告 (レベル 1) C4397
ms.date: 11/04/2016
f1_keywords:
- C4397
helpviewer_keywords:
- C4397
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
ms.openlocfilehash: 17ad322980a199b9602c4aa1ea60d818e657eaa1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311254"
---
# <a name="compiler-warning-level-1-c4397"></a>コンパイラの警告 (レベル 1) C4397

DefaultCharSetAttribute は無視されます

<xref:System.Runtime.InteropServices.DefaultCharSetAttribute> は、Microsoft C++ コンパイラによって無視されます。 DLL の文字セットを指定するには、DllImport の CharSet オプションを使用します。 詳細については、「 [C++ Interop の使用 (暗黙的な PInvoke)](../../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。

## <a name="example"></a>例

次の例では、C4397 が生成されます。

```cpp
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
