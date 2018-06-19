---
title: ドキュメント/ビュー アーキテクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c9554af9443bbd6a6394789343294630104c96f1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350056"
---
# <a name="documentview-architecture"></a>ドキュメント/ビュー アーキテクチャ
既定では、MFC アプリケーション ウィザードは、アプリケーションのスケルトンをドキュメント クラスとビュー クラスを作成します。 MFC には、これら 2 つのクラスにデータの管理が分離されます。 ドキュメントは、データを格納およびデータ印刷の管理および、データの複数のビューの更新を調整します。 ビューは、データを表示し、選択や編集でのユーザー操作を管理します。  
  
 このモデルでは、MFC のドキュメント オブジェクトは読み取りし、永続的ストレージにデータを書き込みます。 (データベースなど) が存在する限り、ドキュメントは、データにインターフェイスを提供も可能性があります。 個別のビュー オブジェクトは、ユーザー選択ウィンドウ内のデータを表示およびデータの編集からデータの表示を管理します。 ビューは、ドキュメントからデータを表示を取得し、データ変更の文書に通信します。  
  
 オーバーライドしたり、ドキュメント/ビューの分離を無視することが簡単に、中にほとんどの場合は、このモデルに準拠する理由があります。 最良の 1 つは、同じドキュメント、スプレッドシート、グラフ ビューの両方などの複数のビューが必要なときです。 ドキュメント/ビュー モデルには、個別のビュー オブジェクトが共通のコードをドキュメントにすべてのビューに (、計算エンジンなど) を配置するときに、データの各ビューを表すことができます。 ドキュメントは、データが変更されるたびに、すべてのビューを更新するタスクも受け取ります。  
  
 MFC ドキュメント/ビュー アーキテクチャでは、複数のビュー、複数のドキュメント タイプ、分割ウィンドウ、およびその他のユーザー インターフェイスの重要な機能をサポートするために簡単です。  
  
 両方に、ユーザーとプログラマが、表示されている MFC フレームワークの部分は、ドキュメントとビューです。 フレームワークとアプリケーションの開発作業のほとんどは、ドキュメントとビュー クラスの記述に移動します。 この記事ファミリについて説明します。  
  
-   ドキュメント、ビュー、およびそれらの相互作用 framework での目的。  
  
-   必要なことにそれらを実装します。  
  
 ドキュメント/ビューの中心となる 4 つのキー クラスがあります。  
  
 [CDocument](../mfc/reference/cdocument-class.md) (または[COleDocument](../mfc/reference/coledocument-class.md)) クラスを格納またはデータをプログラムの制御に使用されるオブジェクトをサポートします。 プログラマが定義するドキュメント クラスの基本機能を提供します。 ドキュメントでは、ユーザーが通常ファイル メニューの 開く コマンドでが開きますおよび ファイル メニューの 保存 コマンドで保存されるデータの単位を表します。  
  
 [CView](../mfc/reference/cview-class.md) (またはその派生クラスのいずれか) プログラマが定義するビュークラスの基本機能を提供します。 ビューがドキュメントにアタッチし、ドキュメントとユーザー間の媒介として機能します。 ビューは、画面上のドキュメントのイメージを表示しますし、ユーザー入力をドキュメントに操作として解釈します。 ビューでは、印刷と印刷プレビューの画像も表示します。  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md) (またはそのバリエーションの 1 つ) が、ドキュメントの 1 つまたは複数のビューを囲むフレームを提供するオブジェクトをサポートします。  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) (または[関数](../mfc/reference/csingledoctemplate-class.md)または[CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md))、指定された型の 1 つまたは複数の既存のドキュメントを調整し、適切な作成を管理できるオブジェクトをサポートしていますドキュメント、ビュー、およびその型のフレーム ウィンドウのオブジェクト。  
  
 次の図は、ドキュメントとそのビューの関係を示しています。  
  
 ![ビューが表示されているドキュメントの一部である](../mfc/media/vc379n1.gif "vc379n1")  
ドキュメントとビュー  
  
 クラス ライブラリのドキュメント/ビューの実装では、データ自体の表示とデータ上でユーザー操作の間を区切ります。 データに対するすべての変更は、ドキュメント クラスを通じて管理されます。 ビューにアクセスしてデータを更新するには、このインターフェイスを呼び出します。  
  
 ドキュメント、関連付けられたビュー、および、ビュー、フレーム ウィンドウは、ドキュメント テンプレートによって作成されます。 ドキュメント テンプレートは、作成して 1 つのドキュメントの種類のすべてのドキュメントの管理を担当します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ドキュメント/ビュー アーキテクチャの全体像](../mfc/a-portrait-of-the-document-view-architecture.md)  
  
-   [ドキュメント/ビュー アーキテクチャの利点](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [アプリケーション ウィザードで作成したドキュメントとビュー クラス](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)  
  
-   [ドキュメント/ビュー アーキテクチャの代替手段](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [シングル ドキュメントへのマルチ ビューの追加](../mfc/adding-multiple-views-to-a-single-document.md)  
  
-   [ドキュメントの使い方](../mfc/using-documents.md)  
  
-   [ビューの使い方](../mfc/using-views.md)  
  
-   [複数のドキュメント タイプ、ビュー、フレーム ウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
-   [ドキュメントとビュー クラスを独自の追加を初期化します。](../mfc/creating-new-documents-windows-and-views.md)  
  
-   [ドキュメントとビューを用いたデータベース クラス](../data/mfc-using-database-classes-with-documents-and-views.md)  
  
-   [ドキュメントとビューを用いないデータベース クラスの使用](../data/mfc-using-database-classes-without-documents-and-views.md)  
  
-   [サンプル](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス要素](../mfc/user-interface-elements-mfc.md)   
 [Windows](../mfc/windows.md)   
 [フレーム ウィンドウ](../mfc/frame-windows.md)   
 [ドキュメント テンプレートとドキュメント/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [ドキュメント/ビューの作成](../mfc/document-view-creation.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../mfc/creating-new-documents-windows-and-views.md)

