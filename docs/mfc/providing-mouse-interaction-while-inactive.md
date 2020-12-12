---
description: 詳細については、「非アクティブな状態でのマウス操作の提供」をご覧ください。
title: コントロールがアクティブでないときのマウスとの対話
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
ms.openlocfilehash: bd3c069b052b58059de5f311e4ead795400d32fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248737"
---
# <a name="providing-mouse-interaction-while-inactive"></a>コントロールがアクティブでないときのマウスとの対話

コントロールがすぐにアクティブにならない場合でも、コントロールに独自のウィンドウがない場合でも、WM_SETCURSOR メッセージと WM_MOUSEMOVE メッセージの処理が必要になることがあります。 これを実現するには、 `COleControl` インターフェイスの実装を有効にし `IPointerInactive` ます。これは既定で無効になっています。 (このインターフェイスの説明については、 *ACTIVEX SDK* を参照してください。)有効にするには、次のように、 [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)によって返されるフラグのセットにポインタ inactive フラグを含めます。

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]

**MFC ActiveX コントロールウィザード** を使用してコントロールを作成するときに、[[コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)] ページで [**非アクティブなときにマウスポインターの通知** を表示する] オプションを選択すると、このフラグを追加するコードが自動的に生成されます。

インターフェイスを有効にすると、 `IPointerInactive` コンテナーは WM_SETCURSOR を委任し、メッセージを WM_MOUSEMOVE します。 `COleControl`のの実装では `IPointerInactive` 、マウスの座標を適切に調整した後に、コントロールのメッセージマップを通じてメッセージをディスパッチします。 メッセージマップに対応するエントリを追加することによって、メッセージを通常のウィンドウメッセージと同様に処理できます。 これらのメッセージのハンドラーでは、最初に値が **NULL** でないことを確認せずに、 *m_hWnd* メンバー変数 (またはそれを使用するメンバー関数) を使用しないようにします。

また、非アクティブなコントロールが OLE ドラッグアンドドロップ操作の対象になるようにすることもできます。 これには、ユーザーがオブジェクトをドラッグした時点でコントロールをアクティブにする必要があります。これにより、コントロールのウィンドウをドロップ先として登録できるようになります。 ドラッグ中にアクティベーションが発生するようにするには、次のように、 [COleControl:: GetActivationPolicy](../mfc/reference/colecontrol-class.md#getactivationpolicy)をオーバーライドし、POINTERINACTIVE_ACTIVATEONDRAG フラグを返します。

[!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]

インターフェイスを有効にすることは、 `IPointerInactive` 通常、コントロールが常にマウスメッセージを処理できるようにすることを意味します。 インターフェイスをサポートしていないコンテナーでこの動作を取得するには、コントロールを常に表示されている状態でアクティブにする必要があります `IPointerInactive` 。つまり、コントロールには、その他のフラグの間に OLEMISC_ACTIVATEWHENVISIBLE フラグを含める必要があります。 ただし、でサポートされているコンテナーでこのフラグが有効にならないようにするには、 `IPointerInactive` OLEMISC_IGNOREACTIVATEWHENVISIBLE フラグを指定することもできます。

[!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)
