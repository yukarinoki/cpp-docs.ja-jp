---
description: '詳細については、「方法: アンマネージリソースをバイト配列に読み込む」を参照してください。'
title: '方法: アンマネージ リソースをバイト配列に読み込む'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- native resources, loading into Byte array
- unmanaged resources, loading into Byte array
- native resources
ms.assetid: cdada6cd-6d42-437a-a90f-44a0b18d6a93
ms.openlocfilehash: e5a7a88a505d3f02b8e9287d6407ddbe77b99dee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258279"
---
# <a name="how-to-load-unmanaged-resources-into-a-byte-array"></a>方法: アンマネージ リソースをバイト配列に読み込む

このトピックでは、アンマネージリソースを配列に読み込むいくつかの方法について説明 <xref:System.Byte> します。

## <a name="examples"></a>例

アンマネージリソースのサイズがわかっている場合は、clr 配列を事前に割り当てると、CLR 配列の配列ブロックへのポインターを使用して、そのリソースを配列に読み込むことができます。

```cpp
// load_unmanaged_resources_into_Byte_array.cpp
// compile with: /clr
using namespace System;
void unmanaged_func( unsigned char * p ) {
   for ( int i = 0; i < 10; i++ )
      p[ i ] = i;
}

public ref class A {
public:
   void func() {
      array<Byte> ^b = gcnew array<Byte>(10);
      pin_ptr<Byte> p =  &b[ 0 ];
      Byte * np = p;
      unmanaged_func( np );   // pass pointer to the block of CLR array.
      for ( int i = 0; i < 10; i++ )
         Console::Write( b[ i ] );
      Console::WriteLine();
   }
};

int main() {
   A^ g = gcnew A;
   g->func();
}
```

```Output
0123456789
```

このサンプルでは、アンマネージメモリブロックからマネージ配列にデータをコピーする方法を示します。

```cpp
// load_unmanaged_resources_into_Byte_array_2.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

#include <string.h>
int main() {
   char buf[] = "Native String";
   int len = strlen(buf);
   array<Byte> ^byteArray = gcnew array<Byte>(len + 2);

   // convert any native pointer to IntPtr by doing C-Style cast
   Marshal::Copy( (IntPtr)buf, byteArray, 0, len );
}
```

## <a name="see-also"></a>関連項目

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
