---
title: クラスをディスパッチインプラ
ms.date: 11/04/2016
f1_keywords:
- IDispatchImpl
- ATLCOM/ATL::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::IDispatchImpl
- ATLCOM/ATL::IDispatchImpl::GetIDsOfNames
- ATLCOM/ATL::IDispatchImpl::GetTypeInfo
- ATLCOM/ATL::IDispatchImpl::GetTypeInfoCount
- ATLCOM/ATL::IDispatchImpl::Invoke
helpviewer_keywords:
- dual interfaces, classes
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
ms.openlocfilehash: 3b3899a0c4a49aa7fb1bd82af330f5f1cc7329c4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329792"
---
# <a name="idispatchimpl-class"></a>クラスをディスパッチインプラ

デュアル インターフェイスの一部`IDispatch`に既定の実装を提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T,
        const IID* piid= &__uuidof(T),
        const GUID* plibid = &CAtlModule::m_libid,
        WORD wMajor = 1,
        WORD wMinor = 0,
        class tihclass = CComTypeInfoHolder>
class ATL_NO_VTABLE IDispatchImpl : public T
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
[in]デュアル インターフェイス。

*ピッド*<br/>
[in]*T*の IID へのポインター。

*プリビッド*<br/>
[in]インターフェイスに関する情報を含むタイプ ライブラリの LIBID へのポインター。 既定では、サーバー レベルのタイプ ライブラリが渡されます。

*wメジャー*<br/>
[in]タイプ ライブラリのメジャー バージョン。 デフォルトでは、値は 1 です。

*wマイナー*<br/>
[in]タイプ ライブラリのマイナー バージョン。 デフォルトでは、値は 0 です。

*ティクラス*<br/>
[in]*T*の型情報を管理するために使用されるクラス。デフォルトでは、値は`CComTypeInfoHolder`です。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Iディスパッチインプラシプル::Iディスパッチインプラ](#idispatchimpl)|コンストラクターです。 デュアル`AddRef`インターフェイスの型情報を管理するプロテクト メンバー変数を呼び出します。 このデストラクターは `Release` を呼び出します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Iディスパッチインプラッツ::ゲットIdSOfNames](#getidsofnames)|一連の名前を対応する一連のディスパッチ識別子に割り当てます。|
|[I ディスパッチインプラシ::GetTypeInfo](#gettypeinfo)|デュアル インターフェイスの型情報を取得します。|
|[I ディスパッチインプラウンド::取得タイプ情報カウント](#gettypeinfocount)|デュアル インターフェイスで使用できる型情報があるかどうかを判断します。|
|[Iディスパッチインプラシ::呼び出し](#invoke)|デュアル インターフェイスによって公開されるメソッドとプロパティへのアクセスを提供します。|

## <a name="remarks"></a>解説

`IDispatchImpl`は、オブジェクト上の任意`IDispatch`のデュアル インターフェイスの部分に対する既定の実装を提供します。 デュアル インターフェイスは、オートメーション`IDispatch`互換型から派生し、使用する場合のみです。 disp インタフェースと同様に、デュアル インターフェイスは事前バインディングと遅延バインディングをサポートします。ただし、デュアル インターフェイスは vtable バインディングもサポートしています。

の一般的な実装例を次`IDispatchImpl`に示します。

[!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/cpp/idispatchimpl-class_1.h)]

既定では、クラス`IDispatchImpl`はレジストリ内の*T*の型情報を検索します。 未登録のインターフェイスを実装するには、定義済みのバージョン`IDispatchImpl`番号を使用して、レジストリにアクセスせずにクラスを使用できます。 wMajor の`IDispatchImpl`値として 0xFFFF を持つオブジェクトを作成し *、wMinor*の値として*wMinor*0xFFFF を作成する場合、`IDispatchImpl`クラスはレジストリではなく .dll ファイルからタイプ ライブラリを取得します。

`IDispatchImpl`には、デュアル インターフェイスの`CComTypeInfoHolder`型情報を管理する型の静的メンバーが含まれています。 同じデュアル インターフェイスを実装する複数のオブジェクトがある場合は、1`CComTypeInfoHolder`つのインスタンスのみが使用されます。

## <a name="inheritance-hierarchy"></a>継承階層

`T`

`IDispatchImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcom.h

## <a name="idispatchimplgetidsofnames"></a><a name="getidsofnames"></a>Iディスパッチインプラッツ::ゲットIdSOfNames

一連の名前を対応する一連のディスパッチ識別子に割り当てます。

```
STDMETHOD(GetIDsOfNames)(
    REFIID riid,
    LPOLESTR* rgszNames,
    UINT cNames,
    LCID lcid,
    DISPID* rgdispid);
```

### <a name="remarks"></a>解説

Windows SDK の[「IDispatch::GetIDsOfNames」](/windows/win32/api/oaidl/nf-oaidl-idispatch-getidsofnames)を参照してください。

## <a name="idispatchimplgettypeinfo"></a><a name="gettypeinfo"></a>I ディスパッチインプラシ::GetTypeInfo

デュアル インターフェイスの型情報を取得します。

```
STDMETHOD(GetTypeInfo)(
    UINT itinfo,
    LCID lcid,
    ITypeInfo** pptinfo);
```

### <a name="remarks"></a>解説

Windows SDK の[「IDispatch::GetTypeInfo」](/windows/win32/api/oaidl/nf-oaidl-idispatch-gettypeinfo)を参照してください。

## <a name="idispatchimplgettypeinfocount"></a><a name="gettypeinfocount"></a>I ディスパッチインプラウンド::取得タイプ情報カウント

デュアル インターフェイスで使用できる型情報があるかどうかを判断します。

```
STDMETHOD(GetTypeInfoCount)(UINT* pctinfo);
```

### <a name="remarks"></a>解説

Windows `IDispatch::GetTypeInfoCount` SDK を参照してください。

## <a name="idispatchimplidispatchimpl"></a><a name="idispatchimpl"></a>Iディスパッチインプラシプル::Iディスパッチインプラ

コンストラクターです。 デュアル`AddRef`インターフェイスの型情報を管理するプロテクト メンバー変数を呼び出します。 このデストラクターは `Release` を呼び出します。

```
IDispatchImpl();
```

## <a name="idispatchimplinvoke"></a><a name="invoke"></a>Iディスパッチインプラシ::呼び出し

デュアル インターフェイスによって公開されるメソッドとプロパティへのアクセスを提供します。

```
STDMETHOD(Invoke)(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,
    DISPPARAMS* pdispparams,
    VARIANT* pvarResult,
    EXCEPINFO* pexcepinfo,
    UINT* puArgErr);
```

### <a name="remarks"></a>解説

[「IDispatch::呼び出し](/windows/win32/api/oaidl/nf-oaidl-idispatch-invoke)」を参照してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
