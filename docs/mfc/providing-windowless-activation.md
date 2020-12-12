---
description: '詳細情報: ウィンドウなしのアクティベーション'
title: ウィンドウなしのアクティベーション
ms.date: 11/04/2016
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
ms.openlocfilehash: ea9b86c977926e57bd3593ec861498eb5d909f37
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248633"
---
# <a name="providing-windowless-activation"></a>ウィンドウなしのアクティベーション

ウィンドウ作成コード (を呼び出すと発生するすべてのコード `CreateWindow` ) は、実行に時間がかかります。 画面上のウィンドウを保持するコントロールは、ウィンドウのメッセージを管理する必要があります。 このため、ウィンドウなしのコントロールは、windows でのコントロールよりも高速です。

ウィンドウなしのコントロールの利点は、ウィンドウコントロールとは異なり、ウィンドウなしのコントロールは透明な描画と四角形以外の画面領域をサポートすることです。 透明なコントロールの一般的な例として、透明な背景を持つテキストコントロールがあります。 コントロールはテキストを描画しますが、背景は描画しません。そのため、テキストの下に表示される内容はすべて、によって示されます。 新しい形式では、多くの場合、矢印や丸いボタンなど、四角形以外のコントロールが使用されます。

多くの場合、コントロールには独自のウィンドウは必要ありませんが、コンテナーがウィンドウなしのオブジェクトをサポートするように記述されていれば、そのコンテナーのウィンドウサービスを使用できます。 ウィンドウなしのコントロールは、古いコンテナーと下位互換性があります。 ウィンドウなしのコントロールをサポートするために作成されていない古いコンテナーでは、ウィンドウがアクティブになるとウィンドウが作成されます。

ウィンドウなしのコントロールには独自のウィンドウがないため、コンテナー (ウィンドウがある) は、他の方法でコントロールのウィンドウによって提供されたサービスを提供する役割を担います。 たとえば、コントロールがキーボードフォーカスに対してクエリを実行したり、マウスをキャプチャしたり、デバイスコンテキストを取得したりする必要がある場合、これらの操作はコンテナーによって管理されます。 コンテナーは、そのウィンドウに送信されたユーザー入力メッセージを、インターフェイスを使用して、適切なウィンドウなしのコントロールにルーティングし `IOleInPlaceObjectWindowless` ます。 (このインターフェイスの説明については、 *ACTIVEX SDK* を参照してください。) `COleControl` メンバー関数は、これらのサービスをコンテナーから呼び出します。

コントロールがウィンドウなしのアクティベーションを使用するようにするには、 [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)によって返されるフラグのセットに **windowno activate** フラグを含めます。 次に例を示します。

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]

MFC ActiveX コントロールウィザードの [[コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)] ページで **ウィンドウなしのアクティベーション** オプションを選択すると、このフラグを追加するコードが自動的に生成されます。

ウィンドウなしのアクティベーションが有効になっている場合、コンテナーは入力メッセージをコントロールのインターフェイスに委任し `IOleInPlaceObjectWindowless` ます。 `COleControl`では、このインターフェイスを実装することにより、マウスの座標を適切に調整した後、コントロールのメッセージマップを通じてメッセージをディスパッチします。 メッセージマップに対応するエントリを追加することで、通常のウィンドウメッセージのようなメッセージを処理できます。 これらのメッセージのハンドラーでは、最初に値が **NULL** でないことを確認せずに、 *m_hWnd* メンバー変数 (またはそれを使用するメンバー関数) を使用しないようにします。

`COleControl` には、次のように、コンテナーからマウスキャプチャ、キーボードフォーカス、スクロール、およびその他のウィンドウサービスを呼び出すメンバー関数が用意されています。

- [GetFocus](../mfc/reference/colecontrol-class.md#getfocus)、 [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)

- [Getcapture](../mfc/reference/colecontrol-class.md#getcapture)、 [SetCapture](../mfc/reference/colecontrol-class.md#setcapture)、 [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)

- [GetDC](../mfc/reference/colecontrol-class.md#getdc)、 [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)

- [InvalidateRgn](../mfc/reference/colecontrol-class.md#invalidatergn)

- [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)

- [GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)

ウィンドウなしのコントロールでは、対応する `COleControl` `CWnd` メンバー関数またはそれに関連する Win32 API 関数の代わりに、常にメンバー関数を使用する必要があります。

ウィンドウなしのコントロールを OLE ドラッグアンドドロップ操作の対象にすることができます。 通常、これを行うには、コントロールのウィンドウがドロップ先として登録されている必要があります。 コントロールには独自のウィンドウがないため、コンテナーは独自のウィンドウをドロップ先として使用します。 コントロールは、 `IDropTarget` 適切なタイミングでコンテナーが呼び出しを委任できるインターフェイスの実装を提供します。 このインターフェイスをコンテナーに公開するには、 [COleControl:: Getwindowと Droptarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget)をオーバーライドします。 次に例を示します。

[!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)
