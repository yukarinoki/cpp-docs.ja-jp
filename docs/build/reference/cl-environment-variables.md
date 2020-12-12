---
description: '詳細情報: CL 環境変数'
title: 環境変数 CL
ms.date: 06/06/2019
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: 1be95d2c2eddd204846fbcdc8675f28d71c25c0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179175"
---
# <a name="cl-environment-variables"></a>環境変数 CL

CL ツールでは、次の環境変数を使用します。

- CL および \_ CL_ (定義されている場合)。 CL ツールは、CL 環境変数で定義されているオプションと引数をコマンドライン引数に付加し、CL_ で定義されているオプションと引数を処理前に追加し \_ ます。

- を含めます。これは、Visual Studio のインストールのサブディレクトリであるを指している必要があります。

- LIBPATH は、 [#using](../../preprocessor/hash-using-directive-cpp.md)で参照されるメタデータファイルを検索するディレクトリを指定します。 LIBPATH の詳細については、「 [#using](../../preprocessor/hash-using-directive-cpp.md)」を参照してください。

CL または CL_ 環境変数を設定するには、 \_ 次の構文を使用します。

> SET CL = [[*オプション*]...[*file*]...][/link *リンク-オプトイン* ...]\
> SET \_ CL \_ = [[*オプション*]...[*file*]...][/link *リンク-オプトイン* ...]

CL および CL_ 環境変数の引数の詳細につい \_ ては、「 [MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)」を参照してください。

これらの環境変数を使用すると、最も頻繁に使用するファイルとオプションを定義できます。 次に、コマンドラインを使用して、特定の目的のために、より多くのファイルとオプションを CL に提供します。 CL および \_ CL_ 環境変数は、1024文字 (コマンドライン入力制限) に制限されています。

[/D](d-preprocessor-definitions.md)オプションを使用して、等号 () を使用するシンボルを定義することはできません **=** 。 代わりに、等号 () を使用して等号を指定でき **#** ます。 このようにして、CL または \_ CL_ 環境変数を使用して、明示的な値を持つプリプロセッサ定数を定義できます (たとえば、を `/DDEBUG#1` 定義します) `DEBUG=1` 。

関連情報については、「 [環境変数の設定](../setting-the-path-and-environment-variables-for-command-line-builds.md)」を参照してください。

## <a name="examples"></a>例

次のコマンドは、CL 環境変数を設定する例です。

> SET CL =/Zp2/Ox/I\INCLUDE\MYINCLS \ lib¥ binmodemode.OBJ

CL 環境変数が設定されている場合、コマンドラインでを入力すると、 `CL INPUT.C` 有効なコマンドは次のようになります。

> CL/Zp2/Ox/I\INCLUDE\MYINCLS \ LIBBINMODE.OBJ 入力。40u-c

次の例では、単純な CL コマンドを実行すると、FILE1.c および FILE2.c の各ソース ファイルがコンパイルされ、FILE1.obj、FILE2.obj、および FILE3.obj の各オブジェクト ファイルがリンクされます。

> CL = FILE1 と設定します。C FILE2。40u-c
> \_CL_ = FILE3 を設定します。OBJ
> CL

これらの環境変数を使用すると、CL を呼び出すと、次のコマンドラインと同じ効果が得られます。

> CL FILE1。C FILE2。C FILE3。OBJ

## <a name="see-also"></a>関連項目

[コンパイラオプションの設定](compiler-command-line-syntax.md) \
[MSVC コンパイラ オプション](compiler-options.md)
