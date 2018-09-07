---
title: UI サポート クラス (ATL) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.ui
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, support classes
- user interfaces, ATL classes
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1aa28c172b4eb22366d2af55d040cb52c9e84a31
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755236"
---
# <a name="ui-support-classes"></a>UI サポート クラス

次のクラスは、一般的な UI のサポートを提供します。

- [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) Microsoft HTML 解析およびレンダリング エンジンへのインターフェイス。

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md)コントロールとコンテナーを通信に使用するプリンシパルのメソッドを提供します。 アクティブ化し、インプレース コントロールの非アクティブ化を管理します。

- [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md)インプレース コントロールの再アクティブ化を管理します。 ウィンドウなしのコントロール メッセージを受信するようにドラッグ アンド ドロップ操作に参加を有効にします。

- [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md)インプレース コントロールとコンテナー間の通信を支援します。

- [IViewObjectExImpl](../atl/reference/iviewobjecteximpl-class.md)自体を直接表示して、コンテナーの表示の変更を通知するためにコントロールできるようにします。 ちらつきなしの描画、および四角形以外の透過的なコントロール、およびヒット テスト サポートを提供します。

## <a name="related-articles"></a>関連トピック

[ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)

