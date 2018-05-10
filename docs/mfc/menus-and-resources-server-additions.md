---
title: 'メニューとリソース: サーバーの変更点 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IDP_OLE_INIT_FAILED
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86b941820b439afc8b914142b412995df30f109c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="menus-and-resources-server-additions"></a>メニューとリソース : サーバーの変更点
この記事では、メニューやその他のビジュアル編集サーバー (コンポーネント) アプリケーションのリソースに必要な変更について説明します。 サーバー アプリケーションでは、3 つのモードのいずれかで起動できるため、メニュー構造とその他のリソースに多くの追加が必要です。 スタンドアロン、埋め込み、および配置します。 」の説明に従って、[メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)記事、最大 4 つの組のメニューがあります。 ミニサーバーの 3 つだけが使用中に、MDI フル サーバー アプリケーションは、4 つすべてが使用されます。 アプリケーションを作成します メニューのレイアウトかサーバーの種類に必要です。 一部のカスタマイズが必要な可能性があります。  
  
 アプリケーションのウィザードを使用しない場合は、HIERSVR を確認します。RC は、MFC サンプル アプリケーションのリソース スクリプト[HIERSVR](../visual-cpp-samples.md)、これらの変更を実装する方法を参照してください。  
  
 この記事で説明されているトピックは次のとおりです。  
  
-   [サーバーのメニューの追加](#_core_server_menu_additions)  
  
-   [アクセラレータ テーブルの変更点](#_core_server_application_accelerator_table_additions)  
  
-   [文字列テーブルの変更点](../mfc/menus-and-resources-container-additions.md)  
  
-   [ミニサーバーの変更点](#_core_mini.2d.server_additions)  
  
##  <a name="_core_server_menu_additions"></a> サーバーのメニューの追加  
 OLE ビジュアル編集をサポートする追加のメニュー リソース (コンポーネント) のサーバー アプリケーションが必要です。 アプリケーションがスタンドアロン モードで実行するときに使用するメニューを変更する必要はありませんが、アプリケーションを構築する前に、2 つの新しいメニュー リソースを追加する必要があります: インプレース アクティブ化と完全にオープンされているサーバーをサポートする 1 つをサポートするために 1 つです。 両方のメニュー リソースは、完全とミニサーバー アプリケーションによって使用されます。  
  
-   インプレース アクティブ化をサポートするには、スタンドアロン モードで実行するときに使用するメニュー リソースに非常に類似したメニュー リソースを作成する必要があります。 このメニューの違いは、ファイルとウィンドウの項目 (および、アプリケーションとデータではなくを処理するその他のメニュー項目) がないことです。 コンテナー アプリケーションでは、これらのメニュー項目を提供します。 詳細については、上と、このメニューのマージ方法の例では、記事を参照してください。[メニューとリソース: メニューのマージ](../mfc/menus-and-resources-menu-merging.md)です。  
  
-   を完全にオープン ライセンス認証をサポートするには、スタンドアロン モードで実行すると、メニュー リソースを使用するとほぼ同じメニュー リソースを作成する必要があります。 このメニュー リソースに対する唯一の変更は、複合ドキュメントに埋め込まれている項目で、サーバーが動作しているという事実を反映するようにいくつかのアイテムを繰り返しことです。  
  
 この記事に一覧表示、変更に加えて、リソース ファイルを AFXOLESV を含める必要があります。RC は、Microsoft Foundation Class ライブラリの実装に必要です。 このファイルは、定義してサブディレクトリ内です。  
  
##  <a name="_core_server_application_accelerator_table_additions"></a> サーバー アプリケーションのアクセラレータ テーブルの変更点  
 サーバー アプリケーションに新しい 2 つのアクセラレータ テーブル リソースを追加する必要があります。既に説明した新しいメニュー リソースに直接対応します。 最初のアクセラレータ テーブルは、インプレース アクティブ化されると、サーバー アプリケーションが使用されます。 以外にあるファイルおよびウィンドウのメニューのビューのアクセラレータ テーブル内のすべてのエントリで構成されます。  
  
 2 番目のテーブルは、ほぼビューのアクセラレータ テーブルの正確なコピーです。 説明したメニューで行われた変更を書き換えて[Server メニューの追加](#_core_server_menu_additions)です。  
  
 これらのアクセラレータ テーブルの変更の例は、比較、 **IDR_HIERSVRTYPE_SRVR_IP**と**IDR_HIERSVRTYPE_SRVR_EMB**アクセラレータを持つテーブル**IDR_MAINFRAME**Hiersvr です。MFC OLE サンプルに含まれている RC ファイル[HIERSVR](../visual-cpp-samples.md)です。 ファイルとウィンドウのアクセラレータをインプレースでテーブルから不足していると、それらの正確なコピーは、埋め込みテーブル。  
  
##  <a name="_core_string_table_additions_for_server_applications"></a> サーバー アプリケーション用の文字列テーブルの変更点  
 1 つだけの文字列テーブルの追加は、サーバー アプリケーションで必要です: OLE の初期化が失敗したことを示す文字列。 たとえば、アプリケーションのウィザードによって生成される文字列テーブルのエントリを次に示します。  
  
|ID|String|  
|--------|------------|  
|**IDP_OLE_INIT_FAILED**|OLE の初期化に失敗しました。 OLE ライブラリが適切なバージョンを確認します。|  
  
##  <a name="_core_mini.2d.server_additions"></a> ミニサーバーの変更点  
 同じ追加機能を上に示したものと miniservers の適用フル サーバー。 ミニサーバーがスタンドアロン モードで実行されることはできません、ためメイン メニューが大幅に小さくなります。 アプリケーション ウィザードによって作成されたメイン メニューがのみ、ファイル メニュー項目の終了時のみを含むしようとします。 埋め込みおよびインプレースでメニューおよび miniservers のアクセラレータは、フル サーバーの場合と同じです。  
  
## <a name="see-also"></a>関連項目  
 [メニューとリソース (OLE)](../mfc/menus-and-resources-ole.md)   
 [メニューとリソース: メニューの結合](../mfc/menus-and-resources-menu-merging.md)

