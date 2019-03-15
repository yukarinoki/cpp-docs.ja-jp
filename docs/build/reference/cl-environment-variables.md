---
title: 環境変数 CL
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- INCLUDE environment variable
- cl.exe compiler, environment variables
- LIBPATH environment variable
- environment variables, CL compiler
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
ms.openlocfilehash: a15bedc0a5aa8215356a98c3635a2edd1f3cfc5f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807963"
---
# <a name="cl-environment-variables"></a>環境変数 CL

CL ツールでは、次の環境変数を使用します。

- CL と\_CL\_、定義されている場合。 定義されている引数および CL ツールは、オプションと、コマンドライン引数を環境変数 CL で定義されている引数の前に付加し、オプションを追加します\_CL\_、処理する前にします。

- INCLUDE。Visual C++ インストールの \include サブディレクトリを示す必要があります。

- LIBPATH を参照するメタデータ ファイルを検索するディレクトリを指定する[#using](../../preprocessor/hash-using-directive-cpp.md)します。 LIBPATH の詳細については、`#using` の説明を参照してください。

CL を設定するか、 \_CL\_次の構文を使用して環境変数。

> SET CL=[ [*option*] ... [*file*] ...] [/link *link-opt* ...] SET \_CL\_=[ [*option*] ... [*file*] ...] [/link *link-opt* ...]

詳細については、CL の引数に対してと\_CL\_ 、環境変数を参照してください[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)します。

これらの環境変数を使用してよく使用するファイルやオプションを定義し、コマンド ラインを使用して特定用途向けの特定のファイルおよびオプションを定義できます。 CL と\_CL\_環境変数は 1024 文字 (コマンドライン入力の制限) に制限されています。

/D オプションを使用して等号 (=) を使用するシンボルを定義することはできません。 等号の代わりにシャープ記号 (#) を使用することができます。 この方法では、CL を使用することができますまたは\_CL\_明示的な値を持つプリプロセッサ定数を定義する環境変数: たとえば、`/DDEBUG#1`を定義する`DEBUG=1`します。

関連情報については、次を参照してください。[環境変数を設定](../setting-the-path-and-environment-variables-for-command-line-builds.md)します。

## <a name="examples"></a>使用例

CL 環境変数を設定する例を次に示します。

> SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ

この環境変数設定されている場合、入力した場合`CL INPUT.C`コマンドラインで、これは有効なコマンド。

> CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C

次の例では、単純な CL コマンドを実行すると、FILE1.c および FILE2.c の各ソース ファイルがコンパイルされ、FILE1.obj、FILE2.obj、および FILE3.obj の各オブジェクト ファイルがリンクされます。

> SET CL=FILE1.C FILE2.C SET \_CL\_=FILE3.OBJ CL

これは、次のコマンド ラインと同じ効果を持ちます。

> CL FILE1.C FILE2.C FILE3.OBJ

## <a name="see-also"></a>関連項目

[コンパイラ オプションの設定](compiler-command-line-syntax.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)
