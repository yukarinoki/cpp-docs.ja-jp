---
title: CComVariant クラス
ms.date: 11/04/2016
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
ms.openlocfilehash: 40315077ceba3d87e12c8ab426560deef4928793
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833609"
---
# <a name="ccomvariant-class"></a>CComVariant クラス

このクラスは、格納されているデータの型を示すメンバーを提供して、バリアント型をラップします。

## <a name="syntax"></a>構文

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComVariant:: CComVariant](#ccomvariant)|コンストラクターです。|
|[CComVariant:: ~ CComVariant](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComVariant:: Attach](#attach)|オブジェクトにバリアントをアタッチ `CComVariant` します。|
|[CComVariant:: ChangeType](#changetype)|オブジェクトを `CComVariant` 新しい型に変換します。|
|[CComVariant:: Clear](#clear)|オブジェクトをクリア `CComVariant` します。|
|[CComVariant:: Copy](#copy)|オブジェクトにバリアントをコピー `CComVariant` します。|
|[CComVariant:: CopyTo](#copyto)|オブジェクトの内容をコピーし `CComVariant` ます。|
|[CComVariant::D etach](#detach)|基になるバリアントをオブジェクトからデタッチし `CComVariant` ます。|
|[CComVariant:: GetSize](#getsize)|オブジェクトのコンテンツのサイズをバイト数で返し `CComVariant` ます。|
|[CComVariant:: ReadFromStream](#readfromstream)|ストリームからバリアントを読み込みます。|
|[CComVariant:: SetByRef](#setbyref)|オブジェクトを初期化 `CComVariant` し、メンバーを `vt` VT_BYREF に設定します。|
|[CComVariant:: WriteToStream](#writetostream)|基になるバリアントをストリームに保存します。|

### <a name="public-operators"></a>パブリック演算子

|演算子|説明|
|-|-|
|[CComVariant:: operator <](#operator_lt)|`CComVariant`オブジェクトが、指定されたバリアントより小さいかどうかを示します。|
|[CComVariant:: operator >](#operator_gt)|`CComVariant`オブジェクトが、指定されたバリアントよりも大きいかどうかを示します。|
|[operator! =](#operator_neq)|オブジェクトが、 `CComVariant` 指定されたバリアントと等しくないかどうかを示します。|
|[operator =](#operator_eq)|オブジェクトに値を割り当て `CComVariant` ます。|
|[operator = =](#operator_eq_eq)|`CComVariant`オブジェクトが指定されたバリアントと等しいかどうかを示します。|

## <a name="remarks"></a>解説

`CComVariant` union と、共用体に格納されているデータの型を示すメンバーで構成される、バリアント型と VARIANTARG 型をラップします。 バリアントは通常、オートメーションで使用されます。

`CComVariant` variant 型から派生して、バリアントを使用できる場所で使用できるようにします。 たとえば、V_VT マクロを使用しての型を抽出し `CComVariant` たり、バリアントと同様にメンバーに直接アクセスしたりすることができ `vt` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcomcli. h

## <a name="ccomvariantattach"></a><a name="attach"></a> CComVariant:: Attach

オブジェクトの現在の内容を安全にクリアし `CComVariant` 、 *psrc* の内容をこのオブジェクトにコピーして、バリアント型の *psrc* を VT_EMPTY に設定します。

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>パラメーター

*.Psrc*<br/>
からオブジェクトにアタッチされる [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) を指します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*Psrc*によって保持されているデータの所有権は、オブジェクトに転送され `CComVariant` ます。

## <a name="ccomvariantccomvariant"></a><a name="ccomvariant"></a> CComVariant:: CComVariant

各コンストラクター `CComVariant` は、Win32 関数を呼び出す `VariantInit` か、渡されたパラメーターに従ってオブジェクトの値と型を設定することによって、オブジェクトの安全な初期化を処理します。

```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```

### <a name="parameters"></a>パラメーター

*varSrc*<br/>
から `CComVariant` オブジェクトの初期化に使用されるまたはバリアント `CComVariant` 。 変換元バリアントの内容は変換せずにコピー先にコピーされます。

*lpszSrc*<br/>
からオブジェクトの初期化に使用される文字列 `CComVariant` 。 0で終わるワイド (Unicode) 文字列をコンストラクターの LPCOLESTR バージョンに渡すことも、ANSI 文字列を LPCSTR バージョンに渡すこともできます。 どちらの場合も、文字列はを使用して割り当てられた Unicode BSTR に変換され `SysAllocString` ます。 オブジェクトの型が `CComVariant` VT_BSTR されます。

*bSrc*<br/>
から **`bool`** オブジェクトを初期化するために使用する `CComVariant` 。 **`bool`** 引数は、格納される前に VARIANT_BOOL に変換されます。 オブジェクトの型が `CComVariant` VT_BOOL されます。

*nSrc*<br/>
から**`int`** オブジェクトを**BYTE** **`short`** **`long`** **`unsigned short`** **`unsigned long`** **`unsigned int`** 初期化するために使用される、、BYTE、、、longlong、ULONGLONG、、、または `CComVariant` 。 オブジェクトの型は、 `CComVariant` それぞれ VT_I4、VT_UI1、VT_I2、VT_I4、VT_I8、VT_UI8、VT_UI2、VT_UI4、または VT_UI4 になります。

*vtSrc*<br/>
からバリアントの型。 最初のパラメーターがの場合 **`int`** 、有効な型は VT_I4 および VT_INT です。 最初のパラメーターがの場合 **`long`** 、有効な型は VT_I4 および VT_ERROR です。 最初のパラメーターがの場合 **`double`** 、有効な型は VT_R8 および VT_DATE です。 最初のパラメーターがの場合 **`unsigned int`** 、有効な型は VT_UI4 および VT_UINT です。

*fltSrc*<br/>
から **`float`** オブジェクトを初期化するために使用する `CComVariant` 。 オブジェクトの型が `CComVariant` VT_R4 されます。

*dblSrc*<br/>
から **`double`** オブジェクトを初期化するために使用する `CComVariant` 。 オブジェクトの型が `CComVariant` VT_R8 されます。

*cySrc*<br/>
から `CY` オブジェクトを初期化するために使用する `CComVariant` 。 オブジェクトの型が `CComVariant` VT_CY されます。

*.Psrc*<br/>
から `IDispatch` `IUnknown` オブジェクトの初期化に使用されるポインターまたはポインター `CComVariant` 。 `AddRef` は、インターフェイスポインターで呼び出されます。 オブジェクトの型は、 `CComVariant` それぞれ VT_DISPATCH または VT_UNKNOWN になります。

または、オブジェクトの初期化に使用される、SAF のポインター `CComVariant` です。 SAFEARRAY のコピーは、オブジェクトに格納され `CComVariant` ます。 オブジェクトの型は、 `CComVariant` SAFEARRAY の元の型と VT_ARRAY の組み合わせになります。

*cSrc*<br/>
から **`char`** オブジェクトを初期化するために使用する `CComVariant` 。 オブジェクトの型が `CComVariant` VT_I1 されます。

*bstrSrc*<br/>
からオブジェクトの初期化に使用される BSTR `CComVariant` 。 オブジェクトの型が `CComVariant` VT_BSTR されます。

### <a name="remarks"></a>解説

デストラクターは、 [CComVariant:: Clear](#clear)を呼び出すことによってクリーンアップを管理します。

## <a name="ccomvariantccomvariant"></a><a name="dtor"></a> CComVariant:: ~ CComVariant

デストラクターです。

```
~CComVariant() throw();
```

### <a name="remarks"></a>解説

このメソッド [は、CComVariant:: Clear](#clear)を呼び出すことによってクリーンアップを管理します。

## <a name="ccomvariantchangetype"></a><a name="changetype"></a> CComVariant:: ChangeType

オブジェクトを `CComVariant` 新しい型に変換します。

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>パラメーター

*vtNew*<br/>
からオブジェクトの新しい型 `CComVariant` 。

*.Psrc*<br/>
から値が新しい型に変換されるバリアントへのポインター。 既定値は NULL です。これは、 `CComVariant` オブジェクトが代わりに変換されることを意味します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*Psrc*に値を渡すと、 `ChangeType` はこのバリアントを変換のソースとして使用します。 それ以外の場合は、 `CComVariant` オブジェクトがソースになります。

## <a name="ccomvariantclear"></a><a name="clear"></a> CComVariant:: Clear

`CComVariant`Win32 関数を呼び出すことによって、オブジェクトをクリアし `VariantClear` ます。

```
HRESULT Clear();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

デストラクターは自動的に `Clear` を呼び出します。

## <a name="ccomvariantcopy"></a><a name="copy"></a> CComVariant:: Copy

オブジェクトを解放し、 `CComVariant` 指定したバリアントのコピーを割り当てます。

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>パラメーター

*.Psrc*<br/>
からコピーされる [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomvariantcopyto"></a><a name="copyto"></a> CComVariant:: CopyTo

オブジェクトの内容をコピーし `CComVariant` ます。

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>パラメーター

*pstrDest*<br/>
オブジェクトの内容のコピーを受け取る BSTR を指し `CComVariant` ます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`CComVariant`オブジェクトの型は VT_BSTR である必要があります。

## <a name="ccomvariantdetach"></a><a name="detach"></a> CComVariant::D etach

基になるバリアントをオブジェクトからデタッチ `CComVariant` し、オブジェクトの型を VT_EMPTY に設定します。

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
入出力オブジェクトの基になるバリアント値を返します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*Pdest*によって参照されるバリアントの内容は、呼び出し元のオブジェクトの値と型が割り当てられる前に自動的にクリアされることに注意して `CComVariant` ください。

## <a name="ccomvariantgetsize"></a><a name="getsize"></a> CComVariant:: GetSize

単純固定サイズのバリアントの場合、このメソッドは、 **`sizeof`** 基になるデータ型と **SIZEOF (VARTYPE)** の値を返します。

```
ULONG GetSize() const;
```

### <a name="return-value"></a>戻り値

オブジェクトの現在のコンテンツのサイズ (バイト単位) `CComVariant` 。

### <a name="remarks"></a>解説

バリアントにインターフェイスポインターが含まれている場合 `GetSize` は、またはに対してクエリを `IPersistStream` `IPersistStreamInit` 行います。 成功した場合、戻り値は、+ とによって返される値の下位32ビットになり `GetSizeMax` `sizeof(CLSID)` `sizeof(VARTYPE)` ます。 インターフェイスポインターが NULL の場合、は `GetSize` 正の値を返し `sizeof(CLSID)` `sizeof(VARTYPE)` ます。 合計サイズが ULONG_MAX より大きい場合は、 `GetSize` エラーを示すを返し `sizeof(VARTYPE)` ます。

それ以外の場合は、VT_BSTR 型の一時的なバリアントが現在のバリアントから強制されます。 この BSTR の長さは、文字列の長さと文字列自体の長さに加え、null 文字と **sizeof (VARTYPE)** のサイズを加算した値として計算されます。 バリアントを VT_BSTR 型のバリアントに強制的に変換できない場合、は `GetSize` **SIZEOF (VARTYPE)** を返します。

このメソッドによって返されるサイズは、正常な条件下で [CComVariant:: WriteToStream](#writetostream) によって使用されるバイト数と一致します。

## <a name="ccomvariantoperator-"></a><a name="operator_eq"></a> CComVariant:: operator =

オブジェクトに値と対応する型を割り当て `CComVariant` ます。

```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```

### <a name="parameters"></a>パラメーター

*varSrc*<br/>
から`CComVariant`オブジェクトに[VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant)割り当てられるまたはバリアント `CComVariant` 。 変換元バリアントの内容は変換せずにコピー先にコピーされます。

*bstrSrc*<br/>
からオブジェクトに割り当てられる BSTR `CComVariant` 。 オブジェクトの型が `CComVariant` VT_BSTR されます。

*lpszSrc*<br/>
からオブジェクトに割り当てられる文字列 `CComVariant` 。 0で終わるワイド (Unicode) 文字列を演算子の LPCOLESTR バージョンに渡すことも、ANSI 文字列を LPCSTR バージョンに渡すこともできます。 どちらの場合も、文字列はを使用して割り当てられた Unicode BSTR に変換され `SysAllocString` ます。 オブジェクトの型が `CComVariant` VT_BSTR されます。

*bSrc*<br/>
から **`bool`** オブジェクトに割り当てられる `CComVariant` 。 **`bool`** 引数は、格納される前に VARIANT_BOOL に変換されます。 オブジェクトの型が `CComVariant` VT_BOOL されます。

*nSrc*<br/>
から **`int`** **`short`** オブジェクトに割り当てる、BYTE、、、 **`long`** LONGLONG、ULONGLONG、、、 **`unsigned short`** **`unsigned long`** または **`unsigned int`** `CComVariant` 。 オブジェクトの型は、 `CComVariant` それぞれ VT_I4、VT_UI1、VT_I2、VT_I4、VT_I8、VT_UI8、VT_UI2、VT_UI4、または VT_UI4 になります。

*fltSrc*<br/>
から **`float`** オブジェクトに割り当てられる `CComVariant` 。 オブジェクトの型が `CComVariant` VT_R4 されます。

*dblSrc*<br/>
から **`double`** オブジェクトに割り当てられる `CComVariant` 。 オブジェクトの型が `CComVariant` VT_R8 されます。

*cySrc*<br/>
から `CY` オブジェクトに割り当てられる `CComVariant` 。 オブジェクトの型が `CComVariant` VT_CY されます。

*.Psrc*<br/>
から `IDispatch` `IUnknown` オブジェクトに割り当てられるポインターまたはポインター `CComVariant` 。 `AddRef` は、インターフェイスポインターで呼び出されます。 オブジェクトの型は、 `CComVariant` それぞれ VT_DISPATCH または VT_UNKNOWN になります。

または、オブジェクトに割り当てられる SAFEARRAY ポインター `CComVariant` 。 SAFEARRAY のコピーは、オブジェクトに格納され `CComVariant` ます。 オブジェクトの型は、 `CComVariant` SAFEARRAY の元の型と VT_ARRAY の組み合わせになります。

*cSrc*<br/>
からオブジェクトに割り当てられる char `CComVariant` 。 オブジェクトの型が `CComVariant` VT_I1 されます。

## <a name="ccomvariantoperator-"></a><a name="operator_eq_eq"></a> CComVariant:: operator = =

`CComVariant`オブジェクトが指定されたバリアントと等しいかどうかを示します。

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>解説

*Varsrc*の値と型が、オブジェクトの値と型にそれぞれ等しい場合に TRUE を返し `CComVariant` ます。 それ以外の場合は FALSE。 演算子は、ユーザーの既定のロケールを使用して比較を実行します。

演算子は、バリアント型の値のみを比較します。 これは、文字列、整数、および浮動小数点を比較しますが、配列やレコードは比較しません。

## <a name="ccomvariantoperator-"></a><a name="operator_neq"></a> CComVariant:: operator! =

オブジェクトが、 `CComVariant` 指定されたバリアントと等しくないかどうかを示します。

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>解説

*Varsrc*の値または型が、それぞれオブジェクトの値または型と等しくない場合に TRUE を返し `CComVariant` ます。 それ以外の場合は FALSE。 演算子は、ユーザーの既定のロケールを使用して比較を実行します。

演算子は、バリアント型の値のみを比較します。 これは、文字列、整数、および浮動小数点を比較しますが、配列やレコードは比較しません。

## <a name="ccomvariantoperator-lt"></a><a name="operator_lt"></a> CComVariant:: operator &lt;

`CComVariant`オブジェクトが、指定されたバリアントより小さいかどうかを示します。

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>解説

オブジェクトの値 `CComVariant` が *varsrc*の値より小さい場合に TRUE を返します。 それ以外の場合は FALSE。 演算子は、ユーザーの既定のロケールを使用して比較を実行します。

## <a name="ccomvariantoperator-gt"></a><a name="operator_gt"></a> CComVariant:: operator &gt;

`CComVariant`オブジェクトが、指定されたバリアントよりも大きいかどうかを示します。

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>解説

オブジェクトの値 `CComVariant` が *varsrc*の値より大きい場合に TRUE を返します。 それ以外の場合は FALSE。 演算子は、ユーザーの既定のロケールを使用して比較を実行します。

## <a name="ccomvariantreadfromstream"></a><a name="readfromstream"></a> CComVariant:: ReadFromStream

基になるバリアントを、指定したストリームに格納されているバリアントに設定します。

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*pStream*<br/>
からデータを格納しているストリームの [IStream](/windows/win32/api/objidl/nn-objidl-istream) インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`ReadToStream`[Writetostream](#writetostream)に対する以前の呼び出しが必要です。

## <a name="ccomvariantsetbyref"></a><a name="setbyref"></a> CComVariant:: SetByRef

オブジェクトを初期化 `CComVariant` し、メンバーを `vt` VT_BYREF に設定します。

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
バリアントの型 (BSTR、、など) **`int`** **`char`** 。

*未満*<br/>
オブジェクトを初期化するために使用するポインター `CComVariant` 。

### <a name="remarks"></a>解説

`SetByRef` は、 `CComVariant` オブジェクトをポインター *ポイント* に初期化し、メンバーを VT_BYREF に設定する関数テンプレートです `vt` 。 次に例を示します。

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

## <a name="ccomvariantwritetostream"></a><a name="writetostream"></a> CComVariant:: WriteToStream

基になるバリアントをストリームに保存します。

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*pStream*<br/>
からストリームの [IStream](/windows/win32/api/objidl/nn-objidl-istream) インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
