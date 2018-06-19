---
title: '方法: C++ Interop を使用してマーシャ リング コールバックおよびデリゲート |Microsoft ドキュメント'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd1b9a13ebcc9f416a2953f53c98231b7a0df3c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132779"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>方法: C++ Interop を使用してコールバックおよびデリゲートをマーシャリングする
このトピックでは、コールバックのマーシャ リングする方法を示していて、Visual C を使用してマネージ コードとアンマネージ コード間でのデリゲート (コールバックの管理対象のバージョン)。  
  
 次のコード例、[マネージ、アンマネージ](../preprocessor/managed-unmanaged.md)関数は、個別のファイルで定義することもでしたが、マネージ リソースと同じファイル内の関数をアンマネージ #pragma ディレクティブを実装します。 アンマネージ関数のみを含むファイルを使用してコンパイルする必要はありません、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)です。  
  
## <a name="example"></a>例  
 次の例では、マネージ デリゲートをトリガーするアンマネージ API を構成する方法を示します。 マネージ デリゲートを作成し、相互運用機能のいずれかの<xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>デリゲートの基になるエントリ ポイントを取得するために使用します。 このアドレスは、マネージ関数として実装されている事実を認識していなくても呼び出すアンマネージ関数に渡されます。  
  
 注意してが可能であれば、必須ではありません、暗証番号 (pin) を使用してデリゲート[pin_ptr (C + + CLI)](../windows/pin-ptr-cpp-cli.md)から再配置したり、ガベージ コレクターによって破棄されていることがないようにします。 不完全なガベージ コレクションからの保護は、必要なが必要です。 これにより、コレクションが再配置を防ぐことができます、以上に保護を提供ピン留めします。  
  
 デリゲートは、ガベージ コレクション再配置されている場合に影響しません、基にマネージ コールバックのため<xref:System.Runtime.InteropServices.GCHandle.Alloc%2A>デリゲートの再配置を許可するが、破棄を防止は、デリゲートへの参照を追加するために使用します。 Pin_ptr ではなく GCHandle を使用するには、マネージ ヒープの断片化可能性が少なくなります。  
  
```  
// MarshalDelegate1.cpp  
// compile with: /clr  
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   printf_s("[unmanaged] got callback address, calling it...\n");  
   return fp(n, m);  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   return n + m;  
}  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
   GCHandle gch = GCHandle::Alloc(fp);  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
// force garbage collection cycle to prove  
// that the delegate doesn't get disposed  
   GC::Collect();  
  
   int answer = TakesCallback(cb, 243, 257);  
  
// release reference to delegate  
   gch.Free();  
}  
```  
  
## <a name="example"></a>例  
 次の例は、前の例に似ていますが、ここでは、指定された関数ポインターが格納、アンマネージ API でそのことができますが呼び出されるように、いつでも任意の長さの時間のガベージ コレクションが抑制されることを必要とします。 次の例のグローバル インスタンスを使用してその結果、<xref:System.Runtime.InteropServices.GCHandle>を防止デリゲート関数のスコープに依存しない、効果的に再配置します。 前述の最初の例は pin_ptr を使用してこれらの例については、必要はありませんが、ここではありませんどおり、pin_ptr のスコープは 1 つの関数に制限されます。  
  
```  
// MarshalDelegate2.cpp  
// compile with: /clr   
#include <iostream>  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
#pragma unmanaged  
  
// Declare an unmanaged function type that takes two int arguments  
// Note the use of __stdcall for compatibility with managed code  
typedef int (__stdcall *ANSWERCB)(int, int);  
static ANSWERCB cb;  
  
int TakesCallback(ANSWERCB fp, int n, int m) {  
   cb = fp;  
   if (cb) {  
      printf_s("[unmanaged] got callback address (%d), calling it...\n", cb);  
      return cb(n, m);  
   }  
   printf_s("[unmanaged] unregistering callback");  
   return 0;  
}  
  
#pragma managed  
  
public delegate int GetTheAnswerDelegate(int, int);  
  
int GetNumber(int n, int m) {  
   Console::WriteLine("[managed] callback!");  
   static int x = 0;  
   ++x;  
  
   return n + m + x;  
}  
  
static GCHandle gch;  
  
int main() {  
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);  
  
   gch = GCHandle::Alloc(fp);  
  
   IntPtr ip = Marshal::GetFunctionPointerForDelegate(fp);  
   ANSWERCB cb = static_cast<ANSWERCB>(ip.ToPointer());  
   Console::WriteLine("[managed] sending delegate as callback...");  
  
   int answer = TakesCallback(cb, 243, 257);  
  
   // possibly much later (in another function)...  
  
   Console::WriteLine("[managed] releasing callback mechanisms...");  
   TakesCallback(0, 243, 257);  
   gch.Free();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)