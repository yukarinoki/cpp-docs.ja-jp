---
title: ATL コントロール:一般的サポート クラス
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
ms.openlocfilehash: c3d6f7588e333a27a8bc766d982660aaa4d984c9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818610"
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
