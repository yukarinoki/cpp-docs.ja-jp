---
description: '詳細については、テクニカルノート 25: ドキュメント、ビュー、フレームの作成に関するページを参照してください。'
title: 'テクニカル ノート 25: ドキュメント、ビュー、フレームの作成'
ms.date: 11/04/2016
f1_keywords:
- vc.creation
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
ms.openlocfilehash: 034c3670df57de03cf7db8f713937f3d433fbb56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215743"
---
# <a name="tn025-document-view-and-frame-creation"></a>テクニカル ノート 25: ドキュメント、ビュー、フレームの作成

> [!NOTE]
> 次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。 結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。 最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。

このメモでは、WinApps、DocTemplates、ドキュメント、フレーム、およびビューの作成と所有権に関する問題について説明します。

## <a name="winapp"></a>WinApp

システム内に1つのオブジェクトがあり `CWinApp` ます。

このメソッドは、のフレームワークの内部実装によって静的に構築および初期化され `WinMain` ます。 役に立つものを実行するには、から派生する必要があります `CWinApp` (例外: MFC 拡張 dll にインスタンスを設定しないでください。 `CWinApp` 代わりに、初期化が行われ `DllMain` ます)。

1つのオブジェクトは、 `CWinApp` ドキュメントテンプレート (a) のリストを所有し `CPtrList` ます。 アプリケーションごとに1つ以上のドキュメントテンプレートがあります。 DocTemplates は、通常、のリソースファイル (つまり文字列配列) から読み込まれ `CWinApp::InitInstance` ます。

```
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```

1つのオブジェクトは、 `CWinApp` アプリケーション内のすべてのフレームウィンドウを所有します。 アプリケーションのメインフレームウィンドウはに格納されている必要があります `CWinApp::m_pMainWnd` 。通常、  AppWizard で `InitInstance` 実行しない場合は、実装に m_pMainWnd を設定します。 シングルドキュメントインターフェイス (SDI) の場合、これは `CFrameWnd` メインアプリケーションフレームウィンドウとして機能し、唯一のドキュメントフレームウィンドウとして機能するものです。 マルチドキュメントインターフェイス (MDI) の場合、これは `CMDIFrameWnd` 、すべての子を含むメインアプリケーションフレームウィンドウとして機能する MDI-Frame (クラス) です `CFrameWnd` 。 各子ウィンドウは `CMDIChildWnd` (から派生した) クラスであり `CFrameWnd` 、多くのドキュメントフレームウィンドウの1つとして機能します。

## <a name="doctemplates"></a>DocTemplates

は、 `CDocTemplate` ドキュメントの作成者と管理者です。 作成したドキュメントを所有します。 アプリケーションで次に説明するリソースベースの方法を使用する場合、から派生する必要はありません `CDocTemplate` 。

SDI アプリケーションの場合、クラスは `CSingleDocTemplate` 1 つの開いているドキュメントを追跡します。 MDI アプリケーションの場合、クラスは、 `CMultiDocTemplate` `CPtrList` そのテンプレートから作成された現在開いているすべてのドキュメントのリスト () を保持します。 `CDocTemplate::AddDocument` と `CDocTemplate::RemoveDocument` には、テンプレートのドキュメントを追加または削除するための仮想メンバー関数が用意されています。 `CDocTemplate` はのフレンドである `CDocument` ため、ドキュメントを作成し `CDocument::m_pDocTemplate` たドキュメントテンプレートを指すように保護された戻るポインターを設定できます。

`CWinApp` 既定の `OnFileOpen` 実装を処理します。これにより、すべてのドキュメントテンプレートに対してクエリが実行されます。 実装には、既に開いているドキュメントの検索と、新しいドキュメントを開く形式の決定が含まれます。

`CDocTemplate` ドキュメントおよびフレームの UI バインドを管理します。

`CDocTemplate` 名前のないドキュメントの数を保持します。

## <a name="cdocument"></a>CDocument

は `CDocument` 、によって所有されて `CDocTemplate` います。

ドキュメントには、ドキュメントを表示している (から派生した) 現在開いているビューの一覧があり `CView` `CPtrList` ます。

ドキュメントでは、ビューの作成と破棄は行われませんが、作成後に相互にアタッチされます。 ドキュメントが閉じられたとき (つまり、ファイル/閉じるを介して)、添付されているすべてのビューが閉じられます。 ドキュメントの最後のビューが閉じられたとき (つまり、ウィンドウ/閉じる)、ドキュメントは閉じられます。

`CDocument::AddView` `RemoveView` インターフェイスは、ビューリストを維持するために使用されます。 `CDocument` はのフレンドである `CView` ため、戻るポインターを設定でき `CView::m_pDocument` ます。

## <a name="cframewnd"></a>CFrameWnd

A `CFrameWnd` (フレームとも呼ばれます) は、MFC 1.0 と同じ役割を果たしますが、 `CFrameWnd` クラスは多くの場合、新しいクラスを派生させずに使用できるように設計されています。 派生クラス `CMDIFrameWnd` と `CMDIChildWnd` も強化されているため、多くの標準コマンドが既に実装されています。

`CFrameWnd`は、フレームのクライアント領域にウィンドウを作成する役割を担います。 通常、フレームのクライアント領域を埋めるためのメインウィンドウが1つあります。

MDI-Frame ウィンドウの場合、クライアント領域には、すべての MDI-Child フレームウィンドウの親である MDICLIENT コントロールが入力されます。 SDI-Frame ウィンドウまたは MDI-Child フレームウィンドウの場合、クライアント領域には通常、 `CView` から派生したウィンドウオブジェクトが格納されます。 の場合 `CSplitterWnd` 、ビューのクライアント領域にウィンドウオブジェクトが設定され、 `CSplitterWnd` `CView` (分割ペインごとに1つ) の派生ウィンドウオブジェクトがの子ウィンドウとして作成され `CSplitterWnd` ます。

## <a name="see-also"></a>関連項目

[番号別テクニカルノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカルノート](../mfc/technical-notes-by-category.md)
