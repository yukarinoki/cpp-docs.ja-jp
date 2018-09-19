---
title: プロバイダー サービスの既定のオーバーライド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- service providers [OLE DB]
- OLE DB services [OLE DB], overriding defaults
ms.assetid: 08e366c0-74d8-463b-93a6-d58a8dc195f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 561617628e79513434d498d4c5e5af8ff2c189be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104908"
---
# <a name="overriding-provider-service-defaults"></a>プロバイダー サービスの既定のオーバーライド

既定値として OLEDB_SERVICES のプロバイダーのレジストリ値が返されます、 [DBPROP_INIT_OLEDBSERVICES](/previous-versions/windows/desktop/ms716898\(v=vs.85\))データ ソース オブジェクトのプロパティを初期化します。  
  
レジストリ エントリが存在する限りは、プロバイダーのオブジェクトに集計され、ユーザーは、プロバイダーの既定の設定で有効なサービス設定を無効、`DBPROP_INIT_OLEDBSERVICES`プロパティを初期化する前にします。 有効にまたは特定のサービスを無効にするには、ユーザー一般に、現在の値を取得、`DBPROP_INIT_OLEDBSERVICES`プロパティ、設定を有効または無効になっている、特定のプロパティのビットをすべてクリアし、プロパティをリセットします。 `DBPROP_INIT_OLEDBSERVICES` OLE DB または ADO に渡される接続文字列で直接設定できますか`IDataInitialize::GetDatasource`します。 個々 のサービスを有効または無効にする、対応する値は、次の表に表示されます。  
  
|既定のサービスを有効になっています。|DBPROP_INIT_OLEDBSERVICES プロパティの値|接続文字列を値します。|  
|------------------------------|------------------------------------------------|--------------------------------|  
|すべてのサービス (既定値)|`DBPROPVAL_OS_ENABLEALL`|"OLE DB サービス =-1;"|  
|プールを除くすべてと自動確保|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_RESOURCEPOOLING &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT`|"OLE DB サービス =-4;"|  
|クライアント カーソルを除くすべて|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB サービス =-5;"|  
|プールで自動確保、およびクライアント カーソルを除くすべて|`DBPROPVAL_OS_ENABLEALL &`<br /><br /> `~DBPROPVAL_OS_TXNENLISTMENT &`<br /><br /> `~DBPROPVAL_OS_CLIENTCURSOR`|"OLE DB サービス =-7;"|  
|サービスはありません。|`~DBPROPVAL_OS_ENABLEALL`|"OLE DB サービス = 0;"|  
  
プロバイダーのレジストリ エントリが存在しない場合、コンポーネント マネージャーは、プロバイダーのオブジェクトを集計されないと、サービスが起動されない場合でも、ユーザーによって明示的に要求します。  
  
## <a name="see-also"></a>関連項目  

[リソース プール](/previous-versions/windows/desktop/ms713655\(v=vs.85\))   
[コンシューマーがリソース プールを使用する方法](/previous-versions/windows/desktop/ms715907\(v=vs.85\))   
[プロバイダーとの連携効果的にリソース プール](/previous-versions/windows/desktop/ms714906\(v=vs.85\))   
[OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)