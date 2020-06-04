---
title: クラス
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
ms.openlocfilehash: 9c62cc912b3fea3ea68390882bdda37cbfb25a7e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747763"
---
# <a name="ccomptrbase-class"></a>クラス

このクラスは、COM ベースのメモリ ルーチンを使用するスマート ポインター クラスの基礎を提供します。

## <a name="syntax"></a>構文

```
template <class T>
class CComPtrBase
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
スマート ポインターによって参照されるオブジェクト型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コムプターベース::~コムプターベース](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コムプトルベース::アドバイス](#advise)|接続ポイントとクライアントシンクの間に`CComPtrBase`接続を作成します。|
|[コムプターベース::アタッチ](#attach)|既存のポインターの所有権を取得します。|
|[インスタンスを作成します。](#cocreateinstance)|指定したクラス ID またはプログラム ID に関連付けられたクラスのオブジェクトを作成します。|
|[コムプターベース::コピート](#copyto)|ポインターを別のポインター変数`CComPtrBase`にコピーします。|
|[コムプターベース::Dエタッハ](#detach)|ポインターの所有権を解放します。|
|[オブジェクトを指定します。](#isequalobject)|指定した`IUnknown`オブジェクトが`CComPtrBase`、そのオブジェクトに関連付けられている同じオブジェクトを指しているかどうかを確認します。|
|[クエリインターフェイス](#queryinterface)|指定したインターフェイスへのポインターを返します。|
|[CComPtrベース::リリース](#release)|インターフェイスを解放するには、このメソッドを呼び出します。|
|[コムプターベース::セットサイト](#setsite)|`CComPtrBase`オブジェクトのサイトを親オブジェクトの サイト`IUnknown`に設定します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[コムプターベース::オペレーターT*](#operator_t_star)|キャスト演算子。|
|[CComPtrBase::演算子!](#operator_not)|NOT 演算子。|
|[CComPtrBase::オペレーター&](#operator_amp)|&amp; 演算子。|
|[コムプターベース::演算子 *](#operator_star)|\* 演算子。|
|[CComPtrBase::オペレーター<](#ccomptrbase__operator lt)|より小さい演算子。|
|[を使用します。](#operator_eq_eq)|等価演算子。|
|[コムプトルベース::オペレーター ->](#operator_ptr)|メンバへのポインター演算子。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コムプトルベース::p](#p)|ポインター データ メンバー変数。|

## <a name="remarks"></a>解説

このクラスは[、COM](../../atl/reference/ccomqiptr-class.md)メモリ管理ルーチンを使用する他のスマート ポインターの基礎を[提供します。](../../atl/reference/ccomptr-class.md) 派生クラスは独自のコンストラクターと演算子を追加しますが、 によって`CComPtrBase`提供されるメソッドに依存します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcomcli.h

## <a name="ccomptrbaseadvise"></a><a name="advise"></a>コムプトルベース::アドバイス

接続ポイントとクライアントシンクの間に`CComPtrBase`接続を作成します。

```
HRESULT Advise(
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw) throw();
```

### <a name="parameters"></a>パラメーター

*パンク*<br/>
クライアント`IUnknown`の .

*Iid*<br/>
接続ポイントの GUID。 通常、これはコネクション ポイントによって管理される発信インターフェイスと同じです。

*Pdw*<br/>
接続を一意に識別する Cookie へのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

詳細については[、AtlAdvise](connection-point-global-functions.md#atladvise)を参照してください。

## <a name="ccomptrbaseattach"></a><a name="attach"></a>コムプターベース::アタッチ

既存のポインターの所有権を取得します。

```cpp
void Attach(T* p2) throw();
```

### <a name="parameters"></a>パラメーター

*p2*<br/>
オブジェクト`CComPtrBase`は、このポインターの所有権を取得します。

### <a name="remarks"></a>解説

`Attach`既存の`CComPtrBase::p`[CComPtrBase:::p](#release) [CComPtrBase::p](#p)メンバー変数で解放を呼び出し *、p2*を に割り当てます。 オブジェクトが`CComPtrBase`ポインタの所有権を取得すると、ポインタを自動的に`Release`呼び出し、ポインタと、オブジェクトの参照カウントが 0 になると、割り当てられたデータが削除されます。

## <a name="ccomptrbaseccomptrbase"></a><a name="dtor"></a>コムプターベース::~コムプターベース

デストラクターです。

```
~CComPtrBase() throw();
```

### <a name="remarks"></a>解説

が`CComPtrBase`指すインターフェイスを解放します。

## <a name="ccomptrbasecocreateinstance"></a><a name="cocreateinstance"></a>インスタンスを作成します。

指定したクラス ID またはプログラム ID に関連付けられたクラスのオブジェクトを作成します。

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
CLSID の回復に使用される ProgID へのポインター。

*プンクアウター*<br/>
NULL の場合、オブジェクトが集約の一部として作成されないことを示します。 NULL 以外の場合は、集約オブジェクトの`IUnknown`インターフェイス (制御) へのポインター`IUnknown`です。

*コンテキスト*<br/>
新しく作成されたオブジェクトを管理するコードが実行されるコンテキスト。

*rclsid*<br/>
オブジェクトの作成に使用されるデータおよびコードに関連付けられた CLSID。

### <a name="return-value"></a>戻り値

成功、またはREGDB_E_CLASSNOTREG、CLASS_E_NOAGGREGATION、CO_E_CLASSSTRING、または失敗時のE_NOINTERFACEにS_OKを返します。 これらのエラーの説明については[、「コクリエイトクラスインスタンス](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)」および[「CLSIDFromProgID」](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid)を参照してください。

### <a name="remarks"></a>解説

メソッドの最初の形式が呼び出された場合は[、CLSID](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromprogid)を回復するために使用されます。 次に、両方のフォーム[が呼](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)び出されます。

デバッグ ビルドでは[、CComPtrBase::p](#p)が NULL と等しくない場合、アサーション エラーが発生します。

## <a name="ccomptrbasecopyto"></a><a name="copyto"></a>コムプターベース::コピート

ポインターを別のポインター変数`CComPtrBase`にコピーします。

```
HRESULT CopyTo(T** ppT) throw();
```

### <a name="parameters"></a>パラメーター

*Ppt*<br/>
ポインターを受け取る変数の`CComPtrBase`アドレス。

### <a name="return-value"></a>戻り値

成功時にS_OKを返し、失敗時にE_POINTERします。

### <a name="remarks"></a>解説

ポインタを`CComPtrBase` *ppT*にコピーします。 [CComPtrBase::p](#p)メンバー変数の参照カウントがインクリメントされます。

*ppT*が NULL に等しい場合、エラー HRESULT が返されます。 デバッグ ビルドでは *、ppT*が NULL に等しい場合にアサーション エラーが発生します。

## <a name="ccomptrbasedetach"></a><a name="detach"></a>コムプターベース::Dエタッハ

ポインターの所有権を解放します。

```
T* Detach() throw();
```

### <a name="return-value"></a>戻り値

ポインターのコピーを返します。

### <a name="remarks"></a>解説

ポインターの所有権を解放し[、CComPtrBase::p](#p)データ メンバー変数を NULL に設定し、ポインターのコピーを返します。

## <a name="ccomptrbaseisequalobject"></a><a name="isequalobject"></a>オブジェクトを指定します。

指定した`IUnknown`オブジェクトが`CComPtrBase`、そのオブジェクトに関連付けられている同じオブジェクトを指しているかどうかを確認します。

```
bool IsEqualObject(IUnknown* pOther) throw();
```

### <a name="parameters"></a>パラメーター

*その他*<br/>
比較対象の `IUnknown *`。

### <a name="return-value"></a>戻り値

オブジェクトが同一の場合は true、そうでない場合は false を返します。

## <a name="ccomptrbaseoperator-"></a><a name="operator_not"></a>CComPtrBase::演算子!

NOT 演算子。

```
bool operator!() const throw();
```

### <a name="return-value"></a>戻り値

ポインターが NULL`CComHeapPtr`の場合は true、それ以外の場合は false を返します。

## <a name="ccomptrbaseoperator-amp"></a><a name="operator_amp"></a>コムプトルベース::オペレーター&amp;

&amp; 演算子。

```
T** operator&() throw();
```

### <a name="return-value"></a>戻り値

オブジェクトが指すオブジェクトのアドレスを`CComPtrBase`返します。

## <a name="ccomptrbaseoperator-"></a><a name="operator_star"></a>コムプトルベース::オペレーター\*

\* 演算子。

```
T& operator*() const throw();
```

### <a name="return-value"></a>戻り値

[:p の](#p)値を返します。つまり、`CComPtrBase`オブジェクトが参照するオブジェクトへのポインター。

デバッグ ビルドの場合[、CComPtrBase::p](#p)が NULL と等しくない場合、アサーション エラーが発生します。

## <a name="ccomptrbaseoperator-"></a><a name="operator_eq_eq"></a>を使用します。

等価演算子。

```
bool operator== (T* pT) const throw();
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

