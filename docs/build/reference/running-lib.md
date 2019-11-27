---
title: LIB の実行
description: .Lib で使用できるコマンドラインオプションについて説明します。
ms.date: 09/25/2019
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
helpviewer_keywords:
- -MACHINE target platform option
- command files, LIB
- MACHINE target platform option
- colon command files
- VERBOSE library manager option
- /NOLOGO library manager option
- dash option specifier
- /MACHINE target platform option
- forward slash option specifier
- -NOLOGO library manager option
- LIB [C++], running LIB
- -VERBOSE library manager option
- /VERBOSE library manager option
- command files
- NOLOGO library manager option
- slash (/)
- semicolon, command files
- / command files
ms.assetid: d54f5c81-7147-4b2c-a8db-68ce6eb1eabd
ms.openlocfilehash: 0d65c8d8b3b0cd28c7cccda25bfd9512321172f9
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685547"
---
# <a name="running-lib"></a>LIB の実行

LIB は、さまざまなコマンドラインオプションを使用して制御できます。

## <a name="lib-command-line"></a>LIB コマンドライン

LIB を実行するには、コマンド `lib` に続けて、LIB を使用して実行するタスクのオプションとファイル名を入力します。 LIB では、コマンドファイルでコマンドライン入力を受け取ることもできます。これについては、次のセクションで説明します。 LIB は環境変数を使用しません。

## <a name="lib-command-files"></a>LIB コマンドファイル

コマンドファイル内の LIB にコマンドライン引数を渡すには、次の構文を使用します。

> **LIB \@** <em>コマンドファイル</em>

ファイル*コマンドファイル*はテキストファイルです。 アットマーク ( **\@** ) とファイル名の間にスペースやタブを使用することはできません。 *コマンドファイル*名には既定の拡張子がありません。拡張子を含む完全なファイル名を指定する必要があります。 ワイルドカードは使用できません。 絶対パスまたは相対パスをファイル名と共に指定できます。

コマンドファイルでは、コマンドラインで指定できるように、引数はスペースまたはタブで区切ることができます。 引数は改行文字で区切ることもできます。 コメントをマークするには、セミコロン ( **;** ) を使用します。 LIB は、セミコロンから行末までのすべてのテキストを無視します。

コマンドラインのすべてまたは一部をコマンドファイルで指定することができます。また、複数のコマンドファイルを LIB コマンドで使用することもできます。 LIB は、コマンドラインでその場所に指定されているかのように、コマンドファイル入力を受け入れます。 コマンドファイルを入れ子にすることはできません。 **/Nologo**オプションを使用しない限り、LIB はコマンドファイルの内容をエコーします。

## <a name="using-lib-options"></a>LIB オプションの使用

オプションは、ダッシュ ( **-** ) またはスラッシュ ( **/** ) のいずれかのオプション指定子で構成され、その後にオプションの名前が続きます。 オプション名を省略することはできません。 一部のオプションは、コロン ( **:** ) の後に指定された引数を受け取ります。 1 つのオプションの指定には、スペースやタブは挿入できません。 複数のオプションを指定する場合は、各オプションを 1 つ以上のスペースまたはタブで区切ります。 オプション名とそのキーワードまたはファイル名引数は大文字と小文字が区別されませんが、引数として使用される識別子では大文字と小文字が区別されます。 LIB は、コマンドラインとコマンドファイルに指定されている順序でオプションを処理します。 オプションが異なる引数で繰り返される場合は、最後に処理されるものが優先されます。

次のオプションは、LIB のすべてのモードに適用されます。

> **/Errorreport** \[**NONE** &#124; **PROMPT** &#124; QUEUE &#124; **SEND**]

実行時に .lib が失敗する場合は、 **/errorreport**を使用して、これらの内部エラーに関する情報をマイクロソフトに送信できます。

**/Errorreport**の詳細については、「 [/Errorreport (内部コンパイラエラーの報告)](errorreport-report-internal-compiler-errors.md)」を参照してください。

> **/Link再現:** _ディレクトリパス_ \
> **/Linkreprotarget:** _ファイル名_

Microsoft が .lib のクラッシュと内部エラーを診断できるようにするには、 [/link再現](linkrepro.md)オプションを使用します。 これにより、Microsoft がライブラリ操作中に発生した問題を再現できるようにする一連のビルド成果物の*リンク再現*が生成されます。 / [Linkreprotarget](linkreprotarget.md)オプションは、 **/link再現**オプションと共に使用できます。 指定したファイルが .lib によって生成される場合にのみ、リンク再現アーティファクトが生成されます。 詳細については、「 [Microsoft C++ツールセットの問題を報告する方法](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)」を参照してください。

> **/LTCG**

"LTCG" は*リンク時のコード生成*を表します。 この機能を使用するには、コンパイラ ([cl.exe](compiler-options.md))、LIB、リンカー ([リンク](linker-options.md)) を連携させる必要があります。これにより、他のコンポーネントが実行できる内容を超えてコードを最適化することができます。

LIB の場合、 **/ltcg**オプションは、 [/gl](gl-whole-program-optimization.md)コンパイラオプションを使用して生成されたオブジェクトファイルが cl.exe からの入力に含まれることを指定します。 LIB でこのような入力と **/ltcg**が指定されていない場合は、情報メッセージが表示された後に/ltcg が有効になった状態で再起動します。 つまり、このオプションを明示的に設定する必要はありませんが、LIB を再起動する必要がないため、ビルドのパフォーマンスが向上します。

ビルドプロセスでは、LIB からの出力がリンクに送信されます。 LINK には独自の **/ltcg**オプションがあります。 これは、プログラム全体の最適化、ガイド付き最適化のプロファイル (PGO) インストルメンテーションなど、さまざまな最適化を実行するために使用されます。 LINK オプションの詳細については、「 [/ltcg](ltcg-link-time-code-generation.md)」を参照してください。

> **/MACHINE**

プログラムのターゲットプラットフォームを指定します。 通常は、 **/MACHINE**を指定する必要はありません。 LIB は、.obj ファイルからコンピューターの種類を推測します。 ただし、状況によっては、LIB がマシンの種類を特定できず、エラーメッセージを発行することもあります。 このようなエラーが発生した場合は、 **/MACHINE**を指定します。 **/Extract**モードでは、このオプションは検証のみを対象としています。 使用可能なマシンの種類を確認するには、コマンドラインで `lib /?` を使用します。

> **/NOLOGO**

LIB の著作権メッセージとバージョン番号が表示されないようにし、コマンドファイルがエコーされないようにします。

> **/VERBOSE**

追加される .obj ファイルの名前など、セッションの進行状況に関する詳細が表示されます。 情報は標準出力に送信され、ファイルにリダイレクトすることもできます。

> **/WX** **[:NO]**

警告をエラーとして扱います。 詳細については、「[/WX (リンカー警告をエラーとして扱う)](wx-treat-linker-warnings-as-errors.md)」を参照してください。

その他のオプションは、LIB の特定のモードにのみ適用されます。 これらのオプションについては、各モードについて説明するセクションで説明します。

## <a name="see-also"></a>参照

[LIB リファレンス](lib-reference.md)
