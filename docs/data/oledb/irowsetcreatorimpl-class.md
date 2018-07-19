---
title: IRowsetCreatorImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0492994193130ffa6a547691490b4da1ae557c8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102138"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl クラス
同じ機能を実行`IObjectWithSite`OLE DB プロパティこともできますが、 **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**です。  
  
## <a name="syntax"></a>構文

```cpp
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス**IRowsetCreator**です。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|行セット オブジェクトを含むサイトを設定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスから継承[IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765)と上書き[IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)です。 プロバイダー コマンドまたはセッション オブジェクトは、行セットを作成するときに呼び出す`QueryInterface`を探して、行セット オブジェクト`IObjectWithSite`と呼び出し`SetSite`行セット オブジェクトの引き渡し**IUnkown**サイト インターフェイスとしてインターフェイスです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)