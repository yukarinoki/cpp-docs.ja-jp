---
description: 詳細については、「行セットオブジェクトインターフェイス」を参照してください。
title: Rowset オブジェクト インターフェイス
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
ms.openlocfilehash: fc7cbb0ee7c15cc7414144334018afc93888da01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316857"
---
# <a name="rowset-object-interfaces"></a>Rowset オブジェクト インターフェイス

次の表は、行セットオブジェクトの OLE DB によって定義される必須および省略可能なインターフェイスを示しています。

|インターフェイス|必須|OLE DB テンプレートによって実装されますか?|
|---------------|---------------|--------------------------------------|
|[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85))|Mandatory|はい|
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Mandatory|はい|
|[IConvertType](/previous-versions/windows/desktop/ms715926(v=vs.85))|Mandatory|はい|
|[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85))|Mandatory|はい|
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541(v=vs.85))|Mandatory|はい|
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180(v=vs.85))|省略可能|×|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953(v=vs.85))|省略可能|×|
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657(v=vs.85))|省略可能|×|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|はい (ATL を通じて)|
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832(v=vs.85))|省略可能|×|
|[IGetRow](/previous-versions/windows/desktop/ms718047(v=vs.85))|省略可能|×|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))|Optional|はい|
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430(v=vs.85))|省略可能|×|
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700(v=vs.85))|省略可能|×|
|[IRowsetFind](/previous-versions/windows/desktop/ms724221(v=vs.85))|省略可能|×|
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85))|省略可能 (レベル0のプロバイダーでは必須)|はい|
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604(v=vs.85))|省略可能|×|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))|Optional|はい|
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892(v=vs.85))|省略可能|×|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984(v=vs.85))|省略可能|×|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))|Optional|はい|
|[IRowsetView](/previous-versions/windows/desktop/ms709755(v=vs.85))|省略可能|×|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|はい|
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246(v=vs.85))|省略可能|×|

ウィザードで生成された行セットオブジェクトは、継承を通じて、、およびを実装し `IAccessor` `IRowset` `IRowsetInfo` ます。 は `IAccessorImpl` 両方の出力列をバインドします。 インターフェイスは、 `IRowset` 行とデータのフェッチを処理します。 インターフェイスは、 `IRowsetInfo` 行セットのプロパティを処理します。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
