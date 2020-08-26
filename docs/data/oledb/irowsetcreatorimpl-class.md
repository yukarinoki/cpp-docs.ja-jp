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
ms.openlocfilehash: c1ad2c5e97dfe975a3b545e44b512dff7bf512a0
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843445"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl クラス

と同じ機能を実行し `IObjectWithSite` ますが、OLE DB のプロパティも有効に `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` します。

## <a name="syntax"></a>構文

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IRowsetCreator` 。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

| 名前 | 説明 |
|-|-|
|[SetSite](#setsite)|行セットオブジェクトを含むサイトを設定します。|

## <a name="remarks"></a>解説

このクラスは、 [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite) から継承し、 [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)をオーバーライドします。 プロバイダーコマンドまたはセッションオブジェクトが行セットを作成すると、行セットオブジェクトでを呼び出して、行セット `QueryInterface` `IObjectWithSite` `SetSite` オブジェクトの `IUnkown` インターフェイスをサイトインターフェイスとして渡します。

## <a name="irowsetcreatorimplsetsite"></a><a name="setsite"></a> IRowsetCreatorImpl:: SetSite

行セットオブジェクトを含むサイトを設定します。 詳細については、「 [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)」を参照してください。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>パラメーター

*pCreator*<br/>
から `IUnknown` 行セットオブジェクトを管理しているサイトのインターフェイスポインターへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>解説

さらに、に `IRowsetCreatorImpl::SetSite` よって OLE DB プロパティが有効になり `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` ます。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)
