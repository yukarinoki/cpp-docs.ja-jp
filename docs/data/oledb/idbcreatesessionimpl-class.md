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
ms.openlocfilehash: 7f148176b8d5d0c85f3e899cfd117bbb381794b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047396"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl クラス

実装を提供、 [IDBCreateSession](/previous-versions/windows/desktop/ms724076\(v=vs.85\))インターフェイス。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>パラメーター  

*T*<br/>
派生クラス。  
  
*SessionClass*<br/>
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

参照してください[idbcreatesession::createsession](/previous-versions/windows/desktop/ms714942\(v=vs.85\))で、 *OLE DB プログラマーズ リファレンス*します。   
  
## <a name="see-also"></a>関連項目  

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)