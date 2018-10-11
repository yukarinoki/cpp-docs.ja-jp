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
ms.openlocfilehash: b47cbf2b30323cf51881ebaae9f546001a2d61b3
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081501"
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl クラス

OLE DB 実装[IRowsetIdentity](/previous-versions/windows/desktop/ms715913)インターフェイスで、行の id のテストが可能です。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class RowClass = CSimpleRow>  
class ATL_NO_VTABLE IRowsetIdentityImpl   
   : public IRowsetIdentity  
```  
  
### <a name="parameters"></a>パラメーター  

*T*<br/>
派生したクラス`IRowsetIdentityImpl`します。  
  
*RowClass*<br/>
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

参照してください[IRowsetIdentity::IsSameRow](/previous-versions/windows/desktop/ms719629)で、 *OLE DB プログラマーズ リファレンス*します。  
  
### <a name="remarks"></a>Remarks  

行ハンドルを比較するには、このメソッドのキャスト、`HROW`ハンドルと`RowClass`メンバーおよび呼び出し`memcmp`ポインターにします。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)