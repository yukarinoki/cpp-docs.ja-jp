---
title: IPersistStorageImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
ms.openlocfilehash: 320ef54c6148adf5354a6a7b1860a84e118dc6de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668989"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl クラス

このクラスは、実装、 [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage)インターフェイス。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IPersistStorageImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPersistStorageImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|オブジェクトのすべてのストレージ オブジェクトを解放し、HandsOff モードに入るように指示します。 ATL の実装では、S_OK を返します。|
|[IPersistStorageImpl::InitNew](#initnew)|新しい記憶域を初期化します。|
|[IPersistStorageImpl::IsDirty](#isdirty)|最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。|
|[IPersistStorageImpl::Load](#load)|指定された記憶域からオブジェクトのプロパティを読み込みます。|
|[IPersistStorageImpl::Save](#save)|オブジェクトのプロパティを指定したストレージに保存します。|
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|そのストレージ オブジェクトへの書き込みを通常モードに戻ることができますをオブジェクトに通知します。 ATL の実装では、S_OK を返します。|

## <a name="remarks"></a>Remarks

`IPersistStorageImpl` 実装して、 [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage)インターフェイス、オブジェクトの読み込みを要求するクライアントのできるし、ストレージを使用して、永続的なデータを保存します。

このクラスの実装には、クラスが必要です。`T`の実装を、`IPersistStreamInit`インターフェイスを介して使用できる`QueryInterface`します。 通常これはそのクラス`T`から派生する必要があります[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)、エントリを提供`IPersistStreamInit`で、 [COM マップ](com-map-macros.md)を使用して、[プロパティ マップ](property-map-macros.md)クラスの永続的なデータを記述します。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="getclassid"></a>  IPersistStorageImpl::GetClassID

オブジェクトの CLSID を取得します。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Remarks

参照してください[IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK にします。

##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage

オブジェクトのすべてのストレージ オブジェクトを解放し、HandsOff モードに入るように指示します。

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>Remarks

参照してください[IPersistStorage::HandsOffStorage](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) Windows SDK にします。

##  <a name="initnew"></a>  IPersistStorageImpl::InitNew

新しい記憶域を初期化します。

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>Remarks

ATL の実装のデリゲートを[IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit)インターフェイス。

参照してください[IPersistStorage:InitNew](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-initnew) Windows SDK にします。

##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty

最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>Remarks

ATL の実装のデリゲートを[IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit)インターフェイス。

参照してください[IPersistStorage:IsDirty](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-isdirty) Windows SDK にします。

##  <a name="load"></a>  IPersistStorageImpl::Load

指定された記憶域からオブジェクトのプロパティを読み込みます。

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>Remarks

ATL の実装のデリゲートを[IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit)インターフェイス。 `Load` 「コンテンツ」という名前のストリームを使用して、オブジェクトのデータを取得します。 [保存](#save)メソッドが最初にこのストリームを作成します。

参照してください[IPersistStorage:Load](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-load) Windows SDK にします。

##  <a name="save"></a>  IPersistStorageImpl::Save

オブジェクトのプロパティを指定したストレージに保存します。

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>Remarks

ATL の実装のデリゲートを[IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit)インターフェイス。 ときに`Save`最初が呼び出されると、指定された記憶域に「コンテンツ」をという名前のストリームを作成します。 このストリームは以降の呼び出しで使用し、`Save`と呼び出し[ロード](#load)します。

参照してください[IPersistStorage:Save](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-save) Windows SDK にします。

##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted

そのストレージ オブジェクトへの書き込みを通常モードに戻ることができますをオブジェクトに通知します。

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>Remarks

参照してください[IPersistStorage:SaveCompleted](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted) Windows SDK にします。

## <a name="see-also"></a>関連項目

[記憶域とストリーム](/windows/desktop/Stg/storages-and-streams)<br/>
[IPersistStreamInitImpl クラス](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[IPersistPropertyBagImpl クラス](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
