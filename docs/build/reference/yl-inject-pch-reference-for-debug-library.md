---
title: -Yl (デバッグ ライブラリの PCH 参照の挿入) |Microsoft ドキュメント
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yl
dev_langs:
- C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a73e79cd50343292ae63dfa831a7638d6444fc64
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl (デバッグ ライブラリの PCH 参照の挿入)

**/Yl**オプションがプリコンパイル済みヘッダー ファイルに独自の記号を生成し、プリコンパイル済みヘッダーを使用するすべてのオブジェクト ファイルでこのシンボルへの参照を挿入します。

## <a name="syntax"></a>構文

>**/Yl**  
>**/Yl**_name_  
>**/Yl-**  

### <a name="arguments"></a>引数

*name*  
一意のシンボルの一部として使用されるオプションの名前。

*\-*  
ダッシュ (-) が明示的に無効になります、 **/Yl**コンパイラ オプション。

## <a name="remarks"></a>コメント

**/Yl**コンパイラ オプションを使用して作成されたプリコンパイル済みヘッダー ファイルでの一意のシンボル定義の作成、 [/Yc](../../build/reference/yc-create-precompiled-header-file.md)オプション。 このシンボルへの参照は自動的を使用して、プリコンパイル済みヘッダーをインクルードするすべてのファイルに挿入された、 [/Yu](../../build/reference/yu-use-precompiled-header-file.md)コンパイラ オプション。 **/Yl**オプションが既定で有効になっているときに **/Yc**プリコンパイル済みヘッダー ファイルを作成するために使用します。

**/Yl**_名前_プリコンパイル済みヘッダー ファイルで特定のシンボルを作成するオプションを使用します。 コンパイラを使用して、*名前*作成されるようなシンボルの装飾名の一部として引数\_ \_ @@ \_PchSym\_@00@..@。*名前*、省略記号 (...) を表す一意なコンパイラにより生成された文字の文字列。 場合、*名前*引数を省略すると、コンパイラがシンボル名を自動的に生成されます。 通常、シンボルの名前を知っている必要はありません。 ただし、プロジェクトが 1 つ以上のプリコンパイル済みヘッダー ファイルを使用する場合、 **/Yl**_名前_オプションがどのオブジェクト ファイルでプリコンパイル済みヘッダーを使用してを調べるために役立ちます可能性があります。 使用することができます*名前*ダンプ ファイルにシンボル参照を検索する検索文字列として。

**/Yl-** 既定の動作を無効にし、プリコンパイル済みヘッダー ファイルで特定のシンボルを配置しません。 このプリコンパイル済みヘッダーが含まれているコンパイル済みのファイルは、一般的なシンボル参照を取得できません。

ときに **/Yc**が指定されていない任意 **/Yl**オプションが場合は指定のいずれかに一致する必要がありますが、影響を与えません **/Yl**オプションに渡されるときに **/Yc**は指定します。

使用する場合 **/Yl-**、 **/Yc**と[/Z7](../../build/reference/z7-zi-zi-debug-information-format.md)プリコンパイル済みヘッダー ファイル、デバッグ情報を作成するオプションが、オブジェクト ファイルを作成するために使用したソース ファイルに格納されている、プリコンパイル済みヘッダーではなく、個別の .pdb ファイル。 このオブジェクト ファイルには、ライブラリの一部ができる場合[LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md)エラーまたは[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)ソース ファイルを作成するために使用する場合に、次の警告がこのライブラリと、プリコンパイル済みヘッダー ファイルを使用するビルドで発生する可能性が、プリコンパイル済みヘッダー ファイルを定義しません任意の記号自体。 リンカーが、関連するデバッグ情報と共に、リンクからのオブジェクト ファイルを除外するには、オブジェクト ファイルでは nothing がライブラリ クライアントで参照されるとします。 この問題を解決するには指定 **/Yl** (または削除、 **/Yl-** オプション) を使用すると **/Yc**プリコンパイル済みヘッダー ファイルを作成します。 これにより、デバッグ情報が含まれているライブラリからのオブジェクト ファイルを取得、ビルドにリンクされています。

プリコンパイル済みヘッダーの詳細についてを参照してください。

- [/Y (プリコンパイル済みヘッダー)](../../build/reference/y-precompiled-headers.md)

- [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. 追加、 **/Yl**_名前_コンパイラ オプション、**追加オプション**ボックス。 選択**OK**して変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
