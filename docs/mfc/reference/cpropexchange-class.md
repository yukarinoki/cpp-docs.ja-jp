---
title: CPropExchange クラス
ms.date: 11/04/2016
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
helpviewer_keywords:
- CPropExchange [MFC], ExchangeBlobProp
- CPropExchange [MFC], ExchangeFontProp
- CPropExchange [MFC], ExchangePersistentProp
- CPropExchange [MFC], ExchangeProp
- CPropExchange [MFC], ExchangeVersion
- CPropExchange [MFC], GetVersion
- CPropExchange [MFC], IsAsynchronous
- CPropExchange [MFC], IsLoading
ms.assetid: ed872180-e770-4942-892a-92139d501fab
ms.openlocfilehash: 4210399e32c2bb39008afa75b787c19e3338a7d5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276353"
---
# <a name="cpropexchange-class"></a>CPropExchange クラス

OLE コントロールの永続性の実装をサポートします。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|バイナリ ラージ オブジェクト (BLOB) のプロパティを交換します。|
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|フォントのプロパティを交換します。|
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|コントロールとファイルのプロパティを交換します。|
|[CPropExchange::ExchangeProp](#exchangeprop)|任意の組み込み型のプロパティを交換します。|
|[CPropExchange::ExchangeVersion](#exchangeversion)|OLE コントロールのバージョン番号を交換します。|
|[CPropExchange::GetVersion](#getversion)|OLE コントロールのバージョン番号を取得します。|
|[CPropExchange::IsAsynchronous](#isasynchronous)|プロパティの交換を非同期的に行うかどうかを決定します。|
|[CPropExchange::IsLoading](#isloading)|プロパティがされているかどうかを示す、コントロールに読み込まれるまたはから保存します。|

## <a name="remarks"></a>Remarks

`CPropExchange` 基本クラスはありません。

コンテキストとプロパティの exchange の方向を確立します。

永続化とは、通常、コントロール自体と、メディアの間、そのプロパティによって表される、コントロールの状態情報の交換です。

フレームワークから派生したオブジェクトを構築します`CPropExchange`から読み込まれる OLE コントロールのプロパティができたことを通知には、または永続的に保存されたストレージ。

フレームワークは、このポインターを渡します`CPropExchange`オブジェクトをコントロールの`DoPropExchange`関数。 コントロールのコントロールのスターター ファイルを作成するウィザードを使用した場合`DoPropExchange`関数呼び出し`COleControl::DoPropExchange`します。 基本クラスのバージョン コントロールのストック プロパティを交換します。コントロールに追加した exchange のプロパティを派生クラスのバージョンを変更します。

`CPropExchange` コントロールのプロパティをシリアル化または負荷またはコントロールの作成時にコントロールのプロパティを初期化するために使用します。 `ExchangeProp`と`ExchangeFontProp`のメンバー関数`CPropExchange`にプロパティを格納し、さまざまなメディアから読み込むにすることができます。

使用しての詳細については`CPropExchange`、記事をご覧ください[MFC ActiveX コントロール。プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`CPropExchange`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

##  <a name="exchangeblobprop"></a>  CPropExchange::ExchangeBlobProp

バイナリ ラージ オブジェクト (BLOB) データを格納するプロパティをシリアル化します。

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>パラメーター

*pszPropName*<br/>
交換されるプロパティの名前。

*phBlob*<br/>
プロパティの格納場所を指す変数へのポインター (変数は、クラスのメンバーでは通常)。

*hBlobDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値が読み取りまたはに、によって参照される変数の適切な書き込み*phBlob*します。 場合*hBlobDefault*指定すると、これは、プロパティの既定値として使用します。 この値は、何らかの理由で、コントロールのシリアル化が失敗したときに使用されます。

関数は、 `CArchivePropExchange::ExchangeBlobProp`、 `CResetPropExchange::ExchangeBlobProp`、および`CPropsetPropExchange::ExchangeBlobProp`純粋仮想関数をオーバーライドします。

##  <a name="exchangefontprop"></a>  CPropExchange::ExchangeFontProp

ストレージ メディアとコントロール間でのフォント プロパティを交換します。

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>パラメーター

*pszPropName*<br/>
交換されるプロパティの名前。

*フォント*<br/>
参照を[CFontHolder](../../mfc/reference/cfontholder-class.md)フォント プロパティを含むオブジェクト。

*pFontDesc*<br/>
ポインターを[FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc)フォント プロパティの既定の状態を初期化するための値を含む構造体と*pFontDispAmbient*は NULL です。

*pFontDispAmbient*<br/>
ポインター、`IFontDisp`フォント プロパティの既定の状態を初期化するために使用するフォントのインターフェイス。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

フォントのプロパティは、コントロールに、メディアから読み込まれるが、フォントの特性は、メディアから取得されます、`CFontHolder`によって参照されるオブジェクト*フォント*で初期化されます。 フォントのプロパティが格納される場合、フォント オブジェクトの特性は、メディアに書き込まれます。

関数は、 `CArchivePropExchange::ExchangeFontProp`、 `CResetPropExchange::ExchangeFontProp`、および`CPropsetPropExchange::ExchangeFontProp`純粋仮想関数をオーバーライドします。

##  <a name="exchangepersistentprop"></a>  CPropExchange::ExchangePersistentProp

コントロールとファイルのプロパティを交換します。

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>パラメーター

*pszPropName*<br/>
交換されるプロパティの名前。

*ppUnk*<br/>
プロパティへのポインターを格納している変数へのポインター`IUnknown`インターフェイス (この変数は、クラスのメンバーでは通常)。

*iid*<br/>
コントロールが使用するプロパティのインターフェイスのインターフェイス ID です。

*pUnkDefault*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティは、コントロールに、ファイルから読み込まれるが場合、プロパティが作成され、ファイルから初期化します。 プロパティが格納されている場合、その値は、ファイルに書き込まれます。

関数は、 `CArchivePropExchange::ExchangePersistentProp`、 `CResetPropExchange::ExchangePersistentProp`、および`CPropsetPropExchange::ExchangePersistentProp`純粋仮想関数をオーバーライドします。

##  <a name="exchangeprop"></a>  CPropExchange::ExchangeProp

ストレージ メディアとコントロールの間のプロパティを交換します。

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>パラメーター

*pszPropName*<br/>
交換されるプロパティの名前。

*vtProp*<br/>
交換されるプロパティの種類を指定する記号です。 指定できる値は次のとおりです。

|シンボル|プロパティの型|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_BOOL|**BOOL**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**float**|
|VT_R8|**double**|

*pvProp*<br/>
プロパティの値へのポインター。

*pvDefault*<br/>
プロパティの既定値へのポインター。

### <a name="return-value"></a>戻り値

交換が成功した場合、0 以外の場合失敗した場合は 0。

### <a name="remarks"></a>Remarks

プロパティの値が、メディアから取得されが指すオブジェクトに格納されている場合は、プロパティは、コントロールに、メディアから読み込まれるが、 *pvProp*します。 プロパティは、メディアに格納される場合、オブジェクトの値が指す*pvProp*はメディアに書き込まれます。

関数は、 `CArchivePropExchange::ExchangeProp`、 `CResetPropExchange::ExchangeProp`、および`CPropsetPropExchange::ExchangeProp`純粋仮想関数をオーバーライドします。

##  <a name="exchangeversion"></a>  CPropExchange::ExchangeVersion

バージョン番号の永続化を処理するためにフレームワークによって呼び出されます。

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>パラメーター

*dwVersionLoaded*<br/>
読み込まれている永続的なデータのバージョン番号が格納される変数への参照。

*dwVersionDefault*<br/>
コントロールの現在のバージョン番号。

*bConvert*<br/>
現在のバージョンに永続的なデータを変換するか、読み込まれているのと同じバージョンのまま保持するかどうかを示します。

### <a name="return-value"></a>戻り値

関数が成功した場合、0 以外の場合それ以外の場合は 0 です。

##  <a name="getversion"></a>  CPropExchange::GetVersion

コントロールのバージョン番号を取得するには、この関数を呼び出します。

```
DWORD GetVersion();
```

### <a name="return-value"></a>戻り値

コントロールのバージョン番号。

##  <a name="isasynchronous"></a>  CPropExchange::IsAsynchronous

プロパティの交換を非同期的に行うかどうかを決定します。

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>戻り値

プロパティがある場合は TRUE を返しますが場合は FALSE では、非同期的に交換されます。

##  <a name="isloading"></a>  CPropExchange::IsLoading

プロパティがされているかどうかを判断するには、この関数を呼び出すコントロールに読み込まれるまたはから保存します。

```
BOOL IsLoading();
```

### <a name="return-value"></a>戻り値

プロパティが読み込まれている場合は 0 以外それ以外の場合 0 を返します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)
