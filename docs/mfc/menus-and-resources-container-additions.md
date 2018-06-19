---
title: 'メニューとリソース: コンテナーの変更点 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IDP_OLE_INIT_FAILED
- IDP_FAILED_TO_CREATE
- VK_ESCAPE
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c71e8a79652a86ba412ef829ac1151256d1bf65
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350654"
---
# <a name="menus-and-resources-container-additions"></a>メニューとリソース : コンテナーの変更点
この記事では、メニューやその他のビジュアル編集コンテナー アプリケーションのリソースに必要な変更について説明します。  
  
 コンテナー アプリケーションで、次の 2 つの種類の変更が必要になる: OLE ビジュアル編集し、インプレース アクティブ化に使用される新しいリソースの追加をサポートするために既存のリソースを変更します。 コンテナー アプリケーションを作成するアプリケーションのウィザードを使用する場合、これらの手順が実行されますが、いくつかのカスタマイズを必要な場合があります。  
  
 アプリケーションのウィザードを使用しない場合は、OCLIENT を確認します。RC の場合は、これらの変更を実装する方法を確認して、OCLIENT サンプル アプリケーションのリソース スクリプトです。 MFC OLE サンプルを参照して[OCLIENT](../visual-cpp-samples.md)です。  
  
 この記事で説明されているトピックは次のとおりです。  
  
-   [コンテナーのメニューの追加](#_core_container_menu_additions)  
  
-   [アクセラレータ テーブルの変更点](#_core_container_application_accelerator_table_additions)  
  
-   [文字列テーブルの変更点](#_core_string_table_additions_for_container_applications)  
  
##  <a name="_core_container_menu_additions"></a> コンテナーのメニューの追加  
 [編集] メニューに、次の項目を追加する必要があります。  
  
|アイテム|目的|  
|----------|-------------|  
|**新しいオブジェクトを挿入します。**|ドキュメントにリンクまたは埋め込み項目を挿入する OLE の [オブジェクトの挿入] ダイアログ ボックスを開きます。|  
|**リンク貼り付け.**|アイテムへのリンクをクリップボードにドキュメントに貼り付けます。|  
|**OLE 動詞**|選択した項目のプライマリ動詞を呼び出します。 選択した項目のプライマリの動詞を反映するようにこのメニュー項目の変更のテキスト。|  
|**Links**|既存のリンクされた項目を変更する OLE の [リンクの編集] ダイアログ ボックスを開きます。|  
  
 この記事に一覧表示、変更に加えて、ソース ファイルは AFXOLECL を含める必要があります。RC は、Microsoft Foundation Class ライブラリの実装に必要です。 新しいオブジェクトの挿入とは、必要な唯一のメニュー追加です。 その他の項目を追加することができますが、最も一般的な次のとおりです。  
  
 含まれているアイテムのインプレース アクティブ化をサポートする場合は、コンテナー アプリケーションの新しいメニューを作成する必要があります。 このメニューは、同じファイル メニューとウィンドウのポップアップ メニューが、開いているファイルが、それらの間に配置する 2 つの区切り記号があるときに使用で構成されます。 これらの区切り文字を使用して、サーバー (コンポーネント) の項目 (アプリケーション) がインプレース アクティブ化されたとき、そのメニューを配置する場所を指定します。 このメニューのマージ方法の詳細については、次を参照してください。[メニューとリソース: メニューのマージ](../mfc/menus-and-resources-menu-merging.md)です。  
  
##  <a name="_core_container_application_accelerator_table_additions"></a> コンテナー アプリケーションのアクセラレータ テーブルの変更点  
 コンテナー アプリケーションのアクセラレータ テーブル リソースを少し変更は、インプレース アクティブ化をサポートしている場合に必要です。 最初の変更により、一括編集モードをキャンセルするには、(ESC) は、esc キーを押すようにユーザーにします。 メインのアクセラレータ テーブルに、次のエントリを追加します。  
  
|ID|キー|型|  
|--------|---------|----------|  
|**ID_CANCEL_EDIT_CNTR**|VK_ESCAPE|**VIRTKEY**|  
  
 2 番目の変更では、インプレース アクティブ化用に作成された新しいメニュー リソースに対応する新しいアクセラレータ テーブルを作成します。 このテーブルに加え、ファイルおよびウィンドウのメニューのエントリには、 **VK_ESCAPE**上記のエントリ。 次の例は、MFC のサンプル、インプレース アクティブ化用に作成された、アクセラレータ テーブル[コンテナー](../visual-cpp-samples.md):  
  
|ID|キー|型|  
|--------|---------|----------|  
|`ID_FILE_NEW`|Ctrl + N|**VIRTKEY**|  
|`ID_FILE_OPEN`|Ctrl + O|**VIRTKEY**|  
|**ID_FILE_SAVE**|Ctrl + S|**VIRTKEY**|  
|**ID_FILE_PRINT**|Ctrl + P|**VIRTKEY**|  
|**ID_NEXT_PANE**|VK_F6|**VIRTKEY**|  
|**ID_PREV_PANE**|SHIFT キーを押しながら VK_F6|**VIRTKEY**|  
|**ID_CANCEL_EDIT_CNTR**|VK_ESCAPE|**VIRTKEY**|  
  
##  <a name="_core_string_table_additions_for_container_applications"></a> コンテナー アプリケーションの文字列テーブルの変更点  
 コンテナー アプリケーションの文字列テーブルに対する変更のほとんどに記載されている追加のメニュー項目に対応して[コンテナー メニューの変更点](#_core_container_menu_additions)です。 各メニュー項目が表示されるときに、ステータス バーに表示されるテキストを指定します。 たとえば、アプリケーションのウィザードが生成されますストリング テーブルのエントリを次に示します。  
  
|ID|String|  
|--------|------------|  
|**IDP_OLE_INIT_FAILED**|OLE の初期化に失敗しました。 OLE ライブラリが適切なバージョンを確認します。|  
|**IDP_FAILED_TO_CREATE**|オブジェクトを作成できませんでした。 システム レジストリにオブジェクトを入力することを確認します。|  
  
## <a name="see-also"></a>関連項目  
 [メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)   
 [メニューとリソース: サーバーの変更点](../mfc/menus-and-resources-server-additions.md)

