---
title: プロバイダー サービスの既定をオーバーライドする |Microsoft ドキュメント
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
ms.openlocfilehash: be802c1c3c6ba4b77d1418c9c620840e9ab10170
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110081"
---
# <a name="overriding-provider-service-defaults"></a>プロバイダー サービスの既定のオーバーライド
プロバイダーのレジストリ値を**OLEDB_SERVICES**の既定値として返される、 [DBPROP_INIT_OLEDBSERVICES](https://msdn.microsoft.com/en-us/library/ms716898.aspx)データ ソース オブジェクトのプロパティを初期化します。  
  
 レジストリ エントリが存在する限り、プロバイダーのオブジェクトの集計し、ユーザーは、プロバイダーの既定の設定して有効にするサービスの設定をオーバーライドできます、 **DBPROP_INIT_OLEDBSERVICES**プロパティ初期化の前にします。 有効にするにまたは特定のサービスを無効にするには、ユーザー、通常、現在の値を取得、 **DBPROP_INIT_OLEDBSERVICES**設定プロパティ、またはを有効または無効になっている、特定のプロパティのビットをクリアし、プロパティをリセットします。 **DBPROP_INIT_OLEDBSERVICES** OLE DB や ADO に渡された接続文字列で直接設定することができますか**idatainitialize::getdatasource**です。 個々 のサービスの有効/無効にする、対応する値は、次の表に一覧表示されます。  
  
|既定のサービスを有効になっています。|DBPROP_INIT_OLEDBSERVICES プロパティ値|接続文字列内の値します。|  
|------------------------------|------------------------------------------------|--------------------------------|  
|すべてのサービス (既定値)|**DBPROPVAL_OS_ENABLEALL**|"OLE DB サービス =-1 です"。|  
|以外のすべてのプールと自動確保|**DBPROPVAL_OS_ENABLEALL (&AMP; A)**<br /><br /> **~DBPROPVAL_OS_RESOURCEPOOLING &**<br /><br /> **~DBPROPVAL_OS_TXNENLISTMENT**|"OLE DB サービス =-4;"|  
|以外のすべてのクライアント カーソル|**DBPROPVAL_OS_ENABLEALL** &<br /><br /> ~**DBPROPVAL_OS_CLIENTCURSOR**|"OLE DB サービス =-5;"|  
|プールが、自動確保、およびクライアント カーソルを除くすべて|**DBPROPVAL_OS_ENABLEALL (&AMP; A)**<br /><br /> **~ DBPROPVAL_OS_TXNENLISTMENT (&AMP; A)**<br /><br /> **~DBPROPVAL_OS_CLIENTCURSOR**|"OLE DB サービス =-7;"|  
|サービスはありません。|~**DBPROPVAL_OS_ENABLEALL**|"OLE DB サービス = 0 になります"。|  
  
 プロバイダーのレジストリ エントリが存在しない場合は、コンポーネント マネージャーは、プロバイダーのオブジェクトを集計されないと、サービスは起動しません、ユーザーによって明示的に要求された場合でもです。  
  
## <a name="see-also"></a>関連項目  
 [リソース プール](https://msdn.microsoft.com/en-us/library/ms713655.aspx)   
 [コンシューマーがリソース プールを使用する方法](https://msdn.microsoft.com/en-us/library/ms715907.aspx)   
 [プロバイダーのしくみ効果的では、リソース プール](https://msdn.microsoft.com/en-us/library/ms714906.aspx)   
 [OLE DB サービスの有効化と無効化](../../data/oledb/enabling-and-disabling-ole-db-services.md)