---
title: '方法: C++ Interop を使用して構造体をマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Interop, structures
- structures [C++], marshaling
- data marshaling [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: c2080200-f983-4d6e-a557-cd870f060a54
ms.openlocfilehash: a77745c9a60c9759f8b3b2df91bcbc4cb507533b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544893"
---
# <a name="how-to-marshal-structures-using-c-interop"></a>方法: C++ Interop を使用して構造体をマーシャリングする

このトピックでは、ビジュアルC++相互運用性の1つの側面を示します。 詳細については、「 [Interop (暗黙のC++ PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。

次のコード例では、マネージ[、アン](../preprocessor/managed-unmanaged.md)マネージ #pragma ディレクティブを使用して、マネージ関数とアンマネージ関数を同じファイルに実装しますが、これらの関数は、別々のファイルで定義されている場合と同じ方法で相互運用します。 アンマネージ関数のみを含むファイルを[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)でコンパイルする必要はありません。

## <a name="example"></a>例

次の例では、マネージ関数からアンマネージ関数に構造体を渡す方法を示します。値渡しと参照渡しの両方があります。 この例の構造体には、単純な組み込みデータ型 (「 [Blittable 型と非 Blittable 型](/dotnet/framework/interop/blittable-and-non-blittable-types)」を参照) のみが含まれているので、特別なマーシャリングは必要ありません。 ポインターを含む非 blittable 構造体をマーシャリングする方法については、「[方法: 相互運用をC++使用して埋め込みポインターをマーシャリング](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)する」を参照してください。

```cpp
// PassStruct1.cpp
// compile with: /clr

#include <stdio.h>
#include <math.h>

using namespace System;
using namespace System::Runtime::InteropServices;

#pragma unmanaged

struct Location {
   int x;
   int y;
};

double GetDistance(Location loc1, Location loc2) {
   printf_s("[unmanaged] loc1(%d,%d)", loc1.x, loc1.y);
   printf_s(" loc2(%d,%d)\n", loc2.x, loc2.y);

   double h = loc1.x - loc2.x;
   double v = loc1.y = loc2.y;
   double dist = sqrt( pow(h,2) + pow(v,2) );

   return dist;
}

void InitLocation(Location* lp) {
   printf_s("[unmanaged] Initializing location...\n");
   lp->x = 50;
   lp->y = 50;
}

#pragma managed

int main() {
   Location loc1;
   loc1.x = 0;
   loc1.y = 0;

   Location loc2;
   loc2.x = 100;
   loc2.y = 100;

   double dist = GetDistance(loc1, loc2);
   Console::WriteLine("[managed] distance = {0}", dist);

   Location loc3;
   InitLocation(&loc3);
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);
}
```

## <a name="example"></a>例

次の例では、アンマネージの構造体を値渡しと参照渡しの両方でマネージ関数に渡す方法を示します。 この例の構造体には、単純な組み込みデータ型 (「 [Blittable 型と非 Blittable 型](/dotnet/framework/interop/blittable-and-non-blittable-types)」を参照) のみが含まれているため、特別なマーシャリングは必要ありません。 ポインターを含む非 blittable 構造体をマーシャリングする方法については、「[方法: 相互運用をC++使用して埋め込みポインターをマーシャリング](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)する」を参照してください。

```cpp
// PassStruct2.cpp
// compile with: /clr
#include <stdio.h>
#include <math.h>
using namespace System;

// native structure definition
struct Location {
   int x;
   int y;
};

#pragma managed

double GetDistance(Location loc1, Location loc2) {
   Console::Write("[managed] got loc1({0},{1})", loc1.x, loc1.y);
   Console::WriteLine(" loc2({0},{1})", loc2.x, loc2.y);

   double h = loc1.x - loc2.x;
   double v = loc1.y = loc2.y;
   double dist = sqrt( pow(h,2) + pow(v,2) );

   return dist;
}

void InitLocation(Location* lp) {
   Console::WriteLine("[managed] Initializing location...");
   lp->x = 50;
   lp->y = 50;
}

#pragma unmanaged

int UnmanagedFunc() {
   Location loc1;
   loc1.x = 0;
   loc1.y = 0;

   Location loc2;
   loc2.x = 100;
   loc2.y = 100;

   printf_s("(unmanaged) loc1=(%d,%d)", loc1.x, loc1.y);
   printf_s(" loc2=(%d,%d)\n", loc2.x, loc2.y);

   double dist = GetDistance(loc1, loc2);
   printf_s("[unmanaged] distance = %f\n", dist);

   Location loc3;
   InitLocation(&loc3);
   printf_s("[unmanaged] got x=%d y=%d\n", loc3.x, loc3.y);

    return 0;
}

#pragma managed

int main() {
   UnmanagedFunc();
}
```

## <a name="see-also"></a>参照

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
