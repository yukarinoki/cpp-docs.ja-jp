---
title: LIB の概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8fd3d370da4f841e85086e3d061508d68414e96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379199"
---
# <a name="overview-of-lib"></a>LIB の概要
Lib、インポート ライブラリ、およびエクスポートで使用できるファイル[リンク](../../build/reference/linker-options.md)プログラムを作成するときにします。 LIB は、コマンド プロンプトから実行されます。  
  
 LIB は、次のモードで使用できます。  
  
-   [構築または COFF ライブラリを変更します。](../../build/reference/managing-a-library.md)  
  
-   [ファイルにメンバー オブジェクトを抽出します。](../../build/reference/extracting-a-library-member.md)  
  
-   [インポート ライブラリとエクスポート ファイルを作成します。](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 これらのモードは相互に排他的です。LIB は、一度に 1 つのモードで使用できます。  
  
## <a name="lib-options"></a>Lib オプション  
 次の表には、詳細情報へのリンクを使用して、lib.exe のオプションが一覧表示します。  
  
 **/DEF**  
 インポート ライブラリとエクスポート ファイルを作成します。  
  
 詳細については、次を参照してください。[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)です。  
  
 **/ERRORREPORT**  
 Lib.exe の内部エラーに関する情報を Microsoft に送信します。  
  
 詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)です。  
  
 **/EXPORT**  
 プログラムから関数をエクスポートします。  
  
 詳細については、次を参照してください。[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)です。  
  
 **/EXTRACT します。**  
 既存のライブラリのメンバーのコピーを含むオブジェクト (.obj) ファイルを作成します。  
  
 詳細については、次を参照してください。[ライブラリ メンバーの抽出](../../build/reference/extracting-a-library-member.md)です。  
  
 **/INCLUDE**  
 シンボルをシンボル テーブルに追加します。  
  
 詳細については、次を参照してください。[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)です。  
  
 **/LIBPATH**  
 環境ライブラリ パスをオーバーライドします。  
  
 詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)です。  
  
 **/一覧表示**  
 標準出力に出力ライブラリに関する情報を表示します。  
  
 詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)です。  
  
 **/LTCG**  
 リンク時コード生成を使用してビルドするライブラリが発生します。  
  
 詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)です。  
  
 **/MACHINE**  
 プログラムのターゲット プラットフォームを指定します。  
  
 詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)です。  
  
 **/名前**  
 インポート ライブラリをビルドする場合は、インポート ライブラリを作成する対象の DLL の名前を指定します。  
  
 詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)です。  
  
 **/NODEFAULTLIB**  
 外部参照を解決するときに、検索するライブラリの一覧から 1 つまたは複数の既定のライブラリを削除します。  
  
 詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)です。  
  
 **/NOLOGO**  
 LIB 著作権メッセージとバージョン番号の表示を中止し、コマンド ファイルのエコーを防止します。  
  
 詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)です。  
  
 **/入力出力**  
 既定の出力ファイル名をオーバーライドします。  
  
 詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)です。  
  
 **/削除します。**  
 出力ライブラリからのオブジェクトを除外します。  
  
 詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)です。  
  
 **/SUBSYSTEM**  
 オペレーティング システムに出力ライブラリにリンクすることによって作成されたプログラムを実行する方法を説明します。  
  
 詳細については、次を参照してください。[ライブラリの管理](../../build/reference/managing-a-library.md)です。  
  
 **/VERBOSE**  
 追加される .obj ファイルの名前を含め、セッションの進行状況に関する詳細を表示します。  
  
 詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)です。  
  
 **/WX**  
 警告をエラーとして扱います。  
  
 詳細については、次を参照してください。 [LIB の実行](../../build/reference/running-lib.md)です。  
  
## <a name="see-also"></a>関連項目  
 [LIB リファレンス](../../build/reference/lib-reference.md)   
 [LIB の入力ファイル](../../build/reference/lib-input-files.md)   
 [LIB の出力ファイル](../../build/reference/lib-output-files.md)   
 [他のライブラリ出力](../../build/reference/other-lib-output.md)   
 [ライブラリの構造](../../build/reference/structure-of-a-library.md)