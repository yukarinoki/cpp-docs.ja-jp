---
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
ms.openlocfilehash: 4b630a9728770a5e35e6d6300cf465b90238350c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209795"
---
# <a name="receiving-notifications"></a>通知の受信

OLE DB は、イベントの発生時に通知を受信するためのインターフェイスを提供します。 これらの詳細については、 **OLE DB プログラマーリファレンス**の[OLE DB オブジェクト通知](/previous-versions/windows/desktop/ms725406(v=vs.85))」を参照してください。 これらのイベントのセットアップでは、標準の COM 接続ポイント機構を使用します。 たとえば、`IRowsetNotify` を通じてイベントを取得する ATL オブジェクトは、`IRowsetNotify` をクラス派生リストに追加し、COM_INTERFACE_ENTRY マクロを使用して公開することによって、`IRowsetNotify` インターフェイスを実装します。

`IRowsetNotify` には、さまざまなタイミングで呼び出すことができる3つのメソッドがあります。 これらのメソッドのいずれかにのみ応答する場合は、 [IRowsetNotifyImpl](../../data/oledb/irowsetnotifyimpl-class.md)クラスを使用できます。これにより、目的のメソッドの E_NOTIMPL が返されます。

行セットを作成するときに、返された行セットオブジェクトが `IConnectionPointContainer`をサポートするように指定する必要があります。これは、通知を設定するために必要です。

次のコードは、ATL オブジェクトから行セットを開き、`AtlAdvise` 関数を使用して通知シンクを設定する方法を示しています。 `AtlAdvise` は、`AtlUnadvise`を呼び出すときに使用されるクッキーを返します。

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_IConnectionPointContainer, true);
```

その後、次のコードによって使用されます。

```cpp
product.Open(session, _T("Products"), &propset);

AtlAdvise(product.m_spRowset, GetUnknown(), IID_IRowsetNotify, &m_dwCookie);
```

## <a name="see-also"></a>参照

[アクセサーの使用](../../data/oledb/using-accessors.md)
