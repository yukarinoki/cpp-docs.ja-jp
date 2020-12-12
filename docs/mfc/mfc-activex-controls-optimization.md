---
description: '詳細については、「MFC ActiveX コントロール: Optimization」を参照してください。'
title: 'MFC ActiveX コントロール : 最適化'
ms.date: 09/12/2018
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
ms.openlocfilehash: db7fc1f1bdcdc3a3ffbf3b14d1809806389f0862
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294107"
---
# <a name="mfc-activex-controls-optimization"></a>MFC ActiveX コントロール : 最適化

この記事では、パフォーマンス向上のために ActiveX コントロールを最適化するために使用できる手法について説明します。

>[!IMPORTANT]
> ActiveX は、新しい開発には使用しない従来のテクノロジです。 ActiveX を置き換える最新テクノロジの詳細については、「 [Activex コントロール](activex-controls.md)」を参照してください。

これらのトピックでは [、[表示時にアクティブ化] オプションをオフ](turning-off-the-activate-when-visible-option.md) にし、 [非アクティブのときにマウス操作](providing-mouse-interaction-while-inactive.md) を行うと、アクティブ化されるまでウィンドウを作成しないコントロールについて話し合います。 ウィンドウ [なしのアクティベーションを提供](providing-windowless-activation.md) するトピックでは、ウィンドウがアクティブになった場合でもウィンドウを作成しないコントロールについて説明します。

Windows には、OLE オブジェクトに対して主に2つの欠点があります。アクティブなときにオブジェクトが透明または非表示にならないようにし、コントロールのインスタンス化と表示に大きなオーバーヘッドを追加します。 通常、ウィンドウを作成するには、コントロールの作成時間の60% が必要です。 1つの共有ウィンドウ (通常はコンテナーの) といくつかのディスパッチコードを使用すると、コントロールは同じウィンドウサービスを受け取ります。通常、パフォーマンスが低下することはありません。 ウィンドウを使用すると、オブジェクトのオーバーヘッドがほとんど不要になります。

一部の最適化では、特定のコンテナーでコントロールが使用されている場合、必ずしもパフォーマンスが向上するとは限りません。 たとえば、1996より前にリリースされたコンテナーは、ウィンドウなしのアクティベーションをサポートしていなかったので、この機能を実装しても、古いコンテナーではメリットが得られません。 ただし、ほぼすべてのコンテナーで永続化がサポートされているため、コントロールの永続化コードを最適化すると、どのコンテナーでもパフォーマンスが向上する可能性があります。 1つの特定の種類のコンテナーでの使用を目的としてコントロールが特別に使用されている場合は、そのコンテナーでどの最適化がサポートされているかを調査することをお勧めします。 ただし、通常は、特定のコントロールに適用できるものと同じ数の手法を実装して、コントロールを確実に実行できるようにする必要があります。

これらの最適化の多くは、 [MFC ActiveX コントロールウィザード](reference/mfc-activex-control-wizard.md)の [ [コントロールの設定](reference/control-settings-mfc-activex-control-wizard.md) ] ページで実装できます。

### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>MFC ActiveX コントロールウィザードの OLE 最適化オプション

|MFC ActiveX コントロールウィザードのコントロール設定|アクション|説明|
|-------------------------------------------------------|------------|----------------------|
|[**表示時にアクティブにする**] チェックボックス|Clear|[[表示時にアクティブ化] オプションをオフにする](turning-off-the-activate-when-visible-option.md)|
|**ウィンドウなしのアクティブ化** チェックボックス|選択|[ウィンドウなしのアクティベーション](providing-windowless-activation.md)|
|クリッピングを行っていない **デバイスコンテキスト** のチェックボックス|選択|[クリッピングを行っていないデバイスコンテキストの使用](using-an-unclipped-device-context.md)|
|[**ちらつきなしでアクティブ化** する] チェックボックス|選択|[Flicker-Free アクティベーションの提供](providing-flicker-free-activation.md)|
|[**非アクティブ時のマウスポインター通知**] チェックボックス|選択|[非アクティブな状態でのマウス操作の提供](providing-mouse-interaction-while-inactive.md)|
|最適化された **描画コード** チェックボックス|選択|[コントロールの描画の最適化](optimizing-control-drawing.md)|

これらの最適化を実装するメンバー関数の詳細については、「 [COleControl](reference/colecontrol-class.md)」を参照してください。

詳細については、次を参照してください。

- [永続化と初期化の最適化](optimizing-persistence-and-initialization.md)

- [ウィンドウなしのアクティベーション](providing-windowless-activation.md)

- [[表示時にアクティブ化] オプションをオフにする](turning-off-the-activate-when-visible-option.md)

- [非アクティブな状態でのマウス操作の提供](providing-mouse-interaction-while-inactive.md)

- [Flicker-Free アクティベーションの提供](providing-flicker-free-activation.md)

- [クリッピングを行っていないデバイスコンテキストの使用](using-an-unclipped-device-context.md)

- [コントロールの描画の最適化](optimizing-control-drawing.md)

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール](mfc-activex-controls.md)
