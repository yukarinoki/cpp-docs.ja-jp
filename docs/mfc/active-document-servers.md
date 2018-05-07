---
title: Active ドキュメント サーバー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], servers
- servers [MFC], active document
- active document servers [MFC]
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7cc207541bda3084db6bc8ab3896f46761587169
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="active-document-servers"></a>Active ドキュメント サーバー
その他のアプリケーションの種類のホスト文書を Word、Excel、または PowerPoint などの active ドキュメント サーバーには、アクティブなドキュメントが呼び出されます。 Ole の埋め込みオブジェクトが別のドキュメントのページ内で単に表示されます)、Active ドキュメントは、完全なインターフェイスとそれを作成したサーバー アプリケーションのネイティブ機能を完了します。 ユーザーがドキュメントを作成できる、お気に入り (アクティブなドキュメントが有効になっている場合)、アプリケーションの全機能を使用してまだ扱うことができます、結果として得られるプロジェクトを 1 つのエンティティとして。  
  
 アクティブなドキュメントでは、複数のページを含むことができ、インプレース アクティブでは常にいます。 アクティブ ドキュメントとそのメニューをマージ、ユーザー インターフェイスの一部の制御、**ファイル**と**ヘルプ**コンテナーのメニュー。 コンテナーのすべての編集領域を占有し、ビュー、およびプリンターのページ (余白やページ フッター、) のレイアウトを制御します。  
  
 MFC では、active ドキュメント サーバーにドキュメント/ビューのインターフェイス、コマンドのディスパッチ マップ、印刷、メニュー管理、およびレジストリの管理を実装します。 特定のプログラミング要件については[アクティブ ドキュメント](../mfc/active-documents.md)です。  
  
 MFC では、アクティブなドキュメントに、[関数](../mfc/reference/cdocobjectserver-class.md)から派生したクラス[CCmdTarget](../mfc/reference/ccmdtarget-class.md)、および[CDocObjectServerItem](../mfc/reference/cdocobjectserveritem-class.md)から派生した[COleServerItem](../mfc/reference/coleserveritem-class.md)です。 MFC での active ドキュメント コンテナーをサポートしています、[関数](../mfc/reference/coledocobjectitem-class.md)から派生したクラス[COleClientItem](../mfc/reference/coleclientitem-class.md)です。  
  
 `CDocObjectServer` active ドキュメント インターフェイスをマップを初期化およびアクティブ ドキュメントをライセンス認証します。 MFC には、アクティブなドキュメント内のコマンド ルーティングを処理するマクロも用意されています。 アクティブ ドキュメントをアプリケーションで使用するには、StdAfx.h ファイルに AfxDocOb.h を含めます。  
  
 正規の MFC サーバー フック独自`COleServerItem`-クラスを派生します。 MFC アプリケーション ウィザードは、選択した場合のこのクラスを生成、**ミニ サーバー**または**フル サーバー**アプリケーション サーバーに複合ドキュメント サポートを提供する チェック ボックスです。 選択する場合、 **Active ドキュメント サーバー**  チェック ボックスは、MFC アプリケーション ウィザードがから派生したクラスに生成されます。`CDocObjectServerItem`代わりにします。  
  
 `COleDocObjectItem`クラスになる active ドキュメント コンテナー OLE コンテナーを使用できます。 MFC アプリケーション ウィザードを使用してを選択して、active ドキュメント コンテナーを作成することができます、 **Active ドキュメント コンテナー** MFC アプリケーション ウィザードの [複合ドキュメント サポート] ページでチェック ボックスをオンします。 詳細については、次を参照してください。 [Active ドキュメント コンテナー アプリケーションの作成](../mfc/creating-an-active-document-container-application.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Active ドキュメント コンテインメント](../mfc/active-document-containment.md)

