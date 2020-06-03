---
title: '方法: C++ Interop を使用してコールバックおよびデリゲートをマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- C++ Interop, callbacks and delegates
- interop [C++], callbacks and delegates
- delegates [C++], marshaling
- marshaling [C++], callbacks and delegates
- callbacks [C++], marshaling
ms.assetid: 2313e9eb-5df9-4367-be0f-14b4712d8d2d
ms.openlocfilehash: 592eae0ff59baddb79b810d46669b78ecc801155
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544941"
---
# <a name="how-to-marshal-callbacks-and-delegates-by-using-c-interop"></a>方法: C++ Interop を使用してコールバックおよびデリゲートをマーシャリングする

このトピックでは、Visual C++を使用したマネージコードとアンマネージコード間のコールバックとデリゲート (コールバックのマネージバージョン) のマーシャリングについて説明します。

次のコード例では、マネージ[、アン](../preprocessor/managed-unmanaged.md)マネージ #pragma ディレクティブを使用して、マネージ関数とアンマネージ関数を同じファイルに実装しますが、関数を別のファイルに定義することもできます。 アンマネージ関数のみを含むファイルは、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)を使用してコンパイルする必要はありません。

## <a name="example"></a>例

次の例では、マネージデリゲートをトリガーするようにアンマネージ API を構成する方法を示します。 マネージデリゲートが作成され、<xref:System.Runtime.InteropServices.Marshal.GetFunctionPointerForDelegate%2A>の相互運用メソッドの1つが、デリゲートの基になるエントリポイントを取得するために使用されます。 このアドレスはアンマネージ関数に渡され、マネージ関数として実装されているという事実を知らずに呼び出します。

[Pin_ptr (C++/cli)](../extensions/pin-ptr-cpp-cli.md)を使用してデリゲートをピン留めして、ガベージコレクターによって再配置または破棄されないようにすることはできますが、これは必要ではありません。 不要なガベージコレクションからの保護が必要ですが、ピン留めによってコレクションが禁止され、再配置が妨げられるため、必要以上の保護が提供されます。

デリゲートがガベージコレクションによって再配置された場合、そのデリゲートは、使用されていないマネージコールバックには影響しません。したがって、デリゲートへの参照を追加するために <xref:System.Runtime.InteropServices.GCHandle.Alloc%2A> を使用し、デリゲートの再配置を許可し、破棄を防ぐことができます。 Pin_ptr の代わりに GCHandle を使用すると、マネージヒープの断片化の可能性が軽減されます。

```cpp
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

次の例は前の例と似ていますが、この例では、指定された関数ポインターはアンマネージ API によって格納されるため、いつでも呼び出すことができ、任意の時間にわたってガベージコレクションを抑制する必要があります。 その結果、次の例では、<xref:System.Runtime.InteropServices.GCHandle> のグローバルインスタンスを使用して、関数のスコープに依存せずに、デリゲートが再配置されないようにします。 最初の例で説明したように、この例では pin_ptr を使用する必要はありませんが、この例では、pin_ptr のスコープが1つの関数に限定されているため、この場合は動作しません。

```cpp
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

## <a name="see-also"></a>参照

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
