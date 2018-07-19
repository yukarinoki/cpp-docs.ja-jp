---
title: '方法: PInvoke を使用して文字列をマーシャ リング |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a377e7074e72693a1a63e392c64a6d60c5995b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33133208"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>方法: PInvoke を使用して文字列をマーシャリングする
このトピックのネイティブ受け取る関数を C スタイルの文字列は、CLR の文字列を使用して呼び出すことができる .NET Framework プラットフォーム呼び出しのサポートを使用して system::string を入力します。 Visual の C++ プログラマは、ほとんどのコンパイル時エラーを報告がタイプ セーフではありませんし、実装に時間がかかることができます、P/invoke が用意されているため (可能な場合)、代わりに、C++ Interop 機能を使用することをお勧めします。 アンマネージ API が DLL としてパッケージ化、ソース コードを使用できない場合は、その P/invoke は唯一のオプションが、それ以外の場合を参照してください[を使用して C++ Interop (暗黙の PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)です。  
  
 マネージ コードとアンマネージの文字列がレイアウトされる異なる方法でメモリ内で、マネージ コードにアンマネージ関数から文字列を渡すため必要があります、<xref:System.Runtime.InteropServices.MarshalAsAttribute>文字列データをマーシャ リングするために必要な変換のメカニズムを挿入するようコンパイラに指示する属性正しくかつ安全にします。  
  
 組み込みのデータ型のみを使用する関数と同様<xref:System.Runtime.InteropServices.DllImportAttribute>をネイティブの関数が--へのハンドルの C スタイル文字列を取るものとこれらのエントリ ポイントを定義する代わりに--文字列を渡すために、マネージ エントリ ポイントを宣言するために使用、<xref:System.String>型代わりに使用できます。 これには、必要な変換を実行するコードを挿入するコンパイラ メッセージが表示されます。 各関数の引数、文字列を受け取るアンマネージ関数で、<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性は C スタイルの文字列としてネイティブ関数に文字列オブジェクトをマーシャ リングすることを示すために使用する必要があります。  
  
## <a name="example"></a>例  
 次のコードは、アンマネージ コードとマネージ モジュールで構成されます。 アンマネージ モジュールは、char * の形式での C スタイルの ANSI 文字列を受け取る TakesAString に呼び出される関数を定義する DLL です。 マネージ モジュールは、コマンド ライン アプリケーション TakesAString 関数は、char の代わりにマネージ System.String を取るものと定義を\*です。 <xref:System.Runtime.InteropServices.MarshalAsAttribute> TakesAString が呼び出されたときにマネージ文字列をマーシャ リングする方法を示すために属性を使用します。  
  
```  
// TraditionalDll2.cpp  
// compile with: /LD /EHsc  
#include <windows.h>  
#include <stdio.h>  
#include <iostream>  
  
using namespace std;  
  
#define TRADITIONALDLL_EXPORTS  
#ifdef TRADITIONALDLL_EXPORTS  
#define TRADITIONALDLL_API __declspec(dllexport)  
#else  
#define TRADITIONALDLL_API __declspec(dllimport)  
#endif  
  
extern "C" {  
   TRADITIONALDLL_API void TakesAString(char*);  
}  
  
void TakesAString(char* p) {  
   printf_s("[unmanaged] %s\n", p);  
}  
```  
  
```  
// MarshalString.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
value struct TraditionalDLL  
{  
   [DllImport("TraditionalDLL2.dll")]  
      static public void   
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);  
};  
  
int main() {  
   String^ s = gcnew String("sample string");  
    Console::WriteLine("[managed] passing managed string to unmanaged function...");  
   TraditionalDLL::TakesAString(s);  
   Console::WriteLine("[managed] {0}", s);  
}  
```  
  
 この手法では、ネイティブ関数で文字列に加えられた変更は、文字列のマネージ コピーに反映されませんので、アンマネージ ヒープ上に構築する対象の文字列のコピーが発生します。  
  
 従来のマネージ コードに、DLL の一部は公開されていませんことに注意してください #include ディレクティブです。 実際には、DLL にはアクセス時にのみでの機能に問題が取り込まれるように`DllImport`はコンパイル時に、検出されません。  
  
## <a name="see-also"></a>関連項目  
 [C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)