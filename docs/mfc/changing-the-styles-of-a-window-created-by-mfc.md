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
ms.openlocfilehash: 221092eb25a4f044cda5b379d6774659d9e9d2d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374592"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC で作成したウィンドウのスタイル変更

`WinMain`関数のバージョンでは、MFC は、いくつかの標準ウィンドウ クラスを登録します。 通常は MFC の を編集しないため、`WinMain`この関数では MFC の既定のウィンドウ スタイルを変更する機会はありません。 この記事では、既存のアプリケーションで、このような事前登録されたウィンドウ クラスのスタイルを変更する方法について説明します。

## <a name="changing-styles-in-a-new-mfc-application"></a><a name="_core_changing_styles_in_a_new_mfc_application"></a>新しい MFC アプリケーションでスタイルを変更する

Visual C++ 2.0 以降を使用している場合は、アプリケーションの作成時にアプリケーション ウィザードで既定のウィンドウ スタイルを変更できます。 アプリケーション ウィザードの [ユーザー インターフェイス機能] ページで、メイン フレーム ウィンドウと MDI 子ウィンドウのスタイルを変更できます。 どちらの窓タイプでも、フレームの厚み(太さまたは薄い)と次のいずれかを指定できます。

- ウィンドウに最小化または最大化のコントロールがあるかどうか。

- ウィンドウを最初に最小化するか、最大化するか、または表示しないか。

メイン フレーム ウィンドウの場合は、ウィンドウにシステム メニューがあるかどうかを指定することもできます。 MDI 子ウィンドウの場合は、ウィンドウが分割ペインをサポートするかどうかを指定できます。

## <a name="changing-styles-in-an-existing-application"></a><a name="_core_changing_styles_in_an_existing_application"></a>既存のアプリケーションのスタイルを変更する

既存のアプリケーションでウィンドウ属性を変更する場合は、この記事の残りの部分の手順に従ってください。

アプリケーション ウィザードで作成されたフレームワーク アプリケーションで使用される既定のウィンドウ属性を変更するには、ウィンドウの[PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)仮想メンバー関数をオーバーライドします。 `PreCreateWindow`アプリケーションは、[通常 CDocTemplate](../mfc/reference/cdoctemplate-class.md)クラスによって内部的に管理される作成プロセスにアクセスできます。 フレームワークは、`PreCreateWindow`ウィンドウを作成する直前に呼び出します。 に渡される[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw)構造体を`PreCreateWindow`変更することにより、アプリケーションはウィンドウの作成に使用される属性を変更できます。 たとえば、ウィンドウでキャプションを使用しないようにするには、次のビット単位の操作を使用します。

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../overview/visual-cpp-samples.md)サンプル アプリケーションでは、ウィンドウ属性を変更するこの手法を示します。 アプリケーションの`PreCreateWindow`変更に応じて、関数の基本クラスの実装を呼び出す必要があります。

以下の説明では、SDI の場合と[MDI のケース](#_core_the_mdi_case)について説明します。

## <a name="the-sdi-case"></a><a name="_core_the_sdi_case"></a>SDIケース

単一のドキュメント インターフェイス (SDI) アプリケーションでは、フレームワークの既定のウィンドウ スタイルは **、WS_OVERLAPPEDWINDOW**スタイルと**FWS_ADDTOTITLE**スタイルの組み合わせです。 **FWS_ADDTOTITLE**は、ウィンドウのキャプションにドキュメント タイトルを追加するようにフレームワークに指示する MFC 固有のスタイルです。 SDI アプリケーションのウィンドウ属性を変更するには、派生した`PreCreateWindow`クラス`CFrameWnd`の関数をオーバーライドします (アプリケーション ウィザードが`CMainFrame`名前を付けます)。 次に例を示します。

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

このコードは、最小化ボタンと最大化ボタンを使用せず、大きな枠線を持たないメイン フレーム ウィンドウを作成します。 ウィンドウは、最初は画面の中央に配置されます。

## <a name="the-mdi-case"></a><a name="_core_the_mdi_case"></a>MDIケース

マルチ ドキュメント インターフェイス (MDI) アプリケーションで子ウィンドウのウィンドウ スタイルを変更するには、もう少し作業が必要です。 既定では、アプリケーション ウィザードで作成された MDI アプリケーションは、MFC で定義されている既定の[CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)クラスを使用します。 MDI 子ウィンドウのウィンドウ スタイルを変更するには、プロジェクト内のすべての参照を新`CMDIChildWnd`しいクラスへの参照に`CMDIChildWnd`派生し、新しいクラスへの参照に置き換える必要があります。 アプリケーション`CMDIChildWnd`内の参照は、アプリケーションの`InitInstance`メンバー関数内にしか存在しません。

MDI アプリケーションで使用される既定のウィンドウ スタイルは **、WS_CHILD** **、WS_OVERLAPPEDWINDOW、****およびFWS_ADDTOTITLE**スタイルの組み合わせです。 MDI アプリケーションの子ウィンドウのウィンドウ属性を変更するには、から`CMDIChildWnd`派生したクラスの[PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)関数をオーバーライドします。 次に例を示します。

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

このコードは、最大化ボタンを使用せずに MDI 子ウィンドウを作成します。

### <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [ウィンドウスタイル](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)

- [ウィンドウ スタイル](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>関連項目

[フレーム ウィンドウ スタイル](../mfc/frame-window-styles-cpp.md)
