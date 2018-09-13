---
title: 'MFC ActiveX コントロール: 最適化 |Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: 09d441a44660310a13be264b24286ad2f0ccc6cd
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535185"
---
# <a name="mfc-activex-controls-optimization"></a>MFC ActiveX コントロール : 最適化
この記事では、パフォーマンス向上のため、ActiveX コントロールを最適化するために使用できる手法について説明します。  

>[!IMPORTANT]
> ActiveX は、新規の開発が使用できないレガシ テクノロジです。 ActiveX の上書きの最新のテクノロジの詳細については、次を参照してください。 [ActiveX コントロール](activex-controls.md)します。
  
 トピックでは、[にすることから、アクティブ化表示時にオプション](../mfc/turning-off-the-activate-when-visible-option.md)と[を提供するマウス操作中に非アクティブな](../mfc/providing-mouse-interaction-while-inactive.md)をアクティブ化されるまでウィンドウを作成しないコントロールについて説明します。 トピック[ウィンドウなしのアクティベーション](../mfc/providing-windowless-activation.md)アクティブにしている場合でも、ウィンドウを作成しないコントロールについて説明します。  
  
 Windows OLE オブジェクトの 2 つの主な欠点がある: 透明またはアクティブな場合、四角形以外のオブジェクトは、およびインスタンス化とコントロールの表示に大きなオーバーヘッドを追加します。 通常、ウィンドウを作成すると、コントロールの作成時の 60% がかかります。 1 つの共有ウィンドウ (通常は、コンテナーの) といくつかのディスパッチのコードでは、コントロールは、パフォーマンスの低下なしに一般的に、同じウィンドウ サービスを受信します。 ウィンドウは、オブジェクトの不要なオーバーヘッドがほとんどです。  
  
 いくつかの最適化は必ずしもパフォーマンスが向上しない特定のコンテナー コントロールを使用するとします。 たとえば、ため、この機能の実装は古いコンテナーの特典を提供しません、1996年する前にリリースされたコンテナーはウィンドウなしのアクティベーションをサポートしませんでした。 ただし、ほぼすべてのコンテナーは、コントロールの永続化コードの最適化が任意のコンテナーで、パフォーマンスは向上可能性がありますので、永続化をサポートします。 コントロールは、コンテナーの 1 つの特定の種類で使用するためのものでは具体的には、場合の研究にこれらの最適化のコンテナーでサポートされています。 一般に、ただし、する必要がありますしようとするさまざまなコンテナーのように、コントロールの実行とその可能性があることを確認して、特定のコントロールに適用可能なこれらの手法の多くを実装します。  
  
 これらの最適化の多くを実装することができます、 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)の[コントロール設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)ページ。  
  
### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC ActiveX コントロール ウィザード OLE 最適化オプション  
  
|MFC ActiveX コントロール ウィザード、コントロールの設定|アクション|詳細情報|  
|-------------------------------------------------------|------------|----------------------|  
|**表示時にアクティブ** チェック ボックス|Clear|[オフにすると、ときにアクティブ化 [表示] オプション](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**ウィンドウなしのアクティベーション** チェック ボックス|選択|[ウィンドウなしのアクティベーション](../mfc/providing-windowless-activation.md)|  
|**クリッピングを行わないデバイス コンテキスト** チェック ボックス|選択|[クリッピングを行わないデバイス コンテキストの使用](../mfc/using-an-unclipped-device-context.md)|  
|**アクティブ化のちらつきのない** チェック ボックス|選択|[ちらつきなしのアクティベーションの提供](../mfc/providing-flicker-free-activation.md)|  
|**マウス ポインターの通知時に非アクティブな** チェック ボックス|選択|[コントロールがアクティブでないときのマウスとの対話](../mfc/providing-mouse-interaction-while-inactive.md)|  
|**最適化された描画コード** チェック ボックス|選択|[コントロールの描画の最適化](../mfc/optimizing-control-drawing.md)|  
  
 これらの最適化を実装するメンバー関数の詳細については、次を参照してください。 [COleControl](../mfc/reference/colecontrol-class.md)します。  
  
 詳細については次を参照してください:  
  
-   [永続化と初期化の最適化](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [ウィンドウなしのアクティベーション](../mfc/providing-windowless-activation.md)  
  
-   [オフにすると、ときにアクティブ化 [表示] オプション](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [コントロールがアクティブでないときのマウスとの対話](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [ちらつきなしのアクティベーションの提供](../mfc/providing-flicker-free-activation.md)  
  
-   [クリッピングを行わないデバイス コンテキストの使用](../mfc/using-an-unclipped-device-context.md)  
  
-   [コントロールの描画の最適化](../mfc/optimizing-control-drawing.md)  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)

