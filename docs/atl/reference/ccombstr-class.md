---
title: CComBSTR クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54677e573f36fca65cc46dc5207e8812e4fa4fa6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752931"
---
# <a name="ccombstr-class"></a>CComBSTR クラス

このクラスは、Bstr のラッパーです。

## <a name="syntax"></a>構文

```
class CComBSTR
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComBSTR::CComBSTR](#ccombstr)|コンストラクターです。|
|[CComBSTR:: ~ CComBSTR](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CComBSTR::Append](#append)|文字列を付加`m_str`します。|
|[CComBSTR::AppendBSTR](#appendbstr)|追加するための BSTR`m_str`します。|
|[CComBSTR::AppendBytes](#appendbytes)|指定したバイト数を追加します。`m_str`します。|
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Safearray 内の各要素の最初の文字から BSTR を作成しにアタッチします、`CComBSTR`オブジェクト。|
|[CComBSTR::AssignBSTR](#assignbstr)|BSTR を割り当てます`m_str`します。|
|[CComBSTR::Attach](#attach)|アタッチするための BSTR、`CComBSTR`オブジェクト。|
|[CComBSTR::BSTRToArray](#bstrtoarray)|配列の各要素が含まれる文字を 0 から始まる 1 次元の safearray を作成し、`CComBSTR`オブジェクト。|
|[CComBSTR::ByteLength](#bytelength)|長さを返します`m_str`(バイト単位)。|
|[CComBSTR::Copy](#copy)|コピーを返します`m_str`します。|
|[CComBSTR::CopyTo](#copyto)|コピーを返します`m_str`を使用して、 **[out]** パラメーター|
|[CComBSTR::Detach](#detach)|デタッチ`m_str`から、`CComBSTR`オブジェクト。|
|[CComBSTR::Empty](#empty)|解放`m_str`します。|
|[CComBSTR::Length](#length)|長さを返します`m_str`します。|
|[CComBSTR::LoadString](#loadstring)|文字列リソースを読み込みます。|
|[CComBSTR::ReadFromStream](#readfromstream)|ストリームから BSTR オブジェクトを読み込みます。|
|[CComBSTR::ToLower](#tolower)|文字列を小文字に変換します。|
|[CComBSTR::ToUpper](#toupper)|文字列を大文字に変換します。|
|[CComBSTR::WriteToStream](#writetostream)|保存`m_str`をストリームにします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CComBSTR::operator BSTR](#operator_bstr)|キャストを`CComBSTR`bstr オブジェクト。|
|[CComBSTR::operator!](#operator_not)|TRUE かどうかに応じて、FALSE を返します`m_str`は NULL です。|
|[CComBSTR::operator! =](#operator_neq)|比較、`CComBSTR`文字列を使用します。|
|[CComBSTR::operator (& a)](#operator_amp)|アドレスを返して`m_str`します。|
|[CComBSTR::operator + =](#operator_add_eq)|追加、`CComBSTR`オブジェクトにします。|
|[CComBSTR::operator <](#operator_lt)|比較、`CComBSTR`文字列を使用します。|
|[CComBSTR::operator =](#operator_eq)|値を代入`m_str`します。|
|[CComBSTR::operator = =](#operator_eq_eq)|比較、`CComBSTR`文字列を使用します。|
|[CComBSTR::operator >](#operator_gt)|比較、`CComBSTR`文字列を使用します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CComBSTR::m_str](#m_str)|関連付けられている BSTR が含まれています、`CComBSTR`オブジェクト。|

## <a name="remarks"></a>Remarks

`CComBSTR`クラスは、固定長の文字列である Bstr 用のラッパーです。 長さは、文字列の前に、データのメモリ位置に整数として格納されます。

A [BSTR](/previous-versions/windows/desktop/automat/bstr)が null で終了した後、最後の文字をカウントされますが、文字列に埋め込まれた null 文字を含めることもできます。 文字列の長さは、最初の null 文字しない、文字数によって決まります。

> [!NOTE]
>  `CComBSTR`クラスには、いくつかの引数として文字列を ANSI または Unicode のいずれかを実行するメンバー (コンス トラクター、代入演算子、および比較演算子) が用意されています。 これらの関数の ANSI バージョンは、一時的な Unicode 文字列が内部的に多くの場合、作成されるため、Unicode 対応するより非効率です。 効率性のためには、可能であれば Unicode バージョンを使用します。

> [!NOTE]
>  Visual Studio .NET で実装される改善されたルックアップ動作のためのコードなど`bstr = L"String2" + bstr;`、以前のリリースでコンパイルする代わりに実装するとして`bstr = CStringW(L"String2") + bstr`します。

使用する場合の注意事項の一覧については`CComBSTR`を参照してください[CComBSTR を使用したプログラミング](../../atl/programming-with-ccombstr-atl.md)します。

## <a name="requirements"></a>要件

**ヘッダー:** atlbase.h

##  <a name="append"></a>  CComBSTR::Append

いずれかの追加*lpsz*またはの BSTR メンバー *bstrSrc*に[m_str](#m_str)します。

```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```

### <a name="parameters"></a>パラメーター

*bstrSrc*  
[in]A`CComBSTR`オブジェクトを追加します。

*ch*  
[in]追加する文字。

*lpsz*  
[in]追加する文字の 0 で終わる文字列。 LPCOLESTR オーバー ロードまたは LPCSTR バージョンを使用して ANSI 文字列を使用して Unicode 文字列を渡すことができます。

*nLen*  
[in]文字数*lpsz*を追加します。

### <a name="return-value"></a>戻り値

成功した場合、または任意の標準的な HRESULT エラー値に s_ok を返します。

### <a name="remarks"></a>Remarks

追加する前に、ANSI 文字列を Unicode に変換されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

##  <a name="appendbstr"></a>  CComBSTR::AppendBSTR

指定された BSTR を追加します。 [m_str](#m_str)します。

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>パラメーター

*p*  
[in]追加する BSTR。

### <a name="return-value"></a>戻り値

成功した場合、または任意の標準的な HRESULT エラー値に s_ok を返します。

### <a name="remarks"></a>Remarks

このメソッドに通常のワイド文字の文字列を渡さないでください。 コンパイラはエラーをキャッチし、実行時エラーが発生することはできません。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

##  <a name="appendbytes"></a>  CComBSTR::AppendBytes

指定したバイト数を追加します。 [m_str](#m_str)変換なし。

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>パラメーター

*lpsz*  
[in]追加するバイトの配列へのポインター。

*p*  
[in]追加するバイト数。

### <a name="return-value"></a>戻り値

成功した場合、または任意の標準的な HRESULT エラー値に s_ok を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

##  <a name="arraytobstr"></a>  CComBSTR::ArrayToBSTR

保持されている既存の文字列を解放、`CComBSTR`オブジェクト、safearray 内の各要素の最初の文字から BSTR を作成しにアタッチします、`CComBSTR`オブジェクト。

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>パラメーター

*pSrc*  
[in]文字列を作成するために使用する要素を含むの safearray。

### <a name="return-value"></a>戻り値

成功した場合、または任意の標準的な HRESULT エラー値に s_ok を返します。

##  <a name="assignbstr"></a>  CComBSTR::AssignBSTR

BSTR を割り当てます[m_str](#m_str)します。

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>パラメーター

*bstrSrc*  
[in]現在に割り当てる BSTR`CComBSTR`オブジェクト。

### <a name="return-value"></a>戻り値

成功した場合、または任意の標準的な HRESULT エラー値に s_ok を返します。

##  <a name="attach"></a>  CComBSTR::Attach

アタッチするための BSTR、`CComBSTR`オブジェクトを設定して、 [m_str](#m_str)メンバーを*src*。

```
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>パラメーター

