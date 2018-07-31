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
ms.openlocfilehash: 55c9b4b7e14a9572f5a8922b65a41a9a92a0d688
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337710"
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

## <a name="requirements"></a>要件  
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