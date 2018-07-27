---
title: IRowsetIdentityImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
dev_langs:
- C++
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5cbafe7f43d8a6c7acfaccb52fd22b595bdd0ec4
ms.sourcegitcommit: e5792fcb89b9ba64c401f90f4f26a8e45d4a2359
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2018
ms.locfileid: "39322099"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl クラス
OLE DB 実装[IRowsetIdentity](https://msdn.microsoft.com/library/ms715913.aspx)インターフェイスで、行の id のテストが可能です。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class RowClass = CSimpleRow>  
class ATL_NO_VTABLE IRowsetIdentityImpl   
   : public IRowsetIdentity  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生したクラス`IRowsetIdentityImpl`します。  
  
 *RowClass*  
 記憶域ユニット、`HROW`します。  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[IsSameRow](#issamerow)|同じ行を参照しているかどうかを 2 つの行ハンドルを比較します。|  
  
## <a name="issamerow"></a> Irowsetidentityimpl::issamerow
同じ行を参照しているかどうかを 2 つの行ハンドルを比較します。  
  
### <a name="syntax"></a>構文  
  
```cpp
      STDMETHOD(IsSameRow )(HROW hThisRow,  
   HROW hThatRow);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/library/ms719629.aspx)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  
 行ハンドルを比較するには、このメソッドのキャスト、`HROW`ハンドルと`RowClass`メンバーおよび呼び出し`memcmp`ポインターにします。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
