---
title: Windows 用のアプリケーションを作成するクラスを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa126f2772e1672a1484453fdffdd487b6c45959
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>クラスを使用した Windows アプリケーションの作成
まとめると、Microsoft Foundation Class (MFC) ライブラリのクラスには、「アプリケーション フレームワーク、」Windows オペレーティング システム用のアプリケーションをビルドするを構成します。 非常に一般的なレベルでは、フレームワークは、アプリケーションのスケルトンを定義し、スケルトンに配置可能な標準のユーザー インターフェイスの実装を提供します。 プログラマは、スケルトンの残りの部分を埋めるためには、アプリケーションに固有の作業です。 MFC アプリケーション ウィザードを使用して、詳細な情報のスターター アプリケーション ファイルを作成することによって簡単に開始を取得できます。 Microsoft Visual C リソース エディターをユーザー インターフェイス要素を視覚的に、デザイン コード、およびクラス ライブラリにそれらの要素を接続クラス ビューのコマンドを使用するには、アプリケーション固有のロジックを実装します。  
  
 3.0 以降、MFC フレームワークのバージョンでは、Win32 プラットフォームでは、Microsoft Windows 95 など以降では、プログラミングおよび Windows NT version 3.51 以降をサポートします。 マルチ スレッド MFC Win32 のサポートが含まれます。 バージョン 1.5 を使用*x* 16 ビットのプログラミングを行う必要がある場合。  
  
 この一連のトピックでは、アプリケーション フレームワークの大まかな概要を表示します。 アプリケーションとの作成方法を構成する主要なオブジェクトについても説明します。 次の記事で説明されているトピックでは、次のように示します。  
  
-   [フレームワーク](../mfc/framework-mfc.md)です。  
  
-   フレームワークと」の説明に従って、コードの間で分担[フレームワーク上に構築](../mfc/building-on-the-framework.md)です。  
  
-   [アプリケーション クラス](../mfc/cwinapp-the-application-class.md)、アプリケーション レベルの機能をカプセル化します。  
  
-   どの[ドキュメント テンプレート](../mfc/document-templates-and-the-document-view-creation-process.md)フレーム ウィンドウの作成し、ドキュメントと関連付けられたビューを管理します。  
  
-   クラス[CWnd](../mfc/window-objects.md)、すべてのウィンドウのルートの基本クラスです。  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md)ブラシ、ペンなどです。  
  
 フレームワークの他の部分は次のとおりです。  
  
-   [ウィンドウ オブジェクト: 概要](../mfc/window-objects.md)  
  
-   [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)  
  
-   [CObject、MFC でルート基本クラス](../mfc/using-cobject.md)  
  
-   [ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)  
  
-   [ダイアログ ボックス](../mfc/dialog-boxes.md)  
  
-   [コントロール](../mfc/controls-mfc.md)  
  
-   [コントロール バー](../mfc/control-bars.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [メモリ管理](../mfc/memory-management.md)  
  
     だけでなく、Windows オペレーティング システム用のアプリケーションの作成の利点を提供するので、MFC もはより簡単に具体的には OLE リンクと埋め込み技術を使用するアプリケーションを作成します。 できるアプリケーションを作成する OLE ビジュアル コンテナー、OLE ビジュアル編集サーバー、またはその両方を編集し、オートメーションを追加するには、他のアプリケーションのアプリケーションからオブジェクトを使用または兼ねることができるようにします。  
  
-   [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)  
  
     OLE コントロールの開発キット (CDK) がフレームワークの完全統合されています。 ここでは、mfc ActiveX コントロールの開発の概要を提供します。 (ActiveX コントロールが以前の OLE コントロールです。)  
  
-   [データベース プログラミング](../data/data-access-programming-mfc-atl.md)  
  
     MFC では、書き込みのデータ アクセスを簡単にするデータベース クラスの 2 つのセットも用意されてアプリケーションです。 ODBC データベース クラスを使用して、オープン データベース コネクティビティ (ODBC) ドライバーを使用するデータベースへの接続、テーブルからレコードを選択してレコード情報を表示する画面に表示されるフォームです。 データ アクセス オブジェクト (DAO) クラスを使用して、扱えるデータベース、Microsoft Jet データベース エンジンまたは ODBC データ ソースを含む、外部の (非 Jet) データ ソースを使用します。  
  
     さらに、MFC は完全に Unicode を使用するアプリケーションの作成を有効になっているとマルチバイト文字セット (MBCS)、具体的には 2 バイト文字セット (DBCS)。  
  
 MFC のドキュメントを一般的なガイドラインを参照してください。 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)

