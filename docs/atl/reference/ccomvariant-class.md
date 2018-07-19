---
title: CComVariant クラス |Microsoft Docs
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
ms.openlocfilehash: edc0e098e1f3e80a80dabeda8c0a5f7a58e5e697
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961143"
---
# <a name="ccomvariant-class"></a>CComVariant クラス
このクラスは、格納されているデータの種類を示すメンバーを提供する、バリアント型をラップします。  
  
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
|[CComVariant::Attach](#attach)|バリアントをアタッチ、`CComVariant`オブジェクト。|  
|[CComVariant::ChangeType](#changetype)|変換、`CComVariant`オブジェクトを新しい型。|  
|[CComVariant::Clear](#clear)|消去、`CComVariant`オブジェクト。|  
|[CComVariant::Copy](#copy)|コピーへのバリアント、`CComVariant`オブジェクト。|  
|[CComVariant::CopyTo](#copyto)|内容をコピー、`CComVariant`オブジェクト。|  
|[CComVariant::Detach](#detach)|基になるバリアントのデタッチ、`CComVariant`オブジェクト。|  
|[CComVariant::GetSize](#getsize)|内容のバイト数のサイズを返します、`CComVariant`オブジェクト。|  
|[CComVariant::ReadFromStream](#readfromstream)|ストリームからのバリアントを読み込みます。|  
|[CComVariant::SetByRef](#setbyref)|初期化します、`CComVariant`オブジェクトと設定、 `vt` VT_BYREF するメンバー。|  
|[な](#writetostream)|基になるバリアントをストリームに保存します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|||  
|-|-|  
|[CComVariant::operator <](#operator_lt)|示すかどうか、`CComVariant`オブジェクトが指定されたバリアント型より小さい。|  
|[CComVariant::operator >](#operator_gt)|示すかどうか、`CComVariant`オブジェクトが指定されたバリアント型よりも大きい。|  
|[operator !=](#operator_neq)|示すかどうか、`CComVariant`オブジェクトが、指定されたバリアント型と一致しません。|  
|[演算子 =](#operator_eq)|値を割り当てます、`CComVariant`オブジェクト。|  
|[operator ==](#operator_eq_eq)|示すかどうか、`CComVariant`オブジェクトが指定されたバリアント型。|  
  
## <a name="remarks"></a>Remarks  
 `CComVariant` 共用体と共用体に格納されたデータの種類を示すメンバーから成る VARIANT と VARIANTARG 型をラップします。 バリアントは、Automation で通常使用されます。  
  
 `CComVariant` バリアントを使用できる場所に使用できるように、VARIANT 型から派生します。 型を抽出する V_VT マクロを使用することができます、たとえば、`CComVariant`またはアクセスすることができます、`vt`メンバーを直接と同じように、バリアントで購入できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcomcli.h  
  
##  <a name="attach"></a>  CComVariant::Attach  
 現在の内容を安全に消去、`CComVariant`オブジェクトの内容をコピー *pSrc*に、このオブジェクトのバリアント型を設定し、 *pSrc* VT_EMPTY にします。  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSrc*  
 [in]指す、[バリアント](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant)オブジェクトに接続します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 保持しているデータの所有権*pSrc*に転送される、`CComVariant`オブジェクト。  
  
##  <a name="ccomvariant"></a>  CComVariant::CComVariant  
 各コンス トラクターのセーフな初期化を処理する、`CComVariant`オブジェクトを呼び出すことによって、 `VariantInit` Win32 関数またはオブジェクトの値とに従って渡されるパラメーターの型を設定します。  
  
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
 [in]`CComVariant`または初期化に使用されるバリアント、`CComVariant`オブジェクト。 コピー元のバリアントの内容は、変換せず、変換先にコピーされます。  
  
 *lpszSrc*  
 [in]初期化に使用される文字の文字列、`CComVariant`オブジェクト。 LPCOLESTR バージョンのコンス トラクターまたは LPCSTR バージョンに、ANSI 文字列には、ワイド (Unicode) 文字 0 で終わる文字列を渡すことができます。 いずれの場合も、文字列は Unicode を使用して割り当て BSTR に変換`SysAllocString`します。 種類、`CComVariant`オブジェクトは VT_BSTR になります。  
  
 *bSrc*  
 [in]**Bool**初期化に使用される、`CComVariant`オブジェクト。 **Bool**引数が保存される前に、VARIANT_BOOL に変換されます。 種類、 `CComVariant` VT_BOOL がオブジェクトになります。  
  
 *nSrc*  
 [in]**Int**、**バイト**、**短い**、**長い**、LONGLONG、ULONGLONG、 **unsigned short**、 **unsigned long**、または**符号なし int**初期化に使用される、`CComVariant`オブジェクト。 種類、`CComVariant`オブジェクトは VT_I4、VT_UI1、VT_I2、VT_I4、VT_I8、VT_UI8、VT_UI2、VT_UI4、VT_UI4、またはそれぞれなります。  
  
 *vtSrc*  
 [in]バリアントの型。 最初のパラメーターの場合は**int**、有効な型は VT_I4 と VT_INT します。 最初のパラメーターの場合は**長い**、有効な型は VT_I4 と VT_ERROR します。 最初のパラメーターの場合は**二重**、有効な種類は VT_R8、および VT_DATE します。 最初のパラメーターの場合は**符号なし int**、有効な種類は VT_UI4 と VT_UINT します。  
  
 *fltSrc*  
 [in]**Float**初期化に使用される、`CComVariant`オブジェクト。 種類、 `CComVariant` VT_R4 がオブジェクトになります。  
  
 *dblSrc*  
 [in]**二重**初期化に使用される、`CComVariant`オブジェクト。 種類、 `CComVariant` VT_R8 がオブジェクトになります。  
  
 *cySrc*  
 [in]`CY`初期化に使用される、`CComVariant`オブジェクト。 種類、 `CComVariant` VT_CY がオブジェクトになります。  
  
 *pSrc*  
 [in]`IDispatch`または`IUnknown`ポインターの初期化に使用される、`CComVariant`オブジェクト。 `AddRef` インターフェイス ポインターで呼び出されます。 種類、`CComVariant`オブジェクトが VT_DISPATCH またはで VT_UNKNOWN、それぞれします。  
  
 または、初期化するために使用される SAFERRAY ポインター、`CComVariant`オブジェクト。 SAFEARRAY のコピーが格納されている、`CComVariant`オブジェクト。 種類、`CComVariant`オブジェクトの SAFEARRAY、VT_ARRAY 元の型の組み合わせになります。  
  
 *cSrc*  
 [in]**Char**初期化に使用される、`CComVariant`オブジェクト。 種類、 `CComVariant` VT_I1 がオブジェクトになります。  
  
 *bstrSrc*  
 [in]初期化するために使用される、BSTR、`CComVariant`オブジェクト。 種類、`CComVariant`オブジェクトは VT_BSTR になります。  
  
### <a name="remarks"></a>Remarks  
 デストラクターを呼び出してクリーンアップを管理する[CComVariant::Clear](#clear)します。  
  
##  <a name="dtor"></a>  CComVariant:: ~ CComVariant  
 デストラクターです。  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出してクリーンアップを管理する[CComVariant::Clear](#clear)します。  
  
##  <a name="changetype"></a>  CComVariant::ChangeType  
 変換、`CComVariant`オブジェクトを新しい型。  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *vtNew*  
 [in]新しい型、`CComVariant`オブジェクト。  
  
 *pSrc*  
 [in]値を持つは、新しい型に変換するバリアントへのポインター。 既定値は null の場合、つまり、`CComVariant`オブジェクトはインプレース変換されます。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 値を渡す場合*pSrc*、`ChangeType`このバリアントをソースと変換に使用します。 それ以外の場合、`CComVariant`オブジェクトには、ソースとなります。  
  
##  <a name="clear"></a>  CComVariant::Clear  
 消去、`CComVariant`オブジェクトを呼び出すことによって、 `VariantClear` Win32 関数。  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 デストラクターが自動的に呼び出します`Clear`します。  
  
##  <a name="copy"></a>  CComVariant::Copy  
 解放、`CComVariant`オブジェクトを指定されたバリアント型のコピーを割り当てます。  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>パラメーター  
 *pSrc*  
 [in]ポインター、[バリアント](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant)をコピーします。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
##  <a name="copyto"></a>  CComVariant::CopyTo  
 内容をコピー、`CComVariant`オブジェクト。  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrDest*  
 内容のコピーを受信する BSTR を指す、`CComVariant`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 `CComVariant` VT_BSTR 型のオブジェクトがある必要があります。  
  
##  <a name="detach"></a>  CComVariant::Detach  
 基になるバリアントのデタッチ、`CComVariant`オブジェクトし、オブジェクトの型を VT_EMPTY に設定します。  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDest*  
 [out]オブジェクトの基になるバリアント値を返します。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 によって参照される、バリアントの内容に注意してください*pDest*値と、呼び出し元の型に割り当てられる前に自動的にクリアされます`CComVariant`オブジェクト。  
  
##  <a name="getsize"></a>  CComVariant::GetSize  
 このメソッドが戻るの単純な固定サイズのバリエーション、 **sizeof**プラスの基になるデータ型**終了する**します。  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>戻り値  
 現在の内容のバイト単位のサイズ、`CComVariant`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 バリアントには、インターフェイス ポインターが含まれている場合`GetSize`照会`IPersistStream`または`IPersistStreamInit`します。 成功すると、戻り値がによって返される値の下位 32 ビット`GetSizeMax`だけでなく、 **sizeof** CLSID と**終了する**します。 インターフェイス ポインターが NULL の場合`GetSize`を返します、 **sizeof**プラス CLSID**終了する**します。 合計サイズが、ULONG_MAX を超える場合`GetSize`返します**終了する**エラーを示します。  
  
 その他のすべてのケースで型 VT_BSTR の一時的なバリアントは、現在のバリアントから強制的に変換されます。 この BSTR の長さは、文字列の長さと文字列自体の長さのサイズの正符号の null 文字のサイズの合計として計算されます**終了する**します。 バリアントは VT_BSTR 型のバリアントを強制的に変換できない場合`GetSize`返します**終了する**します。  
  
 このメソッドによって返されるサイズで使用されるバイトの数が一致[な](#writetostream)成功の条件下でします。  
  
##  <a name="operator_eq"></a>  CComVariant::operator =  
 値と対応する型を割り当てます、`CComVariant`オブジェクト。  
  
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
 [in]`CComVariant`または[バリアント](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant)に割り当てられる、`CComVariant`オブジェクト。 コピー元のバリアントの内容は、変換せず、変換先にコピーされます。  
  
 *bstrSrc*  
 [in]割り当てられる BSTR、`CComVariant`オブジェクト。 種類、`CComVariant`オブジェクトは VT_BSTR になります。  
  
 *lpszSrc*  
 [in]文字の文字列に割り当てられる、`CComVariant`オブジェクト。 演算子または LPCSTR バージョンに、ANSI 文字列の LPCOLESTR バージョンには、ワイド (Unicode) 文字 0 で終わる文字列を渡すことができます。 どちらの場合、文字列は Unicode を使用して割り当て BSTR に変換`SysAllocString`します。 種類、`CComVariant`オブジェクトは VT_BSTR になります。  
  
 *bSrc*  
 [in]**Bool**に割り当てられる、`CComVariant`オブジェクト。 **Bool**引数が保存される前に、VARIANT_BOOL に変換されます。 種類、 `CComVariant` VT_BOOL がオブジェクトになります。  
  
 *nSrc*  
 [in]**Int**、BYTE、**短い**、**長い**、LONGLONG、ULONGLONG、 **unsigned short**、 **unsigned long**、または**符号なし int**に割り当てられる、`CComVariant`オブジェクト。 種類、`CComVariant`オブジェクトは VT_I4、VT_UI1、VT_I2、VT_I4、VT_I8、VT_UI8、VT_UI2、VT_UI4、VT_UI4、またはそれぞれなります。  
  
 *fltSrc*  
 [in]**Float**に割り当てられる、`CComVariant`オブジェクト。 種類、 `CComVariant` VT_R4 がオブジェクトになります。  
  
 *dblSrc*  
 [in]**二重**に割り当てられる、`CComVariant`オブジェクト。 種類、 `CComVariant` VT_R8 がオブジェクトになります。  
  
 *cySrc*  
 [in]`CY`に割り当てられる、`CComVariant`オブジェクト。 種類、 `CComVariant` VT_CY がオブジェクトになります。  
  
 *pSrc*  
 [in]`IDispatch`または`IUnknown`ポインターに割り当てられる、`CComVariant`オブジェクト。 `AddRef` インターフェイス ポインターで呼び出されます。 種類、`CComVariant`オブジェクトが VT_DISPATCH またはで VT_UNKNOWN、それぞれします。  
  
 または、SAFEARRAY へのポインターに割り当てられる、`CComVariant`オブジェクト。 SAFEARRAY のコピーが格納されている、`CComVariant`オブジェクト。 種類、`CComVariant`オブジェクトの SAFEARRAY、VT_ARRAY 元の型の組み合わせになります。  
  
 *cSrc*  
 [in]割り当てられる char、`CComVariant`オブジェクト。 種類、 `CComVariant` VT_I1 がオブジェクトになります。  
  
##  <a name="operator_eq_eq"></a>  CComVariant::operator = =  
 示すかどうか、`CComVariant`オブジェクトが指定されたバリアント型。  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Remarks  
 場合に TRUE を返しますの種類と値*varSrc*値よぶ型と等しい、それぞれの`CComVariant`オブジェクト。 それ以外の場合、FALSE です。 演算子では、ユーザーの既定のロケールを使用して、比較を実行します。  
  
 演算子は、バリアント型の値のみを比較します。 文字列、整数、および浮動小数点がないアレイまたはレコードを比較します。  
  
##  <a name="operator_neq"></a>  CComVariant::operator! =  
 示すかどうか、`CComVariant`オブジェクトが、指定されたバリアント型と一致しません。  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Remarks  
 True の場合値または型の*varSrc*型、その値と等しくない、それぞれの`CComVariant`オブジェクト。 それ以外の場合、FALSE です。 演算子では、ユーザーの既定のロケールを使用して、比較を実行します。  
  
 演算子は、バリアント型の値のみを比較します。 文字列、整数、および浮動小数点がないアレイまたはレコードを比較します。  
  
##  <a name="operator_lt"></a>  CComVariant::operator &lt;  
 示すかどうか、`CComVariant`オブジェクトが指定されたバリアント型より小さい。  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Remarks  
 True の場合の値、`CComVariant`オブジェクトがの値より小さい*varSrc*します。 それ以外の場合、FALSE です。 演算子では、ユーザーの既定のロケールを使用して、比較を実行します。  
  
##  <a name="operator_gt"></a>  CComVariant::operator &gt;  
 示すかどうか、`CComVariant`オブジェクトが指定されたバリアント型よりも大きい。  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Remarks  
 True の場合の値、`CComVariant`オブジェクトがの値より大きい*varSrc*します。 それ以外の場合、FALSE です。 演算子では、ユーザーの既定のロケールを使用して、比較を実行します。  
  
##  <a name="readfromstream"></a>  CComVariant::ReadFromStream  
 指定したストリームに含まれるバリアントを基になるバリアントを設定します。  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStream*  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)インターフェイスで、データを含むストリーム。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
### <a name="remarks"></a>Remarks  
 `ReadToStream` 以前の呼び出しを必要と[WriteToStream](#writetostream)します。  
  
##  <a name="setbyref"></a>  CComVariant::SetByRef  
 初期化します、`CComVariant`オブジェクトと設定、 `vt` VT_BYREF するメンバー。  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *T*  
 、たとえば、BSTR、バリアントの型**int**、または**char**します。  
  
 *pT*  
 ポインターの初期化に使用される、`CComVariant`オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 `SetByRef` 関数テンプレートを初期化するには、`CComVariant`オブジェクト ポインターを*pT*設定と、 `vt` VT_BYREF するメンバー。 例えば:  
  
 [!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>  な  
 基になるバリアントをストリームに保存します。  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStream*  
 [in]ポインター、 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)ストリーム上のインターフェイス。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)