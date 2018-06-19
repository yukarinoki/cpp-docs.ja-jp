---
title: CComBSTR クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 7a9130dec2de7d22cfec8a76cdeb31e11388a205
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366446"
---
# <a name="ccombstr-class"></a>CComBSTR クラス
このクラスは、用のラッパー `BSTR`s。  
  
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
|[CComBSTR::Append](#append)|文字列を付加`m_str`です。|  
|[CComBSTR::AppendBSTR](#appendbstr)|追加、`BSTR`に`m_str`です。|  
|[CComBSTR::AppendBytes](#appendbytes)|指定したバイト数を追加`m_str`です。|  
|[CComBSTR::ArrayToBSTR](#arraytobstr)|作成、 `BSTR` safearray 内の各要素の最初の文字からにアタッチし、`CComBSTR`オブジェクト。|  
|[CComBSTR::AssignBSTR](#assignbstr)|割り当てます、`BSTR`に`m_str`です。|  
|[CComBSTR::Attach](#attach)|アタッチ、`BSTR`を`CComBSTR`オブジェクト。|  
|[CComBSTR::BSTRToArray](#bstrtoarray)|文字を配列の各要素がここでは 0 から始まる 1 次元の safearray を作成、`CComBSTR`オブジェクト。|  
|[CComBSTR::ByteLength](#bytelength)|長さを返します`m_str`(バイト単位)。|  
|[CComBSTR::Copy](#copy)|コピーを返します`m_str`です。|  
|[CComBSTR::CopyTo](#copyto)|コピーを返します`m_str`を介して、 **[out]** パラメーター|  
|[CComBSTR::Detach](#detach)|デタッチ`m_str`から、`CComBSTR`オブジェクト。|  
|[CComBSTR::Empty](#empty)|解放`m_str`です。|  
|[CComBSTR::Length](#length)|長さを返します`m_str`です。|  
|[CComBSTR::LoadString](#loadstring)|文字列リソースを読み込みます。|  
|[CComBSTR::ReadFromStream](#readfromstream)|読み込み、`BSTR`ストリームからのオブジェクト。|  
|[CComBSTR::ToLower](#tolower)|文字列を小文字に変換します。|  
|[CComBSTR::ToUpper](#toupper)|文字列を大文字に変換します。|  
|[CComBSTR::WriteToStream](#writetostream)|保存`m_str`をストリームにします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CComBSTR::operator BSTR](#operator_bstr)|キャスト、`CComBSTR`オブジェクトを`BSTR`です。|  
|[CComBSTR::operator!](#operator_not)|返します`true`または`false`かどうかに応じて、`m_str`は`NULL`します。|  
|[CComBSTR::operator! =](#operator_neq)|比較、`CComBSTR`文字列を使用します。|  
|[CComBSTR::operator (& a)](#operator_amp)|アドレスを返します`m_str`です。|  
|[CComBSTR::operator + =](#operator_add_eq)|追加、`CComBSTR`オブジェクトにします。|  
|[CComBSTR::operator <](#operator_lt)|比較、`CComBSTR`文字列を使用します。|  
|[CComBSTR::operator =](#operator_eq)|値を割り当てます`m_str`です。|  
|[CComBSTR::operator = =](#operator_eq_eq)|比較、`CComBSTR`文字列を使用します。|  
|[CComBSTR::operator >](#operator_gt)|比較、`CComBSTR`文字列を使用します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComBSTR::m_str](#m_str)|含まれています、`BSTR`に関連付けられている、`CComBSTR`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CComBSTR`クラスは、ラッパーの`BSTR`s で、固定長の文字列です。 長さは、文字列内のデータの前のメモリ位置に整数値として格納されます。  
  
 A [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228)が null で終了した後、最後の文字をカウントすることがありますも文字列に埋め込まれた null 文字を含めることができます。 文字列の長さは、最初の null 文字ではない、文字数によって決まります。  
  
> [!NOTE]
>  `CComBSTR`クラスは、ANSI または Unicode のいずれかの文字列を引数としてメンバー (コンス トラクター、代入演算子、および比較演算子) の数を提供します。 これらの関数の ANSI バージョンは、一時的な Unicode 文字列は内部的に作成される多くの場合、ので、Unicode 対応するよりも効率が低下します。 効率性のためには、可能であれば Unicode バージョンを使用します。  
  
> [!NOTE]
>  Visual Studio .NET で実装される強化された検索の動作によりコードなど`bstr = L"String2" + bstr;`、以前のリリースでコンパイルする代わりに実装するとして`bstr = CStringW(L"String2") + bstr`です。  
  
 使用する場合の注意事項の一覧については`CComBSTR`を参照してください[CComBSTR を使用したプログラミング](../../atl/programming-with-ccombstr-atl.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="append"></a>  CComBSTR::Append  
 追加するか`lpsz`または`BSTR`のメンバー`bstrSrc`に[m_str](#m_str)です。  
  
```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [in]A`CComBSTR`追加するオブジェクト。  
  
 *ch*  
 [in]追加する文字。  
  
 `lpsz`  
 [in]追加する文字の 0 で終わる文字列。 使用して Unicode 文字列を渡すことができます、 **LPCOLESTR**オーバー ロードまたは ANSI 文字列を使用して、`LPCSTR`バージョン。  
  
 `nLen`  
 [in]文字の数`lpsz`を追加します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合、または任意の標準`HRESULT`エラー値。  
  
### <a name="remarks"></a>コメント  
 追加する前に、ANSI 文字列を Unicode に変換されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]  
  
##  <a name="appendbstr"></a>  CComBSTR::AppendBSTR  
 指定した追加`BSTR`に[m_str](#m_str)です。  
  
```
HRESULT AppendBSTR(BSTR p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]A`BSTR`を追加します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合、または任意の標準`HRESULT`エラー値。  
  
### <a name="remarks"></a>コメント  
 このメソッドには、通常のワイド文字の文字列を渡さないでください。 コンパイラは、エラーをキャッチしたと、実行時エラーが発生することはできません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]  
  
##  <a name="appendbytes"></a>  CComBSTR::AppendBytes  
 指定したバイト数の追加[m_str](#m_str)変換なし。  
  
```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpsz`  
 [in]追加するバイトの配列へのポインター。  
  
 `p`  
 [in]追加するバイト数。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合、または任意の標準`HRESULT`エラー値。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]  
  
##  <a name="arraytobstr"></a>  CComBSTR::ArrayToBSTR  
 保持されている既存の文字列を解放、`CComBSTR`オブジェクトを作成し、 `BSTR` safearray 内の各要素の最初の文字からにアタッチし、`CComBSTR`オブジェクト。  
  
```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pSrc`  
 [in]文字列を作成するために使用する要素を含む safearray します。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合、または任意の標準`HRESULT`エラー値。  
  
##  <a name="assignbstr"></a>  CComBSTR::AssignBSTR  
 割り当てます、`BSTR`に[m_str](#m_str)です。  
  
```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [in]A`BSTR`現在に割り当てる`CComBSTR`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合、または任意の標準`HRESULT`エラー値。  
  
##  <a name="attach"></a>  CComBSTR::Attach  
 アタッチ、`BSTR`を`CComBSTR`オブジェクトを設定して、 [m_str](#m_str)メンバー *src*です。  
  
```
void Attach(BSTR src) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *src*  
 [in]`BSTR`オブジェクトにアタッチします。  
  
### <a name="remarks"></a>コメント  
 このメソッドには、通常のワイド文字の文字列を渡さないでください。 コンパイラは、エラーをキャッチしたと、実行時エラーが発生することはできません。  
  
> [!NOTE]
>  場合、このメソッドがアサート`m_str`以外**NULL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="bstrtoarray"></a>  CComBSTR::BSTRToArray  
 文字を配列の各要素がここでは 0 から始まる 1 次元の safearray を作成、`CComBSTR`オブジェクト。  
  
```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ppArray`  
 [out]関数の結果を保持するために使用した safearray へのポインター。  
  
### <a name="return-value"></a>戻り値  
 `S_OK` 成功した場合、または任意の標準`HRESULT`エラー値。  
  
##  <a name="bytelength"></a>  CComBSTR::ByteLength  
 内のバイト数を返します`m_str`、終端の null 文字を除外します。  
  
```
unsigned int ByteLength() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 長さ、 [m_str](#m_str)メンバー (バイト単位)。  
  
### <a name="remarks"></a>コメント  
 場合 0 を返します`m_str`は**NULL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]  
  
##  <a name="ccombstr"></a>  CComBSTR::CComBSTR  
 コンストラクターです。 既定のコンス トラクターは、設定、 [m_str](#m_str)メンバー **NULL**です。  
  
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
 `nSize`  
 [入力] `sz` からコピーする文字数、または `CComBSTR` の文字数の初期サイズ。  
  
 `sz`  
 [入力] コピーする文字列。 Unicode バージョンを指定します、 **LPCOLESTR**; ANSI バージョンを指定します、`LPCSTR`です。  
  
 `pSrc`  
 [入力] コピーする文字列。 Unicode バージョンを指定します、 **LPCOLESTR**; ANSI バージョンを指定します、`LPCSTR`です。  
  
 *src*  
 [入力] `CComBSTR` オブジェクト。  
  
 `guid`  
 [in]参照、 **GUID**構造体。  
  
### <a name="remarks"></a>コメント  
 コピー コンス トラクター セット`m_str`のコピーを`BSTR`のメンバー *src*です。**REFGUID**コンス トラクターの変換、 **GUID**を使用して文字列を**StringFromGUID2**し、結果を格納します。  
  
 その他のコンストラクターは、`m_str` を指定された文字列のコピーに設定します。 `nSize` の値を渡した場合は、`nSize` 分の文字だけがコピーされ、終端の null 文字が付加されます。  
  
 `CComBSTR` は移動セマンティクスをサポートします。 移動コンス トラクターを使用することができます (右辺値参照を受け取るコンス トラクター ( `&&`) オブジェクトのコピーのオーバーヘッドなしに、引数として渡した古いのオブジェクトと同じ基になるデータを使用する新しいオブジェクトを作成します。  
  
 デストラクターは、`m_str` が指す文字列を解放します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]  
  
##  <a name="dtor"></a>  CComBSTR:: ~ CComBSTR  
 デストラクターです。  
  
```
~CComBSTR();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターは、`m_str` が指す文字列を解放します。  
  
##  <a name="copy"></a>  CComBSTR::Copy  
 コピーを返し、割り当てます`m_str`です。  
  
```
BSTR Copy() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 コピー、 [m_str](#m_str)メンバー。 場合`m_str`は**NULL**、返します**NULL**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]  
  
##  <a name="copyto"></a>  CComBSTR::CopyTo  
 コピーを返し、割り当てます[m_str](#m_str)パラメーターを通じてします。  
  
```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pbstr*  
 [out]アドレス、`BSTR`すると、このメソッドによって割り当てられた文字列が返されます。  
  
 `pvarDest`  
 [out]アドレス、**バリアント**すると、このメソッドによって割り当てられた文字列が返されます。  
  
### <a name="return-value"></a>戻り値  
 標準的な`HRESULT`コピーの成否を示す値。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出した後、**バリアント**によって示される`pvarDest`型である`VT_BSTR`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]  
  
##  <a name="detach"></a>  CComBSTR::Detach  
 デタッチ[m_str](#m_str)から、`CComBSTR`オブジェクトおよびセット`m_str`に**NULL**です。  
  
```
BSTR Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 `BSTR`に関連付けられている、`CComBSTR`オブジェクト。  
  
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
 内の文字の数を返します`m_str`、終端の null 文字を除外します。  
  
```
unsigned int Length() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 長さ、 [m_str](#m_str)メンバー。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]  
  
##  <a name="loadstring"></a>  CComBSTR::LoadString  
 指定された文字列リソースを読み込みます`nID`し、このオブジェクトに格納します。  
  
```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 参照してください[LoadString](http://msdn.microsoft.com/library/windows/desktop/ms647486) Windows SDK にします。  
  
### <a name="return-value"></a>戻り値  
 返します**true**文字列が正常に読み込まれたそれ以外の場合を返します**false**です。  
  
### <a name="remarks"></a>コメント  
 最初の関数は、経由でによって識別されるモジュールからリソースを読み込みます、`hInst`パラメーター。 関連付けられているリソース モジュールから 2 番目の関数が、リソースを読み込みます、 [CComModule](../../atl/reference/ccommodule-class.md)-このプロジェクトで使用されるオブジェクトを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]  
  
##  <a name="m_str"></a>  CComBSTR::m_str  
 含まれています、`BSTR`に関連付けられている、`CComBSTR`オブジェクト。  
  
```
BSTR m_str;
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]  
  
##  <a name="operator_bstr"></a>  CComBSTR::operator BSTR  
 キャスト、`CComBSTR`オブジェクトを`BSTR`です。  
  
```  
operator BSTR() const throw();
```  
  
### <a name="remarks"></a>コメント  
 渡す`CComBSTR`を持つ関数オブジェクト **[in] BSTR**パラメーター。  
  
### <a name="example"></a>例  
 例を参照して[CComBSTR::m_str](#m_str)です。  
  
##  <a name="operator_not"></a>  CComBSTR::operator!  
 チェックするかどうか`BSTR`文字列が NULL です。  
  
```
bool operator!() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合、 [m_str](#m_str)メンバーは**NULL**、それ以外の**false**です。  
  
### <a name="remarks"></a>コメント  
 この演算子は、空の文字列ではなく、NULL 値に対してのみを確認します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]  
  
##  <a name="operator_neq"></a>  CComBSTR::operator! =  
 返します、論理的に反対の[演算子 = =](#operator_eq_eq)です。  
  
```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [入力] `CComBSTR` オブジェクト。  
  
 `pszSrc`  
 [in]0 で終わる文字列。  
  
 `nNull`  
 [in]必要があります**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象のアイテムと等しくない場合、`CComBSTR`オブジェクト。 それ以外の場合を返します**false**です。  
  
### <a name="remarks"></a>コメント  
 `CComBSTR`s は、ユーザーの既定のロケールのコンテキストでテキストと比較されます。 最後の比較演算子は、格納されている文字列だけを比較**NULL**です。  
  
##  <a name="operator_amp"></a>  CComBSTR::operator &amp;  
 アドレスを返します、`BSTR`に格納されている、 [m_str](#m_str)メンバー。  
  
```
BSTR* operator&() throw();
```  
  
### <a name="remarks"></a>コメント  
 `CComBstr operator &` 特殊なアサーションに関連付けられている、メモリ リークの特定に役立ちます。 プログラムには、ときにアサートされます、`m_str`メンバーを初期化します。 このアサーションがプログラマで使用されている状況調べるために作成された、`& operator`に新しい値を割り当てる`m_str`メンバーの最初の割り当てを解放せず`m_str`です。 場合`m_str`"NULL"と等しい、プログラムでは、その m_str まだ割り当てられていない前提としています。 この場合、プログラム アサートは発生しません。  
  
 このアサーションは、既定では無効です。 定義`ATL_CCOMBSTR_ADDRESS_OF_ASSERT`このアサーションを有効にします。  
  
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
 `bstrSrc`  
 [in]A`CComBSTR`追加するオブジェクト。  
  
 `pszSrc`  
 [in]追加する 0 で終わる文字列。  
  
### <a name="remarks"></a>コメント  
 `CComBSTR`s は、ユーザーの既定のロケールのコンテキストでテキストと比較されます。 **LPCOLESTR**比較を実行を使用して`memcmp`各文字列の未加工データにします。 `LPCSTR`比較は実行が、同じ方法での一時的な Unicode コピー`pszSrc`が作成されました。 最後の比較演算子は、格納されている文字列だけを比較**NULL**です。  
  
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
 返します**true**比較対象のアイテムがある場合よりも低い`CComBSTR`オブジェクト。 それ以外の場合を返します**false**です。  
  
### <a name="remarks"></a>コメント  
 比較は、ユーザーの既定のロケールを使用して実行します。  
  
##  <a name="operator_eq"></a>  CComBSTR::operator =  
 セット、 [m_str](#m_str)メンバーのコピーを`pSrc`またはデータベースのコピー、`BSTR`のメンバー *src*です。移動代入演算子を移動`src`コピーせずします。   
  
```
CComBSTR& operator= (const CComBSTR& src);  
CComBSTR& operator= (LPCOLESTR pSrc);  
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```  
  
### <a name="remarks"></a>コメント  
 `pSrc`パラメーターを指定するか、 **LPCOLESTR** Unicode バージョンのまたは`LPCSTR`ANSI バージョン。  
  
### <a name="example"></a>例  
 例を参照して[CComBSTR::Copy](#copy)です。  
  
##  <a name="operator_eq_eq"></a>  CComBSTR::operator = =  
 比較、`CComBSTR`文字列を使用します。 `CComBSTR`s は、ユーザーの既定のロケールのコンテキストでテキストと比較されます。  
  
```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrSrc`  
 [入力] `CComBSTR` オブジェクト。  
  
 `pszSrc`  
 [in]0 で終わる文字列。  
  
 `nNull`  
 [in]必要があります**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象のアイテムと等しい場合、`CComBSTR`オブジェクト。 それ以外の場合を返します**false**です。  
  
### <a name="remarks"></a>コメント  
 最後の比較演算子は、格納されている文字列だけを比較**NULL**です。  
  
##  <a name="operator_gt"></a>  CComBSTR::operator &gt;  
 比較、`CComBSTR`文字列を使用します。  
  
```
bool operator>(const CComBSTR& bstrSrc) const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象となる項目がより大きい場合、`CComBSTR`オブジェクト。 それ以外の場合を返します**false**です。  
  
### <a name="remarks"></a>コメント  
 比較は、ユーザーの既定のロケールを使用して実行します。  
  
##  <a name="readfromstream"></a>  CComBSTR::ReadFromStream  
 セット、 [m_str](#m_str)メンバーを`BSTR`指定したストリームに含まれています。  
  
```
HRESULT ReadFromStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)データを格納しているストリーム上のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **ReadToStream**への呼び出しによって書き出さデータ形式に対応するのには、現在の位置に、ストリームの内容を必要と[WriteToStream](#writetostream)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]  
  
##  <a name="tolower"></a>  CComBSTR::ToLower  
 格納されている文字列を小文字に変換します。  
  
```
HRESULT ToLower() throw();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 参照してください**CharLowerBuff**変換を実行する方法の詳細についてです。  
  
##  <a name="toupper"></a>  CComBSTR::ToUpper  
 格納されている文字列を大文字に変換します。  
  
```
HRESULT ToUpper() throw();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 参照してください**CharUpperBuff**変換を実行する方法の詳細についてです。  
  
##  <a name="writetostream"></a>  CComBSTR::WriteToStream  
 保存、 [m_str](#m_str)ストリームへのメンバーです。  
  
```
HRESULT WriteToStream(IStream* pStream) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)ストリーム上のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 使用して、ストリームの内容から BSTR を再作成することができます、 [ReadFromStream](#readfromstream)関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ATL と MFC 文字列変換マクロ](string-conversion-macros.md)
