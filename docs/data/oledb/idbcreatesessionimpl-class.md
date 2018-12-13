---
title: IDBCreateSessionImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
ms.openlocfilehash: ecc06bf5e3514ea87c86de17dbafd59b9da9f8b6
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556423"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl クラス

実装を提供、 [IDBCreateSession](https://docs.microsoft.com/previous-versions/windows/desktop/ms724076(v=vs.85))インターフェイス。

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

## <a name="requirements"></a>必要条件

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

参照してください[idbcreatesession::createsession](https://docs.microsoft.com/previous-versions/windows/desktop/ms714942(v=vs.85))で、 *OLE DB プログラマーズ リファレンス*します。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)