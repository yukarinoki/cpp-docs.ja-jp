---
title: Debug クラス (C + + CLI) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fddf192b21b878c82ca663da657c55e32fd9173d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106207"
---
# <a name="debug-class-ccli"></a>Debug クラス (C++/CLI)
使用する場合<xref:System.Diagnostics.Debug>Visual C のアプリケーションで、動作が、デバッグとリリース ビルドの間で変更されません。  
  
## <a name="remarks"></a>コメント  
 動作は、 <xref:System.Diagnostics.Trace> Debug クラスの動作と同じですが、シンボル定義されているトレースに依存します。 つまりする必要のある`#ifdef`すべてトレースに関連するコードをリリース ビルドでのデバッグ動作を防ぐためにします。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例は、常に使用してコンパイルするかどうかに関係なく、出力ステートメントを実行 **/DDEBUG**または **/DTRACE**です。  
  
### <a name="code"></a>コード  
  
```  
// mcpp_debug_class.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
   Trace::Unindent();  
  
   Debug::WriteLine("test");  
}  
```  
  
### <a name="output"></a>出力  
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 予期しない動作を取得する (つまり、"test"が出力されない、リリース ビルド) を使用する必要があります、`#ifdef`と`#endif`ディレクティブです。 上記のコード サンプルは、この修正プログラムを示すために下に変更されます。  
  
### <a name="code"></a>コード  
  
```  
// mcpp_debug_class2.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
  
#ifdef TRACE   // checks for a debug build  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
#endif  
   Trace::Unindent();  
  
#ifdef DEBUG   // checks for a debug build  
   Debug::WriteLine("test");  
#endif   //ends the conditional block  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)