---
title: '方法: C++ Interop を使用して Unicode 文字列をマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- Unicode, marshaling strings
ms.assetid: 96c2141d-6c5d-43ef-a1aa-5785afb9a9aa
ms.openlocfilehash: da320dbd41e7158e3bc2482b96a73c1f4728a01b
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414309"
---
# <a name="how-to-marshal-unicode-strings-using-c-interop"></a>方法: C++ Interop を使用して Unicode 文字列をマーシャリングする

このトピックでは、Visual C++ 相互運用性の1つのファセットについて説明します。 詳細については、「 [C++ Interop の使用 (暗黙的な PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)」を参照してください。

次のコード例では、マネージ [、アン](../preprocessor/managed-unmanaged.md) マネージ #pragma ディレクティブを使用して、マネージ関数とアンマネージ関数を同じファイルに実装しますが、これらの関数は、別々のファイルで定義されている場合と同じ方法で相互運用します。 アンマネージ関数のみを含むファイルを [/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)でコンパイルする必要はありません。

このトピックでは、Unicode 文字列をマネージ関数からアンマネージ関数に渡す方法、およびその逆を行う方法について説明します。 他の文字列型との相互運用については、次のトピックを参照してください。

- [方法: C++ Interop を使用して ANSI 文字列をマーシャリングする](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [方法: C++ Interop を使用して COM 文字列をマーシャリングする](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

## <a name="example-pass-unicode-string-from-managed-to-unmanaged-function"></a>例: マネージからアンマネージ関数に Unicode 文字列を渡す

マネージ関数からアンマネージ関数に Unicode 文字列を渡すには、PtrToStringChars 関数 (Vcclr .h で宣言されています) を使用して、マネージ文字列が格納されているメモリ内のにアクセスできます。 このアドレスはネイティブ関数に渡されるため、文字列データが再配置されないように、 [pin_ptr (C++/cli)](../extensions/pin-ptr-cpp-cli.md) でメモリを固定することが重要です。アンマネージ関数の実行中にガベージコレクションサイクルを実行する必要があります。

```cpp
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

## <a name="example-data-marshaling-required-to-access-unicode-string"></a>例: Unicode 文字列にアクセスするために必要なデータマーシャリング

次の例は、アンマネージ関数によって呼び出されたマネージ関数で Unicode 文字列にアクセスするために必要なデータマーシャリングを示しています。 ネイティブ Unicode 文字列を受け取るマネージ関数は、メソッドを使用してマネージ文字列に変換し <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> ます。

```cpp
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
