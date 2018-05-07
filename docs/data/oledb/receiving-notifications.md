---
title: 通知を受け取る |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9e1dee5c63281c729cdb798a190938c6433aac0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="receiving-notifications"></a>通知の受信
OLE DB は、イベントが発生したときに通知を受信するためのインターフェイスを提供します。 については、 [OLE DB オブジェクト通知](https://msdn.microsoft.com/en-us/library/ms725406.aspx)で、 *OLE DB プログラマーズ リファレンス*です。 これらのイベントのセットアップでは、標準の COM 接続ポイント メカニズムを使用します。 たとえばが使用してイベントを取得する ATL オブジェクト`IRowsetNotify`を実装、`IRowsetNotify`インターフェイスを追加して`IRowsetNotify`クラスから派生した一覧、およびを通じて公開することを**COM_INTERFACE_ENTRY**マクロです。  
  
 `IRowsetNotify` 呼び出すことができるさまざまなタイミングで、次の 3 つのメソッドがあります。 これらのメソッドの 1 つのみに応答する場合は、使用、 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)クラス**E_NOTIMPL**の興味のあるいないメソッドです。  
  
 行セットを作成するときにする必要がありますプロバイダーに指示をサポートする、返された行セット オブジェクトを表示する**IConnectionPointContainer**、必要な通知を設定します。  
  
 次のコードは、ATL オブジェクトから行セットを開き、使用する方法を示しています、`AtlAdvise`通知シンクを設定する関数。 `AtlAdvise` 呼び出すときに使用される cookie が返されます`AtlUnadvise`です。  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IConnectionPointContainer, true);  
  

product.Open(session, _T("Products"), &propset);  
  

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);  
```  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)