*src*  
[in]オブジェクトにアタッチする BSTR。

### <a name="remarks"></a>Remarks

このメソッドに通常のワイド文字の文字列を渡さないでください。 コンパイラはエラーをキャッチし、実行時エラーが発生することはできません。

> [!NOTE]
>  場合、このメソッドはアサート`m_str`以外の場合します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="bstrtoarray"></a>  CComBSTR::BSTRToArray

配列の各要素が含まれる文字を 0 から始まる 1 次元の safearray を作成し、`CComBSTR`オブジェクト。

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>パラメーター

*ppArray*  
[out]関数の結果を保持するために使用する safearray へのポインター。

### <a name="return-value"></a>戻り値

成功した場合、または任意の標準的な HRESULT エラー値に s_ok を返します。

##  <a name="bytelength"></a>  CComBSTR::ByteLength

内のバイト数を返します`m_str`、終端の null 文字は除きます。

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>戻り値

長さ、 [m_str](#m_str)メンバー (バイト単位)。

### <a name="remarks"></a>Remarks

0 を返します`m_str`は NULL です。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

##  <a name="ccombstr"></a>  CComBSTR::CComBSTR

コンストラクターです。 既定のコンス トラクターは、設定、 [m_str](#m_str)メンバーを NULL にします。

```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);  
CComBSTR(REFGUID  guid);  
CComBSTR(int nSize);  
CComBSTR(int nSize, LPCOLESTR sz);  
CComBSTR(int nSize, LPCSTR sz);  
CComBSTR(LPCOLESTR pSrc);  
CComBSTR(LPCSTR pSrc);  
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="parameters"></a>パラメーター

*nSize*  
[in]コピーする文字数*sz*または文字数の初期サイズ、`CComBSTR`します。

*sz*  
[入力] コピーする文字列。 Unicode バージョンを LPCOLESTR; を指定しますANSI バージョンには、LPCSTR を指定します。

*pSrc*  
[入力] コピーする文字列。 Unicode バージョンを LPCOLESTR; を指定しますANSI バージョンには、LPCSTR を指定します。

*src*  
[入力] `CComBSTR` オブジェクト。

*guid*  
[in]参照を`GUID`構造体。

### <a name="remarks"></a>Remarks

コピー コンス トラクターのセット`m_str`の BSTR メンバーのコピーに*src*します。`REFGUID`コンス トラクターに GUID を使用して文字列に変換します`StringFromGUID2`し結果を格納します。

その他のコンストラクターは、`m_str` を指定された文字列のコピーに設定します。 値を渡す場合*nSize*、のみ*nSize*終端の null 文字に続く文字がコピーされます。

`CComBSTR` は移動セマンティクスをサポートします。 移動コンストラクター (右辺値参照 `&&` を取るコンストラクター) を使用して、オブジェクト コピーのオーバーヘッドなしに、引数として渡した古いオブジェクトと同一の基になるデータを使用する新しいオブジェクトを作成することができます。

デストラクターは、`m_str` が指す文字列を解放します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

##  <a name="dtor"></a>  CComBSTR:: ~ CComBSTR

デストラクターです。

```
~CComBSTR();
```

### <a name="remarks"></a>Remarks

デストラクターは、`m_str` が指す文字列を解放します。

##  <a name="copy"></a>  CComBSTR::Copy

割り当てるしのコピーを返します`m_str`します。

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>戻り値

コピー、 [m_str](#m_str)メンバー。 場合`m_str`が NULL では NULL を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

##  <a name="copyto"></a>  CComBSTR::CopyTo

割り当てるしのコピーを返します[m_str](#m_str)パラメーターを使用しています。

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>パラメーター

*pbstr*  
[out]このメソッドによって割り当てられた文字列が返される BSTR のアドレス。

*呼び出した*  
[out]このメソッドによって割り当てられた文字列が返されるバリアントのアドレス。

### <a name="return-value"></a>戻り値

成功した場合またはコピーの失敗を示す標準の HRESULT 値。

### <a name="remarks"></a>Remarks

このメソッドを呼び出した後、バリアントが指す*呼び出した*型 VT_BSTR になります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

##  <a name="detach"></a>  CComBSTR::Detach

デタッチ[m_str](#m_str)から、`CComBSTR`オブジェクトとセット`m_str`を NULL にします。

```
BSTR Detach() throw();
```

### <a name="return-value"></a>戻り値

BSTR に関連付けられている、`CComBSTR`オブジェクト。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

##  <a name="empty"></a>  CComBSTR::Empty

解放、 [m_str](#m_str)メンバー。

```
void Empty() throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

##  <a name="length"></a>  CComBSTR::Length

内の文字の数を返します`m_str`、終端の null 文字は除きます。

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>戻り値

長さ、 [m_str](#m_str)メンバー。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

##  <a name="loadstring"></a>  CComBSTR::LoadString

指定された文字列リソースを読み込む*nID*し、このオブジェクトに格納します。

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>パラメーター

参照してください[LoadString](/windows/desktop/api/winuser/nf-winuser-loadstringa) Windows SDK にします。

### <a name="return-value"></a>戻り値

かどうか、文字列が正常に読み込まれる; TRUE を返しますそれ以外の場合、FALSE を返します。

### <a name="remarks"></a>Remarks

最初の関数がを介してによって識別されるモジュールから、リソースを読み込み、 *hInst*パラメーター。 2 番目の関数に関連付けられているリソース モジュールからのリソースの読み込み、 [CComModule](../../atl/reference/ccommodule-class.md)-このプロジェクトで使用されるオブジェクトを派生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

##  <a name="m_str"></a>  CComBSTR::m_str

関連付けられている BSTR が含まれています、`CComBSTR`オブジェクト。

```
BSTR m_str;
```

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

##  <a name="operator_bstr"></a>  CComBSTR::operator BSTR

キャストを`CComBSTR`bstr オブジェクト。

```  
operator BSTR() const throw();
```

### <a name="remarks"></a>Remarks

渡すことができる`CComBSTR`を持つ関数オブジェクト **[in] BSTR**パラメーター。

### <a name="example"></a>例

例をご覧ください[CComBSTR::m_str](#m_str)します。

##  <a name="operator_not"></a>  CComBSTR::operator!

BSTR 文字列が NULL であるかどうかを確認します。

```
bool operator!() const throw();
```

### <a name="return-value"></a>戻り値

True の場合、 [m_str](#m_str)メンバーは NULL。 それ以外の場合、FALSE。

### <a name="remarks"></a>Remarks

のみ、この演算子は空の文字列ではなく、NULL 値を確認します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="operator_neq"></a>  CComBSTR::operator! =

返すのと論理的に反対[演算子 = =](#operator_eq_eq)します。

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>パラメーター

*bstrSrc*  
[入力] `CComBSTR` オブジェクト。

*pszSrc*  
[in]0 で終わる文字列。

*nNull*  
[in]NULL にする必要があります。

### <a name="return-value"></a>戻り値

比較対象となる項目が等しくない場合は TRUE を返します、`CComBSTR`オブジェクト。 それ以外の場合は FALSE を返します。

### <a name="remarks"></a>Remarks

`CComBSTR`s は、ユーザーの既定のロケールのコンテキストでは、テキストと比較されます。 最後の比較演算子は、NULL に対して含まれる文字列だけを比較します。

##  <a name="operator_amp"></a>  CComBSTR::operator &amp;

格納されている BSTR のアドレスを返して、 [m_str](#m_str)メンバー。

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Remarks

`CComBstr operator &` 特殊なアサーションに関連付けられていることと、メモリ リークを特定します。 プログラムでは、ときにアサート、`m_str`メンバーを初期化します。 このアサーションは、プログラマが使用して状況を識別するために作成された、`& operator`に新しい値を代入する`m_str`メンバーの最初の割り当てを解放せず`m_str`します。 場合`m_str`NULL と等しい、プログラムでは、その m_str がまだ割り当てられていませんでした。 この場合、プログラムはアサートされません。

このアサーションは、既定では無効です。 このアサーションが有効にする ATL_CCOMBSTR_ADDRESS_OF_ASSERT を定義します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

##  <a name="operator_add_eq"></a>  CComBSTR::operator + =

文字列を追加、`CComBSTR`オブジェクト。

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);  
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>パラメーター

*bstrSrc*  
[in]A`CComBSTR`オブジェクトを追加します。

*pszSrc*  
[in]追加する、0 で終わる文字列。

### <a name="remarks"></a>Remarks

`CComBSTR`s は、ユーザーの既定のロケールのコンテキストでは、テキストと比較されます。 LPCOLESTR 比較が行われますを使用して`memcmp`各文字列の生データにします。 LPCSTR 比較は実行と同じ方法での一時的な Unicode がコピーされたら*pszSrc*が作成されました。 最後の比較演算子は、NULL に対して含まれる文字列だけを比較します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

##  <a name="operator_lt"></a>  CComBSTR::operator &lt;

比較、`CComBSTR`文字列を使用します。

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>戻り値

比較対象となる項目がある場合は TRUE を返しますより小さい`CComBSTR`オブジェクト。 それ以外の場合は FALSE を返します。

### <a name="remarks"></a>Remarks

比較は、ユーザーの既定のロケールを使用して実行されます。

##  <a name="operator_eq"></a>  CComBSTR::operator =

セット、 [m_str](#m_str)メンバーのコピーを*pSrc*またはのメンバーは、BSTR のコピーに*src*します。移動代入演算子を移動`src`コピーせずします。

```
CComBSTR& operator= (const CComBSTR& src);  
CComBSTR& operator= (LPCOLESTR pSrc);  
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Remarks

*PSrc*パラメーターは Unicode バージョンの LPCOLESTR または LPCSTR の ANSI バージョンのいずれかを指定します。

### <a name="example"></a>例

例をご覧ください[CComBSTR::Copy](#copy)します。

##  <a name="operator_eq_eq"></a>  CComBSTR::operator = =

比較、`CComBSTR`文字列を使用します。 `CComBSTR`s は、ユーザーの既定のロケールのコンテキストでは、テキストと比較されます。

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>パラメーター

*bstrSrc*  
[入力] `CComBSTR` オブジェクト。

*pszSrc*  
[in]0 で終わる文字列。

*nNull*  
[in]NULL にする必要があります。

### <a name="return-value"></a>戻り値

比較対象のアイテムと等しい場合は TRUE を返します、`CComBSTR`オブジェクト。 それ以外の場合は FALSE を返します。

### <a name="remarks"></a>Remarks

最後の比較演算子は、NULL に対して含まれる文字列だけを比較します。

##  <a name="operator_gt"></a>  CComBSTR::operator &gt;

比較、`CComBSTR`文字列を使用します。

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>戻り値

比較対象のアイテムがより大きい場合は TRUE を返します、`CComBSTR`オブジェクト。 それ以外の場合は FALSE を返します。

### <a name="remarks"></a>Remarks

比較は、ユーザーの既定のロケールを使用して実行されます。

##  <a name="readfromstream"></a>  CComBSTR::ReadFromStream

セット、 [m_str](#m_str) BSTR の指定したストリームに含まれるメンバー。

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>パラメーター

*pStream*  
[in]ポインター、 [IStream](/windows/desktop/api/objidl/nn-objidl-istream)インターフェイスで、データを含むストリーム。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

`ReadToStream` 現在の位置への呼び出しによって書き出さデータ形式と互換性があるストリームの内容を必要と[WriteToStream](#writetostream)します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

##  <a name="tolower"></a>  CComBSTR::ToLower

格納されている文字列を小文字に変換します。

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

参照してください`CharLowerBuff`変換を実行する方法の詳細についてはします。

##  <a name="toupper"></a>  CComBSTR::ToUpper

格納されている文字列を大文字に変換します。

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

参照してください`CharUpperBuff`変換を実行する方法の詳細についてはします。

##  <a name="writetostream"></a>  CComBSTR::WriteToStream

保存、 [m_str](#m_str)ストリームのメンバー。

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>パラメーター

*pStream*  
[in]ポインター、 [IStream](/windows/desktop/api/objidl/nn-objidl-istream)ストリーム上のインターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

使用して、ストリームの内容から BSTR を再作成することができます、 [ReadFromStream](#readfromstream)関数。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)   
[ATL と MFC 文字列変換マクロ](string-conversion-macros.md)
