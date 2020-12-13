---
description: 詳細情報:/Yl (デバッグライブラリの PCH 参照の挿入)
title: /Yl (デバッグ ライブラリの PCH 参照の挿入)
ms.date: 01/29/2018
f1_keywords:
- /yl
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
ms.openlocfilehash: f1d05b4e0c38377233e9aaf6299227f7fbaebd55
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151854"
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (デバッグ ライブラリの PCH 参照の挿入)

**/Yl** オプションを指定すると、プリコンパイル済みヘッダーファイル内に一意のシンボルが生成され、プリコンパイル済みヘッダーを使用するすべてのオブジェクトファイルにこのシンボルへの参照が挿入されます。

## <a name="syntax"></a>構文

>**/Yl**\
>**/Yl**_名_\
>**/Yl-**

### <a name="arguments"></a>引数

*name*<br/>
一意の記号の一部として使用される省略可能な名前。

*\-*<br/>
ダッシュ (-) は、 **/Yl** コンパイラオプションを明示的に無効にします。

## <a name="remarks"></a>解説

**/Yl** コンパイラオプションは、 [/yc](yc-create-precompiled-header-file.md)オプションを使用して作成されたプリコンパイル済みヘッダーファイルに一意のシンボル定義を作成します。 このシンボルへの参照は、 [/yu](yu-use-precompiled-header-file.md) コンパイラオプションを使用して、プリコンパイル済みヘッダーを含むすべてのファイルに自動的に挿入されます。 **/Yl** オプションは、 **/yc** を使用してプリコンパイル済みヘッダーファイルを作成する場合に既定で有効になります。

**/Yl**_name_ オプションは、プリコンパイル済みヘッダーファイル内で識別可能なシンボルを作成するために使用されます。 コンパイラは、作成した装飾シンボル名の一部として *name* 引数を使用します `__@@_PchSym_@00@...@name` 。ここで、省略記号 (...) はコンパイラによって生成される一意の文字列を表します。 *Name* 引数を省略すると、コンパイラによってシンボル名が自動的に生成されます。 通常、シンボルの名前を知る必要はありません。 ただし、プロジェクトで複数のプリコンパイル済みヘッダーファイルを使用する場合、 **/Yl**_name_ オプションは、プリコンパイル済みヘッダーを使用するオブジェクトファイルを特定するのに便利な場合があります。 *名前* を検索文字列として使用して、シンボル参照をダンプファイルで検索できます。

**/Yl-** は既定の動作を無効にし、プリコンパイル済みヘッダーファイルに識別シンボルを配置しません。 このプリコンパイル済みヘッダーを含むコンパイル済みファイルは、共通のシンボル参照を取得しません。

**/Yc** が指定されていない場合、 **/Yl** オプションは何の効果もありませんが、指定した場合は、 **/yc** を指定したときに渡された **/Yl** オプションに一致する必要があります。

**/Yl-**、 **/Yc** 、および [/Z7](z7-zi-zi-debug-information-format.md)オプションを使用してプリコンパイル済みヘッダーファイルをビルドする場合、デバッグ情報は、別の .pdb ファイルではなく、プリコンパイル済みヘッダーの作成に使用されるソースファイルのオブジェクトファイルに格納されます。 このオブジェクトファイルがライブラリの一部になった場合、プリコンパイル済みヘッダーファイルを作成するために使用されるソースファイルにシンボルそのものが定義されていない場合は、このライブラリとプリコンパイル済みヘッダーファイルを使用するビルドで [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) errors または [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) warning が発生する可能性があります。 ライブラリクライアントでオブジェクトファイルが参照されていない場合、リンカーは、関連付けられているデバッグ情報と共に、リンクからオブジェクトファイルを除外できます。 この問題を解決するには、 **/yc** を使用してプリコンパイル済みヘッダーファイルを作成するときに、 **/Yl** (または **/Yl-** オプションを削除する) を指定します。 これにより、デバッグ情報を含むライブラリからのオブジェクトファイルがビルドにリンクされます。

プリコンパイル済みヘッダーの詳細については、以下を参照してください。

- [/Y (プリコンパイル済みヘッダー)](y-precompiled-headers.md)

- [プリコンパイル済みヘッダーファイル](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] ボックスに **/Yl**_name_ コンパイラオプションを追加します。 **[OK]** を選択して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
