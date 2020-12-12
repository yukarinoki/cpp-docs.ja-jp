---
description: '詳細については、「メニューとリソース: サーバーの追加」を参照してください。'
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
ms.openlocfilehash: e53031fd030efa498bd80bdb191f76f66f63d343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122877"
---
# <a name="menus-and-resources-server-additions"></a>メニューとリソース : サーバーの変更点

この記事では、ビジュアル編集サーバー (コンポーネント) アプリケーションのメニューやその他のリソースに対して行う必要がある変更について説明します。 サーバーアプリケーションでは、[スタンドアロン]、[埋め込み]、または [配置済み] の3つのモードのいずれかで起動できるため、メニュー構造やその他のリソースに多くの追加を行う必要があります。 「 [メニューとリソース (OLE)](menus-and-resources-ole.md) 」の記事で説明されているように、最大4組のメニューがあります。 4つすべてが MDI フルサーバーアプリケーションに使用されますが、ミニサーバーでは3つだけが使用されます。 アプリケーションウィザードによって、目的のサーバーの種類に必要なメニューレイアウトが作成されます。 一部のカスタマイズが必要になる場合があります。

アプリケーションウィザードを使用しない場合は、HIERSVR を調べることをお勧めします。RC は、MFC サンプルアプリケーション [HIERSVR](../overview/visual-cpp-samples.md)のリソーススクリプトで、これらの変更がどのように実装されているかを確認します。

この記事では、次のトピックについて説明します。

- [サーバーメニューの追加](#_core_server_menu_additions)

- [アクセラレータテーブルの追加](#_core_server_application_accelerator_table_additions)

- [文字列テーブルの追加](menus-and-resources-container-additions.md)

- [ミニミニ追加](#_core_mini.2d.server_additions)

## <a name="server-menu-additions"></a><a name="_core_server_menu_additions"></a> サーバーメニューの追加

OLE ビジュアル編集をサポートするには、サーバー (コンポーネント) アプリケーションにメニューリソースが追加されている必要があります。 アプリケーションをスタンドアロンモードで実行するときに使用するメニューは変更する必要はありませんが、アプリケーションをビルドする前に2つの新しいメニューリソースを追加する必要があります。1つはインプレースライセンス認証をサポートし、もう1つはサーバーを完全に開いていることをサポートします。 両方のメニューリソースは、フルアプリケーションとミニミニアプリケーションで使用されます。

- インプレースアクティブ化をサポートするには、スタンドアロンモードで実行するときに使用するメニューリソースとよく似たメニューリソースを作成する必要があります。 このメニューの違いは、ファイルとウィンドウの項目 (およびデータではなく、アプリケーションを処理するその他のメニュー項目) がないことです。 コンテナーアプリケーションは、これらのメニュー項目を提供します。 このメニューの結合方法の詳細と例については、「 [メニューとリソース: メニューのマージ](menus-and-resources-menu-merging.md)」を参照してください。

- 完全に開いたアクティベーションをサポートするには、スタンドアロンモードで実行するときに使用するメニューリソースとほぼ同じメニューリソースを作成する必要があります。 このメニューリソースを変更する唯一の方法は、複合ドキュメントに埋め込まれた項目に対してサーバーが動作しているという事実を反映するために、一部の項目が繰り返しされることです。

この記事に記載されている変更に加えて、リソースファイルには AFXOLESV を含める必要があります。RC。 Microsoft Foundation Class ライブラリの実装に必要です。 このファイルは、Mfc/Include サブディレクトリにあります。

## <a name="server-application-accelerator-table-additions"></a><a name="_core_server_application_accelerator_table_additions"></a> サーバーアプリケーションアクセラレータテーブルの追加

2つの新しいアクセラレータテーブルリソースをサーバーアプリケーションに追加する必要があります。これらは、前に説明した新しいメニューリソースに直接対応しています。 最初のアクセラレータテーブルは、サーバーアプリケーションが適切にアクティブ化されるときに使用されます。 これは、[ファイル] メニューと [ウィンドウ] メニューに関連付けられているものを除き、ビューのアクセラレータテーブル内のすべてのエントリで構成されます。

2番目のテーブルは、ビューのアクセラレータテーブルのほぼ同一のコピーです。 「 [サーバーメニューの追加](#_core_server_menu_additions)」で説明されている [完全に開く] メニューに加えられた変更の違い。

これらのアクセラレータテーブルの変更の例については、IDR_HIERSVRTYPE_SRVR_IP と IDR_HIERSVRTYPE_SRVR_EMB アクセラレータテーブルを HIERSVR の IDR_MAINFRAME と比較してください。RC ファイルは、MFC OLE サンプル [HIERSVR](../overview/visual-cpp-samples.md)に含まれています。 埋め込み先テーブルにファイルとウィンドウアクセラレータがありません。このアクセラレータの正確なコピーは、埋め込みテーブルに格納されています。

## <a name="string-table-additions-for-server-applications"></a><a name="_core_string_table_additions_for_server_applications"></a> サーバーアプリケーションの文字列テーブルの追加

サーバーアプリケーションでは、1つの文字列テーブルの追加のみが必要です。 OLE の初期化が失敗したことを示す文字列です。 例として、アプリケーションウィザードによって生成される文字列テーブルのエントリを次に示します。

|id|String|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE の初期化に失敗しました。 OLE ライブラリが正しいバージョンであることを確認します。|

## <a name="miniserver-additions"></a><a name="_core_mini.2d.server_additions"></a> ミニミニ追加

すべてのサーバーについては、上記のミニサーバーにも同じ追加機能が適用されます。 ミニモードはスタンドアロンモードでは実行できないため、メインメニューはかなり小さくなります。 アプリケーションウィザードによって作成されたメインメニューには、[終了] と [バージョン情報] のみを含む [ファイル] メニューのみがあります。 Miniservers 用の埋め込みメニューと埋め込みメニューおよびアクセラレータは、フルサーバーの場合と同じです。

## <a name="see-also"></a>関連項目

[メニューとリソース (OLE)](menus-and-resources-ole.md)<br/>
[メニューとリソース: メニューのマージ](menus-and-resources-menu-merging.md)
