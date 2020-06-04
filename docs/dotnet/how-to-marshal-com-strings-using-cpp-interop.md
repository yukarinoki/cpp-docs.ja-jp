---
title: '方法: C++ Interop を使用して COM 文字列をマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- C++ Interop, strings
- data marshaling [C++], strings
- COM [C++], marshaling strings
ms.assetid: 06590759-bf99-4e34-a3a9-4527ea592cc2
ms.openlocfilehash: 8dfdad892261d5ae2d3494734458e1447f8ebd7c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545229"
---
# <a name="how-to-marshal-com-strings-using-c-interop"></a>方法: C++ Interop を使用して COM 文字列をマーシャリングする

このトピックでは、BSTR (COM プログラミングで好まれる基本的な文字列形式) をマネージ関数からアンマネージ関数に渡す方法、およびその逆の方法について説明します。 他の文字列型との相互運用については、次のトピックを参照してください。

- [方法: C++ Interop を使用して Unicode 文字列をマーシャリングする](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [方法: C++ Interop を使用して ANSI 文字列をマーシャリングする](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

次のコード例では、マネージ[、アン](../preprocessor/managed-unmanaged.md)マネージ #pragma ディレクティブを使用して、マネージ関数とアンマネージ関数を同じファイルに実装しますが、これらの関数は、別々のファイルで定義されている場合と同じ方法で相互運用します。 アンマネージ関数のみを含むファイルを[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)でコンパイルする必要はありません。

## <a name="example"></a>例

次の例では、BSTR (COM プログラミングで使用される文字列形式) をマネージ関数からアンマネージ関数に渡す方法を示します。 呼び出し元のマネージ関数は、<xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> を使用して、.NET System.string のコンテンツの BSTR 表現のアドレスを取得します。 このポインターは[pin_ptr (C++/cli)](../extensions/pin-ptr-cpp-cli.md)を使用して固定されており、アンマネージ関数の実行中にガベージコレクションサイクル中にその物理アドレスが変更されないようにします。 ガベージコレクターは、 [pin_ptr (C++/cli)](../extensions/pin-ptr-cpp-cli.md)がスコープ外になるまで、メモリを移動できません。

```cpp
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

次の例は、アンマネージからアンマネージ関数に BSTR を渡す方法を示しています。 受信マネージ関数は、の文字列を BSTR として使用するか、<xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> を使用して、他のマネージ関数で使用するために <xref:System.String> に変換することができます。 BSTR を表すメモリはアンマネージヒープに割り当てられるため、アンマネージヒープにはガベージコレクションが存在しないため、ピン留めは必要ありません。

```cpp
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

## <a name="see-also"></a>参照

[C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)
