---
description: '詳細情報: CAtlServiceModuleT:: Handler 関数'
title: 'CAtlServiceModuleT:: Handler 関数'
ms.date: 11/04/2016
helpviewer_keywords:
- Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
ms.openlocfilehash: 934c612b6fdfd47bb9966536cc335da58fbd38c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148370"
---
# <a name="catlservicemodulethandler-function"></a>CAtlServiceModuleT:: Handler 関数

`CAtlServiceModuleT::Handler` は、サービスコントロールマネージャー (SCM) がサービスの状態を取得するためにを呼び出し、さまざまな命令 (停止や一時停止など) を提供するルーチンです。 SCM は、サービスが実行する処理を示すために、操作コードをに渡し `Handler` ます。 既定の ATL によって生成されるサービスは、stop 命令のみを処理します。 SCM が stop 命令を渡した場合、サービスはプログラムが停止しようとしていることを SCM に通知します。 次に、サービスはを呼び出して、 `PostThreadMessage` 終了メッセージをそれ自体にポストします。 これにより、メッセージループが終了し、サービスは最終的に終了します。

詳細な手順を処理するには、コンストラクターで初期化されたデータメンバーを変更する必要があり `m_status` `CAtlServiceModuleT` ます。 このデータメンバーは、サービスコントロールパネルアプリケーションでサービスを選択したときに有効にするボタンを SCM に通知します。

## <a name="see-also"></a>関連項目

[サービス](../atl/atl-services.md)<br/>
[CAtlServiceModuleT:: Handler](../atl/reference/catlservicemodulet-class.md#handler)
