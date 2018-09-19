---
title: CComPtrBase クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase
- ATLCOMCLI/ATL::CComPtrBase::Advise
- ATLCOMCLI/ATL::CComPtrBase::Attach
- ATLCOMCLI/ATL::CComPtrBase::CoCreateInstance
- ATLCOMCLI/ATL::CComPtrBase::CopyTo
- ATLCOMCLI/ATL::CComPtrBase::Detach
- ATLCOMCLI/ATL::CComPtrBase::IsEqualObject
- ATLCOMCLI/ATL::CComPtrBase::QueryInterface
- ATLCOMCLI/ATL::CComPtrBase::Release
- ATLCOMCLI/ATL::CComPtrBase::SetSite
- ATLCOMCLI/ATL::CComPtrBase::p
dev_langs:
- C++
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 70ba26e5893b21393a3466ae7cf1c6cea43b81ef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070159"
---
# <a name="ccomptrbase-class"></a>CComPtrBase クラス

このクラスは、メモリの COM ベースのルーチンを使用するスマート ポインター クラスの基盤を提供します。

## <a name="syntax"></a>構文

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
スマート ポインターによって参照されるオブジェクトの種類。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComPtrBase:: ~ CComPtrBase](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComPtrBase::Advise](#advise)|間の接続を作成するには、このメソッドを呼び出して、`CComPtrBase`の接続ポイントとクライアントのシンク。|
|[CComPtrBase::Attach](#attach)|既存のポインターの所有権を取得するには、このメソッドを呼び出します。|
|[CComPtrBase::CoCreateInstance](#cocreateinstance)|指定したクラス ID、またはプログラムの ID に関連付けられているクラスのオブジェクトを作成するには、このメソッドを呼び出す|
|[CComPtrBase::CopyTo](#copyto)|コピーするには、このメソッドを呼び出す、`CComPtrBase`別のポインター変数へのポインター。|
|[CComPtrBase::Detach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|
|[CComPtrBase::IsEqualObject](#isequalobject)|場合にチェックするには、このメソッドを呼び出して、指定した`IUnknown`に関連付けられている同じオブジェクトを指す、`CComPtrBase`オブジェクト。|
|[CComPtrBase::QueryInterface](#queryinterface)|指定したインターフェイスへのポインターを返すには、このメソッドを呼び出します。|
|[CComPtrBase::Release](#release)|インターフェイスを解放するには、このメソッドを呼び出します。|
|[CComPtrBase::SetSite](#setsite)|サイトを設定するには、このメソッドを呼び出して、`CComPtrBase`オブジェクトを`IUnknown`の親オブジェクト。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComPtrBase::operator T *](#operator_t_star)|キャスト演算子です。|
|[CComPtrBase::operator!](#operator_not)|NOT 演算子。|
|[CComPtrBase::operator (& a)](#operator_amp)|& 演算子。|
|[CComPtrBase::operator *](#operator_star)|\* 演算子。|
|[CComPtrBase::operator <](#ccomptrbase__operator lt)|小さいの演算子よりもします。|
|[CComPtrBase::operator = =](#operator_eq_eq)|等値演算子。|
|[CComPtrBase::operator -> します。](#operator_ptr)|メンバーへのポインター演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[解放](#p)|ポインターのデータ メンバー変数です。|

## <a name="remarks"></a>Remarks

このクラスは、COM メモリ管理ルーチンを使用して他のスマート ポインターの基礎を提供[CComQIPtr](../../atl/reference/ccomqiptr-class.md)と[CComPtr](../../atl/reference/ccomptr-class.md)します。 派生クラスは、独自のコンス トラクターと演算子がによって提供される方法を利用して`CComPtrBase`します。

## <a name="requirements"></a>要件

**ヘッダー:** atlcomcli.h

##  <a name="advise"></a>  CComPtrBase::Advise

間の接続を作成するには、このメソッドを呼び出して、`CComPtrBase`の接続ポイントとクライアントのシンク。

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>パラメーター

*pUnk*<br/>
クライアントへのポインター`IUnknown`します。

*iid*<br/>
接続ポイントの GUID です。 通常、これは、接続ポイントによって管理するアウトゴーイング インターフェイスと同じです。

*pdw*<br/>
接続を一意に識別するクッキーへのポインター。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

参照してください[AtlAdvise](connection-point-global-functions.md#atladvise)詳細についてはします。

##  <a name="attach"></a>  CComPtrBase::Attach

既存のポインターの所有権を取得するには、このメソッドを呼び出します。

```
void Attach(T* p2) throw();
```

### <a name="parameters"></a>パラメーター

*p2*<br/>
`CComPtrBase` This ポインターの所有権を持つオブジェクト。

### <a name="remarks"></a>Remarks

`Attach` 呼び出し[CComPtrBase::Release](#release)既存の[解放](#p)メンバー変数とし、割り当てます*p2*に`CComPtrBase::p`します。 ときに、`CComPtrBase`オブジェクト ポインターの所有権を取得する、自動的に呼び出すことが、`Release`オブジェクトの参照カウントが 0 になった場合、ポインターにポインターをいずれかを削除するデータを割り当てられています。

##  <a name="dtor"></a>  CComPtrBase:: ~ CComPtrBase

デストラクターです。

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>Remarks

によって示されるインターフェイスを解放`CComPtrBase`します。

##  <a name="cocreateinstance"></a>  CComPtrBase::CoCreateInstance

指定したクラス ID、またはプログラムの ID に関連付けられているクラスのオブジェクトを作成するには、このメソッドを呼び出す

```
HRESULT CoCreateInstance(  
    LPCOLESTR szProgID,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();

HRESULT CoCreateInstance(  
    REFCLSID rclsid,
    LPUNKNOWN pUnkOuter = NULL,
    DWORD dwClsContext = CLSCTX_ALL) throw();
```

### <a name="parameters"></a>パラメーター

*szProgID*<br/>
ProgID、CLSID を回復するために使用へのポインター。

*pUnkOuter*<br/>
NULL の場合は、集計の一部として、オブジェクトが作成されていないことを示します。 かどうか、NULL 以外の場合は、集約オブジェクトへのポインター`IUnknown`インターフェイス (制御`IUnknown`)。

*dwClsContext*<br/>
新しく作成されたオブジェクトを管理するコードを実行するコンテキスト。

*rclsid*<br/>
CLSID は、データとオブジェクトの作成に使用されるコードに関連付けられています。

### <a name="return-value"></a>戻り値

失敗した場合、成功した場合、または REGDB_E_CLASSNOTREG、CLASS_E_NOAGGREGATION、CO_E_CLASSSTRING または E_NOINTERFACE に S_OK を返します。 参照してください[とも](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)と[この](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromprogid)のこれらのエラーの説明。

### <a name="remarks"></a>Remarks

メソッドの最初のフォームを呼び出すと、[この](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromprogid)CLSID を回復するために使用します。 どちらの形式を呼び出して[とも](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)します。

場合、デバッグ ビルドで、アサーション エラーが発生[解放](#p)は NULL と等しくありません。

##  <a name="copyto"></a>  CComPtrBase::CopyTo

コピーするには、このメソッドを呼び出す、`CComPtrBase`別のポインター変数へのポインター。

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>パラメーター

*ppT*<br/>
受け取る変数のアドレス、`CComPtrBase`ポインター。

### <a name="return-value"></a>戻り値

成功した場合、正常には、S_OK を返します。

### <a name="remarks"></a>Remarks

コピー、`CComPtrBase`へのポインター *ppT*します。 参照カウント、[解放](#p)メンバー変数が増加します。

場合に返される HRESULT エラー *ppT*が NULL です。 場合、デバッグ ビルドで、アサーション エラーが発生*ppT*が NULL です。

##  <a name="detach"></a>  CComPtrBase::Detach

ポインターの所有権を解放するには、このメソッドを呼び出します。

```
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>Remarks

ポインターの所有権を解放、[解放](#p)に null の場合、データ メンバー変数と、ポインターのコピーを返します。

##  <a name="isequalobject"></a>  CComPtrBase::IsEqualObject

場合にチェックするには、このメソッドを呼び出して、指定した`IUnknown`に関連付けられている同じオブジェクトを指す、`CComPtrBase`オブジェクト。

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>パラメーター

*pOther*<br/>
比較対象の `IUnknown *`。

### <a name="return-value"></a>戻り値

オブジェクトと同じ、false をそれ以外の場合がある場合に true を返します。

##  <a name="operator_not"></a>  CComPtrBase::operator!

NOT 演算子。

```
bool operator!() const throw();
```

### <a name="return-value"></a>戻り値

場合は true を返します、`CComHeapPtr`ポインターが NULL、false それ以外の場合。

##  <a name="operator_amp"></a>  CComPtrBase::operator &amp;

& 演算子。

```
T** operator&() throw();
```

### <a name="return-value"></a>戻り値

指すオブジェクトのアドレスを返して、`CComPtrBase`オブジェクト。

##  <a name="operator_star"></a>  CComPtrBase::operator \*

\* 演算子。

```
T& operator*() const throw();
```

### <a name="return-value"></a>戻り値

値を返します[解放](#p); によって参照されるオブジェクトへのポインターは、`CComPtrBase`オブジェクト。

場合に、アサーション エラーが発生するデバッグ ビルドで場合、[解放](#p)は NULL と等しくありません。

##  <a name="operator_eq_eq"></a>  CComPtrBase::operator = =

等値演算子。

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>パラメーター

*pT*<br/>
オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

場合は true を返します`CComPtrBase`と*pT*オブジェクトを指す同じ、false それ以外の場合。

##  <a name="operator_ptr"></a>  CComPtrBase::operator-&gt;

メンバーへのポインター演算子。

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>戻り値

値を返します、[解放](#p)メンバー変数のデータ。

### <a name="remarks"></a>Remarks

この演算子によって示されるクラスのメソッドを呼び出すを使用して、`CComPtrBase`オブジェクト。 場合、デバッグ ビルドで、アサーション エラーが発生、`CComPtrBase`データ メンバーが NULL をポイントします。

##  <a name="operator_lt"></a>  CComPtrBase::operator &lt;

小さいの演算子よりもします。

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>パラメーター

*pT*<br/>
オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

ポインターは、現在のオブジェクトによって管理されている場合は true を返しますでは、比較するポインターより小さいです。

##  <a name="operator_t_star"></a>  CComPtrBase::operator T\*

キャスト演算子です。

```
operator T*() const throw();
```

### <a name="remarks"></a>Remarks

クラス テンプレートで定義されたオブジェクト データ型へのポインターを返します。

##  <a name="p"></a>  解放

ポインターのデータ メンバー変数です。

```
T* p;
```

### <a name="remarks"></a>Remarks

このメンバー変数は、ポインターの情報を保持します。

##  <a name="queryinterface"></a>  CComPtrBase::QueryInterface

指定したインターフェイスへのポインターを返すには、このメソッドを呼び出します。

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>パラメーター

*Q*<br/>
オブジェクトの種類のインターフェイス ポインターが必要です。

*pp*<br/>
要求されたインターフェイス ポインターを受け取る出力変数のアドレス。

### <a name="return-value"></a>戻り値

エラー発生時に成功した場合、または E_NOINTERFACE S_OK を返します。

### <a name="remarks"></a>Remarks

このメソッドを呼び出す[iunknown::queryinterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_))します。

場合、デバッグ ビルドで、アサーション エラーが発生*pp*は NULL と等しくありません。

##  <a name="release"></a>  CComPtrBase::Release

インターフェイスを解放するには、このメソッドを呼び出します。

```
void Release() throw();
```

### <a name="remarks"></a>Remarks

インターフェイスがリリースされると[解放](#p)NULL に設定されます。

##  <a name="setsite"></a>  CComPtrBase::SetSite

サイトを設定するには、このメソッドを呼び出して、`CComPtrBase`オブジェクトを`IUnknown`の親オブジェクト。

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>パラメーター

*punkParent*<br/>
ポインター、`IUnknown`親のインターフェイス。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

このメソッドを呼び出す[AtlSetChildSite](composite-control-global-functions.md#atlsetchildsite)します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
