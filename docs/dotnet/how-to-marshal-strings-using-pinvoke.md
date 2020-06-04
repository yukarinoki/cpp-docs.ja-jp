---
title: '方法: PInvoke を使用して文字列をマーシャリングする'
ms.custom: get-started-article
ms.date: 09/09/2016
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
ms.openlocfilehash: e89177261aa32d34ea392030078d4088ea61e2a5
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545223"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>方法: PInvoke を使用して文字列をマーシャリングする

このトピックでは、.NET Framework プラットフォーム呼び出しサポートを使用して CLR 文字列型の System:: String を使用して、C スタイルの文字列を受け入れるネイティブ関数を呼び出す方法について説明します。 Visual C++プログラマは、(可能なC++場合は) 代わりに相互運用機能を使用することをお勧めします。これは、P/Invoke ではコンパイル時のエラー報告がほとんどなく、タイプセーフではないため、実装が面倒な場合があるためです。 アンマネージ API が DLL としてパッケージ化されていて、ソースコードが使用できない場合は、P/Invoke が唯一のオプションですが、それ以外の場合は「[相互運用機能 (暗黙的な PInvoke) の使用」をC++ ](../dotnet/using-cpp-interop-implicit-pinvoke.md)参照してください。

マネージ文字列とアンマネージ文字列は、メモリ内では異なる方法で配置されます。したがって、マネージ関数からアンマネージ関数に文字列を渡すには、文字列データを正しく、安全にマーシャリングするために必要な変換機構を挿入するようにコンパイラに指示するために、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性が必要です。

組み込みデータ型のみを使用する関数と同様に、ネイティブ関数にマネージエントリポイントを宣言するために <xref:System.Runtime.InteropServices.DllImportAttribute> が使用されます。ただし、文字列を渡す場合は、これらのエントリポイントを C スタイルの文字列として定義するのではなく、<xref:System.String> 型へのハンドルを使用できます。 これにより、コンパイラは、必要な変換を実行するコードを挿入するように求められます。 文字列を受け取るアンマネージ関数の各関数引数に対して、<xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性を使用して、文字列オブジェクトを C スタイルの文字列としてネイティブ関数にマーシャリングする必要があることを示す必要があります。

マーシャラーは非表示のラッパールーチンでアンマネージ関数への呼び出しをラップし、アンマネージコンテキストでローカルに割り当てられた文字列にマネージ文字列をピン留めしてコピーします。これにより、アンマネージ関数に渡されます。 アンマネージ関数がを返すと、ラッパーはリソースを削除するか、スタック上にある場合は、ラッパーがスコープ外になると再利用されます。 アンマネージ関数は、このメモリの責任を負いません。 アンマネージコードは、独自の CRT によって設定されたヒープ内のメモリのみを作成および削除するため、異なる CRT バージョンを使用するマーシャラーに問題が発生することはありません。

アンマネージ関数が戻り値または出力パラメーターとして文字列を返す場合、マーシャラーはそれを新しいマネージ文字列にコピーしてからメモリを解放します。 詳細については、「[既定のマーシャリング動作](/dotnet/framework/interop/default-marshaling-behavior)」と「[プラットフォーム呼び出しによるデータのマーシャリング](/dotnet/framework/interop/marshaling-data-with-platform-invoke)」を参照してください。

## <a name="example"></a>例

次のコードは、アンマネージモジュールとマネージモジュールで構成されています。 アンマネージモジュールは、C スタイルの ANSI 文字列を char * 形式で受け取る TakesAString という名前の関数を定義する DLL です。 マネージモジュールは、TakesAString 関数をインポートするコマンドラインアプリケーションですが、char\*ではなくマネージ System.string を取得するように定義されています。 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性は、TakesAString が呼び出されたときにマネージ文字列をマーシャリングする方法を示すために使用されます。

```cpp
// TraditionalDll2.cpp
// compile with: /LD /EHsc
#include <windows.h>
#include <stdio.h>
#include <iostream>

using namespace std;

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAString(char*);
}

void TakesAString(char* p) {
   printf_s("[unmanaged] %s\n", p);
}
```

```cpp
// MarshalString.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL
{
   [DllImport("TraditionalDLL2.dll")]
      static public void
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);
};

int main() {
   String^ s = gcnew String("sample string");
    Console::WriteLine("[managed] passing managed string to unmanaged function...");
   TraditionalDLL::TakesAString(s);
   Console::WriteLine("[managed] {0}", s);
}
```

この手法を使用すると、アンマネージヒープに文字列のコピーが作成されるため、ネイティブ関数によって文字列に加えられた変更は、文字列のマネージコピーに反映されません。

DLL の一部は、従来の #include ディレクティブを使用してマネージコードに公開されないことに注意してください。 実際、DLL は実行時にのみアクセスされるため、`DllImport` でインポートされた関数に関する問題はコンパイル時に検出されません。

## <a name="see-also"></a>参照

[C++ での明示的な PInvoke (DllImport 属性) の使用方法](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
