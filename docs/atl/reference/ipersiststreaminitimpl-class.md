---
title: クラスを提供します。
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
ms.openlocfilehash: 0d6ac4639ac0cfb97416ca80b7a2ec3903d7b8e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326460"
---
# <a name="ipersiststreaminitimpl-class"></a>クラスを提供します。

このクラスは、`IUnknown`[インターフェイス](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)の既定の実装を実装し、提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IPersistStreamInitImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[イタシンストリームイニトインプラクティプル::GetクラスID](#getclassid)|オブジェクトの CLSID を取得します。|
|[イティプルストリームイニトインプラクティプル::ゲットサイズマックス](#getsizemax)|オブジェクトのデータを保存するために必要なストリームのサイズを取得します。 ATL の実装はE_NOTIMPL返します。|
|[イティシンティストリームイニトインプラクティプル::イニトニュー](#initnew)|新しく作成されたオブジェクトを初期化します。|
|[IPersistStreamInitImpl::IsDirty](#isdirty)|オブジェクトのデータが最後に保存されてから変更されたかどうかをチェックします。|
|[IPersistStreamInitImpl::ロード](#load)|指定したストリームからオブジェクトのプロパティを読み込みます。|
|[IPersistStreamInitImpl::保存](#save)|オブジェクトのプロパティを指定したストリームに保存します。|

## <a name="remarks"></a>解説

[IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit)インターフェイスを使用すると、クライアントは、オブジェクトを読み込んで、その永続的なデータを単一のストリームに保存するように要求できます。 Class`IPersistStreamInitImpl`は、このインターフェイスの既定の実装を`IUnknown`提供し、デバッグ ビルドでダンプ デバイスに情報を送信することによって実装します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="ipersiststreaminitimplgetclassid"></a><a name="getclassid"></a>イタシンストリームイニトインプラクティプル::GetクラスID

オブジェクトの CLSID を取得します。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>解説

「Windows SDK[の IPersist::GetClassID」](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid)を参照してください。

## <a name="ipersiststreaminitimplgetsizemax"></a><a name="getsizemax"></a>イティプルストリームイニトインプラクティプル::ゲットサイズマックス

オブジェクトのデータを保存するために必要なストリームのサイズを取得します。

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>戻り値

E_NOTIMPL を返します。

### <a name="remarks"></a>解説

Windows SDK の[「IPersistStreamInit::GetSizeMax」](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax)を参照してください。

## <a name="ipersiststreaminitimplinitnew"></a><a name="initnew"></a>イティシンティストリームイニトインプラクティプル::イニトニュー

新しく作成されたオブジェクトを初期化します。

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>解説

Windows SDK の[「IPersistStreamInit::InitNew」](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-initnew)を参照してください。

## <a name="ipersiststreaminitimplisdirty"></a><a name="isdirty"></a>IPersistStreamInitImpl::IsDirty

オブジェクトのデータが最後に保存されてから変更されたかどうかをチェックします。

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>解説

Windows SDK の[「IPersistStreamInit::IsDirty」](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty)を参照してください。

## <a name="ipersiststreaminitimplload"></a><a name="load"></a>IPersistStreamInitImpl::ロード

指定したストリームからオブジェクトのプロパティを読み込みます。

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>解説

ATL は、オブジェクトのプロパティ マップを使用して、この情報を取得します。

「Windows SDK で[の IPersistStreamInit::読み込み」](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-load)を参照してください。

## <a name="ipersiststreaminitimplsave"></a><a name="save"></a>IPersistStreamInitImpl::保存

オブジェクトのプロパティを指定したストリームに保存します。

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>解説

ATL は、オブジェクトのプロパティ マップを使用してこの情報を格納します。

「Windows SDK で[の保存](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-save)」を参照してください。

## <a name="see-also"></a>関連項目

[ストレージとストリーム](/windows/win32/Stg/storages-and-streams)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
