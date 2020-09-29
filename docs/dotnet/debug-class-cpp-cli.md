---
title: Debug クラス (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
ms.openlocfilehash: 47e1b949cb6e998508a3bd362b1c74961cf4cc23
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414153"
---
# <a name="debug-class-ccli"></a>Debug クラス (C++/CLI)

Visual C++ アプリケーションでを使用する場合、 <xref:System.Diagnostics.Debug> デバッグビルドとリリースビルドの間で動作が変わることはありません。

## <a name="remarks"></a>解説

の動作 <xref:System.Diagnostics.Trace> は Debug クラスの動作と同じですが、定義されているシンボルトレースに依存しています。 これは、 `#ifdef` リリースビルドでのデバッグ動作を防ぐために、トレース関連のコードを必要とすることを意味します。

## <a name="example-always-executes-output-statements"></a>例: 常に出力ステートメントを実行する

### <a name="description"></a>説明

次の例では、 **/DDEBUG** または **/DTRACE**のどちらを使用してコンパイルしたかにかかわらず、常に output ステートメントを実行します。

### <a name="code"></a>コード

```cpp
// mcpp_debug_class.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
   Trace::Unindent();

   Debug::WriteLine("test");
}
```

### <a name="output"></a>出力

```Output
    Entering Main
Hello World.
    Exiting Main
test
```

## <a name="example-use-ifdef-and-endif-directives"></a>例: #ifdef ディレクティブと #endif ディレクティブを使用する

### <a name="description"></a>説明

予想される動作を取得するには (リリースビルドに対して "テスト" 出力を印刷しない場合)、ディレクティブとディレクティブを使用する必要があり `#ifdef` `#endif` ます。 前のコードサンプルは、この修正を示すために次のように変更されています。

### <a name="code"></a>コード

```cpp
// mcpp_debug_class2.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();

#ifdef TRACE   // checks for a debug build
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
#endif
   Trace::Unindent();

#ifdef DEBUG   // checks for a debug build
   Debug::WriteLine("test");
#endif   //ends the conditional block
}
```

## <a name="see-also"></a>関連項目

[C++/CLI を使用した .NET プログラミング (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
