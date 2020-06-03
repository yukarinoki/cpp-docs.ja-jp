---
title: Rowset オブジェクト インターフェイス
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
ms.openlocfilehash: d9c2c61714a98d9de09d8657352a14f296e35a58
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544544"
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
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180(v=vs.85))|［オプション］|いいえ|
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953(v=vs.85))|［オプション］|いいえ|
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657(v=vs.85))|［オプション］|いいえ|
|[IConnectionPointContainer](/windows/win32/api/ocidl/nn-ocidl-iconnectionpointcontainer)|［オプション］|はい (ATL を通じて)|
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832(v=vs.85))|［オプション］|いいえ|
|[IGetRow](/previous-versions/windows/desktop/ms718047(v=vs.85))|［オプション］|いいえ|
|[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))|［オプション］|はい|
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430(v=vs.85))|［オプション］|いいえ|
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700(v=vs.85))|［オプション］|いいえ|
|[IRowsetFind](/previous-versions/windows/desktop/ms724221(v=vs.85))|［オプション］|いいえ|
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913(v=vs.85))|省略可能 (レベル0のプロバイダーでは必須)|はい|
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604(v=vs.85))|［オプション］|いいえ|
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))|［オプション］|はい|
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892(v=vs.85))|［オプション］|いいえ|
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984(v=vs.85))|［オプション］|いいえ|
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))|［オプション］|はい|
|[IRowsetView](/previous-versions/windows/desktop/ms709755(v=vs.85))|［オプション］|いいえ|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|［オプション］|はい|
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246(v=vs.85))|［オプション］|いいえ|

ウィザードで生成された行セットオブジェクトは、継承によって `IAccessor`、`IRowset`、および `IRowsetInfo` を実装します。 `IAccessorImpl` は、両方の出力列をバインドします。 `IRowset` インターフェイスは、行とデータをフェッチします。 `IRowsetInfo` インターフェイスは、行セットのプロパティを処理します。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
