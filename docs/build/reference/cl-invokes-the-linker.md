---
title: リンカーを呼び出す CL
ms.date: 11/04/2016
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
ms.openlocfilehash: 1f9bb466ae89b8e3491b027a98b28935e7c8b523
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440184"
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

- MOD1 で関数 `func1` を呼び出し、MOD2 で関数 `func2` を呼び出します。

- MOD1 は、標準ライブラリ関数 `printf_s` と `scanf_s`を呼び出します。

- MOD2 は、`myline` および `mycircle`という名前のグラフィック関数を呼び出します。これは、MYGRAPH .lib という名前のライブラリで定義されています。

このプログラムをビルドするには、次のコマンドラインを使用してコンパイルします。

```
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib
```

最初に C ソースファイルがコンパイルされ、オブジェクトファイルのメイン .obj、MOD1、および MOD2 が作成されます。コンパイラは、標準ライブラリの名前を各 .obj ファイルに配置します。 詳細については、「[ランタイムライブラリの使用](md-mt-ld-use-run-time-library.md)」を参照してください。

CL は、.obj ファイルの名前を MYGRAPH .lib という名前でリンカーに渡します。 リンカーは、次のように外部参照を解決します。

1. MAIN .obj では、`func1` への参照は、MOD1 の定義を使用して解決されます。`func2` への参照は、MOD2 の定義を使用して解決されます。

1. MOD1 では、`printf_s` と `scanf_s` への参照は、リンカーが MOD1 内で検索したライブラリ内の定義を使用して解決されます。

1. MOD2 では、`myline` と `mycircle` への参照は、MYGRAPH .lib の定義を使用して解決されます。

## <a name="see-also"></a>参照

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[コンパイラ オプションの設定](compiler-command-line-syntax.md)
