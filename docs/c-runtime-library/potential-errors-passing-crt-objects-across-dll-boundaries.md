---
title: DLL の境界を越えて CRT オブジェクトを渡す場合に発生する可能性のあるエラー
description: ダイナミックリンクライブラリ (DLL) の境界を越えて Microsoft C ランタイムオブジェクトを渡すときに発生する可能性のある問題の概要。
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- DLL conflicts [C++]
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
ms.openlocfilehash: 2d42803b5eca7a43f122d209b7d9e2d4e45c38de
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008937"
---
# <a name="potential-errors-passing-crt-objects-across-dll-boundaries"></a>DLL の境界を越えて CRT オブジェクトを渡す場合に発生する可能性のあるエラー

Dll の境界を越えた関数呼び出しを使用して、ファイルハンドル、ロケール、環境変数などの C ランタイム (CRT) オブジェクトを DLL の内外に渡すと、dll、または DLL を呼び出すファイルで、CRT ライブラリの異なるコピーが使用された場合に予期しない動作が発生する可能性があります。

関連する問題は、メモリを (またはで明示的に、または、などの方法で `new` `malloc` ) 割り当て `strdup` `strstreambuf::str` て、解放された DLL の境界を越えてポインターを渡すと発生する可能性があります。 DLL とそのコンシューマーが異なる CRT ライブラリのコピーを使用している場合、メモリアクセス違反やヒープの破損が発生する可能性があります。

この問題の別の症状は、次のようなデバッグ中の出力ウィンドウのエラーです。 `HEAP[]: Invalid Address specified to RtlValidateHeap(#,#)`

## <a name="causes"></a>原因

CRT ライブラリのコピーはそれぞれ状態が異なります。アプリまたは DLL により、スレッド ローカル ストレージに保存されます。

ファイルハンドル、環境変数、ロケールなどの CRT オブジェクトは、これらのオブジェクトが割り当てられているか設定されているアプリまたは DLL 内の CRT のコピーに対してのみ有効です。 DLL とそのクライアントが異なる CRT ライブラリのコピーを使用する場合、これらの CRT オブジェクトを DLL の境界を越えて渡すことはできません。また、これらのオブジェクトをもう一方の側で正しく使用することを想定しています。 これは、Visual Studio 2015 以降のユニバーサル CRT より前の CRT バージョンに当てはまります。

Visual Studio 2013 以前で構築されたあらゆるバージョンの Visual Studio について、バージョン固有の CRT ライブラリがありました。 データ構造や名前付け規則など、CRT の内部実装の詳細は、バージョンによって異なります。 CRT の1つのバージョン用にコンパイルされたコードを、別のバージョンの CRT DLL に動的にリンクすることは、まだサポートされていません。 場合によっては機能しますが、設計ではなく、運が多いからです。

CRT ライブラリの各コピーには独自のヒープマネージャーがあるため、1つの CRT ライブラリにメモリを割り当て、DLL の境界を越えてポインターを渡して、CRT ライブラリの別のコピーによって解放されると、ヒープが破損する可能性があります。 Dll の境界を越えて CRT オブジェクトを渡すように DLL を設計した場合、またはメモリを割り当てて DLL の外部で解放する必要がある場合、DLL のクライアントは、DLL と同じ CRT ライブラリのコピーを使用する必要があります。

DLL とそのクライアントは通常、読み込み時に両方とも同じバージョンの CRT DLL にリンクされている場合にのみ、CRT ライブラリの同じコピーを使用します。 Visual Studio 2015 によって使用されているユニバーサル CRT ライブラリの DLL バージョンと、それ以降の Windows 10 は、中央に配置された Windows コンポーネント (ucrtbase.dll) であるため、Visual Studio 2015 以降のバージョンでビルドされたアプリでも同じです。 ただし、CRT コードが同一であっても、あるヒープで割り当てられたメモリを別のヒープを使用するコンポーネントに割り当てることはできません。

## <a name="example-pass-file-handle-across-dll-boundary"></a>例: DLL の境界を越えてファイルハンドルを渡す

### <a name="description"></a>説明

この例では、DLL 境界を越えてファイル ハンドルが渡されます。

DLL ファイルと .exe ファイルは `/MD` 、CRT の1つのコピーを共有するために、でビルドされます。

を使用してリビルドし、 `/MT` CRT の個別のコピーを使用する場合、結果の **test1Main.exe** を実行するとアクセス違反になります。

```cpp
// test1Dll.cpp
// compile with: cl /EHsc /W4 /MD /LD test1Dll.cpp
#include <stdio.h>
__declspec(dllexport) void writeFile(FILE *stream)
{
   char   s[] = "this is a string\n";
   fprintf( stream, "%s", s );
   fclose( stream );
}
```

```cpp
// test1Main.cpp
// compile with: cl /EHsc /W4 /MD test1Main.cpp test1Dll.lib
#include <stdio.h>
#include <process.h>
void writeFile(FILE *stream);

int main(void)
{
   FILE  * stream;
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );
   writeFile(stream);
   system( "type fprintf.out" );
}
```

```Output
this is a string
```

## <a name="example-pass-environment-variables-across-dll-boundary"></a>例: DLL の境界を越えて環境変数を渡す

### <a name="description"></a>説明

この例では、DLL の境界を越えて環境変数が渡されます。

```cpp
// test2Dll.cpp
// compile with: cl /EHsc /W4 /MT /LD test2Dll.cpp
#include <stdio.h>
#include <stdlib.h>

__declspec(dllexport) void readEnv()
{
   char *libvar;
   size_t libvarsize;

   /* Get the value of the MYLIB environment variable. */
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );

   if( libvar != NULL )
      printf( "New MYLIB variable is: %s\n", libvar);
   else
      printf( "MYLIB has not been set.\n");
   free( libvar );
}
```

```cpp
// test2Main.cpp
// compile with: cl /EHsc /W4 /MT test2Main.cpp test2dll.lib
#include <stdlib.h>
#include <stdio.h>

void readEnv();

int main( void )
{
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );
   readEnv();
}
```

```Output
MYLIB has not been set.
```

DLL と .exe ファイルの両方がでビルドされ、 `/MD` CRT のコピーが1つしか使用されない場合、プログラムは正常に実行され、次の出力が生成されます。

```
New MYLIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>関連項目

[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)
