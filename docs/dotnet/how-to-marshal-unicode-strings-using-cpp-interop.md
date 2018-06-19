---
title: '方法: C++ Interop を使用して Unicode 文字列をマーシャ リング |Microsoft ドキュメント'
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
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e5290958a55c61dd55adac0f182af7163896d694
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130465"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>方法: C++ Interop を使用して Unicode 文字列をマーシャリングする
このトピックでは、Visual C の相互運用性のファセットの 1 つを示します。 詳細については、次を参照してください。[を使用して C++ Interop (暗黙の PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)です。  
  
 次のコード例、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)個別のファイルで定義されている場合、これらの関数が同様に、相互運用が、マネージ リソースと、同じファイル内の関数をアンマネージ #pragma ディレクティブを実装します。 アンマネージ関数のみを含むファイルを使用してコンパイルする必要はありません[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)です。  
  
 このトピックでは、Unicode 文字列をする方法を示しますをアンマネージ関数と、その逆に、管理対象から渡されます。 その他の文字列型との相互運用、次のトピックを参照してください。  
  
-   [方法: C++ Interop を使用して ANSI 文字列をマーシャリングする](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [方法: C++ Interop を使用して COM 文字列をマーシャリングする](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
## <a name="example"></a>例  
 Unicode 文字列をマネージからアンマネージ関数に渡す、(Vcclr.h で宣言) PtrToStringChars 関数を使用するマネージ文字列が格納されているメモリにアクセスします。 このアドレスはネイティブ関数に渡される、のでことが重要で、メモリを固定する[pin_ptr (C + + CLI)](../windows/pin-ptr-cpp-cli.md)を文字列データが再配置することを防ぐためにガベージ コレクション サイクルを実行中に、アンマネージ関数を実行します。  
  
```  
// MarshalUnicode1.cpp  
// compile with: /clr  
#include <iostream>  
#include <stdio.h>  
#include <vcclr.h>  
  
using namespace std;  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
void NativeTakesAString(const wchar_t* p) {  
   printf_s("(native) received '%S'\n", p);  
}  
  
#pragma managed  
  
int main() {  
   String^ s = gcnew String("test string");  
   pin_ptr<const wchar_t> str = PtrToStringChars(s);  
  
   Console::WriteLine("(managed) passing string to native func...");  
   NativeTakesAString( str );  
}  
```  
  
## <a name="example"></a>例  
 次の例では、アンマネージ関数によって呼び出されるマネージ関数で Unicode 文字列にアクセスするために必要なデータのマーシャ リングを示します。 ネイティブの Unicode 文字列を受け取ると、マネージ関数を使用して管理対象の文字列に変換、<xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A>メソッドです。  
  
```  
// MarshalUnicode2.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace std;  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma managed  
  
void ManagedStringFunc(wchar_t* s) {  
   String^ ms = Marshal::PtrToStringUni((IntPtr)s);  
   Console::WriteLine("(managed) received '{0}'", ms);  
}  
  
#pragma unmanaged  
  
void NativeProvidesAString() {  
   cout << "(unmanaged) calling managed func...\n";  
   ManagedStringFunc(L"test string");  
}  
  
#pragma managed  
  
int main() {  
   NativeProvidesAString();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)