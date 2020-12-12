---
description: '詳細情報: IDBCreateSessionImpl クラス'
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
ms.openlocfilehash: 8456ce4ec7bde5721ac6753ed9ec64d69c63e41f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317481"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl クラス

[IDBCreateSession](/previous-versions/windows/desktop/ms724076(v=vs.85))インターフェイスの実装を提供します。

## <a name="syntax"></a>構文

```cpp
template <class T, class SessionClass>
class ATL_NO_VTABLE IDBCreateSessionImpl
   : public IDBCreateSession
```

### <a name="parameters"></a>パラメーター

*T*<br/>
クラス (から派生)

*SessionClass*<br/>
セッションオブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

| 名前 | 説明 |
|-|-|
|[CreateSession](#createsession)|データソースオブジェクトから新しいセッションを作成し、新しく作成されたセッションで要求されたインターフェイスを返します。|

## <a name="remarks"></a>解説

データソースオブジェクトの必須のインターフェイスです。

## <a name="idbcreatesessionimplcreatesession"></a><a name="createsession"></a> IDBCreateSessionImpl:: CreateSession

データソースオブジェクトから新しいセッションを作成し、新しく作成されたセッションで要求されたインターフェイスを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppDBSession);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス* の「 [IDBCreateSession:: CreateSession](/previous-versions/windows/desktop/ms714942(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
