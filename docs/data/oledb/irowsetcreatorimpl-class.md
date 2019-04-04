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
ms.openlocfilehash: 8e3d5b3ff01dd37eec9f00dac2f2ce28013fc258
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659677"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl クラス

同じ機能を実行します。 `IObjectWithSite` OLE DB プロパティができますが、`DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`します。

## <a name="syntax"></a>構文

```cpp
template < class T >
class ATL_NO_VTABLE IRowsetCreatorImpl
   : public IObjectWithSiteImpl< T >
```

### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス`IRowsetCreator`します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atldb.h

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[SetSite](#setsite)|行セット オブジェクトを含むサイトを設定します。|

## <a name="remarks"></a>Remarks

このクラスから継承[IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite)と上書き[IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite)します。 プロバイダー コマンドまたはセッション オブジェクトは、行セットを作成するときに呼び出す`QueryInterface`、行セット オブジェクトを探して`IObjectWithSite`と呼び出し`SetSite`、行セット オブジェクトの引き渡し`IUnkown`サイト インターフェイスとしてインターフェイス。

## <a name="setsite"></a> Irowsetcreatorimpl::setsite

行セット オブジェクトを含むサイトを設定します。 詳細については、[IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite)を参照してください。

### <a name="syntax"></a>構文

```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);
```

#### <a name="parameters"></a>パラメーター

*pCreator*<br/>
[in]ポインター、`IUnknown`行セット オブジェクトを管理するサイトのインターフェイス ポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT です。

### <a name="remarks"></a>Remarks

さらに、`IRowsetCreatorImpl::SetSite`により、OLE DB`DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`プロパティ。

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)