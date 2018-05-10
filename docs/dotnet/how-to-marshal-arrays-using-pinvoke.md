---
title: '方法: PInvoke を使用して配列をマーシャ リング |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling [C++], arrays
- platform invoke [C++], arrays
- interop [C++], arrays
- data marshaling [C++], arrays
ms.assetid: a1237797-a2da-4df4-984a-6333ed3af406
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 03e3cf184828c33c63c5252344eb0041640729cb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-arrays-using-pinvoke"></a>方法: PInvoke を使用して配列をマーシャリングする
このトピックの C スタイルの文字列は、CLR の文字列型を使用して呼び出すことができますを受け入れる関数をネイティブ<xref:System.String>.NET Framework プラットフォーム呼び出しのサポートを使用します。 Visual の C++ プログラマは、ほとんどのコンパイル時エラーを報告がタイプ セーフではありませんし、実装に時間がかかることができます、P/invoke が用意されているため (可能な場合)、代わりに、C++ Interop 機能を使用することをお勧めします。 アンマネージ API が DLL としてパッケージ化され、ソース コードを使用できない、P/invoke が唯一のオプション (それ以外の場合を参照してください[を使用して C++ Interop (暗黙の PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md))。  
  
## <a name="example"></a>例  
 ネイティブおよびマネージ配列にはメモリに異なるレイアウト、ためには、変換、またはマーシャ リングが必要がありますマネージ/アンマネージの境界上で正常に転送します。 このトピックでは、マネージ コードから単純な (blitable) 項目の配列をネイティブ関数に渡される方法を示します。  
  
 マネージ/アンマネージ データが一般に、マーシャ リングの場合は true、<xref:System.Runtime.InteropServices.DllImportAttribute>属性が使用されるネイティブ関数の各マネージ エントリ ポイントを作成するために使用します。 引数としての配列を受け取る関数の場合、<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性は、データをマーシャ リングする方法をコンパイラに指定にも使用する必要があります。 次の例で、<xref:System.Runtime.InteropServices.UnmanagedType>を C スタイル配列として、マネージ配列をマーシャ リングするかを示す列挙を使用します。  
  
 次のコードはアンマネージとマネージ モジュールで構成されます。 アンマネージ モジュールは、整数の配列を受け取る関数を定義する DLL です。 2 番目のモジュールは、この関数のインポートは、マネージ配列の観点から定義および使用する管理対象のコマンド ライン アプリケーション、<xref:System.Runtime.InteropServices.MarshalAsAttribute>配列が呼び出されたときに、ネイティブ配列に変換することを指定する属性。  
  
 マネージ モジュールは、/clr と共にコンパイルします。  
  
```cpp  
// TraditionalDll4.cpp  
// compile with: /LD /EHsc  
#include <iostream>  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAnArray(int len, int[]);  
}  
  
void TakesAnArray(int len, int a[]) {  
   printf_s("[unmanaged]\n");  
   for (int i=0; i<len; i++)  
      printf("%d = %d\n", i, a[i]);  
}  
```  
  
```cpp  
// MarshalBlitArray.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL {  
   [DllImport("TraditionalDLL4.dll")]  
   static public void TakesAnArray(  
   int len,[MarshalAs(UnmanagedType::LPArray)]array<int>^);  
};  
  
int main() {  
   array<int>^ b = gcnew array<int>(3);  
   b[0] = 11;  
   b[1] = 33;  
   b[2] = 55;  
   TraditionalDLL::TakesAnArray(3, b);  
  
   Console::WriteLine("[managed]");  
   for (int i=0; i<3; i++)  
      Console::WriteLine("{0} = {1}", i, b[i]);  
}  
```  
  
 従来のマネージ コードに、DLL の一部は公開されていませんことに注意してください #include ディレクティブです。 実際には、DLL が実行時にのみアクセスされるための機能に問題と共にインポート<xref:System.Runtime.InteropServices.DllImportAttribute>はコンパイル時に、検出されません。  
  
## <a name="see-also"></a>関連項目  
 [C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)