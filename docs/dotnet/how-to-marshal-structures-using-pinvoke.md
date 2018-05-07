---
title: '方法: PInvoke を使用してマーシャ リング構造体 |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], structures
- platform invoke [C++], structures
- interop [C++], structures
- marshaling [C++], structures
ms.assetid: 35997e6f-9251-4af3-8c6e-0712d64d6a5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4ff1801c9bb2de06ae2717e8f69bcd39fdf3bc98
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-structures-using-pinvoke"></a>方法: PInvoke を使用して構造体をマーシャリングする
このドキュメントでは、C スタイル構造体に呼び出すことによってマネージ関数 P/invoke を使用してを受け入れるどのネイティブ関数について説明します。 代わりに、C++ Interop 機能を使用することをお勧めします P/invoke P/invoke はほとんどのコンパイル時エラーを報告があるので、タイプ セーフではありませんしを実装する、アンマネージ API が DLL としてパッケージ化され、ソース コードが面倒になることができます。P/invoke は唯一のオプションを使用できる、です。 それ以外の場合、次のドキュメントを参照してください。  
  
-   [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
  
-   [方法: PInvoke を使用して文字列をマーシャリングする](../dotnet/how-to-marshal-strings-using-pinvoke.md)
  
 既定では、ネイティブおよびマネージ構造体レイアウトが異なる、メモリ内、正常に追加の手順をデータの整合性を維持するマネージ/アンマネージの境界を越えて構造体を渡すことが必要です。  
  
 このドキュメントでは、ネイティブの構造と結果の構造をアンマネージ関数に渡される方法に相当するマネージを定義するために必要な手順について説明します。 このドキュメントであると推定単純な構造体 — 文字列またはポインターを含まないもの — 使用されます。 非 blittable 型の相互運用性については、次を参照してください。[を使用して C++ Interop (暗黙の PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)です。 P/invoke では、戻り値として非 blittable 型を持つことはできません。 マネージ コードとアンマネージ コードで同じ表現である Blittable 型です。 詳細については、次を参照してください。 [blittable 型と非 Blittable 型](http://msdn.microsoft.com/Library/d03b050e-2916-49a0-99ba-f19316e5c1b3)です。  
  
 単純なをマーシャ リングするマネージ/アンマネージの境界を越えて blittable 型の構造体最初必要があります各ネイティブ構造体のマネージ バージョンが定義されています。 これらの構造体は、任意の有効な名前を持つことができます。2 つの構造、データ レイアウト以外のネイティブおよびマネージのバージョン間の関係はありません。 したがって、管理対象のバージョンには、サイズとネイティブ バージョンと同じ順序で同じフィールドが含まれている重要なは。 (非互換性は実行時までに明らかなならないため、構造体のマネージ コードとネイティブ バージョンが、同等であることを確認するメカニズムはありません。 これは 2 つの構造が同じデータ レイアウトを持つことを確認するプログラマの責任です。)  
  
 使用する必要はパフォーマンス向上のためのマネージ構造体のメンバーを並べ替え場合があります、ため、<xref:System.Runtime.InteropServices.StructLayoutAttribute>構造が順番にレイアウトされることを示すために属性。 構造体のパッキング ネイティブ構造体で使用されるものと同じにする設定を明示的に設定することをお勧めします。 (が既定では、Visual C では、8 バイト構造体のマネージ コードの両方のパッキングします。)  
  
1.  次に、使用<xref:System.Runtime.InteropServices.DllImportAttribute>は問題にならないポイントに同じ名前の両方のバージョンを使用する場合、関数シグネチャに構造体のマネージ バージョンを使用して、構造体をそのまま使用するアンマネージ関数に対応するエントリ ポイントを宣言する、構造体。  
  
2.  今すぐ実際にはマネージ関数のように、マネージ コードは、構造体の管理対象のバージョンをアンマネージ関数に渡すことができます。 これらの構造体渡せる値か、参照によって次の例で示すようです。  
  
## <a name="example"></a>例  
 次のコードはアンマネージとマネージ モジュールで構成されます。 アンマネージ モジュールは、場所と場所の構造体の 2 つのインスタンスを受け入れる GetDistance をという名前の関数と呼ばれる構造を定義する DLL です。 2 番目のモジュールは、GetDistance 関数のインポートが MLocation 場所の構造体のマネージそれと同等の観点から定義する管理対象のコマンド ライン アプリケーションです。 実際にはこれらの同じ名前はおそらく; 構造の両方のバージョンを使用します。ただし、別の名前は、管理対象のバージョンの観点から DllImport プロトタイプが定義されていることを示すためにここで使用されます。  
  
 従来を使用してマネージ コードに、DLL の一部は公開されていませんことに注意してください #include ディレクティブです。 実際には、DLL は実行時にのみ、アクセスため DllImport でインポートされた関数に関する問題はコンパイル時に検出されません。  
  
```  
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
  
## <a name="example"></a>例  
  
```  
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
 [C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
