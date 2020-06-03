---
title: クラス
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
ms.openlocfilehash: 7818b15e502bb32640d6b9dbfe1a6e4927c70650
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363986"
---
# <a name="cpropexchange-class"></a>クラス

OLE コントロールの永続性の実装をサポートします。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CPropExchange
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を切り替えました。](#exchangeblobprop)|バイナリ ラージ オブジェクト (BLOB) プロパティを交換します。|
|[を交換します。](#exchangefontprop)|フォント プロパティを交換します。|
|[を交換します。](#exchangepersistentprop)|コントロールとファイルの間でプロパティを交換します。|
|[を交換します。](#exchangeprop)|任意の組み込み型のプロパティを交換します。|
|[を変更します。](#exchangeversion)|OLE コントロールのバージョン番号を交換します。|
|[を取得します。](#getversion)|OLE コントロールのバージョン番号を取得します。|
|[を切り替えました。](#isasynchronous)|プロパティの交換が非同期で行われるかどうかを判断します。|
|[を読み込む](#isloading)|プロパティがコントロールに読み込まれているか、またはコントロールから保存されているかを示します。|

## <a name="remarks"></a>解説

`CPropExchange`は基本クラスを持っていません。

プロパティ交換のコンテキストと方向を確立します。

永続性とは、コントロール自体とメディアの間で、通常はコントロールのプロパティによって表されるコントロールの状態情報を交換することです。

フレームワークは、OLE コントロールのプロパティ`CPropExchange`が読み込まれるか、または永続的な記憶域に格納されることを通知されたときに派生したオブジェクトを構築します。

フレームワークは、コントロールの`CPropExchange``DoPropExchange`関数にこのオブジェクトへのポインターを渡します。 ウィザードを使用してコントロールのスタート ファイルを作成した場合、コントロールの関数が`DoPropExchange`呼び`COleControl::DoPropExchange`出されます。 基本クラスのバージョンは、コントロールのストック プロパティを交換します。派生クラスのバージョンを変更して、コントロールに追加したプロパティを交換します。

`CPropExchange`コントロールのプロパティをシリアル化したり、コントロールの読み込みまたは作成時にコントロールのプロパティを初期化したりするために使用できます。 と の メンバー`CPropExchange`関数は、プロパティを別のメディアに格納したり、別のメディアから読み込むことができます。 `ExchangeFontProp` `ExchangeProp`

の使用方法`CPropExchange`の詳細については[、「MFC ActiveX コントロール : プロパティ ページ」を参照してください](../../mfc/mfc-activex-controls-property-pages.md)。

## <a name="inheritance-hierarchy"></a>継承階層

`CPropExchange`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="cpropexchangeexchangeblobprop"></a><a name="exchangeblobprop"></a>を切り替えました。

バイナリ ラージ オブジェクト (BLOB) データを格納するプロパティをシリアル化します。

```
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,
    HGLOBAL* phBlob,
    HGLOBAL hBlobDefault = NULL) = 0;
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
交換されるプロパティの名前。

*フブロブ*<br/>
プロパティが格納されている場所を指す変数へのポインター (通常、変数はクラスのメンバー)。

*デフォルト*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティの値は *、phBlob*によって参照される変数から読み取られるか、または適切に書き込まれます。 *hBlobDefault*が指定されている場合、プロパティの既定値として使用されます。 この値は、コントロールのシリアル化が失敗した場合に使用されます。

関数`CArchivePropExchange::ExchangeBlobProp`、、`CResetPropExchange::ExchangeBlobProp`および`CPropsetPropExchange::ExchangeBlobProp`この純粋仮想関数をオーバーライドします。

## <a name="cpropexchangeexchangefontprop"></a><a name="exchangefontprop"></a>を交換します。

ストレージ メディアとコントロールの間でフォント プロパティを交換します。

```
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,
    CFontHolder& font,
    const FONTDESC* pFontDesc,
    LPFONTDISP pFontDispAmbient) = 0;
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
交換されるプロパティの名前。

*フォント*<br/>
フォント プロパティを含む[CFontHolder](../../mfc/reference/cfontholder-class.md)オブジェクトへの参照。

*フォントデック*<br/>
*pFontDisp アンビエント*が NULL の場合、フォントプロパティのデフォルト状態を初期化するための値を含む[FONTDESC](/windows/win32/api/olectl/ns-olectl-fontdesc)構造体へのポインタ。

*アンビエント*<br/>
フォント プロパティの`IFontDisp`既定の状態を初期化するために使用するフォントのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

フォント プロパティがメディアからコントロールに読み込まれている場合、フォントの特性はメディアから取得され、*フォント*によって参照される`CFontHolder`オブジェクトは、それらを使用して初期化されます。 フォント プロパティが格納されている場合、フォント オブジェクトの特性はメディアに書き込まれます。

関数`CArchivePropExchange::ExchangeFontProp`、、`CResetPropExchange::ExchangeFontProp`および`CPropsetPropExchange::ExchangeFontProp`この純粋仮想関数をオーバーライドします。

## <a name="cpropexchangeexchangepersistentprop"></a><a name="exchangepersistentprop"></a>を交換します。

コントロールとファイルの間でプロパティを交換します。

```
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,
    LPUNKNOWN* ppUnk,
    REFIID iid,
    LPUNKNOWN pUnkDefault) = 0;
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
交換されるプロパティの名前。

*ppUnk*<br/>
プロパティの`IUnknown`インターフェイスへのポインターを含む変数へのポインター (通常、この変数はクラスのメンバーです)。

*Iid*<br/>
コントロールが使用するプロパティのインターフェイスのインターフェイス ID。

*既定の値*<br/>
プロパティの既定値。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティがファイルからコントロールに読み込まれている場合、プロパティが作成され、ファイルから初期化されます。 プロパティが格納されている場合、その値はファイルに書き込まれます。

関数`CArchivePropExchange::ExchangePersistentProp`、、`CResetPropExchange::ExchangePersistentProp`および`CPropsetPropExchange::ExchangePersistentProp`この純粋仮想関数をオーバーライドします。

## <a name="cpropexchangeexchangeprop"></a><a name="exchangeprop"></a>を交換します。

ストレージ メディアとコントロールの間でプロパティを交換します。

```
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,
    VARTYPE vtProp,
    void* pvProp,
    const void* pvDefault = NULL) = 0 ;
```

### <a name="parameters"></a>パラメーター

*名前を変更します。*<br/>
交換されるプロパティの名前。

*vtプロップ*<br/>
交換されるプロパティの型を指定する記号。 次のいずれかの値になります。

|Symbol|プロパティの型|
|------------|-------------------|
|VT_I2|**short**|
|VT_I4|**長い**|
|VT_BOOL|**Bool**|
|VT_BSTR|`CString`|
|VT_CY|**CY**|
|VT_R4|**float**|
|VT_R8|**double**|

*pv プロップ*<br/>
プロパティの値へのポインター。

*デフォルト*<br/>
プロパティの既定値へのポインター。

### <a name="return-value"></a>戻り値

交換が成功した場合は 0 以外。失敗した場合は 0。

### <a name="remarks"></a>解説

プロパティがメディアからコントロールに読み込まれている場合、プロパティの値はメディアから取得され *、pvProp*が指すオブジェクトに格納されます。 プロパティがメディアに格納されている場合 *、pvProp*が指すオブジェクトの値がメディアに書き込まれます。

関数`CArchivePropExchange::ExchangeProp`、、`CResetPropExchange::ExchangeProp`および`CPropsetPropExchange::ExchangeProp`この純粋仮想関数をオーバーライドします。

## <a name="cpropexchangeexchangeversion"></a><a name="exchangeversion"></a>を変更します。

バージョン番号の永続化を処理するために、フレームワークによって呼び出されます。

```
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,
    DWORD dwVersionDefault,
    BOOL bConvert);
```

### <a name="parameters"></a>パラメーター

*読み込まれたバージョン*<br/>
読み込まれる永続データのバージョン番号が格納される変数への参照。

*デフォルト*<br/>
コントロールの現在のバージョン番号。

*b変換*<br/>
永続データを現在のバージョンに変換するか、読み込まれたものと同じバージョンに維持するかを示します。

### <a name="return-value"></a>戻り値

関数が成功した場合は 0 以外。それ以外の場合は 0。

## <a name="cpropexchangegetversion"></a><a name="getversion"></a>を取得します。

コントロールのバージョン番号を取得します。

```
DWORD GetVersion();
```

### <a name="return-value"></a>戻り値

コントロールのバージョン番号。

## <a name="cpropexchangeisasynchronous"></a><a name="isasynchronous"></a>を切り替えました。

プロパティの交換が非同期で行われるかどうかを判断します。

```
BOOL IsAsynchronous();
```

### <a name="return-value"></a>戻り値

プロパティが非同期に交換される場合は TRUE を返し、それ以外の場合は FALSE を返します。

## <a name="cpropexchangeisloading"></a><a name="isloading"></a>を読み込む

プロパティがコントロールに読み込まれているか、またはコントロールから保存されているかを調べます。

```
BOOL IsLoading();
```

### <a name="return-value"></a>戻り値

プロパティが読み込まれている場合は 0 以外。それ以外の場合は 0。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[コントロール::Doプロップエクスチェンジ](../../mfc/reference/colecontrol-class.md#dopropexchange)
