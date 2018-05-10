---
title: 'MFC ActiveX コントロール: 最適化 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], windowless
- flicker-free ActiveX controls
- MFC ActiveX controls [MFC], mouse interaction
- device contexts, unclipped for MFC ActiveX controls
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- MFC ActiveX controls [MFC], flicker-free
- windowless MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- optimizing performance, ActiveX controls
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c91f147637b53250f8d373af9950d6205c82d3e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-optimization"></a>MFC ActiveX コントロール : 最適化
この記事では、パフォーマンス向上のため、ActiveX コントロールを最適化するために使用できるテクニックについて説明します。  
  
 トピック[にするとオフのときに表示アクティブ オプション](../mfc/turning-off-the-activate-when-visible-option.md)と[を提供するマウス操作中に非アクティブな](../mfc/providing-mouse-interaction-while-inactive.md)をアクティブ化されるまでウィンドウを作成しないコントロールについて説明します。 トピック[ウィンドウなしのアクティベーション](../mfc/providing-windowless-activation.md)コントロールをアクティブにしている場合でも、ウィンドウを作成しないことを説明します。  
  
 Windows が OLE オブジェクトの 2 つの主な欠点がある: 透過的なまたはアクティブな場合、四角形以外からオブジェクトできなくなるし、追加のオーバーヘッドが発生する大規模なインスタンス化とコントロールの表示。 通常、ウィンドウを作成すると、コントロールの作成時の 60% がかかります。 1 つの共有ウィンドウ (通常はコンテナーの) と一部のディスパッチのコードでは、コントロールは、パフォーマンスの低下なしに一般的には、同じウィンドウ サービスを受信します。 ウィンドウは、オブジェクトの不要なオーバーヘッドがほとんどです。  
  
 最適化によっては必ずしもパフォーマンスが向上しない、コントロールは、特定のコンテナーで使用される場合。 たとえば、ため、この機能を実装するメリットはありません、古いコンテナーに、1996年する前にリリースされたコンテナーはウィンドウなしのアクティベーションをサポートしませんでした。 ただし、ほぼすべてのコンテナーは、コントロールの永続化のコードの最適化は任意のコンテナーで、パフォーマンスは向上可能性があります、永続化をサポートします。 コントロールは、コンテナーの 1 つの特定の種類で使用するためのものでは具体的には、場合調べようとするこれらの最適化のコンテナーでサポートされています。 一般に、ただし、必要がありますしようとするさまざまなコンテナーのように、コントロールの実行だけでなく、可能性のあることを確認する、特定のコントロールに適用可能なこれらの手法の多くを実装します。  
  
 これらの最適化の多くを実装することができます、 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)の[コントロール設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)ページ。  
  
### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC ActiveX コントロール ウィザード OLE 最適化オプション  
  
|MFC ActiveX コントロール ウィザード コントロールの設定|アクション|詳細情報|  
|-------------------------------------------------------|------------|----------------------|  
|**表示時にアクティブ** チェック ボックス|Clear|[電源を切る、アクティブ化するときに [表示] オプション](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**ウィンドウなしのアクティベーション** チェック ボックス|選択|[ウィンドウなしのアクティベーション](../mfc/providing-windowless-activation.md)|  
|**クリッピングを行わないデバイス コンテキスト** チェック ボックス|選択|[クリッピングを行わないデバイス コンテキストの使用](../mfc/using-an-unclipped-device-context.md)|  
|**ちらつきなしのアクティベーション** チェック ボックス|選択|[ちらつきなしのアクティベーションの提供](../mfc/providing-flicker-free-activation.md)|  
|**マウス ポインター通知アクティブでないとき** チェック ボックス|選択|[コントロールがアクティブでないときのマウスとの対話](../mfc/providing-mouse-interaction-while-inactive.md)|  
|**最適化された描画コード** チェック ボックス|選択|[コントロールの描画の最適化](../mfc/optimizing-control-drawing.md)|  
  
 これらの最適化を実装するメンバー関数の詳細については、次を参照してください。 [COleControl](../mfc/reference/colecontrol-class.md)です。 メンバー関数は、によって一覧表示される、使用するよう[ウィンドウなしの操作](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df)と[ポインター処理関数の使用頻度の低い](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df)です。  
  
 詳細については次を参照してください:  
  
-   [永続化と初期化の最適化](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [ウィンドウなしのアクティベーション](../mfc/providing-windowless-activation.md)  
  
-   [電源を切る、アクティブ化するときに [表示] オプション](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [コントロールがアクティブでないときのマウスとの対話](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [ちらつきなしのアクティベーションの提供](../mfc/providing-flicker-free-activation.md)  
  
-   [クリッピングを行わないデバイス コンテキストの使用](../mfc/using-an-unclipped-device-context.md)  
  
-   [コントロールの描画の最適化](../mfc/optimizing-control-drawing.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

