---
title: '方法: アンマネージ メモリ内のオブジェクト参照を保持 |Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object references, in native functions
- objects [C++], reference in native functions
- references, to objects in native functions
- gcroot keyword [C++], object reference in native function
ms.assetid: a61eb8ce-3982-477d-8d3d-2173fd57166d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3153a34844885e2b753bf68d74b7757c5d11fb1d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443463"
---
# <a name="how-to-hold-object-reference-in-unmanaged-memory"></a>方法: アンマネージ メモリ内にオブジェクト参照を保持する

ラップする gcroot.h を使用することができます<xref:System.Runtime.InteropServices.GCHandle>をアンマネージ メモリ内の CLR オブジェクトの参照を保持します。 また、使用することができます`GCHandle`直接します。

## <a name="example"></a>例

```
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

`GCHandle` アンマネージ メモリ内のマネージ オブジェクトの参照を保持するための手段が表示されます。  使用する、<xref:System.Runtime.InteropServices.GCHandle.Alloc%2A>マネージ オブジェクトへの非透過ハンドルを作成するメソッドをおよび<xref:System.Runtime.InteropServices.GCHandle.Free%2A>を解放します。 また、<xref:System.Runtime.InteropServices.GCHandle.Target%2A>メソッドでは、マネージ コードでハンドルからオブジェクト参照を取得できます。

```
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