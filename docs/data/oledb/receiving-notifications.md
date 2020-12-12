---
description: '詳細情報: 通知の受信'
title: 通知の受信
ms.date: 10/24/2018
helpviewer_keywords:
- notifications [C++], OLE DB consumers
- receiving notifications in OLE DB
- events [C++], notifications in OLE DB
- notifications [C++], events
- OLE DB consumers, notifications
- rowsets, event notifications
- OLE DB providers, notifications
ms.assetid: 305a1103-0c87-40c8-94bc-7fbbdd52ae32
ms.openlocfilehash: 1885223a7d2b3e932cf449312eab989ecf1d2554
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316883"
---
# <a name="receiving-notifications"></a>通知の受信

OLE DB は、イベントの発生時に通知を受信するためのインターフェイスを提供します。 これらの詳細については、 **OLE DB プログラマーリファレンス** の [OLE DB オブジェクト通知](/previous-versions/windows/desktop/ms725406(v=vs.85))」を参照してください。 これらのイベントのセットアップでは、標準の COM 接続ポイント機構を使用します。 たとえば、を介してイベントを取得する ATL オブジェクトは、 `IRowsetNotify` `IRowsetNotify` `IRowsetNotify` クラス派生リストにを追加し、COM_INTERFACE_ENTRY マクロを使用してそれを公開することで、インターフェイスを実装します。

`IRowsetNotify` には3つのメソッドがあり、さまざまなタイミングで呼び出すことができます。 これらのメソッドのいずれかにのみ応答する場合は、 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md) クラスを使用できます。これにより、目的のメソッドの E_NOTIMPL が返されます。

行セットを作成するときに、返された行セットオブジェクトがサポートするようにプロバイダーに通知する必要があります `IConnectionPointContainer` 。これは、通知を設定するために必要です。

次のコードは、ATL オブジェクトから行セットを開き、関数を使用して通知シンクを設定する方法を示して `AtlAdvise` います。 `AtlAdvise` を呼び出すときに使用されるクッキーを返し `AtlUnadvise` ます。

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

その後、次のコードによって使用されます。

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)
