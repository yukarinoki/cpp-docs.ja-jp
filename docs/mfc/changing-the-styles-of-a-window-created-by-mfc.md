---
title: MFC で作成したウィンドウのスタイル変更
ms.date: 11/04/2016
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
ms.openlocfilehash: c8a3a5d9b8b007887dfb31f7459c0269377b38fd
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294162"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC で作成したウィンドウのスタイル変更

そのバージョンので、`WinMain`関数、MFC では、いくつかの標準のウィンドウ クラスを登録できます。 MFC の通常編集しないので、 `WinMain`、ある関数を使用する MFC の既定のウィンドウ スタイルを変更する機会はありません。 この記事では、既存のアプリケーションでこのような登録済みのウィンドウ クラスのスタイルを変更する方法について説明します。

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> 新しい MFC アプリケーションでスタイルを変更します。

2.0 以降の Visual C を使用している場合は、アプリケーションを作成するときにアプリケーション ウィザードで既定のウィンドウ スタイルを変更できます。 アプリケーション ウィザードのユーザー インターフェイス機能 ページで、メイン フレーム ウィンドウと MDI 子ウィンドウのスタイルを変更できます。 ウィンドウのどちらの種類では、そのフレームの太さ (シックまたはシン) を指定でき、次のいずれか。

- かどうか、ウィンドウには、最小化または最大化のコントロールがあります。

- かどうか、ウィンドウが表示されます、最初に最小化されている最大化、またはどちらもします。

メイン フレーム ウィンドウのウィンドウのシステム メニューにあるかどうかを指定することもできます。 MDI 子ウィンドウ、ウィンドウが分割ペインをサポートするかどうかを指定できます。

##  <a name="_core_changing_styles_in_an_existing_application"></a> 既存のアプリケーションでスタイルを変更します。

既存のアプリケーションでウィンドウの属性を変更する場合は代わりにこの記事の残りの指示に従ってください。

アプリケーション ウィザードで作成したフレームワーク アプリケーションで使用される既定のウィンドウ属性を変更するには、ウィンドウをオーバーライド[PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)仮想メンバー関数。 `PreCreateWindow` により、アプリケーションは通常によって内部的に管理、作成プロセスにアクセスする、 [CDocTemplate](../mfc/reference/cdoctemplate-class.md)クラス。 Framework 呼び出し`PreCreateWindow`ウィンドウを作成する前にします。 変更することによって、 [CREATESTRUCT](/windows/desktop/api/winuser/ns-winuser-tagcreatestructa)に渡された構造体`PreCreateWindow`アプリケーションは、ウィンドウを作成するために使用する属性を変更できます。 たとえば、ウィンドウがキャプションを使用しないことを確認するには、するには、次のビットごとの演算を使用します。

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../visual-cpp-samples.md)サンプル アプリケーションは、ウィンドウの属性を変更するためには、この手法を示します。 アプリケーションの変更に応じて`PreCreateWindow`関数の基本クラス実装を呼び出す必要があります。

次の説明は、SDI の場合、 [MDI ケース](#_core_the_mdi_case)します。

##  <a name="_core_the_sdi_case"></a> SDI ケース

シングル ドキュメント インターフェイス (SDI) アプリケーション、フレームワークの既定のウィンドウ スタイルがの組み合わせ、 **WS_OVERLAPPEDWINDOW**と**FWS_ADDTOTITLE**スタイル。 **FWS_ADDTOTITLE**がウィンドウのキャプションにドキュメントのタイトルを追加するために、フレームワークに指示する MFC 固有のスタイル。 SDI アプリケーションでウィンドウの属性を変更するには、オーバーライド、`PreCreateWindow`から派生したクラスで関数`CFrameWnd`(がアプリケーションのウィザード名`CMainFrame`)。 例:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

このコードは、最小化ボタンとサイズ変更境界なしに、メイン フレーム ウィンドウを作成します。 ウィンドウが画面に最初に中央に配置します。

##  <a name="_core_the_mdi_case"></a> MDI の場合

マルチ ドキュメント インターフェイス (MDI) アプリケーションでの子ウィンドウのウィンドウ スタイルを変更する、もう少し作業が必要です。 アプリケーション ウィザードで作成した MDI アプリケーションは既定では、既定値を使用[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) MFC で定義されているクラス。 MDI 子ウィンドウのウィンドウ スタイルを変更するから新しいクラスを派生する必要があります`CMDIChildWnd`へのすべての参照を置き換えると`CMDIChildWnd`新しいクラスへの参照をプロジェクトにします。 ほとんどの場合への参照のみ`CMDIChildWnd`アプリケーションでのアプリケーションのある`InitInstance`メンバー関数。

MDI アプリケーションで使用される既定のウィンドウ スタイルがの組み合わせ、 **WS_CHILD**、 **WS_OVERLAPPEDWINDOW**、および**FWS_ADDTOTITLE**スタイル。 MDI アプリケーションの子ウィンドウのウィンドウの属性を変更するには、オーバーライド、 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)から派生したクラスで関数`CMDIChildWnd`します。 例:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

このコードでは、最大化ボタンなしの windows MDI 子フォームを作成します。

### <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [Windows のスタイル](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)

- [ウィンドウ スタイル](/windows/desktop/winmsg/window-styles)

## <a name="see-also"></a>関連項目

[フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)
