---
title: Catlservicemodulet::handler 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs:
- C++
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c8dc0b0d41a18c775258e1eacddd8e4dbebdb3d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039219"
---
# <a name="catlservicemodulethandler-function"></a>Catlservicemodulet::handler 関数

`CAtlServiceModuleT::Handler` サービス コントロール マネージャー (SCM) は、サービスの状態を取得し、さまざまな命令 (など、停止または一時停止) を付けますを呼び出すルーチンです。 SCM を操作するコードを渡します`Handler`を示す、サービスが行う必要があります。 既定の ATL によって生成されたサービスでは、stop 命令のみ処理します。 SCM には、stop 命令が成功した場合、サービスは、プログラムが停止しようとしていますが、SCM を指示します。 サービスを呼び出して`PostThreadMessage`自体に中止メッセージを投稿します。 メッセージ ループを終了このし、サービスが最終的に終了します。

詳細な手順についてを処理するためには、変更する必要があります、`m_status`データ メンバーの初期化で、`CAtlServiceModuleT`コンス トラクター。 このデータ メンバーは、コントロール パネルの サービス アプリケーションで、サービスが選択されているときに有効にするボタンを SCM に指示します。

## <a name="see-also"></a>関連項目

[サービス](../atl/atl-services.md)<br/>
[Catlservicemodulet::handler](../atl/reference/catlservicemodulet-class.md#handler)

