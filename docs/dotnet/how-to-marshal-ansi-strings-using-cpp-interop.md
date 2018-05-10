---
title: '方法: C++ Interop を使用して ANSI 文字列をマーシャ リング |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3690ca242b8c50c84c6eb4a8a7a437937268c6b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>方法: C++ Interop を使用して ANSI 文字列をマーシャリングする
このトピックでは、ANSI 文字列をする方法を示していますが、C++ Interop、.NET Framework を使用して渡す<xref:System.String>ANSI への変換は余分な手順が Unicode 形式で文字列を表します。 その他の文字列型との相互運用、次のトピックを参照してください。  
  
-   [方法: C++ Interop を使用して Unicode 文字列をマーシャリングする](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [方法: C++ Interop を使用して COM 文字列をマーシャリングする](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
 次のコード例、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)個別のファイルで定義されている場合、これらの関数が同様に、相互運用が、マネージ リソースと、同じファイル内の関数をアンマネージ #pragma ディレクティブを実装します。 アンマネージ関数のみを含むファイルを使用してコンパイルする必要はないため[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)、そのパフォーマンス特性を保持することができます。  
  
## <a name="example"></a>例  
 マネージからアンマネージ関数を使用して、ANSI 文字列を渡すことを示します<xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>です。 このメソッドは、アンマネージ ヒープのメモリが割り当てられ、変換を実行した後は、アドレスを返します。 つまり、ピン留めは必要ありません (アンマネージ関数に GC ヒープにメモリが渡されません) ため、IntPtr がから返されたこと<xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A>明示的に解放する必要がありますか、メモリがリークする結果。  
  
```  
// MarshalANSI1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const char* p) {  
   printf_s("(native) received '%s'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("sample string");  
   IntPtr ip = Marshal::StringToHGlobalAnsi(s);  
   const char* str = static_cast<const char*>(ip.ToPointer());  
  
   Console::WriteLine("(managed) passing string...");  
   NativeTakesAString( str );  
  
   Marshal::FreeHGlobal( ip );  
}  
```  
  
## <a name="example"></a>例  
 次の例では、アンマネージ関数によって呼び出されるマネージ関数内の ANSI 文字列にアクセスするために必要なデータのマーシャ リングを示します。 ネイティブの文字列を受け取ると、マネージ関数が直接使用するかを使用して管理対象の文字列に変換、<xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A>メソッドを表示します。  
  
```  
// MarshalANSI2.cpp  
// compile with: /clr  
#include <iostream>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(char* s) {  
   String^ ms = Marshal::PtrToStringAnsi(static_cast<IntPtr>(s));  
   Console::WriteLine("(managed): received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(native) calling managed func...\n";  
   ManagedStringFunc("test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)