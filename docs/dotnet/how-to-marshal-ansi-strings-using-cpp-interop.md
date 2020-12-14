---
description: '詳細については、「方法: C++ Interop を使用して ANSI 文字列をマーシャリングする」を参照してください。'
title: '方法: C++ Interop を使用して ANSI 文字列をマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- ANSI [C++], marshaling strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
ms.assetid: 5eda2eb6-5140-40f0-82cf-7ce171fffb45
ms.openlocfilehash: 7a06e045c3c097cb866c6d289ce24638a6965d1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258266"
---
# <a name="how-to-marshal-ansi-strings-using-c-interop"></a>方法: C++ Interop を使用して ANSI 文字列をマーシャリングする

このトピックでは、C++ Interop を使用して ANSI 文字列を渡す方法について説明しますが、.NET Framework は <xref:System.String> Unicode 形式の文字列を表します。そのため、ansi への変換は追加の手順です。 他の文字列型との相互運用については、次のトピックを参照してください。

- [方法: C++ Interop を使用して Unicode 文字列をマーシャリングする](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [方法: C++ Interop を使用して COM 文字列をマーシャリングする](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

次のコード例では、マネージ [、アン](../preprocessor/managed-unmanaged.md) マネージ #pragma ディレクティブを使用して、マネージ関数とアンマネージ関数を同じファイルに実装しますが、これらの関数は、別々のファイルで定義されている場合と同じ方法で相互運用します。 アンマネージ関数のみを含むファイルは、 [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)を使用してコンパイルする必要がないため、パフォーマンス特性を保持できます。

## <a name="example-pass-ansi-string"></a>例: Pass ANSI string

この例では、を使用して、マネージからアンマネージ関数に ANSI 文字列を渡す方法を示し <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> ます。 このメソッドは、アンマネージヒープにメモリを割り当て、変換の実行後にアドレスを返します。 これは、(GC ヒープのメモリがアンマネージ関数に渡されないため) ピン留めが不要で、から返される IntPtr が <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> 明示的に解放されるか、またはメモリリークの結果になる必要があることを意味します。

```cpp
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

## <a name="example-data-marshaling-required-to-access-ansi-string"></a>例: ANSI 文字列にアクセスするために必要なデータマーシャリング

次の例は、アンマネージ関数によって呼び出されるマネージ関数で ANSI 文字列にアクセスするために必要なデータマーシャリングを示しています。 ネイティブ文字列を受け取るマネージ関数は、この関数を直接使用するか、メソッドを使用してマネージ文字列に変換することができ <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> ます。以下に例を示します。

```cpp
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
