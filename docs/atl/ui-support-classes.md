---
description: 詳細については、「UI Support Classes」を参照してください。
title: UI サポートクラス (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- user interfaces, support classes
- user interfaces, ATL classes
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
ms.openlocfilehash: d8bc345db05ef886c2a054356ae6bd8d299c8045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138256"
---
# <a name="ui-support-classes"></a>UI サポートクラス

次のクラスは、UI の一般的なサポートを提供します。

- [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) Microsoft HTML 解析およびレンダリングエンジンへのインターフェイスです。

- [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) コンテナーがコントロールと通信するための主要なメソッドを提供します。 インプレースコントロールのアクティブ化と非アクティブ化を管理します。

- [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md) インプレースコントロールの再アクティブ化を管理します。 ウィンドウなしのコントロールがメッセージを受信できるようにします。ドラッグアンドドロップ操作に参加することもできます。

- [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md) インプレースコントロールとそのコンテナーとの間の通信を支援します。

- [Iviewの Teximpl](../atl/reference/iviewobjecteximpl-class.md) コントロールがそれ自体を直接表示し、そのディスプレイの変更をコンテナーに通知できるようにします。 ちらつきなしの描画、四角形でない透明なコントロール、およびヒットテストのサポートを提供します。

## <a name="related-articles"></a>関連記事

[ATL チュートリアル](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>関連項目

[クラスの概要](../atl/atl-class-overview.md)
