---
title: 行セット オブジェクト インターフェイス
ms.date: 10/24/2018
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
ms.openlocfilehash: 3f20550558a4af4b286aa0de170763df979ffc5d
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556583"
---
# <a name="rowset-object-interfaces"></a>行セット オブジェクト インターフェイス

次の表では、行セット オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。

|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|
|---------------|---------------|--------------------------------------|
|[IAccessor](https://docs.microsoft.com/previous-versions/windows/desktop/ms719672(v=vs.85))|必須|はい|
|[IColumnsInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms724541(v=vs.85))|必須|はい|
|[IConvertType](https://docs.microsoft.com/previous-versions/windows/desktop/ms715926(v=vs.85))|必須|はい|
|[IRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms720986(v=vs.85))|必須|はい|
|[IRowsetInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms724541(v=vs.85))|必須|はい|
|[IChapteredRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms718180(v=vs.85))|Optional|いいえ|
|[IColumnsInfo2](https://docs.microsoft.com/previous-versions/windows/desktop/ms712953(v=vs.85))|Optional|いいえ|
|[IColumnsRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms722657(v=vs.85))|Optional|いいえ|
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|はい (ATL) を使用|
|[IDBAsynchStatus](https://docs.microsoft.com/previous-versions/windows/desktop/ms709832(v=vs.85))|Optional|いいえ|
|[IGetRow](https://docs.microsoft.com/previous-versions/windows/desktop/ms718047(v=vs.85))|Optional|いいえ|
|[IRowsetChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms715790(v=vs.85))|Optional|はい|
|[IRowsetChapterMember](https://docs.microsoft.com/previous-versions/windows/desktop/ms725430(v=vs.85))|Optional|いいえ|
|[IRowsetCurrentIndex](https://docs.microsoft.com/previous-versions/windows/desktop/ms709700(v=vs.85))|Optional|いいえ|
|[IRowsetFind](https://docs.microsoft.com/previous-versions/windows/desktop/ms724221(v=vs.85))|Optional|いいえ|
|[IRowsetIdentity](https://docs.microsoft.com/previous-versions/windows/desktop/ms715913(v=vs.85))|(ただし、レベル 0 のプロバイダーに必要) (省略可能)|はい|
|[IRowsetIndex](https://docs.microsoft.com/previous-versions/windows/desktop/ms719604(v=vs.85))|Optional|いいえ|
|[IRowsetLocate](https://docs.microsoft.com/previous-versions/windows/desktop/ms721190(v=vs.85))|Optional|はい|
|[IRowsetRefresh](https://docs.microsoft.com/previous-versions/windows/desktop/ms714892(v=vs.85))|Optional|いいえ|
|[IRowsetScroll](https://docs.microsoft.com/previous-versions/windows/desktop/ms712984(v=vs.85))|Optional|いいえ|
|[IRowsetUpdate](https://docs.microsoft.com/previous-versions/windows/desktop/ms714401(v=vs.85))|Optional|はい|
|[IRowsetView](https://docs.microsoft.com/previous-versions/windows/desktop/ms709755(v=vs.85))|Optional|いいえ|
|[ISupportErrorInfo](https://docs.microsoft.com/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|はい|
|[IRowsetBookmark](https://docs.microsoft.com/previous-versions/windows/desktop/ms714246(v=vs.85))|Optional|いいえ|

ウィザードで生成された行セット オブジェクトを実装して`IAccessor`、`IRowset`と`IRowsetInfo`継承を使用します。 `IAccessorImpl`両方の出力列をバインドします。 `IRowset`インターフェイスは、行のフェッチとデータを処理します。 `IRowsetInfo`インターフェイスは、行セット プロパティを処理します。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
