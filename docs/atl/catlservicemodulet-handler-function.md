---
title: Catlservicemodulet::handler 関数
ms.date: 11/04/2016
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
ms.openlocfilehash: e344fd36ad6c70a80486eef6a10eacd8a88a2baf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273375"
---
# <a name="catlservicemodulethandler-function"></a>Catlservicemodulet::handler 関数

`CAtlServiceModuleT::Handler` サービス コントロール マネージャー (SCM) は、サービスの状態を取得し、さまざまな命令 (など、停止または一時停止) を付けますを呼び出すルーチンです。 SCM を操作するコードを渡します`Handler`を示す、サービスが行う必要があります。 既定の ATL によって生成されたサービスでは、stop 命令のみ処理します。 SCM には、stop 命令が成功した場合、サービスは、プログラムが停止しようとしていますが、SCM を指示します。 サービスを呼び出して`PostThreadMessage`自体に中止メッセージを投稿します。 メッセージ ループを終了このし、サービスが最終的に終了します。

詳細な手順についてを処理するためには、変更する必要があります、`m_status`データ メンバーの初期化で、`CAtlServiceModuleT`コンス トラクター。 このデータ メンバーは、コントロール パネルの サービス アプリケーションで、サービスが選択されているときに有効にするボタンを SCM に指示します。

## <a name="see-also"></a>関連項目

[Services](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)
