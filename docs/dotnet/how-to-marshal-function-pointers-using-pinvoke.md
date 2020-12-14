---
description: '詳細については、「方法: PInvoke を使用して関数ポインターをマーシャリングする」を参照してください。'
title: '方法: PInvoke を使用して関数ポインターをマーシャリングする'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- data marshaling [C++], callbacks and delegates
- interop [C++], callbacks and delegates
- platform invoke [C++], callbacks and delegates
- marshaling [C++], callbacks and delegates
ms.assetid: dcf396fd-a91d-49c0-ab0b-1ea160668a89
ms.openlocfilehash: bfe3f669cf023ed914bdccb3ae15ccafefbb49c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302583"
---
# <a name="how-to-marshal-function-pointers-using-pinvoke"></a>方法: PInvoke を使用して関数ポインターをマーシャリングする

このトピックでは、.NET Framework P/Invoke 機能を使用してアンマネージ関数と相互運用するときに、マネージデリゲートを関数ポインターの代わりに使用する方法について説明します。 ただし、Visual C++ プログラマは、(可能な場合は) C++ 相互運用機能を使用することをお勧めします。これは、P/Invoke ではコンパイル時のエラー報告がほとんどなく、タイプセーフではなく、実装が面倒な場合があるためです。 アンマネージ API が DLL としてパッケージ化されていて、ソースコードが使用できない場合は、P/Invoke が唯一のオプションです。 それ以外の場合は、次のトピックを参照してください。

- [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)

- [方法: C++ Interop を使用してコールバックとデリゲートをマーシャリングする](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

関数ポインターを引数として受け取るアンマネージ Api は、ネイティブ関数ポインターの代わりにマネージデリゲートを使用してマネージコードから呼び出すことができます。 コンパイラは、デリゲートを関数ポインターとしてアンマネージ関数に自動的にマーシャリングし、必要なマネージ/アンマネージ遷移コードを挿入します。

## <a name="example"></a>例

次のコードは、アンマネージモジュールとマネージモジュールで構成されています。 アンマネージモジュールは、関数ポインターを受け取る TakesCallback と呼ばれる関数を定義する DLL です。 このアドレスは、関数を実行するために使用されます。

マネージモジュールは、関数ポインターとしてネイティブコードにマーシャリングされるデリゲートを定義し、属性を使用して <xref:System.Runtime.InteropServices.DllImportAttribute> ネイティブの TakesCallback 関数をマネージコードに公開します。 Main 関数では、デリゲートのインスタンスが作成され、TakesCallback 関数に渡されます。 プログラムの出力は、この関数がネイティブの TakesCallback 関数によって実行されることを示しています。

マネージ関数は、ネイティブ関数の実行中に .NET Framework のガベージコレクションがデリゲートを再配置しないようにするために、マネージデリゲートのガベージコレクションを抑制します。

```cpp
// TraditionalDll5.cpp
// compile with: /LD /EHsc
#include <iostream>
#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   /* Declare an unmanaged function type that takes two int arguments
      Note the use of __stdcall for compatibility with managed code */
   typedef int (__stdcall *CALLBACK)(int);
   TRADITIONALDLL_API int TakesCallback(CALLBACK fp, int);
}

int TakesCallback(CALLBACK fp, int n) {
   printf_s("[unmanaged] got callback address, calling it...\n");
   return fp(n);
}
```

```cpp
// MarshalDelegate.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

public delegate int GetTheAnswerDelegate(int);
public value struct TraditionalDLL {
   [DllImport("TraditionalDLL5.dll")]
   static public int TakesCallback(GetTheAnswerDelegate^ pfn, int n);
};

int GetNumber(int n) {
   Console::WriteLine("[managed] callback!");
   static int x = 0;
   ++x;
   return x + n;
}

int main() {
   GetTheAnswerDelegate^ fp = gcnew GetTheAnswerDelegate(GetNumber);
   pin_ptr<GetTheAnswerDelegate^> pp = &fp;
   Console::WriteLine("[managed] sending delegate as callback...");

   int answer = TraditionalDLL::TakesCallback(fp, 42);
}
```

DLL の一部は、従来の #include ディレクティブを使用してマネージコードに公開されないことに注意してください。 実際、DLL は実行時にのみアクセスされるため、でインポートされた関数に関する問題 <xref:System.Runtime.InteropServices.DllImportAttribute> はコンパイル時に検出されません。

## <a name="see-also"></a>関連項目

[C++ での明示的な PInvoke の使用 (DllImport 属性)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
