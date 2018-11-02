---
title: LIB の実行
ms.date: 09/28/2018
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
ms.openlocfilehash: 73a259faa57d74fbe535bfa329dfc2a39cb6bbad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656977"
---
# <a name="running-lib"></a>LIB の実行

LIB のコントロールには、さまざまなコマンド ライン オプションを使用できます。

## <a name="lib-command-line"></a>LIB のコマンドライン

LIB を実行するコマンドを入力`lib`オプションとタスクのファイル名を続けて使用している LIB を実行します。 LIB では、次のセクションで説明するコマンド ファイルのコマンドラインの入力も受け付けます。 LIB 環境変数を使用しません。

> [!NOTE]
> LINK32.exe に慣れていて LIB32.exe ツールで、Microsoft Win32 ソフトウェア開発キットの Windows NT が使用している、いずれかのコマンド指定`link32 -lib`またはコマンド`lib32`のライブラリを管理して作成ライブラリをインポートします。 使用するメイクファイルとバッチ ファイルを変更してください、`lib`コマンドを代わりにします。

## <a name="lib-command-files"></a>LIB コマンド ファイル

次の構文を使用してコマンド ファイル内の LIB をコマンドライン引数を渡すことができます。

> **LIB \@**  <em>commandfile</em>

ファイル*commandfile*はテキスト ファイルです。 スペースまたはタブ間は入れません、アット マーク (**\@**) とファイル名。 既定の拡張機能はありません。任意の拡張機能を含む、完全なファイル名を指定する必要があります。 ワイルドカードを使用することはできません。 ファイル名では、絶対または相対パスを指定できます。

コマンド ファイルで引数で分離できるスペースまたはタブ。 コマンドラインで可能な限り改行文字で区切ることもできます。 セミコロンで区切ります (**;**) コメントをマークします。 LIB では、行の末尾にセミコロンからすべてのテキストは無視されます。

コマンド ファイルをすべてまたはコマンドラインの一部を指定でき、LIB コマンドでは、複数のコマンド ファイルを使用することができます。 LIB は、コマンドラインでその場所に指定されたものかのように、コマンド ファイルの入力を受け入れます。 コマンド ファイルを入れ子にすることはできません。 /NOLOGO オプションを使用しない場合、LIB はコマンド ファイルの内容をエコーします。

## <a name="using-lib-options"></a>LIB オプションを使用します。

オプションはいずれかをダッシュである、オプション指定子で構成されます (**-**) またはスラッシュ (**/**)、その後に、オプションの名前。 オプション名の省略形は使用できません。 いくつかのオプションは、コロンの後ろに指定された引数を取る (**:**)。 1 つのオプションの指定には、スペースやタブは挿入できません。 複数のオプションを指定する場合は、各オプションを 1 つ以上のスペースまたはタブで区切ります。 オプション名とキーワードやファイル名引数は大文字小文字が区別されませんが、引数として使用される識別子は大文字小文字を区別します。 LIB オプションと、コマンドラインで指定された順序でコマンド ファイルを処理します。 オプションは引数を繰り返し、処理する最後の 1 つが優先されます。

LIB のすべてのモードに、次のオプションが適用されます。

> **/ERRORREPORT** [**NONE** &AMP;#124; **プロンプト** &AMP;#124; **キュー** &AMP;#124; **送信**]

使用することができます lib.exe は、実行時に失敗した場合、 **/ERRORREPORT**これらの内部エラーに関する情報を Microsoft に送信します。

詳細については **/ERRORREPORT**を参照してください[/errorReport (内部コンパイラ エラーを報告する)](../../build/reference/errorreport-report-internal-compiler-errors.md)します。

> **/LTCG**

"LTCG"の略*リンク時コード生成*します。 この機能には、コンパイラ間の協調が必要です ([cl.exe](compiler-options.md))、LIB、およびリンカー ([リンク](linker-options.md)) 任意のコンポーネントを単独で実行できる内容を超えるコードを最適化するためにします。

LIB の **/LTCG**オプションは、cl.exe からの入力を使用して生成されたオブジェクト ファイルを含めることを指定します、 [/GL](gl-whole-program-optimization.md)コンパイラ オプション。 LIB のような入力が発生した場合と **/LTCG**が指定されていない、情報メッセージを表示した後有効になっている/LTCG を再起動します。 つまり、このオプションを明示的に設定する必要はありませんが、処理のため、LIB はそれ自体を再起動する必要はありません、ビルド パフォーマンス速度。

ビルド プロセスでは、LIB の出力はリンクに送信されます。 リンクが、独自の独立した **/LTCG**オプション プログラム全体の最適化、最適化のガイド付きプロファイル (PGO) インストルメンテーションなど、さまざまな最適化を実行するために使用します。 リンク オプションの詳細については、次を参照してください。 [/LTCG](ltcg-link-time-code-generation.md)します。

> **/MACHINE**

プログラムのターゲット プラットフォームを指定します。 通常、/MACHINE オプションを指定する必要はありません。 LIB は、.obj ファイルからコンピューターの種類を推測します。 ただし、いくつかの状況で、LIB はコンピューターの種類を決定することはできませんし、エラー メッセージを発行します。 このようなエラー メッセージが出力された場合は、/MACHINE オプションを指定してください。 /EXTRACT モードでは、このオプションは、検証のみは。 使用`lib /?`で使用可能なマシンの種類を表示するコマンド ライン。

> **/NOLOGO**

LIB 著作権メッセージとバージョン番号の表示を中止し、コマンド ファイルのエコーを防止します。

> **/VERBOSE**

追加される .obj ファイルの名前を含め、セッションの進行状況の詳細を表示します。 情報は標準出力に送信され、ファイルにリダイレクトすることもできます。

> **/WX****[: NO]**

警告をエラーとして扱います。 参照してください[/WX (リンカー警告として扱うエラー)](../../build/reference/wx-treat-linker-warnings-as-errors.md)詳細についてはします。

その他のオプションは、LIB の特定のモードにのみ適用されます。 これらのオプションについては、各モードの説明を参照してください。

## <a name="see-also"></a>関連項目

[LIB リファレンス](../../build/reference/lib-reference.md)
