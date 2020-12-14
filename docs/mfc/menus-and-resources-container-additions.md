---
description: '詳細については、「メニューとリソース: コンテナーの追加」を参照してください。'
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
ms.openlocfilehash: e32167e66693587a32732c1c20fc6d85d3010ecb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253365"
---
# <a name="menus-and-resources-container-additions"></a>メニューとリソース : コンテナーの変更点

この記事では、ビジュアル編集コンテナーアプリケーションで、メニューやその他のリソースに対して行う必要がある変更について説明します。

コンテナーアプリケーションでは、2種類の変更を行う必要があります。既存のリソースに変更を加えて、OLE ビジュアル編集をサポートし、インプレースアクティブ化に使用される新しいリソースを追加します。 アプリケーションウィザードを使用してコンテナーアプリケーションを作成する場合は、これらの手順が実行されますが、カスタマイズが必要になる場合があります。

アプリケーションウィザードを使用しない場合は、OCLIENT を確認することをお勧めします。RC (OCLIENT サンプルアプリケーション用のリソーススクリプト) を使用して、これらの変更がどのように実装されているかを確認します。 「MFC OLE サンプル [OCLIENT](../overview/visual-cpp-samples.md)」を参照してください。

この記事では、次のトピックについて説明します。

- [コンテナーメニューの追加](#_core_container_menu_additions)

- [アクセラレータテーブルの追加](#_core_container_application_accelerator_table_additions)

- [文字列テーブルの追加](#_core_string_table_additions_for_container_applications)

## <a name="container-menu-additions"></a><a name="_core_container_menu_additions"></a> コンテナーメニューの追加

[編集] メニューに次の項目を追加する必要があります。

|項目|目的|
|----------|-------------|
|**新しいオブジェクトの挿入**|[OLE 挿入オブジェクト] ダイアログボックスを開き、リンクされたアイテムまたは埋め込みアイテムをドキュメントに挿入します。|
|**リンクの貼り付け**|クリップボード上のアイテムへのリンクをドキュメントに貼り付けます。|
|**OLE 動詞**|選択した項目の主動詞を呼び出します。 このメニュー項目のテキストは、選択した項目のプライマリ動詞を反映して変更されます。|
|**リンク**|OLE の [リンクの編集] ダイアログボックスを開いて、既存のリンクアイテムを変更します。|

この記事に記載されている変更に加えて、ソースファイルには AFXOLECL を含める必要があります。RC。 Microsoft Foundation Class ライブラリの実装に必要です。 必須メニューの追加は、[新しいオブジェクトの挿入] だけです。 他の項目も追加できますが、ここに挙げたものは最も一般的なものです。

含まれている項目のインプレースアクティブ化をサポートする場合は、コンテナーアプリケーションの新しいメニューを作成する必要があります。 このメニューは、ファイルが開いているときに使用されるのと同じ [ファイル] メニューと [ウィンドウ] ポップアップメニューで構成されていますが、2つの区切り記号が配置されています。 これらの区切り記号を使用して、サーバー (コンポーネント) 項目 (アプリケーション) でメニューを配置する場所を指定します。 このメニューの結合方法の詳細については、「メニュー [とリソース: メニューのマージ](menus-and-resources-menu-merging.md)」を参照してください。

## <a name="container-application-accelerator-table-additions"></a><a name="_core_container_application_accelerator_table_additions"></a> コンテナーアプリケーションアクセラレータテーブルの追加

インプレースアクティベーションをサポートしている場合は、コンテナーアプリケーションのアクセラレータテーブルリソースに小さな変更を加える必要があります。 最初の変更では、ユーザーは ESC キーを押して、インプレース編集モードを取り消すことができます。 次のエントリをメインアクセラレータテーブルに追加します。

|ID|キー|種類|
|--------|---------|----------|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY**|

2番目の変更は、インプレースアクティブ化のために作成された新しいメニューリソースに対応する新しいアクセラレータテーブルを作成することです。 このテーブルには、上の VK_ESCAPE エントリに加えて、[ファイル] メニューと [ウィンドウ] メニューのエントリがあります。 次の例は、MFC サンプル [コンテナー](../overview/visual-cpp-samples.md)のインプレースアクティブ化のために作成されたアクセラレータテーブルです。

|ID|キー|種類|
|--------|---------|----------|
|ID_FILE_NEW|Ctrl + N|**VIRTKEY**|
|ID_FILE_OPEN|Ctrl + O|**VIRTKEY**|
|ID_FILE_SAVE|Ctrl + S|**VIRTKEY**|
|ID_FILE_PRINT|Ctrl + P|**VIRTKEY**|
|ID_NEXT_PANE|VK_F6|**VIRTKEY**|
|ID_PREV_PANE|SHIFT + VK_F6|**VIRTKEY**|
|ID_CANCEL_EDIT_CNTR|VK_ESCAPE|**VIRTKEY**|

## <a name="string-table-additions-for-container-applications"></a><a name="_core_string_table_additions_for_container_applications"></a> コンテナーアプリケーションの文字列テーブルの追加

コンテナーアプリケーションの文字列テーブルに加えられた変更のほとんどは、「 [コンテナーメニューの追加](#_core_container_menu_additions)」で説明されている追加のメニュー項目に対応しています。 各メニュー項目が表示されるときに、ステータスバーに表示されるテキストを指定します。 例として、アプリケーションウィザードによって生成される文字列テーブルのエントリを次に示します。

|id|String|
|--------|------------|
|IDP_OLE_INIT_FAILED|OLE の初期化に失敗しました。 OLE ライブラリが正しいバージョンであることを確認します。|
|IDP_FAILED_TO_CREATE|オブジェクトを作成できませんでした。 オブジェクトがシステムレジストリに入力されていることを確認します。|

## <a name="see-also"></a>関連項目

[メニューとリソース (OLE)](menus-and-resources-ole.md)<br/>
[メニューとリソース: サーバーの追加](menus-and-resources-server-additions.md)
