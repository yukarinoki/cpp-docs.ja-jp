---
title: クラス
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
ms.openlocfilehash: b235b190f237293932705e4d290ac963088722f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326470"
---
# <a name="ipersiststorageimpl-class"></a>クラス

このクラスは、[インターフェイスを](/windows/win32/api/objidl/nn-objidl-ipersiststorage)実装します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IPersistStorageImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を指定します。](#getclassid)|オブジェクトの CLSID を取得します。|
|[IPersist ストレージインプル::ハンズオフストレージ](#handsoffstorage)|オブジェクトにすべてのストレージ オブジェクトを解放し、HandsOff モードに入るように指示します。 ATL 実装はS_OKを返します。|
|[IPersistストレージインプラシット::イニトニュー](#initnew)|新しいストレージを初期化します。|
|[IPersistストレージインプル::IsDirty](#isdirty)|オブジェクトのデータが最後に保存されてから変更されたかどうかをチェックします。|
|[IPersistストレージインプラ](#load)|指定したストレージからオブジェクトのプロパティを読み込みます。|
|[IPersistストレージImpl::保存](#save)|オブジェクトのプロパティを指定したストレージに保存します。|
|[IPersistストレージインプル::保存完了](#savecompleted)|オブジェクトに対して、ストレージ オブジェクトへの書き込みを通常モードに戻すことができることを通知します。 ATL 実装はS_OKを返します。|

## <a name="remarks"></a>解説

`IPersistStorageImpl`は、クライアントがオブジェクトの読み込みとストレージを使用してその永続的なデータの保存を要求できるようにする[IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage)インターフェイスを実装します。

このクラスの実装では、インターフェイス`T`の実装を で`QueryInterface`使用`IPersistStreamInit`できるようにするクラスが必要です。 通常、これは、クラス`T`が[IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md)から派生し`IPersistStreamInit`[、COM マップ](com-map-macros.md)にエントリを提供し、[プロパティ マップ](property-map-macros.md)を使用してクラスの永続的なデータを記述する必要があることを意味します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ipersiststorageimplgetclassid"></a><a name="getclassid"></a>を指定します。

オブジェクトの CLSID を取得します。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>解説

「Windows SDK[の IPersist::GetClassID」](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid)を参照してください。

## <a name="ipersiststorageimplhandsoffstorage"></a><a name="handsoffstorage"></a>IPersist ストレージインプル::ハンズオフストレージ

オブジェクトにすべてのストレージ オブジェクトを解放し、HandsOff モードに入るように指示します。

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

「Windows SDK[の IPersist ストレージ::ハンズオフストレージ](/windows/win32/api/objidl/nf-objidl-ipersiststorage-handsoffstorage)」を参照してください。

## <a name="ipersiststorageimplinitnew"></a><a name="initnew"></a>IPersistストレージインプラシット::イニトニュー

新しいストレージを初期化します。

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>解説

ATL 実装は[、インターフェイス](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)にデリゲートします。

「Windows SDK[の IPersist ストレージ:InitNew」](/windows/win32/api/objidl/nf-objidl-ipersiststorage-initnew)を参照してください。

## <a name="ipersiststorageimplisdirty"></a><a name="isdirty"></a>IPersistストレージインプル::IsDirty

オブジェクトのデータが最後に保存されてから変更されたかどうかをチェックします。

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>解説

ATL 実装は[、インターフェイス](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)にデリゲートします。

「Windows SDK[での記憶域:IsDirty」](/windows/win32/api/objidl/nf-objidl-ipersiststorage-isdirty)を参照してください。

## <a name="ipersiststorageimplload"></a><a name="load"></a>IPersistストレージインプラ

指定したストレージからオブジェクトのプロパティを読み込みます。

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>解説

ATL 実装は[、インターフェイス](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)にデリゲートします。 `Load`は、"Contents" という名前のストリームを使用してオブジェクトのデータを取得します。 [Save](#save)メソッドは、もともとこのストリームを作成します。

「Windows SDK[での IPersist ストレージ:読み込み](/windows/win32/api/objidl/nf-objidl-ipersiststorage-load)」を参照してください。

## <a name="ipersiststorageimplsave"></a><a name="save"></a>IPersistストレージImpl::保存

オブジェクトのプロパティを指定したストレージに保存します。

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>解説

ATL 実装は[、インターフェイス](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)にデリゲートします。 最初`Save`に呼び出されると、指定されたストレージに "Contents" という名前のストリームが作成されます。 このストリームは、Load の`Save`呼び出しと[の](#load)呼び出しで使用されます。

「[ストレージ:Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-save) SDK で保存する」を参照してください。

## <a name="ipersiststorageimplsavecompleted"></a><a name="savecompleted"></a>IPersistストレージインプル::保存完了

オブジェクトに対して、ストレージ オブジェクトへの書き込みを通常モードに戻すことができることを通知します。

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>戻り値

S_OKを返します。

### <a name="remarks"></a>解説

「Windows SDK[で IPersist ストレージ:保存完了](/windows/win32/api/objidl/nf-objidl-ipersiststorage-savecompleted)」を参照してください。

## <a name="see-also"></a>関連項目

[ストレージとストリーム](/windows/win32/Stg/storages-and-streams)<br/>
[クラスを提供します。](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[クラスを永続化します。](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
