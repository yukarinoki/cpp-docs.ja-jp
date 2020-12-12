---
description: '詳細については、「方法: アンマネージメモリにオブジェクト参照を保持する」を参照してください。'
title: '方法: アンマネージ メモリ内にオブジェクト参照を保持する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
ms.openlocfilehash: 9c54d0ce376e57c5865c2fef5987d878bfa8d7f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134928"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>方法: アンマネージ メモリ内にオブジェクト参照を保持する

をラップして <xref:System.Runtime.InteropServices.GCHandle> 、アンマネージメモリ内の CLR オブジェクト参照を保持するために、をラップする gcroot を使用できます。 または、を直接使用することもでき `GCHandle` ます。

## <a name="examples"></a>例

```cpp
// hold_object_reference.cpp
// compile with: /clr
#include "gcroot.h"
using namespace System;

#pragma managed
class StringWrapper {

private:
   gcroot<String ^ > x;

public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      x = str;
   }

   void PrintString() {
      String ^ targetStr = x;
      Console::WriteLine("StringWrapper::x == {0}", targetStr);
   }
};
#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::x == ManagedString
```

`GCHandle` アンマネージメモリにマネージオブジェクト参照を保持する手段を提供します。  メソッドを使用して、 <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> マネージオブジェクトへの不透明なハンドルを作成し、そのハンドルを <xref:System.Runtime.InteropServices.GCHandle.Free%2A> 解放します。 また、 <xref:System.Runtime.InteropServices.GCHandle.Target%2A> メソッドを使用すると、マネージコードのハンドルからオブジェクト参照を取得できます。

```cpp
// hold_object_reference_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#pragma managed
class StringWrapper {
   IntPtr m_handle;
public:
   StringWrapper() {
      String ^ str = gcnew String("ManagedString");
      m_handle = static_cast<IntPtr>(GCHandle::Alloc(str));
   }
   ~StringWrapper() {
      static_cast<GCHandle>(m_handle).Free();
   }

   void PrintString() {
      String ^ targetStr = safe_cast< String ^ >(static_cast<GCHandle>(m_handle).Target);
      Console::WriteLine("StringWrapper::m_handle == {0}", targetStr);
   }
};

#pragma unmanaged
int main() {
   StringWrapper s;
   s.PrintString();
}
```

```Output
StringWrapper::m_handle == ManagedString
```

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
