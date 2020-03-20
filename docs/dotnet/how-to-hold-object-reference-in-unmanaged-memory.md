---
title: '方法: アンマネージ メモリ内にオブジェクト参照を保持する'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
ms.openlocfilehash: 2f2471e36d7551cab9edb68d7babeb1419e8e20c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544953"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>方法: アンマネージ メモリ内にオブジェクト参照を保持する

<xref:System.Runtime.InteropServices.GCHandle>をラップする gcroot を使用して、アンマネージメモリに CLR オブジェクト参照を保持することができます。 または、`GCHandle` を直接使用することもできます。

## <a name="example"></a>例

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

## <a name="example"></a>例

`GCHandle` には、アンマネージメモリにマネージオブジェクト参照を保持する手段が用意されています。  <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> メソッドを使用して、マネージオブジェクトへの非透過的ハンドルを作成し、それを解放する <xref:System.Runtime.InteropServices.GCHandle.Free%2A> します。 また、<xref:System.Runtime.InteropServices.GCHandle.Target%2A> メソッドを使用すると、マネージコードのハンドルからオブジェクト参照を取得できます。

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

## <a name="see-also"></a>参照

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
