---
title: マウスとの対話中にアクティブでない |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], mouse interaction
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c322493a0ee1aebd068ffe1fedb695445b6274aa
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929495"
---
# <a name="providing-mouse-interaction-while-inactive"></a>コントロールがアクティブでないときのマウスとの対話
場合は、コントロールがすぐにアクティブでない可能性がありますかプロセス WM_SETCURSOR と WM_MOUSEMOVE メッセージ コントロールに、独自のウィンドウがあるない場合でもです。 これには、有効にすると`COleControl`の実装、`IPointerInactive`インターフェイスで、既定で無効にします。 (を参照してください、 *ActiveX SDK*このインターフェイスの詳細についてはします)。有効にするには、によって返されるフラグのセットに pointerInactive フラグを含める[オン](../mfc/reference/colecontrol-class.md#getcontrolflags):  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_3.cpp)]  
  
 選択した場合にこのフラグを含めるコードが自動的に生成、**非アクティブ時のマウス ポインター通知** オプションを選択、[コントロール設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)でコントロールを作成するときにページ**MFC ActiveX コントロール ウィザード**です。  
  
 ときに、`IPointerInactive`インターフェイスが有効になっている、コンテナーに WM_SETCURSOR および WM_MOUSEMOVE メッセージを代行させます。 `COleControl`実装の`IPointerInactive`座標を適切にマウスの調整後に、コントロールのメッセージ マップを通じてメッセージをディスパッチします。 メッセージ マップに対応するエントリを追加することでは、通常のウィンドウのメッセージと同じようにメッセージを処理できます。 これらのメッセージのハンドラーでは、使用しないでください、 *m_hWnd*メンバー変数 (またはそれを使用する任意のメンバー関数) の値ではない最初に確認**NULL**です。  
  
 OLE ドラッグ アンド ドロップ操作の対象となる、非アクティブなコントロールをすることもできます。 これは、コントロールのウィンドウがドロップ先として登録できるように、上に、ユーザーがオブジェクトをドラッグする時点でコントロールをアクティブ化する必要があります。 ドラッグ中をライセンス認証には、オーバーライド[がアクティブ](../mfc/reference/colecontrol-class.md#getactivationpolicy)、POINTERINACTIVE_ACTIVATEONDRAG フラグを返すとします。  
  
 [!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_4.cpp)]  
  
 有効にすると、`IPointerInactive`通常インターフェイスでは常にマウスのメッセージの処理に対応しているコントロールを表示することを意味します。 サポートされていない、コンテナーでこの動作を取得する、`IPointerInactive`インターフェイス、する必要があります、コントロールが常にアクティブに表示される、コントロールはその他のフラグ間されてフラグを含める必要があります。 ただし、このフラグを防ぐために、コンテナー内の効果を取得はサポート`IPointerInactive`、OLEMISC_IGNOREACTIVATEWHENVISIBLE フラグを指定することもできます。  
  
 [!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/cpp/providing-mouse-interaction-while-inactive_5.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)