true を`CComPtrBase`返す場合 *、pT*が同じオブジェクトを指し、そうでない場合は false を返します。

## <a name="ccomptrbaseoperator--gt"></a><a name="operator_ptr"></a>コムプターベース::オペレーター -&gt;

メンバーへのポインター演算子。

```
_NoAddRefReleaseOnCComPtr<T>* operator->() const throw();
```

### <a name="return-value"></a>戻り値

データ メンバー変数[CComPtrBase::p](#p)の値を返します。

### <a name="remarks"></a>解説

この演算子は、オブジェクトが指すクラスのメソッドを`CComPtrBase`呼び出すために使います。 デバッグ ビルドでは、`CComPtrBase`データ メンバーが NULL を指すとアサーション エラーが発生します。

## <a name="ccomptrbaseoperator-lt"></a><a name="operator_lt"></a>コムプトルベース::オペレーター&lt;

より小さい演算子。

```
bool operator<(T* pT) const throw();
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

現在のオブジェクトによって管理されているポインターが比較対象のポインターより小さい場合は true を返します。

## <a name="ccomptrbaseoperator-t"></a><a name="operator_t_star"></a>コムプトルベース::オペレーターT\*

キャスト演算子。

```
operator T*() const throw();
```

### <a name="remarks"></a>解説

クラス テンプレートで定義されているオブジェクト データ型へのポインターを返します。

## <a name="ccomptrbasep"></a><a name="p"></a>コムプトルベース::p

ポインター データ メンバー変数。

```
T* p;
```

### <a name="remarks"></a>解説

このメンバー変数は、ポインター情報を保持します。

## <a name="ccomptrbasequeryinterface"></a><a name="queryinterface"></a>クエリインターフェイス

指定したインターフェイスへのポインターを返します。

```
template <class Q> HRESULT QueryInterface(Q
** pp) const throw();
```

### <a name="parameters"></a>パラメーター

*Q*<br/>
インターフェイス ポインターが必要なオブジェクト型。

*頁*<br/>
要求されたインターフェイス ポインターを受け取る出力変数のアドレス。

### <a name="return-value"></a>戻り値

成功時にS_OKを返し、失敗した場合はE_NOINTERFACEを返します。

### <a name="remarks"></a>解説

このメソッド[は、IUnknown::クエリインターフェイス](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))を呼び出します。

デバッグ ビルドでは *、pp*が NULL と等しくない場合にアサーション エラーが発生します。

## <a name="ccomptrbaserelease"></a><a name="release"></a>CComPtrベース::リリース

インターフェイスを解放するには、このメソッドを呼び出します。

```cpp
void Release() throw();
```

### <a name="remarks"></a>解説

インターフェイスが解放され[、CComPtrBase::p](#p)が NULL に設定されます。

## <a name="ccomptrbasesetsite"></a><a name="setsite"></a>コムプターベース::セットサイト

`CComPtrBase`オブジェクトのサイトを親オブジェクトの サイト`IUnknown`に設定します。

```
HRESULT SetSite(IUnknown* punkParent) throw();
```

### <a name="parameters"></a>パラメーター

*パンクペアレント*<br/>
親の`IUnknown`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドは[、アトリセットチャイルドサイト](composite-control-global-functions.md#atlsetchildsite)を呼び出します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
