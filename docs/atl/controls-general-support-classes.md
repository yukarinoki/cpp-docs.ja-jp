---
title: ATL コントロール:一般的サポート クラス
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.controls
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: bf5c1b9e2f4fb7414cc34d457bc0d8b1e27dcd91
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263001"
---
# <a name="controls-general-support-classes"></a>コントロール:一般的サポート クラス

次のクラスは、ATL コントロールの一般的なサポートを提供します。

- [CComControl](../atl/reference/ccomcontrol-class.md) ATL のコントロールに不可欠なヘルパー関数とデータ メンバーで構成します。

- [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md)コントロールに必要なメソッドを提供します。

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md)コントロールとコンテナーを通信に使用するプリンシパルのメソッドを提供します。 アクティブ化し、インプレース コントロールの非アクティブ化を管理します。

- [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md)コンテナー コントロールの読み込み時に遅延を避けるためのヘルプを 1 つの呼び出しに初期化を結合します。

- [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md)それ以外の場合に非アクティブなコントロールの最小限のマウスとの対話を提供します。

## <a name="sample-program"></a>サンプル プログラム

[ATLFire](../visual-cpp-samples.md)

## <a name="related-articles"></a>関連トピック

[ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)
