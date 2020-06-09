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
ms.openlocfilehash: f3fd9f83112737e944d83cf00da685d81fe8b2a7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624946"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC で作成したウィンドウのスタイル変更

関数のバージョンでは `WinMain` 、MFC によっていくつかの標準ウィンドウクラスが登録されます。 通常は MFC を編集しないため、この関数では `WinMain` mfc の既定のウィンドウスタイルを変更することはできません。 この記事では、既存のアプリケーションでこのような事前登録さウィンドウクラスのスタイルを変更する方法について説明します。

## <a name="changing-styles-in-a-new-mfc-application"></a><a name="_core_changing_styles_in_a_new_mfc_application"></a>新しい MFC アプリケーションでのスタイルの変更

Visual C++ 2.0 以降を使用している場合は、アプリケーションの作成時にアプリケーションウィザードで既定のウィンドウスタイルを変更できます。 アプリケーションウィザードの [ユーザーインターフェイスの機能] ページでは、メインフレームウィンドウと MDI 子ウィンドウのスタイルを変更できます。 いずれのウィンドウの種類でも、枠の太さ (太または細い) と、次のいずれかを指定できます。

- ウィンドウに最小化コントロールまたは最大化コントロールがあるかどうかを指定します。

- ウィンドウを最初に最小化するか、最大化するか、またはどちらも表示しないかを指定します。

メインフレームウィンドウでは、ウィンドウにシステムメニューを表示するかどうかを指定することもできます。 MDI 子ウィンドウの場合は、ウィンドウでスプリッターペインをサポートするかどうかを指定できます。

## <a name="changing-styles-in-an-existing-application"></a><a name="_core_changing_styles_in_an_existing_application"></a>既存のアプリケーションのスタイルを変更する

既存のアプリケーションでウィンドウ属性を変更する場合は、この記事の残りの部分に記載されている手順に従ってください。

アプリケーションウィザードで作成されたフレームワークアプリケーションで使用される既定のウィンドウ属性を変更するには、ウィンドウの[PreCreateWindow](reference/cwnd-class.md#precreatewindow)仮想メンバー関数をオーバーライドします。 `PreCreateWindow`アプリケーションが通常、 [CDocTemplate](reference/cdoctemplate-class.md)クラスによって内部的に管理されている作成プロセスにアクセスできるようにします。 フレームワークは、 `PreCreateWindow` ウィンドウを作成する直前にを呼び出します。 に渡された[CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw)構造体を変更することにより、 `PreCreateWindow` アプリケーションはウィンドウの作成に使用する属性を変更できます。 たとえば、ウィンドウがキャプションを使用しないようにするには、次のビットごとの演算を使用します。

[!code-cpp[NVC_MFCDocView#15](codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../overview/visual-cpp-samples.md)サンプルアプリケーションは、ウィンドウ属性を変更するためのこの手法を示しています。 アプリケーションの変更内容によっては、 `PreCreateWindow` 関数の基本クラスの実装を呼び出すことが必要になる場合があります。

次の説明では、SDI のケースと[MDI のケース](#_core_the_mdi_case)について説明します。

## <a name="the-sdi-case"></a><a name="_core_the_sdi_case"></a>SDI ケース

シングルドキュメントインターフェイス (SDI) アプリケーションでは、フレームワークの既定のウィンドウスタイルは、 **WS_OVERLAPPEDWINDOW**スタイルと**FWS_ADDTOTITLE**スタイルを組み合わせたものです。 **FWS_ADDTOTITLE**は、ウィンドウのキャプションにドキュメントタイトルを追加するようフレームワークに指示する MFC 固有のスタイルです。 SDI アプリケーションでウィンドウ属性を変更するには、 `PreCreateWindow` から派生したクラス `CFrameWnd` (アプリケーションウィザードの名前) の関数をオーバーライドし `CMainFrame` ます。 次に例を示します。

[!code-cpp[NVC_MFCDocViewSDI#11](codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

このコードは、最小化ボタンと最大化ボタンを使用せず、サイズを大きくすることなく、メインフレームウィンドウを作成します。 ウィンドウは、最初は画面の中央に配置されます。

## <a name="the-mdi-case"></a><a name="_core_the_mdi_case"></a>MDI ケース

マルチドキュメントインターフェイス (MDI) アプリケーションで子ウィンドウのウィンドウスタイルを変更するには、もう少し作業が必要です。 既定では、アプリケーションウィザードで作成された MDI アプリケーションは、MFC で定義されている既定の[CMDIChildWnd](reference/cmdichildwnd-class.md)クラスを使用します。 MDI 子ウィンドウのウィンドウスタイルを変更するには、から新しいクラスを派生させ、 `CMDIChildWnd` プロジェクト内のへのすべての参照を `CMDIChildWnd` 新しいクラスへの参照で置き換える必要があります。 ほとんどの場合、アプリケーション内のへの参照は `CMDIChildWnd` アプリケーションの `InitInstance` メンバー関数にあります。

MDI アプリケーションで使用される既定のウィンドウスタイルは、 **WS_CHILD**、 **WS_OVERLAPPEDWINDOW**、および**FWS_ADDTOTITLE**スタイルを組み合わせたものです。 MDI アプリケーションの子ウィンドウのウィンドウ属性を変更するには、から派生したクラスの[PreCreateWindow](reference/cwnd-class.md#precreatewindow)関数をオーバーライドし `CMDIChildWnd` ます。 次に例を示します。

[!code-cpp[NVC_MFCDocView#16](codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

このコードは、[最大化] ボタンを使用せずに MDI 子ウィンドウを作成します。

### <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [Windows スタイル](reference/styles-used-by-mfc.md#window-styles)

- [フレームウィンドウスタイル](frame-window-styles-cpp.md)

- [ウィンドウスタイル](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>関連項目

[フレーム ウィンドウ スタイル](frame-window-styles-cpp.md)
