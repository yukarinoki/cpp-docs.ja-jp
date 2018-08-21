---
title: IDBCreateSessionImpl クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 756cc7ba203a1655bf5112d9c03e84707644f1e5
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337571"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl クラス
実装を提供、 [IDBCreateSession](https://msdn.microsoft.com/library/ms724076.aspx)インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 派生クラス。  
  
 *SessionClass*  
 セッション オブジェクト。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h 
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[CreateSession](#createsession)|データ ソース オブジェクトから新しいセッションを作成し、新しく作成されたセッションで要求されたインターフェイスを返します。|  
  
## <a name="remarks"></a>Remarks  
 データ ソース オブジェクトの必須インターフェイス。  

## <a name="createsession"></a> Idbcreatesessionimpl::createsession
データ ソース オブジェクトから新しいセッションを作成し、新しく作成されたセッションで要求されたインターフェイスを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession);  
```  
  
#### <a name="parameters"></a>パラメーター  
 参照してください[idbcreatesession::createsession](https://msdn.microsoft.com/library/ms714942.aspx)で、 *OLE DB プログラマーズ リファレンス*します。   
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)