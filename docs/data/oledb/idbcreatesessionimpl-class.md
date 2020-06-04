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
ms.openlocfilehash: cff1ca374c9489cb9c5df0dad153c4bf7a4cbc9e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210783"
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

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="interface-methods"></a>インターフェイス メソッド

|||
|-|-|
|[CreateSession](#createsession)|データソースオブジェクトから新しいセッションを作成し、新しく作成されたセッションで要求されたインターフェイスを返します。|

## <a name="remarks"></a>解説

データソースオブジェクトの必須のインターフェイスです。

## <a name="idbcreatesessionimplcreatesession"></a><a name="createsession"></a>IDBCreateSessionImpl:: CreateSession

データソースオブジェクトから新しいセッションを作成し、新しく作成されたセッションで要求されたインターフェイスを返します。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,
   REFIID riid,
   IUnknown ** ppDBSession);
```

#### <a name="parameters"></a>パラメーター

*OLE DB プログラマーリファレンス*の「 [IDBCreateSession:: CreateSession](/previous-versions/windows/desktop/ms714942(v=vs.85)) 」を参照してください。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
