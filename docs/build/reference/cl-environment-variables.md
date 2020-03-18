---
title: 環境変数 CL
ms.date: 06/06/2019
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 4d6b1982b1e544459a025d6cb7bee75666e7130e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440249"
---
# <a name="cl-environment-variables"></a>環境変数 CL

CL ツールでは、次の環境変数を使用します。

- CL および \_CL_ (定義されている場合)。 Cl ツールは、CL 環境変数で定義されているオプションと引数をコマンドライン引数に付加し、\_CL_ で定義されているオプションと引数を処理前に追加します。

- を含めます。これは、Visual Studio のインストールのサブディレクトリであるを指している必要があります。

- LIBPATH は、 [#using](../../preprocessor/hash-using-directive-cpp.md)で参照されるメタデータファイルを検索するディレクトリを指定します。 LIBPATH の詳細については、「 [#using](../../preprocessor/hash-using-directive-cpp.md)」を参照してください。

CL または \_CL_ 環境変数は、次の構文を使用して設定できます。

> SET CL = [[*オプション*]...[*file*]...][/link*リンク-オプトイン*...]\
> SET \_CL\_= [[*オプション*]...[*file*]...][/link*リンク-オプトイン*...]

CL および \_CL_ 環境変数の引数の詳細については、「 [MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)」を参照してください。

これらの環境変数を使用すると、最も頻繁に使用するファイルとオプションを定義できます。 次に、コマンドラインを使用して、特定の目的のために、より多くのファイルとオプションを CL に提供します。 環境変数 CL_ CL および \_は、1024文字 (コマンドライン入力制限) に制限されています。

[/D](d-preprocessor-definitions.md)オプションを使用して、等号 ( **=** ) を使用するシンボルを定義することはできません。 代わりに、等号 ( **#** ) を使用して等号を指定できます。 このようにして、CL または \_CL_ 環境変数を使用して、明示的な値を持つプリプロセッサ定数を定義できます。たとえば、`DEBUG=1`を定義する `/DDEBUG#1` ます。

関連情報については、「[環境変数の設定](../setting-the-path-and-environment-variables-for-command-line-builds.md)」を参照してください。

## <a name="examples"></a>例

次のコマンドは、CL 環境変数を設定する例です。

> SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ

CL 環境変数が設定されている場合、コマンドラインで `CL INPUT.C` を入力すると、有効なコマンドは次のようになります。

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

次の例では、単純な CL コマンドを実行すると、FILE1.c および FILE2.c の各ソース ファイルがコンパイルされ、FILE1.obj、FILE2.obj、および FILE3.obj の各オブジェクト ファイルがリンクされます。

> SET CL=FILE1.C FILE2.C \
> \_CL_ = FILE3 に設定します。OBJ
> CL

これらの環境変数を使用すると、CL を呼び出すと、次のコマンドラインと同じ効果が得られます。

> CL FILE1。C FILE2。C FILE3。OBJ

## <a name="see-also"></a>参照

[コンパイラオプションの設定](compiler-command-line-syntax.md) \
[MSVC コンパイラ オプション](compiler-options.md)
