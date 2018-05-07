---
title: MFC で作成したウィンドウのスタイルを変更する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- window styles [MFC]
- WS_OVERLAPPEDWINDOW macro [MFC]
- single document interface (SDI), changing window attributes
- MDI [MFC], window styles
- windows [MFC], MFC
- child windows [MFC], styles
- MFC, windows
- CFrameWnd class [MFC], window styles
- CREATESTRUCT macro [MFC]
- CMDIChildWnd class [MFC], changing window styles
- multidocument interface style
- PreCreateWindow method [MFC], window styles
- single document interface (SDI), style
- default window style
- defaults [MFC], window style
- PreCreateWindow method [MFC], changing window styles
- CMainFrame class [MFC]
- styles [MFC], windows
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34ea35bd43e2bf4e96cbc1552ff169789c1068a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC で作成したウィンドウのスタイル変更
そのバージョンので、`WinMain`関数、MFC では、いくつかの標準のウィンドウ クラスを登録します。 通常、MFC を編集していないため`WinMain`、いる関数を使用する MFC の既定のウィンドウ スタイルを変更する機会はありません。 この記事では、既存のアプリケーションでこのような登録済みのウィンドウ クラスのスタイルを変更する方法について説明します。  
  
##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> 新しい MFC アプリケーションでスタイルを変更します。  
 2.0 またはそれ以降の Visual C を使用している場合は、アプリケーションを作成するときに、アプリケーションのウィザードで既定のウィンドウ スタイルを変更できます。 アプリケーション ウィザードのユーザー インターフェイス機能 ページで、メイン フレーム ウィンドウおよび MDI 子ウィンドウのスタイルを変更できます。 ウィンドウのどちらの種類では、そのフレームの太さ (シック (thick) またはシン) を指定できますと、次のいずれか。  
  
-   かどうか、ウィンドウには、最小または最大化のコントロールがあります。  
  
-   かどうか、ウィンドウが表示されます、最初に最小化されている最大化、またはどちらもします。  
  
 メイン フレーム ウィンドウのウィンドウにシステム メニューがあるかどうかも指定できます。 MDI 子ウィンドウのウィンドウが分割ウィンドウをサポートするかどうかを指定できます。  
  
##  <a name="_core_changing_styles_in_an_existing_application"></a> 既存のアプリケーションでスタイルを変更します。  
 既存のアプリケーションでウィンドウの属性を変更する場合は代わりにこの記事の残りの指示に従います。  
  
 アプリケーションのウィザードで作成した framework アプリケーションで使用される既定のウィンドウの属性を変更する上書きウィンドウの[PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)仮想メンバー関数。 `PreCreateWindow` アプリケーションは、通常によって内部的に管理、作成プロセスにアクセスする、 [CDocTemplate](../mfc/reference/cdoctemplate-class.md)クラスです。 フレームワークによって`PreCreateWindow`ウィンドウを作成する前にします。 変更することによって、 [CREATESTRUCT](../mfc/reference/createstruct-structure.md)に構造体が渡される`PreCreateWindow`、アプリケーション ウィンドウを作成するための属性を変更できます。 たとえば、ウィンドウがキャプションを使用しないことを確認するには、するには、次のビットごとの演算を使用します。  
  
 [!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]  
  
 [CTRLBARS](../visual-cpp-samples.md)サンプル アプリケーションは、ウィンドウの属性を変更するためには、この手法を示します。 アプリケーションの変更に応じて`PreCreateWindow`関数の基本クラス実装を呼び出す必要があります。  
  
 次の説明は、SDI の場合、 [MDI ケース](#_core_the_mdi_case)です。  
  
##  <a name="_core_the_sdi_case"></a> SDI ケース  
 シングル ドキュメント インターフェイス (SDI) アプリケーション、フレームワークの既定のウィンドウ スタイルの組み合わせ、 **WS_OVERLAPPEDWINDOW**と**FWS_ADDTOTITLE**スタイル。 **FWS_ADDTOTITLE**ウィンドウのキャプションにドキュメントのタイトルを追加するためにフレームワークに指示する MFC 固有のスタイルします。 中の SDI アプリケーション ウィンドウの属性を変更するには、上書き、`PreCreateWindow`から派生したクラスで関数`CFrameWnd`(するアプリケーション ウィザード名`CMainFrame`)。 例えば:  
  
 [!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]  
  
 このコードでは、最小化ボタンやサイズ変更境界のないメイン フレーム ウィンドウを作成します。 ウィンドウは画面に最初に中央揃えされます。  
  
##  <a name="_core_the_mdi_case"></a> MDI の場合  
 マルチ ドキュメント インターフェイス (MDI) アプリケーションの子ウィンドウのウィンドウ スタイルを変更するには、少しの作業が必要です。 既定では、アプリケーションのウィザードで作成した MDI アプリケーションは既定値を使用して[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) MFC で定義されたクラスです。 MDI 子ウィンドウのウィンドウ スタイルを変更するから新しいクラスを派生する必要があります`CMDIChildWnd`とすべての参照を置換`CMDIChildWnd`プロジェクトで、新しいクラスへの参照を使用します。 ほとんどの場合、のみへの参照を`CMDIChildWnd`アプリケーション内にある、アプリケーションの`InitInstance`メンバー関数。  
  
 MDI アプリケーションで使用される既定のウィンドウ スタイルがの組み合わせ、 **WS_CHILD**、 **WS_OVERLAPPEDWINDOW**、および**FWS_ADDTOTITLE**スタイル。 MDI アプリケーションの子ウィンドウのウィンドウの属性を変更するには、上書き、 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)から派生したクラスで関数`CMDIChildWnd`です。 例えば:  
  
 [!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]  
  
 このコードは、最大化ボタンせず windows MDI 子フォームを作成します。  
  
### <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ウィンドウ スタイル](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
-   [フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)  
  
-   [ウィンドウ スタイル](http://msdn.microsoft.com/library/windows/desktop/ms632600)  
  
## <a name="see-also"></a>関連項目  
 [フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)

