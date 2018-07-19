---
title: 'TN025: ドキュメント、表示、およびフレームの作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.creation
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97db14dcb8c0b8b5b71823cf39d6bf36f0d19f25
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956695"
---
# <a name="tn025-document-view-and-frame-creation"></a>テクニカル ノート 25: ドキュメント、ビュー、フレームの作成
> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 このノートでは、作成、ウィンドウ、ドキュメント、フレーム、およびビューの作成と所有権の問題について説明します。  
  
## <a name="winapp"></a>WinApp  
 1 つを使用する必要がある`CWinApp`システム内のオブジェクト。  
  
 静的に構築されのフレームワークの内部実装によって初期化`WinMain`です。 派生する必要があります`CWinApp`に有効な (例外: MFC 拡張 Dll にはできません、`CWinApp`インスタンス — で初期化が行われる`DllMain`代わりに)。  
  
 1 つ`CWinApp`オブジェクトをドキュメント テンプレートの一覧を所有している (、 `CPtrList`)。 アプリケーションごとに 1 つまたは複数のドキュメント テンプレートがあります。 ウィンドウは通常、リソース ファイル (つまり、文字列配列) からに読み込ま`CWinApp::InitInstance`です。  
  
```  
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```  
  
 1 つ`CWinApp`オブジェクトには、アプリケーション内のすべてのフレーム ウィンドウを所有しています。 アプリケーションのメイン フレーム ウィンドウに保存するか`CWinApp::m_pMainWnd`; 通常設定*m_pMainWnd*で、`InitInstance`実装が AppWizard でそれを行う場合。 シングル ドキュメント インターフェイス (SDI) に対してこれは 1 つ`CFrameWnd`のみドキュメント フレーム ウィンドウと同様に、アプリケーションのメイン フレーム ウィンドウとして機能します。 MDI フレームは、マルチ ドキュメント インターフェイス (MDI) (クラス`CMDIFrameWnd`) アプリケーションのメイン フレーム ウィンドウを含むすべての子として機能する`CFrameWnd`s。 クラスの各子ウィンドウは、 `CMDIChildWnd` (から派生した`CFrameWnd`) し、場合によっては多数のドキュメント フレーム ウィンドウのいずれかとして機能します。  
  
## <a name="doctemplates"></a>ウィンドウ  
 `CDocTemplate`作成者とドキュメントの管理者は、します。 作成したドキュメントが所有しています。 派生する必要はありません、アプリケーションでは、次に示すリソース ベースのアプローチを使用する場合`CDocTemplate`です。  
  
 SDI アプリケーションは、クラス`CSingleDocTemplate`の 1 つ開いているドキュメントを追跡します。 MDI アプリケーションは、クラス`CMultiDocTemplate`リストを保持 (、 `CPtrList`) そのテンプレートから作成されたすべての現在開いているドキュメントのです。 `CDocTemplate::AddDocument` および`CDocTemplate::RemoveDocument`を追加またはテンプレートからドキュメントを削除するため、仮想メンバー関数を提供します。 `CDocTemplate` フレンド`CDocument`プロテクト セットアップできるように`CDocument::m_pDocTemplate`バック ポインターの元のドキュメントを作成したドキュメント テンプレートにポイントします。  
  
 `CWinApp` 既定値を処理する`OnFileOpen`実装で、すべてのドキュメント テンプレートはさらにクエリを実行します。 実装には、既に開いているドキュメントを検索し、どの形式で新しいドキュメントを開くの決定が含まれています。  
  
 `CDocTemplate` ドキュメントおよびフレームの UI のバインドを管理します。  
  
 `CDocTemplate` 名前のないドキュメントの数のカウントを保持します。  
  
## <a name="cdocument"></a>CDocument  
 A`CDocument`によって所有されて、`CDocTemplate`です。  
  
 ドキュメントのビューを開く現在のリストがある (から派生した`CView`) ドキュメントを表示する (、 `CPtrList`)。  
  
 ドキュメントの作成/破棄しない、ビューがアタッチされている相互に作成した後。 文書が閉じているときに (つまり、を通じてファイル/終了)、接続されているすべてのビューは閉じられます。 (つまり、ウィンドウまたは Close) ドキュメントの最後のビューが閉じられたときに、ドキュメントは閉じられます。  
  
 `CDocument::AddView`、`RemoveView`インターフェイスは、ビューのリストを維持するために使用します。 `CDocument` フレンド`CView`セットアップできるように、`CView::m_pDocument`バック ポインター。  
  
## <a name="cframewnd"></a>CFrameWnd  
 A `CFrameWnd` (フレームとも呼ばれます) が MFC 1.0 と同様に、同じロールをようになりましたが、再生、`CFrameWnd`クラスが新しいクラスを派生することがなく、多くの場合に使用されるように設計されています。 派生クラス`CMDIFrameWnd`と`CMDIChildWnd`標準コマンドの多くは既に実装されても強化されています。  
  
 `CFrameWnd`のフレームのクライアント領域内の windows の作成を担当します。 通常、フレームのクライアント領域を埋める 1 つのメイン ウィンドウがあります。  
  
 MDI フレーム ウィンドウのクライアント領域はすべての MDI 子フレーム ウィンドウの親である MDICLIENT コントロールが入力されます。 SDI フレーム ウィンドウまたは MDI 子フレーム ウィンドウは、クライアント領域は通常で埋め、 `CView`-window オブジェクトを派生します。 場合`CSplitterWnd`、ビューのクライアント領域はで埋め、`CSplitterWnd`ウィンドウ オブジェクトおよび`CView`-派生ウィンドウ オブジェクト (各分割ウィンドウ枠の 1 つ) の子ウィンドウとして作成されます、`CSplitterWnd`です。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

