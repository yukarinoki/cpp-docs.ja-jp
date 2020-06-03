---
title: クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
ms.openlocfilehash: c1448a5638b263a87403edf0baca170f0f952e26
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748140"
---
# <a name="ccombstr-class"></a>クラス

このクラスは[BSTR](/previous-versions/windows/desktop/automat/bstr)のラッパーです。

## <a name="syntax"></a>構文

```
class CComBSTR
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CComBSTR::CComBSTR](#ccombstr)|コンストラクターです。|
|[::~CComBSTR](#dtor)|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[追加](#append)|に文字列を`m_str`追加します。|
|[を使用します。](#appendbstr)|に BSTR を`m_str`追加します。|
|[バイト数を追加します。](#appendbytes)|指定したバイト数を に`m_str`追加します。|
|[コミュブスト](#arraytobstr)|セーフ配列内の各要素の最初の文字から BSTR を作成し、オブジェクトに`CComBSTR`アタッチします。|
|[を使用します。](#assignbstr)|に BSTR を`m_str`割り当てます。|
|[アタッチ](#attach)|BSTR をオブジェクトに`CComBSTR`アタッチします。|
|[コムブストル::ブストアレイ](#bstrtoarray)|0 から始まる 1 次元セーフ配列を作成`CComBSTR`します。|
|[バイト長](#bytelength)|バイト単位の長`m_str`さを返します。|
|[CComBSTR::コピー](#copy)|の`m_str`コピーを返します。|
|[コムブスト::コピート](#copyto)|**[out]** `m_str`パラメータを使用してのコピーを返します。|
|[コムブストル::Dエタッハ](#detach)|オブジェクト`m_str`からデタッチ`CComBSTR`します。|
|[空](#empty)|フリース`m_str`.|
|[長さ](#length)|の長さを`m_str`返します。|
|[を使用します。](#loadstring)|文字列リソースを読み込みます。|
|[ストリームを読み取る](#readfromstream)|ストリームから BSTR オブジェクトを読み込みます。|
|[コムブスト::トローワー](#tolower)|文字列を小文字に変換します。|
|[コムブスト::トアッパー](#toupper)|文字列を大文字に変換します。|
|[ストリームを書き込む](#writetostream)|ストリーム`m_str`に保存します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[オペレーター BSTR](#operator_bstr)|オブジェクトを`CComBSTR`BSTR にキャストします。|
|[演算子 !](#operator_not)|NULL かどうか`m_str`に応じて、TRUE または FALSE を返します。|
|[演算子 !=](#operator_neq)|を`CComBSTR`文字列と比較します。|
|[&演算子](#operator_amp)|のアドレスを返`m_str`します。|
|[演算子 +=](#operator_add_eq)|オブジェクトに`CComBSTR`a を追加します。|
|[<演算子](#operator_lt)|を`CComBSTR`文字列と比較します。|
|[演算子 =](#operator_eq)|に値を代入します`m_str`。|
|[演算子 ==](#operator_eq_eq)|を`CComBSTR`文字列と比較します。|
|[>演算子](#operator_gt)|を`CComBSTR`文字列と比較します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[コムブスト::m_str](#m_str)|オブジェクトに関連付けられた BSTR を`CComBSTR`格納します。|

## <a name="remarks"></a>解説

クラス`CComBSTR`は、長さプレフィックスの文字列である、SDR のラッパーです。 長さは、文字列のデータの前にあるメモリ位置に整数として格納されます。

[BSTR](/previous-versions/windows/desktop/automat/bstr)は、最後にカウントされた文字の後に NULL で終わるが、文字列内に埋め込まれた null 文字を含むこともできます。 文字列の長さは、最初の NULL 文字ではなく、文字数によって決まります。

> [!NOTE]
> この`CComBSTR`クラスには、ANSI または Unicode 文字列を引数として受け取る多数のメンバ (コンストラクタ、代入演算子、および比較演算子) が用意されています。 これらの関数の ANSI バージョンは、一時的な Unicode 文字列が内部で作成されることが多いため、Unicode のバージョンよりも効率が低くなります。 効率を高めるには、可能な限り Unicode バージョンを使用してください。

> [!NOTE]
> Visual Studio .NET で実装される参照動作が強化されているため、以前`bstr = L"String2" + bstr;`のリリースでコンパイルされたようなコードを実装する必要があります`bstr = CStringW(L"String2") + bstr`。

を使用`CComBSTR`する際の注意の一覧については[、「CComBSTR を使用したプログラミング](../../atl/programming-with-ccombstr-atl.md)」を参照してください。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlbase.h

## <a name="ccombstrappend"></a><a name="append"></a>追加

m_strに *、bstrSrc*の*lpsz*または BSTR[メンバーを追加](#m_str)します。

```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```

### <a name="parameters"></a>パラメーター

*bstrSrc*<br/>
[in]追加`CComBSTR`するオブジェクト。

*Ch*<br/>
[in]追加する文字。

*lpsz*<br/>
[in]追加する 0 で終わる文字列。 ユニコード文字列は、LPCOLESTR オーバーロードまたは LPCSTR バージョンを介して ANSI 文字列を渡すことができます。

*nlen*<br/>
[in]追加する*lpsz*からの文字数。

### <a name="return-value"></a>戻り値

成功した場合、または標準の HRESULT エラー値をS_OKします。

### <a name="remarks"></a>解説

ANSI 文字列は、追加される前に Unicode に変換されます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

## <a name="ccombstrappendbstr"></a><a name="appendbstr"></a>を使用します。

指定した BSTR を[m_str](#m_str)に追加します。

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
[in]追加する BSTR。

### <a name="return-value"></a>戻り値

成功した場合、または標準の HRESULT エラー値をS_OKします。

### <a name="remarks"></a>解説

通常のワイド文字ストリングをこのメソッドに渡しません。 コンパイラはエラーをキャッチできず、実行時エラーが発生します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

## <a name="ccombstrappendbytes"></a><a name="appendbytes"></a>バイト数を追加します。

変換を行わずに指定したバイト数[をm_str](#m_str)に追加します。

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>パラメーター

*lpsz*<br/>
[in]追加するバイト配列へのポインター。

*P*<br/>
[in]追加するバイト数。

### <a name="return-value"></a>戻り値

成功した場合、または標準の HRESULT エラー値をS_OKします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

## <a name="ccombstrarraytobstr"></a><a name="arraytobstr"></a>コミュブスト

オブジェクトに保持されている既存の文字列を`CComBSTR`解放し、セーフ配列内の各要素の最初の文字から BSTR を作成し、`CComBSTR`オブジェクトにアタッチします。

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>パラメーター

*pSrc*<br/>
[in]文字列の作成に使用する要素を格納しているセーフ配列。

### <a name="return-value"></a>戻り値

成功した場合、または標準の HRESULT エラー値をS_OKします。

## <a name="ccombstrassignbstr"></a><a name="assignbstr"></a>を使用します。

BSTR を[m_str](#m_str)に割り当てます。

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>パラメーター

*bstrSrc*<br/>
[in]現在`CComBSTR`のオブジェクトに割り当てる BSTR。

### <a name="return-value"></a>戻り値

成功した場合、または標準の HRESULT エラー値をS_OKします。

## <a name="ccombstrattach"></a><a name="attach"></a>アタッチ

bstr をオブジェクトにアタッチ`CComBSTR`するには[、m_str](#m_str)メンバーを*src*に設定します。

```cpp
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]オブジェクトにアタッチする BSTR。

