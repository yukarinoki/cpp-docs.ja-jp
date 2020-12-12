---
description: 詳細については、「派生ウィンドウクラス」を参照してください。
title: ウィンドウ クラスの派生
ms.date: 11/04/2016
helpviewer_keywords:
- window class hierarchy
- hierarchies, window classes
- classes [MFC], derived
- CWnd class [MFC], classes derived from
- derived classes [MFC], window classes
- window classes [MFC], derived
ms.assetid: 6f7e437e-fbde-4a06-bfab-72d9dbf05292
ms.openlocfilehash: 9219267b5351f972257d9770f8e8b38039b85788
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335895"
---
# <a name="derived-window-classes"></a>ウィンドウ クラスの派生

[CWnd](reference/cwnd-class.md)から windows を直接作成することも、から新しいウィンドウクラスを派生させることもでき `CWnd` ます。 これは、独自のカスタム ウィンドウを作成する一般的な方法です。 ただし、フレームワーク プログラムで使用されるほとんどのウィンドウは、MFC に用意されている、`CWnd` から派生するフレーム ウィンドウ クラスのいずれかから作成されます。

## <a name="frame-window-classes"></a>フレーム ウィンドウ クラス

[CFrameWnd](reference/cframewnd-class.md)<br/>
単一ドキュメントとそのビューを囲む SDI フレーム ウィンドウに使用されます。 フレーム ウィンドウは、アプリケーションのメイン フレーム ウィンドウであり、現在のドキュメントのフレーム ウィンドウでもあります。

[CMDIFrameWnd](reference/cmdiframewnd-class.md)<br/>
MDI アプリケーションのメイン フレーム ウィンドウとして使用されます。 メイン フレーム ウィンドウは、すべての MDI ドキュメント ウィンドウのコンテナーであり、そのメニュー バーを MDI ドキュメント ウィンドウと共有します。 MDI フレーム ウィンドウはデスクトップに表示される最上位ウィンドウです。

[CMDIChildWnd](reference/cmdichildwnd-class.md)<br/>
MDI メイン フレーム ウィンドウで開かれる個々のドキュメントに使用されます。 各ドキュメントとそのビューは、MDI メイン フレーム ウィンドウに含まれている MDI 子フレーム ウィンドウの中に収まります。 MDI 子ウィンドウの外観は一般的なフレーム ウィンドウと非常に似ていますが、デスクトップ上に表示されるのではなく、MDI フレーム ウィンドウの内部に格納されます。 ただし、MDI 子ウィンドウには独自のメニュー バーがなく、それを含む MDI フレーム ウィンドウのメニュー バーを共有する必要があります。

詳細については、「 [フレームウィンドウ](frame-windows.md)」を参照してください。

## <a name="other-window-classes-derived-from-cwnd"></a>CWnd から派生するその他のウィンドウ クラス

フレーム ウィンドウに加え、次に示すその他のいくつかの主なウィンドウ カテゴリが `CWnd` から派生しています。

*ビュー*<br/>
ビューは、 `CWnd` から派生したクラス [CView](reference/cview-class.md) (またはその派生クラスの1つ) を使用して作成されます。 ビューはドキュメントにアタッチされ、ドキュメントとユーザーの仲介役として機能します。 ビューは、一般に SDI フレーム ウィンドウまたは MDI 子フレーム ウィンドウのクライアント領域 (または、ツール バーやステータス バーで占有されていないクライアント領域の部分) を占める子ウィンドウです (MDI 子ウィンドウではありません)。

*ダイアログボックス*<br/>
ダイアログボックスは、の派生クラスである CDialog を使用して作成され `CWnd` ます。 [](reference/cdialog-class.md)

*フォーム*<br/>
ダイアログボックスなどのダイアログボックステンプレートリソースに基づくフォームビューは、 [CFormView](reference/cformview-class.md)、 [CRecordView](reference/crecordview-class.md)、または [CDaoRecordView](reference/cdaorecordview-class.md)クラスを使用して作成されます。

*コントロール*<br/>
ボタン、リスト ボックス、コンボ ボックスなどのコントロールは、`CWnd` から派生する他のクラスを使用して作成されます。 「 [コントロールのトピック](controls-mfc.md)」を参照してください。

*コントロールバー*<br/>
コントロールを含む子ウィンドウ。 たとえば、ツール バーやステータス バーが該当します。 「 [コントロールバー](control-bars.md)」を参照してください。

## <a name="window-class-hierarchy"></a>ウィンドウ クラスの階層構造

Mfc *リファレンス* の [mfc 階層図](hierarchy-chart.md)を参照してください。 ビューについては、「 [ドキュメント/ビューアーキテクチャ](document-view-architecture.md)」で説明されています。 ダイアログボックスについては、「 [ダイアログボックス](dialog-boxes.md)」で説明されています。

## <a name="creating-your-own-special-purpose-window-classes"></a>独自の特殊用途ウィンドウ クラスの作成

クラス ライブラリに用意されているウィンドウ クラスに加えて、特殊用途の子ウィンドウが必要な場合があります。 このようなウィンドウを作成するには、独自の [CWnd](reference/cwnd-class.md)派生クラスを作成し、それをフレームまたはビューの子ウィンドウにします。 フレームワークは、ドキュメントのフレーム ウィンドウのクライアント領域の範囲を管理することに注意してください。 クライアント領域のほとんどはビューによって管理されますが、コントロール バーや独自のカスタム ウィンドウなど、他のウィンドウは、ビューと領域を共有する場合があります。 フレームウィンドウのクライアント領域に子ウィンドウを配置するには、クラス [CView](reference/cview-class.md) と [CControlBar](reference/ccontrolbar-class.md) の機構と対話する必要がある場合があります。

[Windows の作成](creating-windows.md) については、ウィンドウオブジェクトとそれらが管理するウィンドウの作成について説明します。

## <a name="see-also"></a>関連項目

[ウィンドウオブジェクト](window-objects.md)
