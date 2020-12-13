---
description: '詳細情報: IPersistStorageImpl クラス'
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
ms.openlocfilehash: 1d3d996886b587c25988139eed62e409650b5d4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139335"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl クラス

このクラスは、 [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) インターフェイスを実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス `IPersistStorageImpl` 。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPersistStorageImpl:: GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|
|[IPersistStorageImpl:: ハンドラー Soffstorage](#handsoffstorage)|オブジェクトに対して、すべてのストレージオブジェクトを解放し、HandsOff モードに移行するように指示します。 ATL 実装は S_OK を返します。|
|[IPersistStorageImpl:: InitNew](#initnew)|新しいストレージを初期化します。|
|[IPersistStorageImpl:: IsDirty](#isdirty)|オブジェクトのデータが最後に保存されてから変更されたかどうかを確認します。|
|[IPersistStorageImpl:: Load](#load)|指定されたストレージからオブジェクトのプロパティを読み込みます。|
|[IPersistStorageImpl:: Save](#save)|オブジェクトのプロパティを指定されたストレージに保存します。|
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|ストレージオブジェクトに書き込むために通常モードに戻ることができることをオブジェクトに通知します。 ATL 実装は S_OK を返します。|

## <a name="remarks"></a>解説

`IPersistStorageImpl`[IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage)インターフェイスを実装します。これにより、クライアントは、オブジェクトがストレージを使用して、永続データを読み込んだ後保存するように要求できます。

このクラスを実装 `T` するには、を `IPersistStreamInit` 介して使用可能なインターフェイスの実装を行うクラスが必要です `QueryInterface` 。 通常、これは、クラスが `T` [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)から派生し、 `IPersistStreamInit` [COM マップ](com-map-macros.md)にのエントリを提供し、 [プロパティマップ](property-map-macros.md) を使用してクラスの永続データを記述する必要があることを意味します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [atl プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>要件

**ヘッダー:** atlcom. h

## <a name="ipersiststorageimplgetclassid"></a><a name="getclassid"></a> IPersistStorageImpl:: GetClassID

オブジェクトの CLSID を取得します。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>解説

Windows SDK の「 [IPersist:: GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) 」を参照してください。

## <a name="ipersiststorageimplhandsoffstorage"></a><a name="handsoffstorage"></a> IPersistStorageImpl:: ハンドラー Soffstorage

オブジェクトに対して、すべてのストレージオブジェクトを解放し、HandsOff モードに移行するように指示します。

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IPersistStorage::](/windows/win32/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) の実行」を参照してください。

## <a name="ipersiststorageimplinitnew"></a><a name="initnew"></a> IPersistStorageImpl:: InitNew

新しいストレージを初期化します。

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>解説

ATL 実装は、 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) インターフェイスにデリゲートします。

Windows SDK の「 [IPersistStorage: InitNew](/windows/win32/api/objidl/nf-objidl-ipersiststorage-initnew) 」を参照してください。

## <a name="ipersiststorageimplisdirty"></a><a name="isdirty"></a> IPersistStorageImpl:: IsDirty

オブジェクトのデータが最後に保存されてから変更されたかどうかを確認します。

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>解説

ATL 実装は、 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) インターフェイスにデリゲートします。

Windows SDK の「 [IPersistStorage: IsDirty](/windows/win32/api/objidl/nf-objidl-ipersiststorage-isdirty) 」を参照してください。

## <a name="ipersiststorageimplload"></a><a name="load"></a> IPersistStorageImpl:: Load

指定されたストレージからオブジェクトのプロパティを読み込みます。

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>解説

ATL 実装は、 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) インターフェイスにデリゲートします。 `Load` "Contents" という名前のストリームを使用して、オブジェクトのデータを取得します。 [Save](#save)メソッドは、このストリームを最初に作成します。

「 [IPersistStorage: Load](/windows/win32/api/objidl/nf-objidl-ipersiststorage-load) in the Windows SDK」を参照してください。

## <a name="ipersiststorageimplsave"></a><a name="save"></a> IPersistStorageImpl:: Save

オブジェクトのプロパティを指定されたストレージに保存します。

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>解説

ATL 実装は、 [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) インターフェイスにデリゲートします。 `Save`が最初に呼び出されると、指定されたストレージに "Contents" という名前のストリームが作成されます。 このストリームは、後での呼び出し `Save` と、 [読み込み](#load)の呼び出しで使用されます。

Windows SDK の「 [IPersistStorage: Save](/windows/win32/api/objidl/nf-objidl-ipersiststorage-save) 」を参照してください。

## <a name="ipersiststorageimplsavecompleted"></a><a name="savecompleted"></a> IPersistStorageImpl::SaveCompleted

ストレージオブジェクトに書き込むために通常モードに戻ることができることをオブジェクトに通知します。

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>戻り値

S_OK を返します。

### <a name="remarks"></a>解説

Windows SDK の「 [IPersistStorage: SaveCompleted](/windows/win32/api/objidl/nf-objidl-ipersiststorage-savecompleted) 」を参照してください。

## <a name="see-also"></a>関連項目

[ストレージとストリーム](/windows/win32/Stg/storages-and-streams)<br/>
[IPersistStreamInitImpl クラス](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[IPersistPropertyBagImpl クラス](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
