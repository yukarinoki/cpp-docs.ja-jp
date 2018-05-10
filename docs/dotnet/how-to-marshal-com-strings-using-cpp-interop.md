---
title: '方法: C++ Interop を使用して COM 文字列をマーシャ リング |Microsoft ドキュメント'
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
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 918825dd6563f59167baa844b94edfc1033498a6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>方法: C++ Interop を使用して COM 文字列をマーシャリングする
このトピックでは、(COM プログラミングで推奨される基本的な文字列形式) の BSTR をする方法を示しますをアンマネージ関数と、その逆に、管理対象から渡されます。 その他の文字列型との相互運用、次のトピックを参照してください。  
  
-   [方法: C++ Interop を使用して Unicode 文字列をマーシャリングする](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [方法: C++ Interop を使用して ANSI 文字列をマーシャリングする](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
 次のコード例、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)個別のファイルで定義されている場合、これらの関数が同様に、相互運用が、マネージ リソースと、同じファイル内の関数をアンマネージ #pragma ディレクティブを実装します。 アンマネージ関数のみを含むファイルを使用してコンパイルする必要はありません[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)です。  
  
## <a name="example"></a>例  
 次の例では、BSTR (COM プログラミングで使用される文字列形式) を渡す方法を示しています、アンマネージ関数をマネージからです。 呼び出し元関数の使用を管理する<xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A>.NET System.String の内容の BSTR 形式のアドレスを取得します。 使用してこのポインターがピン留め[pin_ptr (C + + CLI)](../windows/pin-ptr-cpp-cli.md)をアンマネージ関数の実行中に、その物理アドレスは、ガベージ コレクション サイクル中に変更されないことを確認します。 ガベージ コレクターが移動されるまでメモリを禁止、 [pin_ptr (C + + CLI)](../windows/pin-ptr-cpp-cli.md)がスコープ外になります。  
  
```  
// MarshalBSTR1.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(BSTR bstr) {  
   printf_s("%S", bstr);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = "test string";  
  
   IntPtr ip = Marshal::StringToBSTR(s);  
   BSTR bs = static_cast<BSTR>(ip.ToPointer());  
   pin_ptr<BSTR> b = &bs;  
  
   NativeTakesAString( bs );  
   Marshal::FreeBSTR(ip);  
}  
```  
  
## <a name="example"></a>例  
 次の例では、BSTR を渡す方法を示しています、アンマネージ関数をアンマネージ関数から。 マネージ関数で文字列を BSTR として使用したりを使用して受信<xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A>に変換するために、<xref:System.String>他で使用するマネージ関数です。 BSTR を表すメモリが割り当てられるので、アンマネージ ヒープのピン留めは必要ありません、アンマネージ ヒープのガベージ コレクションが存在しないためです。  
  
```  
// MarshalBSTR2.cpp  
// compile with: /clr  
#define WINVER 0x0502  
#define _AFXDLL  
#include <afxwin.h>  
  
#include <iostream>  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedTakesAString(BSTR bstr) {  
   String^ s = Marshal::PtrToStringBSTR(static_cast<IntPtr>(bstr));  
   Console::WriteLine("(managed) convered BSTR to String: '{0}'", s);  
}  
  
#pragma unmanaged  
  
void UnManagedFunc() {  
   BSTR bs = SysAllocString(L"test string");  
   printf_s("(unmanaged) passing BSTR to managed func...\n");  
   ManagedTakesAString(bs);  
}  
  
#pragma managed  
  
int main() {  
   UnManagedFunc();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)