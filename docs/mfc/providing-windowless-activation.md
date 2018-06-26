---
title: ウィンドウなしのアクティベーション |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- windowless activation of MFC ActiveX controls
- activation [MFC], MFC ActiveX controls
- MFC ActiveX controls [MFC], activate options
- activation [MFC], windowless
ms.assetid: 094903b5-c344-42fa-96ff-ce01e16891c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a42d952ade479c4eb117d21921c9b0feafb81cea
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931952"
---
# <a name="providing-windowless-activation"></a>ウィンドウなしのアクティベーション
ウィンドウを作成するコード (つまり、すべてのものを呼び出すときに発生する`CreateWindow`) を実行するコストがかかります。 保持するコントロール、ウィンドウがウィンドウのメッセージを管理するにが画面に表示されます。 ウィンドウなしのコントロールはウィンドウを持つコントロールよりも高速ではこのためです。  
  
 ウィンドウなしのコントロールの利点はさらには、ウィンドウのコントロールとは異なりウィンドウなしのコントロール サポート透過的な描画および四角形以外の画面領域です。 透明なコントロールの一般的な例は、透明な背景のテキスト コントロールです。 コントロールでは、テキストが、バック グラウンドではないため、あるものはすべてのテキストが透けてに描画します。 新しいフォーム多くの場合を利用できるように矢印などの四角形以外のコントロールのボタンを丸めます。  
  
 多くの場合、独自のウィンドウの必要はありませんし、代わりに、サービスを使用できますウィンドウとコンテナーのコンテナーがウィンドウなしのオブジェクトをサポートするために書き込まれたことです。 ウィンドウなしのコントロールは、古いコンテナーとの下位互換性です。 ウィンドウなしのコントロールをサポートするためには書き込まれません、古いコンテナーには、ウィンドウなしのコントロールは、アクティブなときに、ウィンドウを作成します。  
  
 ウィンドウなしのコントロールは、独自の windows があるないため、コンテナーを持つウィンドウ) はコントロールのウィンドウで提供されてそれ以外の場合はサービスを提供します。 たとえば、コントロールは、キーボード フォーカス、マウスのキャプチャ、またはデバイス コンテキストを取得する必要があります、これらの操作は、コンテナーによって管理されます。 コンテナーは、適切なウィンドウなしのコントロールには、そのウィンドウに送信されるユーザー入力メッセージをルーティングを使用して、`IOleInPlaceObjectWindowless`インターフェイスです。 (を参照してください、 *ActiveX SDK*このインターフェイスの詳細についてはします)。`COleControl`メンバー関数は、コンテナーからこれらのサービスを呼び出します。  
  
 ウィンドウなしのアクティベーションを使用して、コントロールをインクルード、 **windowlessActivate**によって返されるフラグのセットでフラグ[オン](../mfc/reference/colecontrol-class.md#getcontrolflags)です。 例えば:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-windowless-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#6](../mfc/codesnippet/cpp/providing-windowless-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-windowless-activation_3.cpp)]  
  
 選択した場合にこのフラグを含めるコードが自動的に生成、**ウィンドウなしのアクティベーション** オプションを選択、[コントロール設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)MFC ActiveX コントロール ウィザードのページです。  
  
 コンテナーがコントロールの入力メッセージを委任するウィンドウなしのアクティベーションを有効にすると、`IOleInPlaceObjectWindowless`インターフェイスです。 `COleControl`このインターフェイスの実装は、座標を適切にマウスの調整後に、コントロールのメッセージ マップを通じてメッセージをディスパッチします。 メッセージ マップに対応するエントリを追加することでは、通常のウィンドウのメッセージのようにメッセージを処理できます。 これらのメッセージのハンドラーでは、使用しないでください、 *m_hWnd*メンバー変数 (またはそれを使用する任意のメンバー関数) の値ではない最初に確認**NULL**です。  
  
 `COleControl` マウスのキャプチャ、キーボード フォーカス、スクロール、およびなど、必要に応じて、コンテナーから他のウィンドウ サービスを呼び出すメンバー関数を提供します。  
  
-   [フォーカス](../mfc/reference/colecontrol-class.md#getfocus)、 [SetFocus](../mfc/reference/colecontrol-class.md#setfocus)  
  
-   [GetCapture](../mfc/reference/colecontrol-class.md#getcapture)、 [SetCapture](../mfc/reference/colecontrol-class.md#setcapture)、 [ReleaseCapture](../mfc/reference/colecontrol-class.md#releasecapture)  
  
-   [GetDC](../mfc/reference/colecontrol-class.md#getdc)、 [ReleaseDC](../mfc/reference/colecontrol-class.md#releasedc)  
  
-   [戻り](../mfc/reference/colecontrol-class.md#invalidatergn)  
  
-   [ScrollWindow](../mfc/reference/colecontrol-class.md#scrollwindow)  
  
-   [GetClientRect](../mfc/reference/colecontrol-class.md#getclientrect)  
  
 ウィンドウなしのコントロールでは、常に使用することは、`COleControl`メンバー関数、対応するのではなく`CWnd`メンバー関数またはその関連する Win32 API 関数。  
  
 ウィンドウなしのコントロールを OLE ドラッグ アンド ドロップ操作のターゲットにすることができます。 通常、このコントロールのウィンドウがドロップ先として登録する必要があります。 コントロールに、独自のウィンドウがあるないため、コンテナーは、ドロップ先として独自のウィンドウを使用します。 コントロールの実装を提供する、`IDropTarget`インターフェイスをコンテナーは、適切なタイミングで呼び出しを委任できます。 コンテナーには、このインターフェイスを公開するためにオーバーライド[COleControl::GetWindowlessDropTarget](../mfc/reference/colecontrol-class.md#getwindowlessdroptarget)です。 例えば:  
  
 [!code-cpp[NVC_MFC_AxOpt#8](../mfc/codesnippet/cpp/providing-windowless-activation_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)

