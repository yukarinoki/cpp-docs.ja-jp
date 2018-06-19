---
title: CAtlServiceModuleT::Start 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da8d7358c634416941a551c93c6a2772549a3fd2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357278"
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT::Start 関数
サービスが実行されると **_tWinMain**呼び出し**起動時**、さらに呼び出す`CAtlServiceModuleT::Start`です。  
  
 `CAtlServiceModuleT::Start` 配列を設定**SERVICE_TABLE_ENTRY**のスタートアップの機能を各サービスをマップする構造。 この配列は、Win32 API 関数に渡され[余分](http://msdn.microsoft.com/library/windows/desktop/ms686324)です。 1 つの EXE は理論上は、複数のサービスを処理する可能性があり、配列が複数あって**SERVICE_TABLE_ENTRY**構造体。 現時点では、ただし、ATL で生成されたサービスをサポートしている EXE ごとにサービスを 1 つだけです。 したがって、配列では、サービス名を含む 1 つのエントリと **_ServiceMain**スタートアップ関数とします。 **_ServiceMain**の静的メンバー関数は、`CAtlServiceModuleT`非静的メンバー関数を呼び出す`ServiceMain`です。  
  
> [!NOTE]
>  エラー**余分**にサービス コントロールへの接続マネージャー (SCM) こと可能性があります、プログラムがサービスとして実行されていないこと。 この場合、呼び出しプログラム`CAtlServiceModuleT::Run`直接、プログラムがローカル サーバーとして実行できるようにします。 ローカル サーバーとして、プログラムの実行の詳細については、次を参照してください。[デバッグのヒント](../atl/debugging-tips.md)です。  
  
## <a name="see-also"></a>関連項目  
 [サービス](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)

