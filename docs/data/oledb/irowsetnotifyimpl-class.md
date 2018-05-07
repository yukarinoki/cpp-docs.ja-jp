---
title: IRowsetNotifyImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyImpl class
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 860b735863acbcac869a4a297984084946aaf028
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl クラス
実装し、登録[IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)コンシューマー (とも呼ばれる、「シンク」) の通知を処理できるようにします。  
  
## <a name="syntax"></a>構文

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[OnFieldChange](../../data/oledb/irowsetnotifyimpl-onfieldchange.md)|列の値の変更をコンシューマーに通知します。|  
|[OnRowChange](../../data/oledb/irowsetnotifyimpl-onrowchange.md)|行に対する最初の変更や行全体に影響する変更のコンシューマーに通知します。|  
|[OnRowsetChange](../../data/oledb/irowsetnotifyimpl-onrowsetchange.md)|行セット全体に影響する変更をコンシューマーに通知します。|  
  
## <a name="remarks"></a>コメント  
 参照してください[通知の受信](../../data/oledb/receiving-notifications.md)に関するコンシューマーのコネクション ポイントのインターフェイスを実装します。  
  
 `IRowsetNotifyImpl` ダミー実装を提供`IRowsetNotify`、用の空の関数で、`IRowsetNotify`メソッド[OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx)、 [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx)、および[OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx). 実装するときに、このクラスから継承する場合、`IRowsetNotify`インターフェイスに必要なメソッドのみを実装することができます。 また、他のメソッドの空の実装を提供する必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [IRowsetNotifyCP クラス](../../data/oledb/irowsetnotifycp-class.md)