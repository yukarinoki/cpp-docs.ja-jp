---
title: クラス
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
ms.openlocfilehash: 9a84d91e20242fb206d1d3f71fcb3dd207561f62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327225"
---
# <a name="ccomvariant-class"></a>クラス

このクラスは、格納されているデータの型を示すメンバーを提供する VARIANT 型をラップします。

## <a name="syntax"></a>構文

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コミュ・バリアント:コミュ・バリアント](#ccomvariant)|コンストラクターです。|
|[コミュ・バリアント::~コミュ・バリアント](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コミュ・バリアント:アタッチ](#attach)|オブジェクトにバリアント型をアタッチ`CComVariant`します。|
|[を変更します。](#changetype)|オブジェクトを`CComVariant`新しい型に変換します。|
|[コミュ・バリアント:クリア](#clear)|オブジェクトをクリア`CComVariant`します。|
|[コミュ・バリアント:コピー](#copy)|オブジェクトにバリアント型`CComVariant`(VARIANT) をコピーします。|
|[コミュ・バリアント:コピー・トー](#copyto)|オブジェクトの内容を`CComVariant`コピーします。|
|[コミュニア :Dバリアント](#detach)|基になる VARIANT を`CComVariant`オブジェクトからデタッチします。|
|[を指定します。](#getsize)|オブジェクトの内容のバイト数でサイズを`CComVariant`返します。|
|[を読み取る](#readfromstream)|ストリームからバリアント型 (VARIANT) を読み込みます。|
|[を指定します。](#setbyref)|オブジェクトを`CComVariant`初期化し、メンバーを`vt`VT_BYREFに設定します。|
|[を使用します。](#writetostream)|基になる VARIANT をストリームに保存します。|

### <a name="public-operators"></a>パブリック演算子

|||
|-|-|
|[<演算子](#operator_lt)|オブジェクトが指定`CComVariant`した VARIANT より小さいかどうかを示します。|
|[>演算子](#operator_gt)|オブジェクトが指定`CComVariant`した VARIANT より大きいかどうかを示します。|
|[演算子 !=](#operator_neq)|オブジェクトが指定`CComVariant`した VARIANT と等しくないかどうかを示します。|
|[演算子 =](#operator_eq)|`CComVariant`オブジェクトに値を割り当てます。|
|[演算子 ==](#operator_eq_eq)|オブジェクトが指定`CComVariant`した VARIANT と等しいかどうかを示します。|

## <a name="remarks"></a>解説

`CComVariant`和集合と、共用体に格納されているデータの型を示すメンバーから成るバリアント型と VARIANTARG 型をラップします。 VARIANT は通常、オートメーションで使用されます。

`CComVariant`バリアント型から派生するため、バリアント型を使用できる場所であればどこでも使用できます。 たとえば、V_VT マクロを使用して a 型を`CComVariant`抽出したり、VARIANT と同様に`vt`メンバーに直接アクセスすることができます。

## <a name="inheritance-hierarchy"></a>継承階層

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlcomcli.h

## <a name="ccomvariantattach"></a><a name="attach"></a>コミュ・バリアント:アタッチ

オブジェクトの現在の内容を`CComVariant`安全にクリアし *、pSrc*の内容をこのオブジェクトにコピーしてから *、pSrc*のバリアント型をVT_EMPTYに設定します。

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>パラメーター

*pSrc*<br/>
[in]オブジェクトにアタッチする[バリアント型 (VARIANT)](/windows/win32/api/oaidl/ns-oaidl-variant)へのポイント。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*pSrc*が保有するデータの所有権は、オブジェクト`CComVariant`に転送されます。

## <a name="ccomvariantccomvariant"></a><a name="ccomvariant"></a>コミュ・バリアント:コミュ・バリアント

各コンストラクターは`VariantInit`、Win32`CComVariant`関数を呼び出すか、渡されたパラメーターに従ってオブジェクトの値と型を設定することによって、オブジェクトの安全な初期化を処理します。

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
[in]オブジェクト`CComVariant`の初期化に使用される`CComVariant`バリアント型 (VARIANT) です。 ソースバリアントの内容は変換されずにコピー先にコピーされます。

*lpszSrc*<br/>
[in]オブジェクトの初期化に使用する`CComVariant`文字列。 ゼロ終端ワイド (Unicode) 文字ストリングを LPCOLESTR バージョンのコンストラクターに、または ANSI ストリングを LPCSTR バージョンに渡すことができます。 どちらの場合も、文字列は を使用して`SysAllocString`割り当てられた Unicode BSTR に変換されます。 オブジェクトの`CComVariant`型はVT_BSTRされます。

*bSrc*<br/>
[in]オブジェクトの初期化に使用される`CComVariant` **bool。** **bool**引数は、保存される前にVARIANT_BOOLに変換されます。 オブジェクトの`CComVariant`型がVT_BOOLされます。

*nSrc*<br/>
[in]**int**、 **BYTE**、**ショート**、**ロング**ロング 、 ULONG、**符号なしの短い**、**符号なし長** `CComVariant` 、 または符号なし**int**を使用してオブジェクトを初期化します。 オブジェクトの`CComVariant`型は、それぞれVT_I4、VT_UI1、VT_I2、VT_I4、VT_I8、VT_UI8、VT_UI2、VT_UI4、またはVT_UI4になります。

*vtSrc*<br/>
[in]バリアントの型。 最初のパラメータが**int**の場合、有効な型はVT_I4され、VT_INT。 最初のパラメータが**long**の場合、有効な型はVT_I4され、VT_ERROR。 最初のパラメータが**倍精度浮動小数点数**の場合、有効な型はVT_R8され、VT_DATE。 最初のパラメータが**符号なし int**の場合、有効な型はVT_UI4され、VT_UINT。

*フルツルク*<br/>
[in]オブジェクトの初期化に使用される`CComVariant`**浮動小数点数**。 オブジェクトの`CComVariant`型がVT_R4されます。

*dblSrc*<br/>
[in]オブジェクト**double**の初期化に使用される`CComVariant`double です。 オブジェクトの`CComVariant`型はVT_R8されます。

*サイスルク*<br/>
[in]オブジェクト`CY`の初期化に使用`CComVariant`されます。 オブジェクトの`CComVariant`型はVT_CYされます。

*pSrc*<br/>
[in]オブジェクト`IDispatch`の`IUnknown`初期化に使用される`CComVariant`またはポインター。 `AddRef`はインターフェイス ポインターで呼び出されます。 オブジェクトの`CComVariant`型はそれぞれVT_DISPATCHまたはVT_UNKNOWNされます。

または、オブジェクトの初期化に使用される`CComVariant`SAFERRAY ポインター。 SAFEARRAY のコピーがオブジェクトに`CComVariant`格納されます。 オブジェクトの`CComVariant`型は、SAFEARRAY の元の型とVT_ARRAYの組み合わせになります。

*Csrc*<br/>
[in]オブジェクトの初期化に使用する`CComVariant` **char。** オブジェクトの`CComVariant`型はVT_I1されます。

*bstrSrc*<br/>
[in]オブジェクトの初期化に使用される`CComVariant`BSTR。 オブジェクトの`CComVariant`型はVT_BSTRされます。

### <a name="remarks"></a>解説

デストラクターは[、CComVariant::Clear](#clear)を呼び出すことによってクリーンアップを管理します。

## <a name="ccomvariantccomvariant"></a><a name="dtor"></a>コミュ・バリアント::~コミュ・バリアント

デストラクターです。

```
~CComVariant() throw();
```

### <a name="remarks"></a>解説

このメソッドは[、CComVariant::Clear](#clear)を呼び出すことによってクリーンアップを管理します。

## <a name="ccomvariantchangetype"></a><a name="changetype"></a>を変更します。

オブジェクトを`CComVariant`新しい型に変換します。

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>パラメーター

*vtNew*<br/>
[in]`CComVariant`オブジェクトの新しい型。

*pSrc*<br/>
[in]値が新しい型に変換される VARIANT へのポインター。 既定値は NULL で、オブジェクト`CComVariant`は所定の位置に変換されます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*pSrc*に値を渡すと`ChangeType`、変換元としてこのバリアントを使用します。 それ以外の`CComVariant`場合、オブジェクトはソースになります。

## <a name="ccomvariantclear"></a><a name="clear"></a>コミュ・バリアント:クリア

Win32`CComVariant`関数を呼`VariantClear`び出してオブジェクトをクリアします。

```
HRESULT Clear();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

デストラクターは、`Clear`を自動的に呼び出します。

## <a name="ccomvariantcopy"></a><a name="copy"></a>コミュ・バリアント:コピー

オブジェクトを`CComVariant`解放し、指定した VARIANT のコピーを割り当てます。

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>パラメーター

*pSrc*<br/>
[in]コピーする[バリアント型 (VARIANT)](/windows/win32/api/oaidl/ns-oaidl-variant)へのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="ccomvariantcopyto"></a><a name="copyto"></a>コミュ・バリアント:コピー・トー

オブジェクトの内容を`CComVariant`コピーします。

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>パラメーター

*最も多い*<br/>
オブジェクトの内容のコピーを受け取る BSTR への`CComVariant`ポイント。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

オブジェクト`CComVariant`は、VT_BSTR型である必要があります。

## <a name="ccomvariantdetach"></a><a name="detach"></a>コミュニア :Dバリアント

基になる VARIANT を`CComVariant`オブジェクトからデタッチし、オブジェクトの型をVT_EMPTYに設定します。

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>パラメーター

*pDest*<br/>
[アウト]オブジェクトの基になる VARIANT 値を返します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

*pDest*によって参照される VARIANT の内容は、呼び出し元`CComVariant`オブジェクトの値と型が割り当てられる前に自動的に消去されます。

## <a name="ccomvariantgetsize"></a><a name="getsize"></a>を指定します。

単純固定サイズの VARIANT の場合、このメソッドは、基になるデータ型**のサイズ**に**sizeof (VARTYPE)** を加えたサイズを返します。

```
ULONG GetSize() const;
```

### <a name="return-value"></a>戻り値

オブジェクトの現在の内容のサイズ (`CComVariant`バイト単位)。

### <a name="remarks"></a>解説

VARIANT にインターフェイス ポインターが含`GetSize`まれている場合は`IPersistStream`、`IPersistStreamInit`または を照会します。 成功した場合、戻り値は、CLSID と`GetSizeMax`**sizeof (VARTYPE)****のサイズ**を足した値の下位 32 ビットです。 インターフェイス ポインタが NULL`GetSize`の場合は、CLSID プラス**サイズのサイズを**返します。 **sizeof** 合計サイズがULONG_MAXより大きい場合は`GetSize`、エラーを示す**sizeof(VARTYPE) を**返します。

それ以外のすべての場合、VT_BSTR型の一時的な VARIANT は、現在の VARIANT から強制変換されます。 この BSTR の長さは、文字列の長さに文字列自体の長さに、null 文字 + **sizeof (VARTYPE)** のサイズを加えた長さのサイズとして計算されます。 バリアント型を型 VT_BSTRのバリアント型に強制変換できない場合は、 `GetSize` **sizeof (VARTYPE)** を返します。

このメソッドによって返されるサイズは、正常な条件下で[使用](#writetostream)されるバイト数と一致します。

## <a name="ccomvariantoperator-"></a><a name="operator_eq"></a>演算子 =

オブジェクトに値と対応する型を`CComVariant`割り当てます。

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
[in]オブジェクトに割り当てられる バリアント`CComVariant`型 ( [VARIANT)](/windows/win32/api/oaidl/ns-oaidl-variant)です。 `CComVariant` ソースバリアントの内容は変換されずにコピー先にコピーされます。

*bstrSrc*<br/>
[in]`CComVariant`オブジェクトに割り当てられる BSTR。 オブジェクトの`CComVariant`型はVT_BSTRされます。

*lpszSrc*<br/>
[in]`CComVariant`オブジェクトに割り当てられる文字列。 ゼロ終端ワイド (Unicode) 文字ストリングを LPCOLESTR バージョンのオペレーターに、または ANSI ストリングを LPCSTR バージョンに渡すことができます。 いずれの場合も、文字列は を使用して`SysAllocString`割り当てられた Unicode BSTR に変換されます。 オブジェクトの`CComVariant`型はVT_BSTRされます。

*bSrc*<br/>
[in]`CComVariant`オブジェクトに割り当てられる**bool。** **bool**引数は、保存される前にVARIANT_BOOLに変換されます。 オブジェクトの`CComVariant`型がVT_BOOLされます。

*nSrc*<br/>
[in]**int**、 BYTE 、 **short**、 **long**、 Longlong 、**符号なしの短い**、**符号なし長**、`CComVariant`または**符号なし int**をオブジェクトに割り当てる。 オブジェクトの`CComVariant`型は、それぞれVT_I4、VT_UI1、VT_I2、VT_I4、VT_I8、VT_UI8、VT_UI2、VT_UI4、またはVT_UI4になります。

*フルツルク*<br/>
[in]オブジェクトに割り当てられる**浮動小数点数**。 `CComVariant` オブジェクトの`CComVariant`型がVT_R4されます。

*dblSrc*<br/>
[in]オブジェクトに割り当てられる**倍精度**浮動小数点数。 `CComVariant` オブジェクトの`CComVariant`型はVT_R8されます。

*サイスルク*<br/>
[in]オブジェクト`CY`に割り当てられる`CComVariant`。 オブジェクトの`CComVariant`型はVT_CYされます。

*pSrc*<br/>
[in]オブジェクトに割り当てられる`IDispatch`または`IUnknown`ポインタ。 `CComVariant` `AddRef`はインターフェイス ポインターで呼び出されます。 オブジェクトの`CComVariant`型はそれぞれVT_DISPATCHまたはVT_UNKNOWNされます。

または、オブジェクトに割り当てる SAFEARRAY`CComVariant`ポインター。 SAFEARRAY のコピーがオブジェクトに`CComVariant`格納されます。 オブジェクトの`CComVariant`型は、SAFEARRAY の元の型とVT_ARRAYの組み合わせになります。

*Csrc*<br/>
[in]`CComVariant`オブジェクトに割り当てられる char。 オブジェクトの`CComVariant`型はVT_I1されます。

## <a name="ccomvariantoperator-"></a><a name="operator_eq_eq"></a>次の演算子 ==

オブジェクトが指定`CComVariant`した VARIANT と等しいかどうかを示します。

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>解説

*varSrc*の値と型が、オブジェクトの値と型と等しい場合は TRUE を`CComVariant`返します。 それ以外の場合は FALSE。 演算子は、ユーザーのデフォルトロケールを使用して比較を実行します。

演算子は、バリアント型の値のみを比較します。 文字列、整数、浮動小数点を比較しますが、配列やレコードは比較しません。

## <a name="ccomvariantoperator-"></a><a name="operator_neq"></a>演算子を使用します。

オブジェクトが指定`CComVariant`した VARIANT と等しくないかどうかを示します。

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>解説

*varSrc*の値または型が、オブジェクトの値または型と等しくない場合は、TRUE を`CComVariant`返します。 それ以外の場合は FALSE。 演算子は、ユーザーのデフォルトロケールを使用して比較を実行します。

演算子は、バリアント型の値のみを比較します。 文字列、整数、浮動小数点を比較しますが、配列やレコードは比較しません。

## <a name="ccomvariantoperator-lt"></a><a name="operator_lt"></a>演算子&lt;

オブジェクトが指定`CComVariant`した VARIANT より小さいかどうかを示します。

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>解説

オブジェクトの値が`CComVariant`*varSrc*の値より小さい場合は TRUE を返します。 それ以外の場合は FALSE。 演算子は、ユーザーのデフォルトロケールを使用して比較を実行します。

## <a name="ccomvariantoperator-gt"></a><a name="operator_gt"></a>演算子&gt;

オブジェクトが指定`CComVariant`した VARIANT より大きいかどうかを示します。

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>解説

`CComVariant`オブジェクトの値が*varSrc*の値より大きい場合は TRUE を返します。 それ以外の場合は FALSE。 演算子は、ユーザーのデフォルトロケールを使用して比較を実行します。

## <a name="ccomvariantreadfromstream"></a><a name="readfromstream"></a>を読み取る

基になる VARIANT を、指定したストリームに含まれる VARIANT に設定します。

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
[in]データを含むストリーム上の[IStream](/windows/win32/api/objidl/nn-objidl-istream)インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`ReadToStream`には、前の呼び出し[が必要です](#writetostream)。

## <a name="ccomvariantsetbyref"></a><a name="setbyref"></a>を指定します。

オブジェクトを`CComVariant`初期化し、メンバーを`vt`VT_BYREFに設定します。

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>パラメーター

*T*<br/>
バリアント型 (BSTR、int、または**int**char など **) の**型。

*Pt*<br/>
オブジェクトの初期化に使用する`CComVariant`ポインター。

### <a name="remarks"></a>解説

`SetByRef`は、ポインター *pT*に`CComVariant`オブジェクトを初期化し、メンバーをVT_BYREFに`vt`設定する関数テンプレートです。 次に例を示します。

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

## <a name="ccomvariantwritetostream"></a><a name="writetostream"></a>を使用します。

基になる VARIANT をストリームに保存します。

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
[in]ストリーム上の[IStream](/windows/win32/api/objidl/nn-objidl-istream)インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
