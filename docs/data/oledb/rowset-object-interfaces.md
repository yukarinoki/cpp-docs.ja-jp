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
ms.openlocfilehash: e8a1a5f5256087a8869426489fe01250b16fc598
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340512"
---
# <a name="rowset-object-interfaces"></a>行セット オブジェクト インターフェイス
次の表では、行セット オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|  
|---------------|---------------|--------------------------------------|  
|[IAccessor](https://msdn.microsoft.com/library/ms719672.aspx)|必須|[はい]|  
|[IColumnsInfo](https://msdn.microsoft.com/library/ms724541.aspx)|必須|[はい]|  
|[IConvertType](https://msdn.microsoft.com/library/ms715926.aspx)|必須|[はい]|  
|[IRowset](https://msdn.microsoft.com/library/ms720986.aspx)|必須|[はい]|  
|[IRowsetInfo](https://msdn.microsoft.com/library/ms724541.aspx)|必須|[はい]|  
|[IChapteredRowset](https://msdn.microsoft.com/library/ms718180.aspx)|Optional|いいえ|  
|[IColumnsInfo2](https://msdn.microsoft.com/library/ms712953.aspx)|Optional|いいえ|  
|[IColumnsRowset](https://msdn.microsoft.com/library/ms722657.aspx)|Optional|いいえ|  
|[IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Optional|はい (ATL) を使用|  
|[IDBAsynchStatus](https://msdn.microsoft.com/library/ms709832.aspx)|Optional|いいえ|  
|[IGetRow](https://msdn.microsoft.com/library/ms718047.aspx)|Optional|いいえ|  
|[IRowsetChange](https://msdn.microsoft.com/library/ms715790.aspx)|Optional|[はい]|  
|[IRowsetChapterMember](https://msdn.microsoft.com/library/ms725430.aspx)|Optional|いいえ|  
|[IRowsetCurrentIndex](https://msdn.microsoft.com/library/ms709700.aspx)|Optional|いいえ|  
|[IRowsetFind](https://msdn.microsoft.com/library/ms724221.aspx)|Optional|いいえ|  
|[IRowsetIdentity](https://msdn.microsoft.com/library/ms715913.aspx)|(ただし、レベル 0 のプロバイダーに必要) (省略可能)|[はい]|  
|[IRowsetIndex](https://msdn.microsoft.com/library/ms719604.aspx)|Optional|いいえ|  
|[IRowsetLocate](https://msdn.microsoft.com/library/ms721190.aspx)|Optional|[はい]|  
|[IRowsetRefresh](https://msdn.microsoft.com/library/ms714892.aspx)|Optional|いいえ|  
|[IRowsetScroll](https://msdn.microsoft.com/library/ms712984.aspx)|Optional|いいえ|  
|[IRowsetUpdate](https://msdn.microsoft.com/library/ms714401.aspx)|Optional|[はい]|  
|[IRowsetView](https://msdn.microsoft.com/library/ms709755.aspx)|Optional|いいえ|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|Optional|[はい]|  
|[IRowsetBookmark](https://msdn.microsoft.com/library/ms714246.aspx)|Optional|いいえ|  
  
 ウィザードで生成された行セット オブジェクトを実装して`IAccessor`、`IRowset`と`IRowsetInfo`継承を使用します。 `IAccessorImpl`両方の出力列をバインドします。 `IRowset`インターフェイスは、行のフェッチとデータを処理します。 `IRowsetInfo`インターフェイスは、行セット プロパティを処理します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)