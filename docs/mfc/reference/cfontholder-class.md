---
description: '詳細情報: CFontHolder クラス'
title: CFontHolder クラス
ms.date: 11/04/2016
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
ms.openlocfilehash: 1670bd9a00c5b6f7990c15ba31d7256afb8d4031
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184297"
---
# <a name="cfontholder-class"></a>CFontHolder クラス

ストック フォント プロパティを実装し、Windows のフォント オブジェクトと `IFont` インターフェイスの機能をカプセル化します。

## <a name="syntax"></a>構文

```
class CFontHolder
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CFontHolder::CFontHolder](#cfontholder)|`CFontHolder` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CFontHolder:: GetDisplayString](#getdisplaystring)|コンテナーのプロパティブラウザーに表示される文字列を取得します。|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|フォントのインターフェイスを返し `IDispatch` ます。|
|[CFontHolder::GetFontHandle](#getfonthandle)|Windows フォントのハンドルを返します。|
|[CFontHolder:: InitializeFont](#initializefont)|オブジェクトを初期化 `CFontHolder` します。|
|[CFontHolder:: QueryTextMetrics](#querytextmetrics)|関連するフォントの情報を取得します。|
|[CFontHolder:: ReleaseFont](#releasefont)|`CFontHolder`およびインターフェイスからオブジェクトを切断し `IFont` `IFontNotification` ます。|
|[CFontHolder:: Select](#select)|フォントリソースをデバイスコンテキストに選択します。|
|[CFontHolder::SetFont](#setfont)|オブジェクトを `CFontHolder` インターフェイスに接続し `IFont` ます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CFontHolder:: m_pFont](#m_pfont)|`CFontHolder`オブジェクトのインターフェイスへのポインター `IFont` 。|

## <a name="remarks"></a>解説

`CFontHolder` に基底クラスがありません。

コントロールのカスタムフォントプロパティを実装するには、このクラスを使用します。 このようなプロパティの作成の詳細については、「 [ActiveX コントロール: フォントの使用](../../mfc/mfc-activex-controls-using-fonts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CFontHolder`

## <a name="requirements"></a>要件

**ヘッダー:** afxctl.h

## <a name="cfontholdercfontholder"></a><a name="cfontholder"></a> CFontHolder::CFontHolder

`CFontHolder` オブジェクトを構築します。

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>パラメーター

*pNotify*<br/>
フォントのインターフェイスへのポインター `IPropertyNotifySink` 。

### <a name="remarks"></a>解説

`InitializeFont`を使用する前に、を呼び出して、結果のオブジェクトを初期化する必要があります。

## <a name="cfontholdergetdisplaystring"></a><a name="getdisplaystring"></a> CFontHolder:: GetDisplayString

コンテナーのプロパティブラウザーに表示できる文字列を取得します。

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>パラメーター

*strValue*<br/>
表示文字列を保持する [CString](../../atl-mfc-shared/reference/cstringt-class.md) への参照。

### <a name="return-value"></a>戻り値

文字列が正常に取得された場合は0以外の値。それ以外の場合は0です。

## <a name="cfontholdergetfontdispatch"></a><a name="getfontdispatch"></a> CFontHolder::GetFontDispatch

フォントのディスパッチインターフェイスへのポインターを取得するには、この関数を呼び出します。

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>戻り値

`CFontHolder`オブジェクトのインターフェイスへのポインター `IFontDisp` 。 を呼び出す場合は、を呼び出す関数が `GetFontDispatch` `IUnknown::Release` このインターフェイスポインターでを呼び出す必要があることに注意してください。

### <a name="remarks"></a>解説

`InitializeFont`を呼び出す前に `GetFontDispatch` を呼び出します。

## <a name="cfontholdergetfonthandle"></a><a name="getfonthandle"></a> CFontHolder::GetFontHandle

Windows フォントのハンドルを取得するには、この関数を呼び出します。

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>パラメーター

*cyLogical*<br/>
コントロールが描画される四角形の高さ (論理単位)。

*cyHimetric*<br/>
コントロールの高さ (MM_HIMETRIC 単位)。

### <a name="return-value"></a>戻り値

フォントオブジェクトへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

*Cylogical* と *cylogical* の比率は、MM_HIMETRIC 単位で表されるフォントのポイントサイズに対して、適切な表示サイズ (論理単位) を計算するために使用されます。

表示サイズ = ( *cylogical*  /  *cylogical*) X フォントサイズ

パラメーターが指定されていないバージョンでは、画面のフォントサイズが正しく設定されたハンドルが返されます。

## <a name="cfontholderinitializefont"></a><a name="initializefont"></a> CFontHolder:: InitializeFont

オブジェクトを初期化 `CFontHolder` します。

```cpp
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>パラメーター

*pFontDesc*<br/>
フォントの特性を指定するフォント記述構造体 ( [Fontdesc](/windows/win32/api/olectl/ns-olectl-fontdesc)) へのポインター。

*pFontDispAmbient*<br/>
コンテナーのアンビエントフォントプロパティへのポインター。

### <a name="remarks"></a>解説

*Pfontdispambient* が NULL でない場合、 `CFontHolder` オブジェクトは、 `IFont` コンテナーのアンビエントフォントプロパティによって使用されるインターフェイスの複製に接続されます。

*Pfontdispambient* が null の場合、 *pfontdesc* によって示されたフォントの説明から新しいフォントオブジェクトが作成されるか、 *pfontdesc* が null の場合は既定の説明から作成されます。

オブジェクトを構築した後に、この関数 `CFontHolder` を呼び出します。

## <a name="cfontholderm_pfont"></a><a name="m_pfont"></a> CFontHolder:: m_pFont

`CFontHolder`オブジェクトのインターフェイスへのポインター `IFont` 。

```
LPFONT m_pFont;
```

## <a name="cfontholderquerytextmetrics"></a><a name="querytextmetrics"></a> CFontHolder:: QueryTextMetrics

オブジェクトによって表される物理フォントに関する情報を取得 `CFontHolder` します。

```cpp
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>パラメーター

*lptm*<br/>
情報を受け取る [Textmetric](/windows/win32/api/wingdi/ns-wingdi-textmetricw) 構造体へのポインター。

## <a name="cfontholderreleasefont"></a><a name="releasefont"></a> CFontHolder:: ReleaseFont

この関数は、 `CFontHolder` オブジェクトをインターフェイスから切断し `IFont` ます。

```cpp
void ReleaseFont();
```

## <a name="cfontholderselect"></a><a name="select"></a> CFontHolder:: Select

コントロールのフォントを指定したデバイスコンテキストに選択するには、この関数を呼び出します。

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
フォントが選択されているデバイスコンテキスト。

*cyLogical*<br/>
コントロールが描画される四角形の高さ (論理単位)。

*cyHimetric*<br/>
コントロールの高さ (MM_HIMETRIC 単位)。

### <a name="return-value"></a>戻り値

置換されるフォントへのポインター。

### <a name="remarks"></a>解説

*Cylogical* および *cylogical* パラメーターの詳細については、「 [GetFontHandle](#getfonthandle) 」を参照してください。

## <a name="cfontholdersetfont"></a><a name="setfont"></a> CFontHolder::SetFont

既存のフォントをすべて解放し、 `CFontHolder` オブジェクトをインターフェイスに接続し `IFont` ます。

```cpp
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>パラメーター

*pNewFont*<br/>
新しいインターフェイスへのポインター `IFont` 。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPropExchange クラス](../../mfc/reference/cpropexchange-class.md)
