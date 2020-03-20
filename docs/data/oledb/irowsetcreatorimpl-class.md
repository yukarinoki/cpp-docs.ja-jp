---
title: IRowsetCreatorImpl クラス
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
ms.openlocfilehash: 8c4253d469c510f5e6eb996ed510ef836844899d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "79544580"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl クラス

`IObjectWithSite` と同じ機能を実行しますが、OLE DB プロパティ `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`も有効にします。

## <a name="syntax"></a>構文

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`IRowsetCreator`から派生したクラス。

## <a name="requirements"></a>要件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[SetSite](#setsite)|行セットオブジェクトを含むサイトを設定します。|

## <a name="remarks"></a>コメント

このクラスは、 [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite)から継承し、 [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)をオーバーライドします。 プロバイダーコマンドまたはセッションオブジェクトは、行セットを作成するときに、`IObjectWithSite` を検索する行セットオブジェクトに対して `QueryInterface` を呼び出し、行セットオブジェクトの `IUnkown` インターフェイスをサイトインターフェイスとして渡し `SetSite` を呼び出します。

## <a name="irowsetcreatorimplsetsite"></a><a name="setsite"></a>IRowsetCreatorImpl:: SetSite

行セットオブジェクトを含むサイトを設定します。 詳細については、「 [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)」を参照してください。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>パラメーター

*pCreator*<br/>
から行セットオブジェクトを管理しているサイトの `IUnknown` インターフェイスポインターへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>コメント

さらに、`IRowsetCreatorImpl::SetSite` によって OLE DB `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` プロパティが有効になります。

## <a name="see-also"></a>参照

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)