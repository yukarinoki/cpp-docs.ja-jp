---
description: '詳細情報: CL がリンカーを呼び出す'
title: リンカーを呼び出す CL
ms.date: 11/04/2016
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
ms.openlocfilehash: ddd693cdba625756b8085d2f8cb3870d8cdc6add
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179162"
---
# <a name="cl-invokes-the-linker"></a>リンカーを呼び出す CL

CL は、/c オプションが使用されていない限り、コンパイル後にリンカーを自動的に呼び出します。 CL は、コンパイル時に作成された .obj ファイルの名前と、コマンドラインで指定された他のすべてのファイルの名前をリンカーに渡します。 リンカーは、リンク環境変数に示されているオプションを使用します。 /Link オプションを使用して、CL コマンドラインでリンカーオプションを指定できます。 /Link オプションに従うオプションは、LINK 環境変数のオプションよりも優先されます。 次の表のオプションでは、リンクが抑制されます。

|オプション|説明|
|------------|-----------------|
|/c|リンクなしでコンパイルする|
|/E、/EP、/P|コンパイルまたはリンクなしの前処理|
|/Zg|関数プロトタイプの生成|
|/Zs|構文の確認|

リンクの詳細については、「 [MSVC リンカー Options](linker-options.md)」を参照してください。

## <a name="example"></a>例

ここでは、3つの C ソースファイル (MAIN、MOD1、および MOD2) をコンパイルしているとします。 各ファイルには、別のファイルで定義された関数の呼び出しが含まれています。

- MOD1 で関数を呼び出し、 `func1` MOD2 の関数を呼び出します。 `func2`

- MOD1 は、標準ライブラリ関数 `printf_s` とを呼び出し `scanf_s` ます。

- MOD2 は、という名前のグラフィック関数を呼び出します。 `myline` `mycircle` これは、mygraph という名前のライブラリで定義されています。

このプログラムをビルドするには、次のコマンドラインを使用してコンパイルします。

```
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib
```

最初に C ソースファイルがコンパイルされ、オブジェクトファイルのメイン .obj、MOD1、および MOD2 が作成されます。コンパイラは、標準ライブラリの名前を各 .obj ファイルに配置します。 詳細については、「 [Run-Time ライブラリの使用](md-mt-ld-use-run-time-library.md)」を参照してください。

CL は、.obj ファイルの名前を MYGRAPH .lib という名前でリンカーに渡します。 リンカーは、次のように外部参照を解決します。

1. メイン .obj では、への参照は `func1` MOD1 の定義を使用して解決されます。への参照は、 `func2` MOD2 の定義を使用して解決されます。

1. MOD1 では、およびへの参照 `printf_s` `scanf_s` は、リンカーが MOD1 内で検索したライブラリ内の定義を使用して解決されます。

1. MOD2 では、およびへの参照 `myline` `mycircle` は、mygraph の定義を使用して解決されます。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[コンパイラ オプションの設定](compiler-command-line-syntax.md)
