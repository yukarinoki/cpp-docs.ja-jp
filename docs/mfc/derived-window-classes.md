---
title: ウィンドウ クラスを派生 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eddc6c59190856d09eae75c6f4314c902740092f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="derived-window-classes"></a>ウィンドウ クラスの派生
Windows から直接を作成する[CWnd](../mfc/reference/cwnd-class.md)から新しいウィンドウ クラスを派生または`CWnd`です。 これは、独自のカスタム ウィンドウを作成する一般的な方法です。 ただし、フレームワーク プログラムで使用されるほとんどのウィンドウは、MFC に用意されている、`CWnd` から派生するフレーム ウィンドウ クラスのいずれかから作成されます。  
  
## <a name="frame-window-classes"></a>フレーム ウィンドウ クラス  
 [CFrameWnd](../mfc/reference/cframewnd-class.md)  
 単一ドキュメントとそのビューを囲む SDI フレーム ウィンドウに使用されます。 フレーム ウィンドウは、アプリケーションのメイン フレーム ウィンドウであり、現在のドキュメントのフレーム ウィンドウでもあります。  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)  
 MDI アプリケーションのメイン フレーム ウィンドウとして使用されます。 メイン フレーム ウィンドウは、すべての MDI ドキュメント ウィンドウのコンテナーであり、そのメニュー バーを MDI ドキュメント ウィンドウと共有します。 MDI フレーム ウィンドウはデスクトップに表示される最上位ウィンドウです。  
  
 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)  
 MDI メイン フレーム ウィンドウで開かれる個々のドキュメントに使用されます。 各ドキュメントとそのビューは、MDI メイン フレーム ウィンドウに含まれている MDI 子フレーム ウィンドウの中に収まります。 MDI 子ウィンドウの外観は一般的なフレーム ウィンドウと非常に似ていますが、デスクトップ上に表示されるのではなく、MDI フレーム ウィンドウの内部に格納されます。 ただし、MDI 子ウィンドウには独自のメニュー バーがなく、それを含む MDI フレーム ウィンドウのメニュー バーを共有する必要があります。  
  
 詳細については、次を参照してください。[フレーム ウィンドウ](../mfc/frame-windows.md)します。  
  
## <a name="other-window-classes-derived-from-cwnd"></a>CWnd から派生するその他のウィンドウ クラス  
 フレーム ウィンドウに加え、次に示すその他のいくつかの主なウィンドウ カテゴリが `CWnd` から派生しています。  
  
 *ビュー*  
 ビューを作成するを使用して、 `CWnd`-派生クラス[CView](../mfc/reference/cview-class.md) (またはその派生クラスのいずれか)。 ビューはドキュメントにアタッチされ、ドキュメントとユーザーの仲介役として機能します。 ビューは、一般に SDI フレーム ウィンドウまたは MDI 子フレーム ウィンドウのクライアント領域 (または、ツール バーやステータス バーで占有されていないクライアント領域の部分) を占める子ウィンドウです (MDI 子ウィンドウではありません)。  
  
 *ダイアログ ボックス*  
 ダイアログ ボックスを使用して作成、 `CWnd`-派生クラス[CDialog](../mfc/reference/cdialog-class.md)です。  
  
 *フォーム*  
 ダイアログ ボックスのダイアログ テンプレート リソースに基づくフォーム ビューを作成するクラスを使用して[CFormView](../mfc/reference/cformview-class.md)、 [CRecordView](../mfc/reference/crecordview-class.md)、または[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)です。  
  
 *コントロール*  
 ボタン、リスト ボックス、コンボ ボックスなどのコントロールは、`CWnd` から派生する他のクラスを使用して作成されます。 参照してください[制御トピック](../mfc/controls-mfc.md)です。  
  
 *コントロール バー*  
 コントロールを含む子ウィンドウ。 たとえば、ツール バーやステータス バーが該当します。 参照してください[コントロール バー](../mfc/control-bars.md)です。  
  
## <a name="window-class-hierarchy"></a>ウィンドウ クラスの階層構造  
 参照してください、 [MFC 階層図](../mfc/hierarchy-chart.md)で、 *『 MFC リファレンス*です。 については、ビュー[ドキュメント/ビュー アーキテクチャ](../mfc/document-view-architecture.md)です。 については、ダイアログ ボックス[ ダイアログ ボックス](../mfc/dialog-boxes.md)です。  
  
## <a name="creating-your-own-special-purpose-window-classes"></a>独自の特殊用途ウィンドウ クラスの作成  
 クラス ライブラリに用意されているウィンドウ クラスに加えて、特殊用途の子ウィンドウが必要な場合があります。 このようなウィンドウを作成するには、独自に作成[CWnd](../mfc/reference/cwnd-class.md)-クラスを派生し、フレームまたはビューの子ウィンドウを作成します。 フレームワークは、ドキュメントのフレーム ウィンドウのクライアント領域の範囲を管理することに注意してください。 クライアント領域のほとんどはビューによって管理されますが、コントロール バーや独自のカスタム ウィンドウなど、他のウィンドウは、ビューと領域を共有する場合があります。 クラスのメカニズムと対話する必要があります[CView](../mfc/reference/cview-class.md)と[CControlBar](../mfc/reference/ccontrolbar-class.md)のフレーム ウィンドウのクライアント領域内の子ウィンドウの位置を決定します。  
  
 [ウィンドウの作成](../mfc/creating-windows.md)ウィンドウ オブジェクトと、windows の管理の作成について説明します。  
  
## <a name="see-also"></a>関連項目  
 [Window オブジェクト](../mfc/window-objects.md)

