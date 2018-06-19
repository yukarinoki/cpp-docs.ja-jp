---
title: LIB の実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLibrarianTool.TargetMachine
- Lib
- VC.Project.VCLibrarianTool.PrintProgress
- VC.Project.VCLibrarianTool.SuppressStartupBanner
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c306ba58bfef11f92d7e861272aad2aa605c8fde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377575"
---
# <a name="running-lib"></a>LIB の実行
LIB のコントロールには、さまざまなコマンド ライン オプションを使用できます。  
  
## <a name="lib-command-line"></a>LIB コマンドライン  
 LIB を実行するコマンドを入力`lib`オプションとタスクのファイル名を続けて使用している LIB を実行します。 LIB は、コマンド ファイルは、次のセクションで説明されているようにコマンドラインの入力も受け入れます。 LIB 環境変数を使用しません。  
  
> [!NOTE]
>  場合は、LINK32.exe に慣れているし、ツールで、Microsoft Win32 ソフトウェア開発キット用 Windows NT が使用している、いずれかのコマンド指定の LIB32.exe`link32 -lib`またはコマンド`lib32`のライブラリを管理して、作成ライブラリをインポートします。 使用するメイクファイルおよびバッチ ファイルを変更してください、`lib`コマンドを使用します。  
  
## <a name="lib-command-files"></a>LIB コマンド ファイル  
 次の構文を使用してコマンド ファイルの LIB をコマンドライン引数を渡すことができます。  
  
```  
LIB @commandfile  
```  
  
 ファイル`commandfile`テキスト ファイルです。 スペースやタブは使用できませんの間、アット マーク (@) とファイル名。 既定の拡張機能はありません。任意の拡張子を含めた、完全なファイル名を指定する必要があります。 ワイルドカードは使用できません。 ファイル名では、絶対または相対パスを指定できます。  
  
 コマンド ファイル内の引数できます。 で区切るスペースまたはタブ、; コマンドラインでことができます。改行文字で区切ることもできます。 セミコロン (;) を使用すると、コメントをマークできます。 LIB は、行の末尾にセミコロンからすべてのテキストを無視します。  
  
 コマンド ファイルのすべてまたはコマンドラインの一部を指定でき、LIB コマンドで 1 つ以上のコマンド ファイルを使用することができます。 LIB は、コマンドラインでその場所に、指定した場合と、コマンド ファイルの入力を受け入れます。 コマンド ファイルを入れ子にすることはできません。 /NOLOGO オプションを使用しない限り、コマンド ファイルの内容がエコーされます。  
  
## <a name="using-lib-options"></a>LIB のオプションを使用します。  
 オプションは、ダッシュ (-) またはスラッシュ (/)、オプションの名前を続けて、オプション指定子で構成されます。 オプション名の省略形は使用できません。 いくつかのオプションは、コロン (:) の後ろに指定された引数を取る。 1 つのオプションの指定には、スペースやタブは挿入できません。 複数のオプションを指定する場合は、各オプションを 1 つ以上のスペースまたはタブで区切ります。 オプション名、およびその引数キーワードやファイル名は大文字と小文字が区別されませんが、引数として使用される識別子は大文字小文字を区別します。 LIB は、コマンドラインで指定された順序とコマンド ファイル内のオプションを処理します。 オプションは異なる引数を持つで繰り返される場合は、処理される最後の 1 つが優先されます。  
  
 LIB のすべてのモードに、次のオプションが適用されます。  
  
 /ERRORREPORT [NONE&AMP;#124;プロンプト&AMP;#124;キュー&AMP;#124;送信]  
 Lib.exe は、実行時に失敗した場合、これらの内部エラーに関する情報を Microsoft に送信する/ERRORREPORT を使用することができます。  
  
 /ERRORREPORT の詳細については、次を参照してください。 [/errorReport (内部コンパイラ エラーの報告)](../../build/reference/errorreport-report-internal-compiler-errors.md)です。  
  
 /LTCG  
 リンク時コード生成を使用してビルドするライブラリが発生します。  詳細については、次を参照してください。 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)です。  
  
 /MACHINE  
 プログラムのターゲット プラットフォームを指定します。 通常、/MACHINE を指定する必要はありません。 LIB は、.obj ファイルからコンピューターの種類を推測します。 ただし、いくつかの状況で、LIB はコンピューターの種類を決定することはできませんし、エラー メッセージを発行します。 このようなエラー メッセージが出力された場合は、/MACHINE オプションを指定してください。 /EXTRACT モードでは、このオプションはのみ検証します。 使用して`lib /?`コマンドラインでため使用可能なコンピューターの種類を参照してください。  
  
 /NOLOGO  
 LIB 著作権メッセージとバージョン番号の表示を中止し、コマンド ファイルのエコーを防止します。  
  
 /VERBOSE  
 追加される .obj ファイルの名前を含め、セッションの進行状況に関する詳細を表示します。 情報は標準出力に送信され、ファイルにリダイレクトすることもできます。  
  
 /WX [: なし]  
 警告をエラーとして扱います。 参照してください[/WX (リンカー警告のエラーとして)](../../build/reference/wx-treat-linker-warnings-as-errors.md)詳細についてはします。  
  
 その他のオプションは、モード固有にのみ適用されます。 これらのオプションについては、各モードの説明を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [LIB リファレンス](../../build/reference/lib-reference.md)