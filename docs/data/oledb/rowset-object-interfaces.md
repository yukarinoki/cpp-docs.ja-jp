---
title: 行セット オブジェクト インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- interfaces, OLE DB
- OLE DB, interfaces
- rowset objects [OLE DB]
- OLE DB provider templates, object interfaces
- interfaces, list of
ms.assetid: 0d7a5d48-2fe4-434f-a84b-157c1fdc3494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 58986c7b80f2bb84b222047efc7aae359c0cd5b1
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083894"
---
# <a name="rowset-object-interfaces"></a>行セット オブジェクト インターフェイス

次の表では、行セット オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](/previous-versions/windows/desktop/ms719672)|必須|はい|  
|[IColumnsInfo](/previous-versions/windows/desktop/ms724541)|必須|はい|  
|[IConvertType](/previous-versions/windows/desktop/ms715926)|必須|はい|  
|[IRowset](/previous-versions/windows/desktop/ms720986)|必須|はい|  
|[IRowsetInfo](/previous-versions/windows/desktop/ms724541)|必須|はい|  
|[IChapteredRowset](/previous-versions/windows/desktop/ms718180)|Optional|いいえ|  
|[IColumnsInfo2](/previous-versions/windows/desktop/ms712953)|Optional|いいえ|  
|[IColumnsRowset](/previous-versions/windows/desktop/ms722657)|Optional|いいえ|  
|[IConnectionPointContainer](/windows/desktop/api/ocidl/nn-ocidl-iconnectionpointcontainer)|Optional|はい (ATL) を使用|  
|[IDBAsynchStatus](/previous-versions/windows/desktop/ms709832)|Optional|いいえ|  
|[IGetRow](/previous-versions/windows/desktop/ms718047)|Optional|いいえ|  
|[IRowsetChange](/previous-versions/windows/desktop/ms715790)|Optional|はい|  
|[IRowsetChapterMember](/previous-versions/windows/desktop/ms725430)|Optional|いいえ|  
|[IRowsetCurrentIndex](/previous-versions/windows/desktop/ms709700)|Optional|いいえ|  
|[IRowsetFind](/previous-versions/windows/desktop/ms724221)|Optional|いいえ|  
|[IRowsetIdentity](/previous-versions/windows/desktop/ms715913)|(ただし、レベル 0 のプロバイダーに必要) (省略可能)|はい|  
|[IRowsetIndex](/previous-versions/windows/desktop/ms719604)|Optional|いいえ|  
|[IRowsetLocate](/previous-versions/windows/desktop/ms721190)|Optional|はい|  
|[IRowsetRefresh](/previous-versions/windows/desktop/ms714892)|Optional|いいえ|  
|[IRowsetScroll](/previous-versions/windows/desktop/ms712984)|Optional|いいえ|  
|[IRowsetUpdate](/previous-versions/windows/desktop/ms714401)|Optional|はい|  
|[IRowsetView](/previous-versions/windows/desktop/ms709755)|Optional|いいえ|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|Optional|はい|  
|[IRowsetBookmark](/previous-versions/windows/desktop/ms714246)|Optional|いいえ|  
  
ウィザードで生成された行セット オブジェクトを実装して`IAccessor`、`IRowset`と`IRowsetInfo`継承を使用します。 `IAccessorImpl`両方の出力列をバインドします。 `IRowset`インターフェイスは、行のフェッチとデータを処理します。 `IRowsetInfo`インターフェイスは、行セット プロパティを処理します。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)