---
title: MFC アプリケーション アーキテクチャ クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1174a994f345f4b7733e82603b5a49ed8977651
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-application-architecture-classes"></a>MFC アプリケーション アーキテクチャ クラス
このカテゴリのクラスは、framework アプリケーションのアーキテクチャに貢献します。 ほとんどのアプリケーションに共通の機能を指定します。 アプリケーション固有の機能を追加するためにフレームワークに入力します。 通常、これを行うアーキテクチャ クラスから新しいクラスの派生とし、新しいメンバーの追加または既存のメンバー関数をオーバーライドします。  
  
 [アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)数種類の異なる方法でアプリケーション フレームワークを使用してすべてのアプリケーションを生成します。 SDI (シングル ドキュメント インターフェイス) と MDI (マルチ ドキュメント インターフェイス) アプリケーション最大限活用ドキュメント/ビュー アーキテクチャと呼ばれる framework の一部です。 その他の種類のダイアログ ベースのアプリケーションで、フォーム ベースのアプリケーションでは、Dll などのアプリケーションでは、ドキュメント/ビュー アーキテクチャの機能の一部のみを使用します。  
  
 ドキュメント/ビュー アプリケーションは、ドキュメント、ビュー、およびフレーム ウィンドウの 1 つ以上のセットを含んでいます。 ドキュメント テンプレート オブジェクトには、各ドキュメント/ビュー/フレーム セットについては、クラスが関連付けられます。  
  
 MFC アプリケーションでのドキュメント/ビュー アーキテクチャを使用する必要はありません、さまざまな利点があります。 印刷と印刷プレビューはサポートされて、MFC OLE コンテナーとサーバーのサポートはドキュメント/ビュー アーキテクチャに基づきます。  
  
 すべての MFC アプリケーションには、少なくとも 2 つのオブジェクトがある: アプリケーション オブジェクトから派生した[CWinApp](../mfc/reference/cwinapp-class.md)、やある種のメイン ウィンドウのオブジェクトから (多くの場合、間接的に) 派生[CWnd](../mfc/reference/cwnd-class.md)です。 (メイン ウィンドウがから派生するほとんどの場合、 [CFrameWnd](../mfc/reference/cframewnd-class.md)、 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)、または[CDialog](../mfc/reference/cdialog-class.md)から派生する`CWnd`)。  
  
 ドキュメント/ビュー アーキテクチャを使用するアプリケーションでは、追加のオブジェクトを含んでいます。 プリンシパルのオブジェクトは次のとおりです。  
  
-   クラスから派生したアプリケーション オブジェクト[CWinApp](../mfc/reference/cwinapp-class.md)する前に説明したように、します。  
  
-   1 つまたは複数のドキュメント クラスのオブジェクト クラスから派生した[CDocument](../mfc/reference/cdocument-class.md)です。 ドキュメント クラスのオブジェクトは、ビューで操作されるデータの内部表現を担当します。 データ ファイルに関連付けられている必要があります。  
  
-   クラスから派生した 1 つまたは複数のビュー オブジェクト[CView](../mfc/reference/cview-class.md)です。 各ビューは、ドキュメントにアタッチされ、フレーム ウィンドウに関連付けられているされるウィンドウです。 ビューは、ドキュメント クラスのオブジェクトに含まれているデータの操作を表示します。  
  
 ドキュメント/ビュー アプリケーションでは、フレーム ウィンドウも含まれます (から派生した[CFrameWnd](../mfc/reference/cframewnd-class.md)) ドキュメント テンプレートと (から派生した[CDocTemplate](../mfc/reference/cdoctemplate-class.md))。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../mfc/class-library-overview.md)

