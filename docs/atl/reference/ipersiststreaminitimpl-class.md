---
title: IPersistStreamInitImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
ms.openlocfilehash: b5ab433ed08b150e6c344d65657a910542856e77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62197620"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl クラス

このクラスは実装`IUnknown`の既定の実装を提供し、 [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit)インターフェイス。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IPersistStreamInitImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|オブジェクトの CLSID を取得します。|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|オブジェクトのデータを保存するために必要なストリームのサイズを取得します。 ATL の実装では、E_NOTIMPL を返します。|
|[IPersistStreamInitImpl::InitNew](#initnew)|新しく作成されたオブジェクトを初期化します。|
|[IPersistStreamInitImpl::IsDirty](#isdirty)|最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。|
|[IPersistStreamInitImpl::Load](#load)|指定したストリームからオブジェクトのプロパティを読み込みます。|
|[IPersistStreamInitImpl::Save](#save)|オブジェクトのプロパティを指定したストリームに保存します。|

## <a name="remarks"></a>Remarks

[IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit)インターフェイスにより、クライアントは、オブジェクトは読み込みし、その永続的なデータを 1 つのストリームに保存を要求します。 クラス`IPersistStreamInitImpl`このインターフェイスの既定の実装を提供し、実装`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

##  <a name="getclassid"></a>  IPersistStreamInitImpl::GetClassID

オブジェクトの CLSID を取得します。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Remarks

参照してください[IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK にします。

##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax

オブジェクトのデータを保存するために必要なストリームのサイズを取得します。

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>Remarks

参照してください[IPersistStreamInit::GetSizeMax](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) Windows SDK にします。

##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew

新しく作成されたオブジェクトを初期化します。

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>Remarks

参照してください[IPersistStreamInit::InitNew](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) Windows SDK にします。

##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty

最後に保存してから、オブジェクトのデータが変更されたかどうかを確認します。

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>Remarks

参照してください[IPersistStreamInit::IsDirty](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) Windows SDK にします。

##  <a name="load"></a>  IPersistStreamInitImpl::Load

指定したストリームからオブジェクトのプロパティを読み込みます。

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>Remarks

ATL では、オブジェクトのプロパティのマップを使用して、この情報を取得します。

参照してください[IPersistStreamInit::Load](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-load) Windows SDK にします。

##  <a name="save"></a>  IPersistStreamInitImpl::Save

オブジェクトのプロパティを指定したストリームに保存します。

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>Remarks

ATL では、オブジェクトのプロパティ マップを使用して、この情報を格納します。

参照してください[IPersistStreamInit::Save](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-save) Windows SDK にします。

## <a name="see-also"></a>関連項目

[記憶域とストリーム](/windows/desktop/Stg/storages-and-streams)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
