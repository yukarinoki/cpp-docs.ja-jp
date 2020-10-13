---
title: '方法: PInvoke を使用して構造体をマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
ms.openlocfilehash: e132505ef536a79c67afdd76443c2637c08f923b
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008744"
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>方法: PInvoke を使用して構造体をマーシャリングする

このドキュメントでは、C スタイルの構造体を受け入れるネイティブ関数を、P/Invoke を使用してマネージ関数から呼び出す方法について説明します。 P/invoke はコンパイル時のエラー報告をほとんど行わず、タイプセーフではなく、実装するのが面倒なため、アンマネージ API が DLL としてパッケージされていてソースコードを使用できない場合、p/invoke が唯一のオプションであるため、p/Invoke の代わりに C++ Interop 機能を使用することをお勧めします それ以外の場合は、次のドキュメントを参照してください。

- [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [方法: PInvoke を使用して文字列をマーシャリングする](../dotnet/how-to-marshal-strings-using-pinvoke.md)

既定では、ネイティブ構造体とマネージ構造体はメモリに異なる方法で配置されるため、構造体をマネージ/アンマネージ境界を越えて正常に渡すには、データの整合性を維持するための追加の手順が必要になります。

このドキュメントでは、ネイティブ構造体に相当するマネージ型を定義するために必要な手順と、結果の構造体をアンマネージ関数に渡す方法について説明します。 このドキュメントでは、単純な構造 (文字列またはポインターを含まない) が使用されていることを前提としています。 非 blittable の相互運用性の詳細については、「 [C++ Interop の使用 (暗黙的な PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。 P/Invoke は、非 blittable 型を戻り値として持つことはできません。 Blittable 型はマネージコードとアンマネージコードで同じ表現を持ちます。 詳細については、「 [Blittable 型と非 Blittable 型](/dotnet/framework/interop/blittable-and-non-blittable-types)」を参照してください。

マネージ/アンマネージ境界を越えて単純な blittable 構造体をマーシャリングするには、まず、各ネイティブ構造のマネージバージョンを定義する必要があります。 これらの構造体は、任意の有効な名前を持つことができます。データレイアウト以外の2つの構造体のネイティブバージョンとマネージバージョンの間にはリレーションシップがありません。 そのため、マネージバージョンには、ネイティブバージョンと同じ順序で同じサイズのフィールドが含まれていることが重要です。 (構造体のマネージバージョンとネイティブバージョンが等価であることを保証する機構はないため、非互換性は実行時まで明らかになりません。 2つの構造体が同じデータレイアウトを持つようにするには、プログラマが行う必要があります)。

マネージ構造体のメンバーは、パフォーマンスのために再配置されることがあるため、構造体が順番に配置されることを示すには、属性を使用する必要があり <xref:System.Runtime.InteropServices.StructLayoutAttribute> ます。 また、構造体のパッキング設定を、ネイティブ構造体で使用されるものと同じになるように明示的に設定することもお勧めします。 (既定では、Visual C++ では、両方のマネージコードに8バイト構造のパッキングが使用されます)。

1. 次に、を使用して、 <xref:System.Runtime.InteropServices.DllImportAttribute> 構造体を受け入れるアンマネージ関数に対応するエントリポイントを宣言します。ただし、この構造体の両方のバージョンで同じ名前を使用する場合、議論ポイントである関数シグネチャで構造体のマネージバージョンを使用します。

1. マネージコードは、実際にはマネージ関数であるかのように、構造体のマネージバージョンをアンマネージ関数に渡すことができるようになりました。 これらの構造体は、次の例に示すように、値または参照によって渡すことができます。

## <a name="unmanaged-and-a-managed-modules"></a>アンマネージモジュールとマネージモジュール

次のコードは、アンマネージモジュールとマネージモジュールで構成されています。 アンマネージモジュールは、Location という構造体と、Location 構造体の2つのインスタンスを受け入れる GetDistance と呼ばれる関数を定義する DLL です。 2番目のモジュールは、GetDistance 関数をインポートする管理されたコマンドラインアプリケーションですが、場所の構造体である MLocation と同等のマネージ表現を使用して定義します。 実際には、構造の両方のバージョンで同じ名前が使用される可能性があります。ただし、ここでは、DllImport プロトタイプがマネージバージョンの観点で定義されていることを示すために、別の名前を使用しています。

DLL の一部は、従来の #include ディレクティブを使用してマネージコードに公開されないことに注意してください。 実際、DLL は実行時にのみアクセスされるため、DllImport を使用してインポートされた関数に関する問題はコンパイル時に検出されません。

### <a name="example-unmanaged-dll-module"></a>例: アンマネージ DLL モジュール

```cpp
// TraditionalDll3.cpp
// compile with: /LD /EHsc
#include <iostream>
#include <stdio.h>
#include <math.h>

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
   #define TRADITIONALDLL_API __declspec(dllexport)
#else
   #define TRADITIONALDLL_API __declspec(dllimport)
#endif

#pragma pack(push, 8)
struct Location {
   int x;
   int y;
};
#pragma pack(pop)

extern "C" {
   TRADITIONALDLL_API double GetDistance(Location, Location);
   TRADITIONALDLL_API void InitLocation(Location*);
}

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
```

### <a name="example-managed-command-line-application-module"></a>例: マネージコマンドラインアプリケーションモジュール

```cpp
// MarshalStruct_pi.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Sequential, Pack=8)]
value struct MLocation {
   int x;
   int y;
};

value struct TraditionalDLL {
   [DllImport("TraditionalDLL3.dll")]
   static public double GetDistance(MLocation, MLocation);
   [DllImport("TraditionalDLL3.dll")]
   static public double InitLocation(MLocation*);
};

int main() {
   MLocation loc1;
   loc1.x = 0;
   loc1.y = 0;

   MLocation loc2;
   loc2.x = 100;
   loc2.y = 100;

   double dist = TraditionalDLL::GetDistance(loc1, loc2);
   Console::WriteLine("[managed] distance = {0}", dist);

   MLocation loc3;
   TraditionalDLL::InitLocation(&loc3);
   Console::WriteLine("[managed] x={0} y={1}", loc3.x, loc3.y);
}
```

```Output
[unmanaged] loc1(0,0) loc2(100,100)
[managed] distance = 141.42135623731
[unmanaged] Initializing location...
[managed] x=50 y=50
```

## <a name="see-also"></a>関連項目

[C++ での明示的な PInvoke の使用 (DllImport 属性)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
