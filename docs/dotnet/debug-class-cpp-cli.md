---
title: Debug クラス (C +/cli CLI) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: eecda10f2fd88b902a54fe9f4dc4de8edc4bc1b0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413563"
---
# <a name="debug-class-ccli"></a>Debug クラス (C++/CLI)

使用する場合<xref:System.Diagnostics.Debug>Visual C アプリケーションで、動作が、デバッグとリリース ビルドの間変更されません。

## <a name="remarks"></a>Remarks

動作は、<xref:System.Diagnostics.Trace>デバッグ クラスの動作と同じですが、シンボルが定義されているトレースによって異なります。 つまりする必要のある`#ifdef`トレースに関連するコードをリリース ビルドでのデバッグ動作を防ぐためにします。

## <a name="example"></a>例

### <a name="description"></a>説明

次の例は、常に使用してコンパイルするかどうかに関係なく、出力ステートメントを実行 **/DDEBUG**または **/DTRACE**します。

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

## <a name="example"></a>例

### <a name="description"></a>説明

想定される動作を取得する (つまり、"test"出力されない、リリース ビルド) を使用する必要があります、`#ifdef`と`#endif`ディレクティブ。 上記のコード サンプルは、この修正プログラムを示すために以下に変更されます。

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

[C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)