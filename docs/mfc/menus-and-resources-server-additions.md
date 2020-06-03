---
title: 'メニューとリソース : サーバーの変更点'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE visual editing servers [MFC]
- accelerator tables [MFC], server applications
- visual editing [MFC], application menus and resources
- server applications [MFC], accelerator table
- string tables [MFC], visual editing applications
- servers [MFC], menu additions
- resources [MFC], server applications
- OLE server applications [MFC], menus and resources
- string editing [MFC], visual editing applications
- IDP_OLE_INIT_FAILED macro [MFC]
- server applications [MFC], OLE menus and resources
- OLE initialization failure [MFC]
ms.assetid: 56ce9e8d-8f41-4db8-8dee-e8b0702d057c
ms.openlocfilehash: 8366cd8b0376766b7914c94a24cef6598761a805
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375990"
---
# <a name="menus-and-resources-server-additions"></a>メニューとリソース : サーバーの変更点

この記事では、ビジュアル編集サーバー (コンポーネント) アプリケーションのメニューやその他のリソースに対して行う必要がある変更について説明します。 サーバー アプリケーションは、スタンドアロン、埋め込み、または場所の 3 つのモードのいずれかで開始できるため、メニュー構造やその他のリソースに多くの追加が必要です。 [「メニューとリソース (OLE)」](../mfc/menus-and-resources-ole.md)の記事で説明したように、最大 4 つのメニュー セットがあります。 4 つすべてが MDI フルサーバー アプリケーションに使用され、ミニサーバーには 3 つだけが使用されます。 アプリケーション ウィザードは、必要なサーバーの種類に必要なメニュー レイアウトを作成します。 カスタマイズが必要な場合があります。

アプリケーション・ウィザードを使用しない場合は、HIERSVR を参照してください。RC は、MFC サンプル アプリケーション[HIERSVR](../overview/visual-cpp-samples.md)のリソース スクリプトで、これらの変更がどのように実装されているかを確認します。

この記事で扱うトピックは次のとおりです。

- [サーバー メニューの追加](#_core_server_menu_additions)

- [アクセラレータ テーブルの追加](#_core_server_application_accelerator_table_additions)

- [文字列テーブルの追加](../mfc/menus-and-resources-container-additions.md)

- [ミニサーバーの追加](#_core_mini.2d.server_additions)

## <a name="server-menu-additions"></a><a name="_core_server_menu_additions"></a>サーバー メニューの追加

サーバー (コンポーネント) アプリケーションには、OLE ビジュアル編集をサポートするためにメニュー リソースが追加されている必要があります。 アプリケーションがスタンドアロン モードで実行されるときに使用されるメニューは変更する必要はありませんが、アプリケーションをビルドする前に、インプレース アクティブ化をサポートするメニュー リソースと、サーバーを完全に開くことをサポートする 2 つの新しいメニュー リソースを追加する必要があります。 両方のメニュー リソースは、フル サーバー アプリケーションとミニサーバー アプリケーションで使用されます。

- インプレース アクティベーションをサポートするには、スタンドアロン モードで実行する場合に使用するメニュー リソースとよく似たメニュー リソースを作成する必要があります。 このメニューの違いは、ファイルとウィンドウの項目 (およびデータではなく、アプリケーションを扱うその他のメニュー項目) がないことです。 コンテナー アプリケーションは、これらのメニュー項目を提供します。 このメニューマージ手法の詳細と例については、「[メニューとリソース: メニューのマージ](../mfc/menus-and-resources-menu-merging.md)」を参照してください。

- 完全に開かれたアクティブ化をサポートするには、スタンドアロン モードで実行する場合に使用されるメニュー リソースとほぼ同じメニュー リソースを作成する必要があります。 このメニュー リソースに対する唯一の変更は、サーバーが複合ドキュメントに埋め込まれたアイテムで動作しているという事実を反映して、いくつかの項目が再ワードされるということです。

この資料に記載されている変更に加えて、リソース ファイルには AFXOLESV を含める必要があります。RC は、マイクロソフト 財団クラス ライブラリの実装に必要です。 このファイルは MFC\Include サブディレクトリにあります。

## <a name="server-application-accelerator-table-additions"></a><a name="_core_server_application_accelerator_table_additions"></a>サーバー アプリケーション アクセラレータ テーブルの追加

2 つの新しいアクセラレータ テーブル リソースをサーバー アプリケーションに追加する必要があります。前述した新しいメニュー リソースに直接対応します。 最初のアクセラレータ テーブルは、サーバー アプリケーションがインプレースでアクティブ化されるときに使用されます。 このファイルは、ビューのアクセラレータ テーブル内のすべてのエントリで構成され、ファイルとウィンドウのメニューに関連付けられているエントリを除きます。

2 番目のテーブルは、ビューのアクセラレータ テーブルのほぼ正確なコピーです。 相違は、 サーバーメニュー追加機能 に記載されている、完全に開いているメニューで行われた変更[と並行して行われます](#_core_server_menu_additions)。

これらのアクセラレーター表の変更の例については、IDR_HIERSVRTYPE_SRVR_IPとIDR_HIERSVRTYPE_SRVR_EMBアクセラレーター表を HIERSVR のIDR_MAINFRAMEと比較してください。MFC OLE サンプル[HIERSVR](../overview/visual-cpp-samples.md)に含まれている RC ファイル 。 埋め込みテーブルには、ファイルとウィンドウのアクセラレータが存在しません。

## <a name="string-table-additions-for-server-applications"></a><a name="_core_string_table_additions_for_server_applications"></a>サーバー アプリケーションの文字列テーブル追加

サーバー アプリケーションでは、OLE 初期化が失敗したことを示す文字列として、1 つの文字列テーブルの追加のみが必要です。 例として、アプリケーション ウィザードによって生成される文字列テーブルエントリを次に示します。

|id|String|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE の初期化に失敗しました。 OLE ライブラリが正しいバージョンであることを確認してください。|

## <a name="miniserver-additions"></a><a name="_core_mini.2d.server_additions"></a>ミニサーバーの追加

フルサーバーの場合は、上記のミニサーバーと同じ追加機能が適用されます。 ミニサーバーはスタンドアロン モードでは実行できないため、メイン メニューのサイズは大幅に小さくなります。 アプリケーション ウィザードで作成されるメイン メニューには、[ファイル] メニューのみが表示され、[Exit] と [About] という項目だけが含まれています。 ミニサーバー用の埋め込みメニューとインプレース メニューとアクセラレータは、フル サーバーのメニューと同じです。

## <a name="see-also"></a>関連項目

[メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[メニューとリソース : メニューの結合](../mfc/menus-and-resources-menu-merging.md)
