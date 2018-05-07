---
title: 'TN048: MFC データベース アプリケーション用の ODBC セットアップおよび管理プログラムの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.odbc
dev_langs:
- C++
helpviewer_keywords:
- installing ODBC
- ODBC, installing
- setup, ODBC setup programs
- TN048
- ODBC, and MFC
- MFC, database applications
ms.assetid: d456cdd4-0513-4a51-80c0-9132b66115ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c08366f995c1ecb4182fff04a88ac37fe7334bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="tn048-writing-odbc-setup-and-administration-programs-for-mfc-database-applications"></a>テクニカル ノート 48: MFC データベース アプリケーション用の ODBC セットアップおよび管理プログラムの作成
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 MFC データベース クラスを使用するアプリケーションでは、ODBC コンポーネントをインストールするセットアップ プログラムを必要があります。 既定のドライバーを指定してデータ ソースを構成するのには、使用可能なドライバーについての情報を取得する ODBC 管理者プログラムも必要です。 ここでは、これらのプログラムを作成する ODBC インストーラーの API の使用について説明します。  
  
##  <a name="_mfcnotes_writing_an_odbc_setup_program"></a> ODBC セットアップ プログラムの作成  
 MFC データベース アプリケーション (ODBC ODBC ドライバー マネージャーが必要です。DLL) とデータ ソースを取得できる ODBC ドライバー。 多くの ODBC ドライバーでは、追加のネットワークとの通信の Dll も必要です。 ほとんどの ODBC ドライバーは、ODBC の必須コンポーネントをインストールするセットアップ プログラムに付属します。 MFC データベース クラスを使用するアプリケーション開発者が実行できます。  
  
-   ODBC コンポーネントをインストールするドライバー固有のセットアップ プログラムに依存します。 これは、それ以上開発者の作業: ドライバーのセットアップ プログラムを再配布することだけです。  
  
-   または、ドライバー マネージャーとドライバーのインストールは独自のセットアップ プログラムを記述することができます。  
  
 ODBC インストーラーの API は、アプリケーション固有のセットアップ プログラムの作成に使用できます。 インストーラーの API 内の関数は、ODBC インストーラー DLL によって実装される — ODBCINST です。ODBCCP32 および 16 ビット Windows DLL です。Win32 の DLL です。 アプリケーションが呼び出すことができます**SQLInstallODBC** DLL で、ODBC ドライバー マネージャー、ODBC ドライバー、およびそのいずれかにインストールされます installer で翻訳者が必要です。 インストールされているドライバーと翻訳者が、ODBCINST で記録します。INI ファイル (または、レジストリ、NT)。 **SQLInstallODBC** ODBC への完全パスが必要です。INF ファイルをインストールするドライバーの一覧が含まれており、それぞれのドライバーを構成するファイルについて説明します。 ドライバー マネージャーと翻訳者に関する同様の情報も含まれています。 ODBC です。通常、INF ファイルは、ドライバーの開発者によって提供されます。  
  
 プログラムは、ODBC の個々 のコンポーネントをインストールすることもできます。 プログラムの最初の呼び出し、ドライバー マネージャーをインストールする**SQLInstallDriverManager**インストーラー ドライバー マネージャーのターゲット ディレクトリを取得するための DLL にします。 これは、通常、Windows の Dll が存在するディレクトリです。 プログラム、ODBC の [ODBC ドライバー マネージャー] セクションの情報を使用しています。INF ファイルをこのディレクトリにインストール ディスクからドライバー マネージャーと関連ファイルをコピーします。 プログラムの最初の呼び出し、個々 のドライバーをインストールする**SQLInstallDriver**のインストーラーに追加するドライバーの仕様、ODBCINST DLL にします。INI ファイル (または、レジストリ、NT)。 **SQLInstallDriver**ドライバーのターゲット ディレクトリを返します: 通常の Windows Dll が存在するディレクトリ。 プログラムの ODBC ドライバーのセクションの情報を使用しています。INF ファイルをこのディレクトリにインストール ディスクからドライバ DLL と関連ファイルをコピーします。  
  
 ODBC の詳細についてはします。INF、ODBCINST です。INI およびインストーラーの API を使用して ODBC SDK を参照してください。*プログラマーズ リファレンス、* 19 章、ODBC のソフトウェアをインストールします。  
  
##  <a name="_mfcnotes_writing_an_odbc_administrator"></a> Odbc データ ソース アドミニストレーターの書き込み  
 MFC データベース アプリケーションが 2 つの方法のいずれかで ODBC データ ソースを次のように構成を設定できます。  
  
-   (プログラムまたはコントロール パネルのアイテムとして使用可能) の ODBC アドミニストレーターを使用します。  
  
-   データ ソースを構成する独自のプログラムを作成します。  
  
 データ ソースを構成するプログラムは、インストーラー DLL への関数呼び出しを使用します。 インストーラー DLL は、セットアップをデータ ソースを構成する DLL を呼び出します。 各ドライバー; の 1 つのセットアップ DLL があります。ドライバー DLL 自体、または別の DLL がある可能性があります。 DLL のセットアップでは、ドライバーがサポートされている場合、データ ソースと、既定の変換プログラムへの接続に必要な情報をユーザーを要求します。 DLL と Windows Api は、ODBC でこの情報を記録し、インストーラーを呼び出します。INI ファイル (レジストリ)。  
  
 プログラムの呼び出しをユーザーが追加、変更、およびデータ ソースを削除 ダイアログ ボックスを表示する**SQLManageDataSources**の DLL のインストーラーにします。 この関数には、DLL が、コントロール パネルから呼び出されると、インストーラーが呼び出されます。 追加、変更、またはデータ ソースを削除する**SQLManageDataSources**呼び出し**ConfigDSN**でそのデータ ソースに関連付けられているドライバーのセットアップ DLL です。 ソースの追加、変更、またはデータの削除を直接、プログラムが呼び出す**SQLConfigDataSource**の DLL のインストーラーにします。 プログラムでは、データ ソースおよび実行するアクションを指定するオプションの名前を渡します。 **SQLConfigDataSource**呼び出し**ConfigDSN**セットアップ DLL 内から引数を渡します**SQLConfigDataSource**です。  
  
 詳細については、ODBC SDK を参照してください。*プログラマーズ リファレンス、* 23 章、DLL 関数の参照をセットアップ、および章 24、インストーラー DLL 関数を参照します。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

