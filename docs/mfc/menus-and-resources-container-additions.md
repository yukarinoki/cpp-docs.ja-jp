---
title: 'メニューとリソース : コンテナーの変更点'
ms.date: 11/04/2016
f1_keywords:
- IDP_OLE_INIT_FAILED
- IDP_FAILED_TO_CREATE
- VK_ESCAPE
helpviewer_keywords:
- application accelerator table [MFC]
- VK_ESCAPE key [MFC]
- IDP_FAILED_TO_CREATE macro [MFC]
- visual editing, application menus and resources
- OLE containers [MFC], menus and resources
- accelerator tables [MFC], container applications
- IDP_OLE_INIT_FAILED macro [MFC]
- CONTAIN tutorial [MFC]
- Links menu item [MFC]
ms.assetid: 425448be-8ca0-412e-909a-a3a9ce845288
ms.openlocfilehash: c8da58316f471f7b7d26e142cc1dd1ccaa6ad8b5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364793"
---
# <a name="menus-and-resources-container-additions"></a>メニューとリソース : コンテナーの変更点

この記事では、ビジュアル編集コンテナー アプリケーションのメニューやその他のリソースに対して行う必要がある変更について説明します。

コンテナ アプリケーションでは、OLE ビジュアル編集をサポートするための既存のリソースの変更と、インプレース アクティブ化に使用する新しいリソースの追加という 2 種類の変更を行う必要があります。 アプリケーション ウィザードを使用してコンテナー アプリケーションを作成する場合、これらの手順は実行されますが、カスタマイズが必要な場合があります。

アプリケーション ウィザードを使用しない場合は、OCLIENT を参照してください。RC は、これらの変更がどのように実装されているかを確認するための、OCLIENT サンプル アプリケーションのリソース スクリプトです。 MFC の OLE サンプル[OCLIENT](../overview/visual-cpp-samples.md)を参照してください。

この記事で扱うトピックは次のとおりです。

- [コンテナメニューの追加](#_core_container_menu_additions)

- [アクセラレータ テーブルの追加](#_core_container_application_accelerator_table_additions)

- [文字列テーブルの追加](#_core_string_table_additions_for_container_applications)

## <a name="container-menu-additions"></a><a name="_core_container_menu_additions"></a>コンテナメニューの追加

[編集] メニューに次の項目を追加する必要があります。

|Item|目的|
|----------|-------------|
|**新しいオブジェクトの挿入**|[OLE オブジェクトの挿入] ダイアログ ボックスを開き、リンクされたアイテムまたは埋め込みアイテムを文書に挿入します。|
|**リンク貼り付け**|クリップボードのアイテムへのリンクをドキュメントに貼り付けます。|
|**OLE 動詞**|選択した項目の主動詞を呼び出します。 このメニュー項目のテキストは、選択した項目の主動詞を反映して変更されます。|
|**リンク**|既存のリンクアイテムを変更するために、[リンクの編集] ダイアログ ボックスを開きます。|

この資料に記載されている変更に加えて、ソース ファイルに AFXOLECL を含める必要があります。RC は、マイクロソフト 財団クラス ライブラリの実装に必要です。 [新しいオブジェクトを挿入] は、メニューの追加が必要な唯一の項目です。 他の項目も追加できますが、ここに記載されている項目が最も一般的です。

コンテナー アプリケーションの新しいメニューを作成する必要があります。 このメニューは、ファイルを開いているときに使用する[ファイル]メニューと[ウィンドウ]ポップアップメニューで構成されていますが、ファイルの間には2つの区切り文字が配置されています。 これらの区切り記号は、サーバー (コンポーネント) 項目 (アプリケーション) がアクティブになったときに、そのメニューを配置する場所を示すために使用されます。 このメニューマージ手法の詳細については、「[メニューとリソース : メニューのマージ](../mfc/menus-and-resources-menu-merging.md)」を参照してください。

## <a name="container-application-accelerator-table-additions"></a><a name="_core_container_application_accelerator_table_additions"></a>コンテナー アプリケーション アクセラレータ テーブルの追加

コンテナー アプリケーションのアクセラレータ テーブル リソースに対する小さな変更は、インプレース アクティブ化をサポートしている場合に必要です。 最初の変更により、ユーザーはエスケープ キー (ESC) を押して、インプレース編集モードをキャンセルできます。 メイン アクセラレータ テーブルに次のエントリを追加します。

|id|Key|Type|
|--------|---------|----------|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY**|

2 番目の変更は、インプレース アクティブ化用に作成された新しいメニュー リソースに対応する新しいアクセラレータ テーブルを作成することです。 このテーブルには、上記のVK_ESCAPEエントリに加えて、ファイルメニューとウィンドウメニューのエントリがあります。 次の例は、MFC サンプル CONTAINER でのインプレース アクティブ化用に作成されたアクセラレータ テーブル[です](../overview/visual-cpp-samples.md)。

|id|Key|Type|
|--------|---------|----------|
|ID_FILE_NEW|Ctrl + N|**VIRTKEY**|
|ID_FILE_OPEN|Ctrl + O|**VIRTKEY**|
|ID_FILE_SAVE|Ctrl + S|**VIRTKEY**|
|ID_FILE_PRINT|Ctrl + P|**VIRTKEY**|
|ID_NEXT_PANE|VK_F6|**VIRTKEY**|
|ID_PREV_PANE|shift キーを押しながらVK_F6|**VIRTKEY**|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY**|

## <a name="string-table-additions-for-container-applications"></a><a name="_core_string_table_additions_for_container_applications"></a>コンテナアプリケーション用の文字列テーブル追加

コンテナアプリケーションの文字列テーブルに対する変更のほとんどは、「[コンテナメニュー追加](#_core_container_menu_additions)」で説明されている追加メニュー項目に対応しています。 各メニュー項目が表示されるときに、ステータス バーに表示されるテキストを指定します。 例として、アプリケーション ウィザードによって生成される文字列テーブルエントリを次に示します。

|id|String|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE の初期化に失敗しました。 OLE ライブラリが正しいバージョンであることを確認してください。|
|IDP_FAILED_TO_CREATE|オブジェクトの作成に失敗しました。 オブジェクトがシステム レジストリに入力されていることを確認します。|

## <a name="see-also"></a>関連項目

[メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)<br/>
[メニューとリソース: サーバーの変更点](../mfc/menus-and-resources-server-additions.md)
