---
title: 環境変数 CL |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f3986097bcb5028d9ad708c9a3132f5e417d502
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372612"
---
# <a name="cl-environment-variables"></a>環境変数 CL

CL ツールでは、次の環境変数を使用します。

- CL と\_CL\_定義されている場合、します。 CL ツール オプションとそのコマンドライン引数を環境変数 CL に定義されている引数を先頭のオプションを追加し、内の引数で定義\_CL\_、処理する前にします。

- INCLUDE。Visual C++ インストールの \include サブディレクトリを示す必要があります。

- 参照されているメタデータ ファイルを検索するディレクトリを指定する LIBPATH [#using](../../preprocessor/hash-using-directive-cpp.md)です。 LIBPATH の詳細については、`#using` の説明を参照してください。

CL を設定するか、 \_CL\_次の構文を使用して環境変数。

> CL の設定 = [*オプション*].[*ファイル*]...][/link*リンク-opt* ...]  
> 設定\_CL\_= [*オプション*].[*ファイル*]...][/link*リンク-opt* ...]

詳細については、CL の引数に対してと\_CL\_環境変数を参照してください[コンパイラのコマンドライン構文](../../build/reference/compiler-command-line-syntax.md)です。

これらの環境変数を使用してよく使用するファイルやオプションを定義し、コマンド ラインを使用して特定用途向けの特定のファイルおよびオプションを定義できます。 CL と\_CL\_環境変数は、1024 文字 (コマンドライン入力の制限) に制限されます。

/D オプションを使用して等号 (=) を使用するシンボルを定義することはできません。 等号の代わりにシャープ記号 (#) を使用することができます。 この方法では、CL を使用することができますまたは\_CL\_環境変数を明示的な値を持つプリプロセッサ定数を定義する — たとえば、`/DDEBUG#1`を定義する`DEBUG=1`です。

関連情報については、次を参照してください。[環境変数の設定](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)です。

## <a name="examples"></a>使用例

CL 環境変数を設定する例を次に示します。

> CL =/Zp2/Ox/I\INCLUDE\MYINCLS \LIB\BINMODE を設定します。OBJ

この環境変数設定されている場合、入力した場合`CL INPUT.C`コマンドラインで、これは、有効なコマンド。

> CL/Zp2/Ox/I\INCLUDE\MYINCLS \LIB\BINMODE です。OBJ 入力します。C

次の例では、単純な CL コマンドを実行すると、FILE1.c および FILE2.c の各ソース ファイルがコンパイルされ、FILE1.obj、FILE2.obj、および FILE3.obj の各オブジェクト ファイルがリンクされます。

> セット CL FILE1 を = です。C FILE2 です。C  
> 設定\_CL\_= ファイル 3 と指定します。OBJ  
> CL  

これは、次のコマンド ラインと同じ効果を持ちます。

> CL FILE1 です。C FILE2 です。C ファイル 3 と指定します。OBJ

## <a name="see-also"></a>関連項目

[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
[コンパイラ オプション](../../build/reference/compiler-options.md)
