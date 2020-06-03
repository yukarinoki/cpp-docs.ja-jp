---
title: 'テクニカル ノート 25: ドキュメント、ビュー、フレームの作成'
ms.date: 11/04/2016
f1_keywords:
- vc.creation
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
ms.openlocfilehash: 2fdabdcb1a87d4a5661348588d49303290c966ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370371"
---
# <a name="tn025-document-view-and-frame-creation"></a>テクニカル ノート 25: ドキュメント、ビュー、フレームの作成

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このノートでは、WinApps、DocTemplates、ドキュメント、フレーム、ビューの作成と所有権の問題について説明します。

## <a name="winapp"></a>ウィンアプリ

システムには`CWinApp`1 つのオブジェクトがあります。

これは、フレームワークの内部実装によって静的に構築され、初期化されます`WinMain`。 有用な処理を`CWinApp`行うには、派生元にする必要があります (例外: MFC`CWinApp`拡張 DLL には`DllMain`インスタンスを持つべきではありません。

1`CWinApp`つのオブジェクトは、ドキュメント テンプレートのリスト`CPtrList`を所有しています ( a ) 。 アプリケーションごとに 1 つ以上のドキュメント テンプレートがあります。 DocTemplates は通常、 のリソース ファイル (文字列配列) から`CWinApp::InitInstance`読み込まれます。

```
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```

1`CWinApp`つのオブジェクトは、アプリケーション内のすべてのフレーム ウィンドウを所有します。 アプリケーションのメイン フレーム ウィンドウは に格納`CWinApp::m_pMainWnd`する必要があります。通常は、AppWizard`InitInstance`に対してm_pMainWndを実行させなければ、*実装で設定*します。 シングル ドキュメント インターフェイス (SDI)`CFrameWnd`の場合、これは、メイン アプリケーション フレーム ウィンドウと、唯一のドキュメント フレーム ウィンドウとして機能する 1 つです。 マルチ ドキュメント インターフェイス (MDI) の場合、これはすべての子`CMDIFrameWnd``CFrameWnd`を含むメイン アプリケーション フレーム ウィンドウとして機能する MDI フレーム (クラス) です。 各子ウィンドウはクラス`CMDIChildWnd`( から`CFrameWnd`派生 ) であり、多くのドキュメント フレーム ウィンドウの 1 つとして機能します。

## <a name="doctemplates"></a>ドキュメントテンプレート

は`CDocTemplate`、ドキュメントの作成者とマネージャーです。 作成するドキュメントを所有します。 アプリケーションで、以下に説明するリソース ベースのアプローチを使用する場合は、`CDocTemplate`から派生する必要はありません。

SDI アプリケーションの場合、クラス`CSingleDocTemplate`は開いているドキュメントを 1 つ追跡します。 MDI アプリケーションの場合、クラス`CMultiDocTemplate`は、そのテンプレートから`CPtrList`作成されたすべての現在開いているドキュメントのリスト (a) を保持します。 `CDocTemplate::AddDocument`テンプレート`CDocTemplate::RemoveDocument`に対してドキュメントを追加または削除するための仮想メンバー関数を提供します。 `CDocTemplate`はフレンド`CDocument`なので、保護された`CDocument::m_pDocTemplate`バックポインタを設定して、ドキュメントを作成したドキュメントテンプレートを元に戻すことができます。

`CWinApp`は、すべての`OnFileOpen`ドキュメント テンプレートを照会する既定の実装を処理します。 実装には、既に開いているドキュメントを検索し、新しいドキュメントを開く形式を決定することが含まれます。

`CDocTemplate`は、ドキュメントとフレームの UI バインディングを管理します。

`CDocTemplate`は、名前のないドキュメントの数を保持します。

## <a name="cdocument"></a>CDocument

A`CDocument`は によって`CDocTemplate`所有されます。

ドキュメントには、現在開いているビュー ( から`CView`派生した ) のリストがあり`CPtrList`、ドキュメントを表示しています ( a ) 。

ドキュメントはビューを作成/破棄しませんが、作成後に互いに関連付けられます。 ドキュメントが閉じられると (ファイル/閉じる)、添付されたビューはすべて閉じられます。 ドキュメントの最後のビューが閉じられると (つまり、ウィンドウ/閉じる)、ドキュメントは閉じられます。

インターフェイス`CDocument::AddView``RemoveView`は、ビュー リストを維持するために使用されます。 `CDocument`の友人`CView`なので、戻るポインタを`CView::m_pDocument`設定できます。

## <a name="cframewnd"></a>CFrameWnd

(`CFrameWnd`フレームとも呼ばれます) は MFC 1.0 と同じ役割を果た`CFrameWnd`しますが、現在では新しいクラスを派生させずに、多くの場合に使用するように設計されています。 派生クラス`CMDIFrameWnd`と強化`CMDIChildWnd`されているので、多くの標準コマンドが既に実装されています。

`CFrameWnd`は、フレームのクライアント領域にウィンドウを作成します。 通常、フレームのクライアント領域に 1 つのメイン ウィンドウが埋め込まれます。

MDI フレーム ウィンドウの場合、クライアント領域には、すべての MDI 子フレーム ウィンドウの親となる MDICLIENT コントロールが格納されます。 SDI フレーム ウィンドウまたは MDI 子フレーム ウィンドウの場合、クライアント領域は通常、派生`CView`ウィンドウ オブジェクトで埋められます。 の場合`CSplitterWnd`、ビューのクライアント領域には`CSplitterWnd`ウィンドウ オブジェクトが格納され`CView`、-derived window オブジェクト (分割ペインごとに 1 つ) が子ウィンドウとして作成`CSplitterWnd`されます。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