### <a name="remarks"></a>解説

通常のワイド文字ストリングをこのメソッドに渡しません。 コンパイラはエラーをキャッチできず、実行時エラーが発生します。

> [!NOTE]
> このメソッドは、非`m_str`NULL の場合にアサートします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstrbstrtoarray"></a><a name="bstrtoarray"></a>コムブストル::ブストアレイ

0 から始まる 1 次元セーフ配列を作成`CComBSTR`します。

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>パラメーター

*を実行する*<br/>
[アウト]関数の結果を保持するために使用されるセーフ配列へのポインター。

### <a name="return-value"></a>戻り値

成功した場合、または標準の HRESULT エラー値をS_OKします。

## <a name="ccombstrbytelength"></a><a name="bytelength"></a>バイト長

終端の NULL 文字`m_str`を除く、 のバイト数を返します。

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>戻り値

[m_str](#m_str)メンバーの長さ (バイト単位)。

### <a name="remarks"></a>解説

NULL の`m_str`場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

## <a name="ccombstrccombstr"></a><a name="ccombstr"></a>CComBSTR::CComBSTR

コンストラクターです。 既定のコンストラクターは[、m_str](#m_str)メンバーを NULL に設定します。

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

*Nsize*<br/>
[in]*sz*からコピーする文字数、または の文字の初期サイズを指定`CComBSTR`します。

*Sz*<br/>
[入力] コピーする文字列。 ユニコード・バージョンは、LPCOLESTR を指定します。ANSI バージョンは LPCSTR を指定します。

*pSrc*<br/>
[入力] コピーする文字列。 ユニコード・バージョンは、LPCOLESTR を指定します。ANSI バージョンは LPCSTR を指定します。

*src*<br/>
[入力] `CComBSTR` オブジェクト。

*guid*<br/>
[in]`GUID`構造体への参照。

### <a name="remarks"></a>解説

コピー コンストラクターは`m_str`、 *src*の BSTR メンバーのコピーに設定します。 コンストラクター`REFGUID`は、GUID を文字列に変換し`StringFromGUID2`、その結果を格納します。

その他のコンストラクターは、`m_str` を指定された文字列のコピーに設定します。 *nSize*に値を渡すと *、nSize*文字だけがコピーされ、その後に null 文字が終了します。

`CComBSTR` は移動セマンティクスをサポートします。 移動コンストラクター (右辺値参照 `&&` を取るコンストラクター) を使用して、オブジェクト コピーのオーバーヘッドなしに、引数として渡した古いオブジェクトと同一の基になるデータを使用する新しいオブジェクトを作成することができます。

デストラクターは、`m_str` が指す文字列を解放します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

## <a name="ccombstrccombstr"></a><a name="dtor"></a>::~CComBSTR

デストラクターです。

```
~CComBSTR();
```

### <a name="remarks"></a>解説

デストラクターは、`m_str` が指す文字列を解放します。

## <a name="ccombstrcopy"></a><a name="copy"></a>CComBSTR::コピー

のコピーを割り当てて`m_str`返します。

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>戻り値

[m_str](#m_str)メンバーのコピー。 NULL`m_str`の場合は、NULL を返します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

## <a name="ccombstrcopyto"></a><a name="copyto"></a>コムブスト::コピート

パラメーターを使用して[m_str](#m_str)のコピーを割り当てて返します。

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>パラメーター

*pbstr*<br/>
[アウト]このメソッドによって割り当てられた文字列を返す BSTR のアドレス。

*pvarDest*<br/>
[アウト]このメソッドによって割り当てられた文字列を返す VARIANT のアドレス。

### <a name="return-value"></a>戻り値

コピーの成功または失敗を示す標準 HRESULT 値。

### <a name="remarks"></a>解説

このメソッドを呼び出した後 *、pvarDest*が指すバリアント型はVT_BSTR型になります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

## <a name="ccombstrdetach"></a><a name="detach"></a>コムブストル::Dエタッハ

オブジェクトから[m_str](#m_str)を`CComBSTR`デタッチし、NULL に設定`m_str`します。

```
BSTR Detach() throw();
```

### <a name="return-value"></a>戻り値

`CComBSTR`オブジェクトに関連付けられている BSTR。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

## <a name="ccombstrempty"></a><a name="empty"></a>空

[m_str](#m_str)メンバーを解放します。

```cpp
void Empty() throw();
```

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

## <a name="ccombstrlength"></a><a name="length"></a>長さ

の末尾の null`m_str`文字を除く、 内の文字数を返します。

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>戻り値

[m_str](#m_str)メンバーの長さ。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

## <a name="ccombstrloadstring"></a><a name="loadstring"></a>を使用します。

*nID*で指定された文字列リソースを読み込み、このオブジェクトに格納します。

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>パラメーター

「Windows SDK[のロード文字列](/windows/win32/api/winuser/nf-winuser-loadstringw)」を参照してください。

### <a name="return-value"></a>戻り値

文字列が正常に読み込まれた場合は TRUE を返します。それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

最初の関数は *、hInst*パラメーターを使用してユーザーによって識別されたモジュールからリソースを読み込みます。 2 番目の関数は、このプロジェクトで使用される[CComModule](../../atl/reference/ccommodule-class.md)派生オブジェクトに関連付けられたリソース モジュールからリソースを読み込みます。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

## <a name="ccombstrm_str"></a><a name="m_str"></a>コムブスト::m_str

オブジェクトに関連付けられた BSTR を`CComBSTR`格納します。

```
BSTR m_str;
```

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

## <a name="ccombstroperator-bstr"></a><a name="operator_bstr"></a>オペレーター BSTR

オブジェクトを`CComBSTR`BSTR にキャストします。

```
operator BSTR() const throw();
```

### <a name="remarks"></a>解説

**BSTR**パラメータ`CComBSTR`を持つ関数にオブジェクトを渡すことができます。

### <a name="example"></a>例

[CComBSTR::m_str](#m_str)の例を参照してください。

## <a name="ccombstroperator-"></a><a name="operator_not"></a>演算子 !

BSTR 文字列が NULL かどうかをチェックします。

```
bool operator!() const throw();
```

### <a name="return-value"></a>戻り値

[m_str](#m_str)メンバーが NULL の場合は TRUE を返します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この演算子は、空の文字列ではなく、NULL 値のみをチェックします。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_neq"></a>演算子 !=

[演算子 ==](#operator_eq_eq)の論理反対を返します。

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>パラメーター

*bstrSrc*<br/>
[入力] `CComBSTR` オブジェクト。

*pszSrc*<br/>
[in]ゼロで終わる文字列。

*null*<br/>
[in]NULL である必要があります。

### <a name="return-value"></a>戻り値

比較対象の項目がオブジェクトと等しくない場合は`CComBSTR`TRUE を返します。それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

`CComBSTR`s は、ユーザーのデフォルトロケールのコンテキストでテキストで比較されます。 最後の比較演算子は、含まれている文字列を NULL と比較するだけです。

## <a name="ccombstroperator-amp"></a><a name="operator_amp"></a>演算子&amp;

[m_str](#m_str)メンバーに格納されている BSTR のアドレスを返します。

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>解説

`CComBstr operator &`には、メモリ リークを識別するために、特別なアサーションが関連付けられます。 プログラムは、メンバーが`m_str`初期化されるとアサートします。 このアサーションは、プログラマが を使用して、`& operator`の最初の`m_str`割り当`m_str`てを解放せずにメンバーに新しい値を割り当てる状況を識別するために作成されました。 NULL`m_str`に等しい場合、プログラムはm_strがまだ割り当てられていなかったと見なします。 この場合、プログラムはアサートしません。

このアサーションは、既定では有効になっていません。 このアサーションを有効にするATL_CCOMBSTR_ADDRESS_OF_ASSERTを定義します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

## <a name="ccombstroperator-"></a><a name="operator_add_eq"></a>演算子 +=

オブジェクトに文字列を`CComBSTR`追加します。

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>パラメーター

*bstrSrc*<br/>
[in]追加`CComBSTR`するオブジェクト。

*pszSrc*<br/>
[in]追加する 0 で終わる文字列。

### <a name="remarks"></a>解説

`CComBSTR`s は、ユーザーのデフォルトロケールのコンテキストでテキストで比較されます。 LPCOLESTR 比較は、各`memcmp`ストリングの生データを使用して行われます。 LPCSTR 比較は *、pszSrc*の一時的なユニコード・コピーが作成された後でも同じ方法で実行されます。 最後の比較演算子は、含まれている文字列を NULL と比較するだけです。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

## <a name="ccombstroperator-lt"></a><a name="operator_lt"></a>演算子&lt;

を`CComBSTR`文字列と比較します。

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>戻り値

比較対象の項目がオブジェクトより小さい場合は`CComBSTR`TRUE を返します。それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

比較は、ユーザーのデフォルトロケールを使用して実行されます。

## <a name="ccombstroperator-"></a><a name="operator_eq"></a>演算子 =

[m_str](#m_str)メンバーを*pSrc*のコピーまたは*src*の BSTR メンバーのコピーに設定します。 移動代入演算子は、`src`コピーせずに移動します。

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>解説

*pSrc*パラメーターは、ユニコード・バージョンの場合は LPCOLESTR、ANSI バージョンの場合は LPCSTR のいずれかを指定します。

### <a name="example"></a>例

[「CComBSTR::コピー](#copy)」の例を参照してください。

## <a name="ccombstroperator-"></a><a name="operator_eq_eq"></a>演算子 ==

を`CComBSTR`文字列と比較します。 `CComBSTR`s は、ユーザーのデフォルトロケールのコンテキストでテキストで比較されます。

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>パラメーター

*bstrSrc*<br/>
[入力] `CComBSTR` オブジェクト。

*pszSrc*<br/>
[in]ゼロで終わる文字列。

*null*<br/>
[in]NULL である必要があります。

### <a name="return-value"></a>戻り値

比較対象の項目がオブジェクトと等しい場合は`CComBSTR`TRUE を返します。それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

最後の比較演算子は、含まれている文字列を NULL と比較するだけです。

## <a name="ccombstroperator-gt"></a><a name="operator_gt"></a>演算子&gt;

を`CComBSTR`文字列と比較します。

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>戻り値

比較対象の項目がオブジェクトより大きい場合は`CComBSTR`TRUE を返します。それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

比較は、ユーザーのデフォルトロケールを使用して実行されます。

## <a name="ccombstrreadfromstream"></a><a name="readfromstream"></a>ストリームを読み取る

指定したストリームに含まれる BSTR に[m_str](#m_str)メンバーを設定します。

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
[in]データを含むストリーム上の[IStream](/windows/win32/api/objidl/nn-objidl-istream)インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`ReadToStream`現在の位置にあるストリームの内容は[、 WriteToStream](#writetostream)の呼び出しによって書き出されたデータ形式と互換性を持っている必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

## <a name="ccombstrtolower"></a><a name="tolower"></a>コムブスト::トローワー

含まれている文字列を小文字に変換します。

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

変換`CharLowerBuff`の実行方法の詳細については、「」を参照してください。

## <a name="ccombstrtoupper"></a><a name="toupper"></a>コムブスト::トアッパー

含まれている文字列を大文字に変換します。

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

変換`CharUpperBuff`の実行方法の詳細については、「」を参照してください。

## <a name="ccombstrwritetostream"></a><a name="writetostream"></a>ストリームを書き込む

[m_str](#m_str)メンバーをストリームに保存します。

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>パラメーター

*pストリーム*<br/>
[in]ストリーム上の[IStream](/windows/win32/api/objidl/nn-objidl-istream)インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ストリームの内容から BSTR を再作成するには[、ReadFromStream](#readfromstream)関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[ATL および MFC 文字列変換マクロ](string-conversion-macros.md)
