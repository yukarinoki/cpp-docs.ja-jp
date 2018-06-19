---
title: CComVariant クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e2ebef74f6da48d2124d69f002a85c467db73406
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366017"
---
# <a name="ccomvariant-class"></a>CComVariant クラス
このクラスをラップ、`VARIANT`格納されているデータの種類を表すメンバーを提供する型。  
  
## <a name="syntax"></a>構文  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|コンストラクターです。|  
|[CComVariant:: ~ CComVariant](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|アタッチ、**バリアント**を`CComVariant`オブジェクト。|  
|[CComVariant::ChangeType](#changetype)|変換、`CComVariant`オブジェクトを新しい型。|  
|[CComVariant::Clear](#clear)|消去、`CComVariant`オブジェクト。|  
|[CComVariant::Copy](#copy)|コピー、**バリアント**を`CComVariant`オブジェクト。|  
|[CComVariant::CopyTo](#copyto)|内容をコピー、`CComVariant`オブジェクト。|  
|[CComVariant::Detach](#detach)|基になるデタッチ**バリアント**から、`CComVariant`オブジェクト。|  
|[CComVariant::GetSize](#getsize)|コンテンツのバイト数のサイズを返します、`CComVariant`オブジェクト。|  
|[CComVariant::ReadFromStream](#readfromstream)|読み込み、**バリアント**ストリームからです。|  
|[CComVariant::SetByRef](#setbyref)|初期化、`CComVariant`オブジェクトと設定、 **vt**メンバー **VT_BYREF**です。|  
|[な](#writetostream)|基になる保存**バリアント**をストリームにします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|||  
|-|-|  
|[CComVariant::operator <](#operator_lt)|示すかどうか、`CComVariant`オブジェクトが、指定より小さい**バリアント**です。|  
|[CComVariant::operator >](#operator_gt)|示すかどうか、`CComVariant`オブジェクトが、指定よりも大きい**バリアント**です。|  
|[operator !=](#operator_neq)|示すかどうか、`CComVariant`オブジェクトが、指定したと等しくない**バリアント**です。|  
|[演算子 =](#operator_eq)|値を割り当てます、`CComVariant`オブジェクト。|  
|[operator ==](#operator_eq_eq)|示すかどうか、`CComVariant`オブジェクトが、指定した**バリアント**です。|  
  
## <a name="remarks"></a>コメント  
 `CComVariant` ラップ、`VARIANT and VARIANTARG`は共用体と共用体に格納されたデータの種類を示す、メンバーの型。 **VARIANT**s はオートメーションで用いられます。  
  
 `CComVariant` 派生した、**バリアント**入力できるように任意の場所に使用される、**バリアント**使用できます。 たとえば、使用することができます、 **V_VT**の種類を抽出するマクロ、`CComVariant`またはアクセスすることができます、 **vt**メンバーの直接と同じようにすることができます、**バリアント**です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="attach"></a>  CComVariant::Attach  
 安全に、現在の内容をクリア、`CComVariant`オブジェクトの内容をコピー`pSrc`にこのオブジェクトのバリアント型を設定し、`pSrc`に`VT_EMPTY`です。  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSrc`  
 [in]指す、[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)オブジェクトにアタッチされています。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 保持しているデータの所有権`pSrc`に転送される、`CComVariant`オブジェクト。  
  
##  <a name="ccomvariant"></a>  CComVariant::CComVariant  
 各コンス トラクターは、の安全な初期化を処理、`CComVariant`オブジェクトを呼び出して、 `VariantInit` Win32 関数またはオブジェクトの値とに従って渡されるパラメーターの型を設定します。  
  
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
 *varSrc*  
 [in]`CComVariant`または`VARIANT`初期化するために使用される、`CComVariant`オブジェクト。 コピー元のバリアントの内容は、変換せずに、変換先にコピーされます。  
  
 `lpszSrc`  
 [in]初期化するために使用される文字の文字列、`CComVariant`オブジェクト。 0 で終わる (Unicode) 文字するワイド文字列を渡すことができます、 **LPCOLESTR**バージョンのコンス トラクターまたは ANSI 文字列を`LPCSTR`バージョン。 どちらの場合、文字列は Unicode に変換`BSTR`を使用して割り当て**SysAllocString**です。 型、`CComVariant`オブジェクトがある`VT_BSTR`です。  
  
 `bSrc`  
 [in]`bool`初期化するために使用される、`CComVariant`オブジェクト。 `bool`引数には変換は、 **VARIANT_BOOL**保存される前にします。 型、`CComVariant`オブジェクトがある`VT_BOOL`です。  
  
 `nSrc`  
 [in]`int`、**バイト**、**短い**、**長い**、 **LONGLONG**、**使い**、 **unsigned short**、 `unsigned long`、または`unsigned int`初期化するために使用される、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_I4`、 `VT_UI1`、 `VT_I2`、 `VT_I4`、 **VT_I8**、 **VT_UI8**、 **VT_UI2**、 **VT_UI4**、または**VT_UI4**、それぞれします。  
  
 `vtSrc`  
 [in]バリアントの型。 最初のパラメーターの場合は`int`、有効な種類は`VT_I4`と**VT_INT**です。 最初のパラメーターの場合は**長い**、有効な種類は`VT_I4`と`VT_ERROR`です。 最初のパラメーターの場合は**二重**、有効な種類は`VT_R8`と`VT_DATE`です。 最初のパラメーターの場合は`unsigned int`、有効な種類は**VT_UI4**と**VT_UINT**です。  
  
 `fltSrc`  
 [in]**Float**初期化するために使用される、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_R4`です。  
  
 `dblSrc`  
 [in]**二重**初期化するために使用される、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_R8`です。  
  
 `cySrc`  
 [in]**CY**初期化するために使用される、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_CY`です。  
  
 `pSrc`  
 [in]`IDispatch`または**IUnknown**ポインターの初期化に使用される、`CComVariant`オブジェクト。 `AddRef` インターフェイス ポインターで呼び出されます。 型、`CComVariant`オブジェクトがある**VT_DISPATCH**または**VT_UNKNOWN**、それぞれします。  
  
 また、 **SAFERRAY**ポインターの初期化に使用される、`CComVariant`オブジェクト。 コピー、 **SAFEARRAY**に格納されて、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトの元の型の組み合わせになります、 **SAFEARRAY**と**VT_ARRAY**です。  
  
 `cSrc`  
 [in]`char`初期化するために使用される、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある**VT_I1**です。  
  
 `bstrSrc`  
 [in]初期化するために使用される、BSTR、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_BSTR`です。  
  
### <a name="remarks"></a>コメント  
 デストラクターを呼び出して[CComVariant::Clear](#clear)です。  
  
##  <a name="dtor"></a>  CComVariant:: ~ CComVariant  
 デストラクターです。  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出してクリーンアップを管理する[CComVariant::Clear](#clear)です。  
  
##  <a name="changetype"></a>  CComVariant::ChangeType  
 変換、`CComVariant`オブジェクトを新しい型。  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `vtNew`  
 [in]新しい型、`CComVariant`オブジェクト。  
  
 `pSrc`  
 [in]ポインター、`VARIANT`値は、新しい型に変換されます。 既定値は**NULL**、つまり、`CComVariant`オブジェクトに変換されます。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 値を渡す場合`pSrc`、`ChangeType`がこれを使う**バリアント**変換のソースとして。 それ以外の場合、`CComVariant`オブジェクトは、ソースになります。  
  
##  <a name="clear"></a>  CComVariant::Clear  
 消去、`CComVariant`オブジェクトを呼び出して、 `VariantClear` Win32 関数。  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 デストラクターを自動的に呼び出します**クリア**です。  
  
##  <a name="copy"></a>  CComVariant::Copy  
 解放、`CComVariant`オブジェクトを指定されたのコピーを割り当てます**バリアント**です。  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSrc`  
 [in]ポインター、[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)をコピーします。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="copyto"></a>  CComVariant::CopyTo  
 内容をコピー、`CComVariant`オブジェクト。  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrDest*  
 指す、`BSTR`の内容のコピーを受信する、`CComVariant`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **CComVariant**オブジェクト型でなければなりません`VT_BSTR`です。  
  
##  <a name="detach"></a>  CComVariant::Detach  
 基になるデタッチ**バリアント**から、`CComVariant`オブジェクトおよびオブジェクトの種類を設定`VT_EMPTY`です。  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 [out]返します、基になる`VARIANT`オブジェクトの値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 なおの内容、`VARIANT`によって参照されている`pDest`値と、呼び出し元の型に割り当てられる前に自動的にクリアされます**CComVariant**オブジェクト。  
  
##  <a name="getsize"></a>  CComVariant::GetSize  
 単純な固定サイズの`VARIANT`s、このメソッドが戻る、`sizeof`基になるデータ型が正符号`sizeof(VARTYPE)`です。  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>戻り値  
 現在のコンテンツのバイト単位のサイズ、`CComVariant`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 場合、`VARIANT`インターフェイス ポインターを含む`GetSize`クエリ`IPersistStream`または`IPersistStreamInit`です。 成功すると、戻り値がによって返される値の下位 32 ビット`GetSizeMax`と`sizeof`、`CLSID`と`sizeof(VARTYPE)`です。 インターフェイス ポインターがある場合`NULL`、`GetSize`を返します、 `sizeof` 、 `CLSID` plus`sizeof(VARTYPE)`です。 合計サイズがより大きい場合`ULONG_MAX`、`GetSize`返します`sizeof(VARTYPE)`エラーを示します。  
  
 その他の場合、一時的な`VARIANT`型の`VT_BSTR`は現在の強制変換`VARIANT`です。 この長さ`BSTR`は、文字列の長さと、文字列自体の長さのサイズの正符号の null 文字のサイズの合計として計算`sizeof(VARTYPE)`です。 場合、`VARIANT`を強制的に変換できない、`VARIANT`型の`VT_BSTR`、`GetSize`返します`sizeof(VARTYPE)`です。  
  
 このメソッドによって返されるサイズが使用されているバイト数と一致する[な](#writetostream)の状況で正常に実行します。  
  
##  <a name="operator_eq"></a>  CComVariant::operator =  
 値とを対応する型が割り当てられます、`CComVariant`オブジェクト。  
  
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
 *varSrc*  
 [in]`CComVariant`または[バリアント](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118)に割り当てられる、`CComVariant`オブジェクト。 コピー元のバリアントの内容は、変換せずに、変換先にコピーされます。  
  
 `bstrSrc`  
 [in]割り当てられる BSTR、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_BSTR`です。  
  
 `lpszSrc`  
 [in]割り当てられる文字の文字列、`CComVariant`オブジェクト。 0 で終わる (Unicode) 文字するワイド文字列を渡すことができます、 **LPCOLESTR**バージョンの演算子または ANSI 文字列を`LPCSTR`バージョン。 どちらの場合、文字列は Unicode に変換`BSTR`を使用して割り当て**SysAllocString**です。 型、`CComVariant`オブジェクトがある`VT_BSTR`です。  
  
 `bSrc`  
 [in]`bool`に割り当てられる、`CComVariant`オブジェクト。 `bool`引数には変換は、 **VARIANT_BOOL**保存される前にします。 型、`CComVariant`オブジェクトがある`VT_BOOL`です。  
  
 `nSrc`  
 [in]`int`、**バイト**、**短い**、**長い**、 **LONGLONG**、**使い**、 **unsigned short**、 `unsigned long`、または`unsigned int`に割り当てられる、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_I4`、 `VT_UI1`、 `VT_I2`、 `VT_I4`、 **VT_I8**、 **VT_UI8**、 **VT_UI2**、 **VT_UI4**、または**VT_UI4**、それぞれします。  
  
 `fltSrc`  
 [in]**Float**に割り当てられる、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_R4`です。  
  
 `dblSrc`  
 [in]**二重**に割り当てられる、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_R8`です。  
  
 `cySrc`  
 [in]**CY**に割り当てられる、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある`VT_CY`です。  
  
 `pSrc`  
 [in]`IDispatch`または**IUnknown**に割り当てられるへのポインター、`CComVariant`オブジェクト。 `AddRef` インターフェイス ポインターで呼び出されます。 型、`CComVariant`オブジェクトがある**VT_DISPATCH**または**VT_UNKNOWN**、それぞれします。  
  
 または、 **SAFEARRAY**に割り当てられるへのポインター、`CComVariant`オブジェクト。 コピー、 **SAFEARRAY**に格納されて、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトの元の型の組み合わせになります、 **SAFEARRAY**と**VT_ARRAY**です。  
  
 `cSrc`  
 [in]割り当てられる char、`CComVariant`オブジェクト。 型、`CComVariant`オブジェクトがある**VT_I1**です。  
  
##  <a name="operator_eq_eq"></a>  CComVariant::operator = =  
 示すかどうか、`CComVariant`オブジェクトが、指定した**バリアント**です。  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します**true**場合は、値と型*varSrc*値と型に等しく、それぞれの`CComVariant`オブジェクト。 それ以外の場合、 **false**です。 演算子では、ユーザーの既定のロケールを使用して、比較を行います。  
  
 演算子は、バリアント型の値のみを比較します。 これは、文字列、整数、および浮動小数点がないアレイまたはレコードを比較します。  
  
##  <a name="operator_neq"></a>  CComVariant::operator! =  
 示すかどうか、`CComVariant`オブジェクトが、指定したと等しくない**バリアント**です。  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します**true**場合値または型の*varSrc*等しくない値または型のそれぞれ、`CComVariant`オブジェクト。 それ以外の場合、 **false**です。 演算子では、ユーザーの既定のロケールを使用して、比較を行います。  
  
 演算子は、バリアント型の値のみを比較します。 これは、文字列、整数、および浮動小数点がないアレイまたはレコードを比較します。  
  
##  <a name="operator_lt"></a>  CComVariant::operator &lt;  
 示すかどうか、`CComVariant`オブジェクトが、指定より小さい**バリアント**です。  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します**true**場合の値、`CComVariant`オブジェクトがの値より小さい*varSrc*です。 それ以外の場合、 **false**です。 演算子では、ユーザーの既定のロケールを使用して、比較を行います。  
  
##  <a name="operator_gt"></a>  CComVariant::operator &gt;  
 示すかどうか、`CComVariant`オブジェクトが、指定よりも大きい**バリアント**です。  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>コメント  
 返します**true**場合の値、`CComVariant`オブジェクトがの値より大きい*varSrc*です。 それ以外の場合、 **false**です。 演算子では、ユーザーの既定のロケールを使用して、比較を行います。  
  
##  <a name="readfromstream"></a>  CComVariant::ReadFromStream  
 基に**バリアント**を**バリアント**指定したストリームに含まれています。  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)データを格納しているストリーム上のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 **ReadToStream**を前回呼び出したときに必要と[WriteToStream](#writetostream)です。  
  
##  <a name="setbyref"></a>  CComVariant::SetByRef  
 初期化、`CComVariant`オブジェクトと設定、 **vt**メンバー **VT_BYREF**です。  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 型**バリアント**など、 `BSTR`、 `int`、または`char`です。  
  
 *pT*  
 ポインターの初期化に使用される、`CComVariant`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `SetByRef` 初期化する関数テンプレートは、`CComVariant`オブジェクト ポインターを*pT*設定と、 **vt**メンバーを**VT_BYREF**です。 例えば:  
  
 [!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>  な  
 基になる保存**バリアント**をストリームにします。  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStream`  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)ストリーム上のインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)