---
title: LIB の概要
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
ms.openlocfilehash: 03209bc409453cab1769606cb972f4572d3617bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548500"
---
# <a name="overview-of-lib"></a>LIB の概要

Lib、インポート ライブラリ、およびファイルで使用できるエクスポート[リンク](../../build/reference/linker-options.md)プログラムを作成するときにします。 LIB は、コマンド プロンプトから実行します。

LIB は、次のモードで使用できます。

- [構築または COFF ライブラリを変更します。](../../build/reference/managing-a-library.md)

- [メンバー オブジェクトをファイルの抽出](../../build/reference/extracting-a-library-member.md)

- [インポート ライブラリとエクスポート ファイルを作成します。](../../build/reference/working-with-import-libraries-and-export-files.md)

これらのモードは相互に排他的です。LIB は、一度に 1 つのみのモードで使用できます。

## <a name="lib-options"></a>Lib オプション

次の表には、詳細情報へのリンクを含む、lib.exe のオプションが一覧表示します。

|オプション|説明|
|-|-|
|**/DEF**|インポート ライブラリとエクスポート ファイルを作成します。<br/><br/>詳細については、次を参照してください。[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)します。|
|**/ERRORREPORT**|   Lib.exe に内部エラーに関する情報をマイクロソフトに送信します。<br/><br/>詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)します。|
|**/EXPORT**|   プログラムから関数をエクスポートします。<br/><br/>詳細については、次を参照してください。[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)します。|
|**/抽出**|   既存のライブラリのメンバーのコピーを含むオブジェクト (.obj) ファイルを作成します。<br/><br/>詳細については、次を参照してください。[ライブラリ メンバーの抽出](../../build/reference/extracting-a-library-member.md)します。|
|**/INCLUDE**|   シンボルをシンボル テーブルに追加します。<br/><br/>詳細については、次を参照してください。[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)します。|
|**/LIBPATH**|   環境ライブラリ パスをオーバーライドします。<br/><br/>詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)します。|
|**/一覧表示**|   標準出力に出力ライブラリに関する情報を表示します。<br/><br/>詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)します。|
|**/LTCG**|   リンク時コード生成を使用してビルドするライブラリをによりします。<br/><br/>詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)します。|
|**/MACHINE**|   プログラムのターゲット プラットフォームを指定します。<br/><br/>詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)します。|
|**/名前**|   インポート ライブラリを構築する場合は、インポート ライブラリが構築されている DLL の名前を指定します。<br/><br/>詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)します。|
|**/NODEFAULTLIB**|   外部参照を解決するときに検索するライブラリの一覧から 1 つまたは複数の既定のライブラリを削除します。<br/><br/>詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)します。|
|**/NOLOGO**|   LIB 著作権メッセージとバージョン番号の表示を中止し、コマンド ファイルのエコーを防止します。<br/><br/>詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)します。|
|**/OUT**|   既定の出力ファイル名をオーバーライドします。<br/><br/>詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)します。|
|**/削除します。**|   出力ライブラリからオブジェクトを省略します。<br/><br/>詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)します。|
|**/SUBSYSTEM**|   出力ライブラリにリンクすることによって作成されたプログラムを実行する方法をオペレーティング システムに指示します。<br/><br/>詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)します。|
|**/VERBOSE**|   追加される .obj ファイルの名前を含め、セッションの進行状況の詳細を表示します。<br/><br/>詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)します。|
|**/WX**|   警告をエラーとして扱います。<br/><br/>詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)します。|

## <a name="see-also"></a>関連項目

[LIB リファレンス](../../build/reference/lib-reference.md)<br/>
[LIB の入力ファイル](../../build/reference/lib-input-files.md)<br/>
[LIB の出力ファイル](../../build/reference/lib-output-files.md)<br/>
[LIB のその他の出力](../../build/reference/other-lib-output.md)<br/>
[ライブラリの構造](../../build/reference/structure-of-a-library.md)