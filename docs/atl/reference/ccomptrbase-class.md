---
description: '詳細情報: CComPtrBase クラス'
title: CComPtrBase クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CComPtrBase class
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
ms.openlocfilehash: 34f197904775bc15366f412e629ef81b26dde74e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142390"
---
# <a name="ccomptrbase-class"></a>CComPtrBase クラス

このクラスは、COM ベースのメモリルーチンを使用するスマートポインタークラスの基礎となります。

## <a name="syntax"></a>構文

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
スマートポインターによって参照されるオブジェクトの種類。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComPtrBase:: ~ CComPtrBase](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComPtrBase:: Advise](#advise)|`CComPtrBase`のコネクションポイントとクライアントのシンクとの間の接続を作成するには、このメソッドを呼び出します。|
|[CComPtrBase:: Attach](#attach)|既存のポインターの所有権を取得するには、このメソッドを呼び出します。|
|[CComPtrBase:: CoCreateInstance](#cocreateinstance)|指定したクラス ID またはプログラム ID に関連付けられているクラスのオブジェクトを作成するには、このメソッドを呼び出します。|
|[CComPtrBase:: CopyTo](#copyto)|`CComPtrBase`ポインターを別のポインター変数にコピーするには、このメソッドを呼び出します。|
|[CComPtrBase::D etach](#detach)|ポインターの所有権を解放するには、このメソッドを呼び出します。|
|[CComPtrBase::IsEqualObject](#isequalobject)|このメソッドを呼び出して、指定したが `IUnknown` オブジェクトに関連付けられている同じオブジェクトを指しているかどうかを確認し `CComPtrBase` ます。|
|[CComPtrBase:: QueryInterface](#queryinterface)|指定したインターフェイスへのポインターを返すには、このメソッドを呼び出します。|
|[CComPtrBase:: Release](#release)|インターフェイスを解放するには、このメソッドを呼び出します。|
|[CComPtrBase:: SetSite](#setsite)|オブジェクトのサイトを親オブジェクトのに設定するには、このメソッドを呼び出し `CComPtrBase` `IUnknown` ます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComPtrBase:: operator T *](#operator_t_star)|キャスト演算子。|
|[CComPtrBase:: operator!](#operator_not)|NOT 演算子。|
|[CComPtrBase:: operator &](#operator_amp)|&amp; 演算子。|
|[CComPtrBase:: operator *](#operator_star)|\* 演算子。|
|[CComPtrBase:: operator <](#ccomptrbase__operator lt)|小なり演算子。|
|[CComPtrBase:: operator = =](#operator_eq_eq)|等値演算子。|
|[CComPtrBase:: operator->](#operator_ptr)|メンバーへのポインター演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComPtrBase::p](#p)|ポインターデータメンバー変数。|

## <a name="remarks"></a>解説

このクラスは、 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) や [CCOMPTR](../../atl/reference/ccomptr-class.md)などの COM メモリ管理ルーチンを使用する他のスマートポインターの基礎となります。 派生クラスは独自のコンストラクターと演算子を追加しますが、によって提供されるメソッドに依存し `CComPtrBase` ます。

## <a name="requirements"></a>要件

**ヘッダー:** atlcomcli. h

## <a name="ccomptrbaseadvise"></a><a name="advise"></a> CComPtrBase:: Advise

`CComPtrBase`のコネクションポイントとクライアントのシンクとの間の接続を作成するには、このメソッドを呼び出します。

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
クライアントのへのポインター `IUnknown` 。

*iid*<br/>
コネクションポイントの GUID。 通常、これは接続ポイントによって管理される送信インターフェイスと同じです。

*ウィザード*<br/>
接続を一意に識別するクッキーへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

詳細については、「 [AtlAdvise](connection-point-global-functions.md#atladvise) 」を参照してください。

## <a name="ccomptrbaseattach"></a><a name="attach"></a> CComPtrBase:: Attach

既存のポインターの所有権を取得するには、このメソッドを呼び出します。

```cpp
void Attach(T* p2) throw();
```

### <a name="parameters"></a>パラメーター

*p2*<br/>
オブジェクトは、 `CComPtrBase` このポインターの所有権を取得します。

### <a name="remarks"></a>解説

`Attach`既存の [CComPtrBase::p](#p)メンバー変数に対して [CComPtrBase:: Release](#release)を呼び出し、 *p2* をに割り当て `CComPtrBase::p` ます。 オブジェクトが `CComPtrBase` ポインターの所有権を取得すると、オブジェクトの `Release` 参照カウントが0になった場合にポインターと割り当てられたデータを削除するポインターに対して、自動的にが呼び出されます。

## <a name="ccomptrbaseccomptrbase"></a><a name="dtor"></a> CComPtrBase:: ~ CComPtrBase

デストラクターです。

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>解説

が指すインターフェイスを解放 `CComPtrBase` します。

## <a name="ccomptrbasecocreateinstance"></a><a name="cocreateinstance"></a> CComPtrBase:: CoCreateInstance

指定したクラス ID またはプログラム ID に関連付けられているクラスのオブジェクトを作成するには、このメソッドを呼び出します。

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
CLSID を回復するために使用される ProgID へのポインター。

*pUnkOuter*<br/>
NULL の場合、オブジェクトが集計の一部として作成されていないことを示します。 NULL 以外の場合、は集約オブジェクトの `IUnknown` インターフェイス (コントロール) へのポインターです `IUnknown` 。

*dwClsContext*<br/>
新しく作成されたオブジェクトを管理するコードが実行されるコンテキスト。

*rclsid*<br/>
オブジェクトの作成に使用されるデータとコードに関連付けられている CLSID。

### <a name="return-value"></a>戻り値

成功した場合は S_OK、失敗した場合は REGDB_E_CLASSNOTREG、CLASS_E_NOAGGREGATION、CO_E_CLASSSTRING または E_NOINTERFACE を返します。 これらのエラーの説明については、「 [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance) And [Clsidfromprogid](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) 」を参照してください。

### <a name="remarks"></a>解説

メソッドの最初の形式が呼び出された場合、CLSID を復旧するために [Clsidfromprogid](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid) が使用されます。 どちらのフォームも [CoCreateClassInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)を呼び出します。

デバッグビルドでは、 [CComPtrBase::p](#p) が NULL と等しくない場合にアサーションエラーが発生します。

## <a name="ccomptrbasecopyto"></a><a name="copyto"></a> CComPtrBase:: CopyTo

`CComPtrBase`ポインターを別のポインター変数にコピーするには、このメソッドを呼び出します。

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>パラメーター

*ppT*<br/>
ポインターを受け取る変数のアドレス `CComPtrBase` 。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合は E_POINTER を返します。

### <a name="remarks"></a>解説

ポインターを `CComPtrBase` *ppT* にコピーします。 [CComPtrBase::p](#p)メンバー変数の参照カウントがインクリメントされます。

*PpT* が NULL の場合は、エラー HRESULT が返されます。 デバッグビルドでは、 *ppT* が NULL に等しい場合にアサーションエラーが発生します。

## <a name="ccomptrbasedetach"></a><a name="detach"></a> CComPtrBase::D etach

ポインターの所有権を解放するには、このメソッドを呼び出します。

```
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>解説

ポインターの所有権を解放し、 [CComPtrBase::p](#p) データメンバー変数を NULL に設定して、ポインターのコピーを返します。

## <a name="ccomptrbaseisequalobject"></a><a name="isequalobject"></a> CComPtrBase::IsEqualObject

このメソッドを呼び出して、指定したが `IUnknown` オブジェクトに関連付けられている同じオブジェクトを指しているかどうかを確認し `CComPtrBase` ます。

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>パラメーター

*その他*<br/>
比較対象の `IUnknown *`。

### <a name="return-value"></a>戻り値

オブジェクトが同一の場合は true、それ以外の場合は false を返します。

## <a name="ccomptrbaseoperator-"></a><a name="operator_not"></a> CComPtrBase:: operator!

NOT 演算子。

```
bool operator!() const throw();
```

### <a name="return-value"></a>戻り値

`CComHeapPtr`ポインターが NULL の場合は true、それ以外の場合は false を返します。

## <a name="ccomptrbaseoperator-amp"></a><a name="operator_amp"></a> CComPtrBase:: operator &amp;

&amp; 演算子。

```
T** operator&() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが指すオブジェクトのアドレスを返し `CComPtrBase` ます。

## <a name="ccomptrbaseoperator-"></a><a name="operator_star"></a> CComPtrBase:: operator \*

\* 演算子。

```
T& operator*() const throw();
```

### <a name="return-value"></a>戻り値

[CComPtrBase::p](#p)の値を返します。つまり、オブジェクトによって参照されるオブジェクトへのポインターです `CComPtrBase` 。

デバッグビルドの場合、 [CComPtrBase::p](#p) が NULL と等しくない場合、アサーションエラーが発生します。

## <a name="ccomptrbaseoperator-"></a><a name="operator_eq_eq"></a> CComPtrBase:: operator = =

等値演算子。

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>パラメーター

*未満*<br/>
オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

`CComPtrBase`と *pT* が同じオブジェクトを指している場合は true、それ以外の場合は false を返します。

## <a name="ccomptrbaseoperator--gt"></a><a name="operator_ptr"></a> CComPtrBase:: operator-&gt;

メンバーへのポインター演算子。

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>戻り値

[CComPtrBase::p](#p)データメンバー変数の値を返します。

### <a name="remarks"></a>解説

この演算子を使用すると、オブジェクトが指すクラスのメソッドを呼び出すことが `CComPtrBase` できます。 デバッグビルドでは、データメンバーが NULL を指している場合、アサーションエラーが発生 `CComPtrBase` します。

## <a name="ccomptrbaseoperator-lt"></a><a name="operator_lt"></a> CComPtrBase:: operator &lt;

小なり演算子。

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>パラメーター

*未満*<br/>
オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

現在のオブジェクトによって管理されているポインターが、比較対象のポインターより小さい場合に true を返します。

## <a name="ccomptrbaseoperator-t"></a><a name="operator_t_star"></a> CComPtrBase:: operator T\*

キャスト演算子。

```
operator T*() const throw();
```

### <a name="remarks"></a>解説

クラステンプレートで定義されているオブジェクトデータ型へのポインターを返します。

## <a name="ccomptrbasep"></a><a name="p"></a> CComPtrBase::p

ポインターデータメンバー変数。

```
T* p;
```

### <a name="remarks"></a>解説

このメンバー変数は、ポインター情報を保持します。

## <a name="ccomptrbasequeryinterface"></a><a name="queryinterface"></a> CComPtrBase:: QueryInterface

指定したインターフェイスへのポインターを返すには、このメソッドを呼び出します。

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>パラメーター

*Q*<br/>
インターフェイスポインターが必要なオブジェクト型。

*ページ*<br/>
要求されたインターフェイスポインターを受け取る出力変数のアドレス。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合は E_NOINTERFACE を返します。

### <a name="remarks"></a>解説

このメソッド [は、IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))を呼び出します。

デバッグビルドでは、 *pp* が NULL と等しくない場合にアサーションエラーが発生します。

## <a name="ccomptrbaserelease"></a><a name="release"></a> CComPtrBase:: Release

インターフェイスを解放するには、このメソッドを呼び出します。

```cpp
void Release() throw();
```

### <a name="remarks"></a>解説

インターフェイスが解放され、 [CComPtrBase::p](#p) が NULL に設定されます。

## <a name="ccomptrbasesetsite"></a><a name="setsite"></a> CComPtrBase:: SetSite

オブジェクトのサイトを親オブジェクトのに設定するには、このメソッドを呼び出し `CComPtrBase` `IUnknown` ます。

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>パラメーター

*punkParent*<br/>
`IUnknown`親のインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

このメソッドは、 [Atlsetchildsite](composite-control-global-functions.md#atlsetchildsite)を呼び出します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
