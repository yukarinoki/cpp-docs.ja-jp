---
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
ms.openlocfilehash: 6a053f127123a9ca21853189b9458738b217ee2b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373811"
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
|[Cフォントホルダー::Cフォントホルダー](#cfontholder)|`CFontHolder` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cフォントホルダー::ゲットディスプレイ文字列](#getdisplaystring)|コンテナーのプロパティ ブラウザーに表示される文字列を取得します。|
|[Cフォントホルダー::フォントディスパッチを取得します](#getfontdispatch)|フォントのインターフェイスを`IDispatch`返します。|
|[Cフォントホルダー::フォントハンドルを取得します](#getfonthandle)|Windows フォントのハンドルを返します。|
|[Cフォントホルダー::初期化フォント](#initializefont)|オブジェクトを`CFontHolder`初期化します。|
|[Cフォントホルダー::クエリテキストメトリックス](#querytextmetrics)|関連するフォントの情報を取得します。|
|[Cフォントホルダー::リリースフォント](#releasefont)|`CFontHolder`インターフェイスからオブジェクトを`IFontNotification`切断します`IFont`。|
|[Cフォントホルダー::選択](#select)|フォント リソースをデバイス コンテキストに選択します。|
|[Cフォントホルダー::セットフォント](#setfont)|オブジェクトを`CFontHolder`インターフェイスに`IFont`接続します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Cフォントホルダー::m_pFont](#m_pfont)|オブジェクトの`CFontHolder``IFont`インターフェイスへのポインター。|

## <a name="remarks"></a>解説

`CFontHolder`は基本クラスを持っていません。

このクラスを使用して、コントロールのカスタム フォント プロパティを実装します。 このようなプロパティの作成については[、「ActiveX コントロール: フォントを使用する](../../mfc/mfc-activex-controls-using-fonts.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CFontHolder`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

## <a name="cfontholdercfontholder"></a><a name="cfontholder"></a>Cフォントホルダー::Cフォントホルダー

`CFontHolder` オブジェクトを構築します。

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>パラメーター

*通知する*<br/>
フォントの`IPropertyNotifySink`インターフェイスへのポインター。

### <a name="remarks"></a>解説

結果のオブジェクト`InitializeFont`を使用する前に、呼び出して初期化する必要があります。

## <a name="cfontholdergetdisplaystring"></a><a name="getdisplaystring"></a>Cフォントホルダー::ゲットディスプレイ文字列

コンテナーのプロパティ ブラウザーに表示できる文字列を取得します。

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>パラメーター

*strValue*<br/>
表示文字列を保持する[CString](../../atl-mfc-shared/reference/cstringt-class.md)への参照。

### <a name="return-value"></a>戻り値

文字列が正常に取得された場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cfontholdergetfontdispatch"></a><a name="getfontdispatch"></a>Cフォントホルダー::フォントディスパッチを取得します

フォントのディスパッチ インターフェイスへのポインターを取得します。

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>戻り値

オブジェクトの`CFontHolder``IFontDisp`インターフェイスへのポインター。 呼び出す`GetFontDispatch`関数は、この`IUnknown::Release`インターフェイス ポインターを呼び出す必要があります。

### <a name="remarks"></a>解説

を`InitializeFont`呼び`GetFontDispatch`出す前に呼び出す.

## <a name="cfontholdergetfonthandle"></a><a name="getfonthandle"></a>Cフォントホルダー::フォントハンドルを取得します

Windows フォントのハンドルを取得します。

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>パラメーター

*サイロジカル*<br/>
コントロールが描画される四角形の高さ (論理単位)。

*サイヒメトリック*<br/>
コントロールの高さ (MM_HIMETRIC単位)。

### <a name="return-value"></a>戻り値

Font オブジェクトへのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

*cyLogical*と*cyHimetric*の比率は、MM_HIMETRIC単位で表されるフォントのポイント サイズに対する適切な表示サイズを論理単位で計算するために使用されます。

表示サイズ = (*サイロジカル* / *サイメトリック*) X フォントサイズ

パラメーターを持たないバージョンは、画面に合わせてフォント サイズのハンドルを返します。

## <a name="cfontholderinitializefont"></a><a name="initializefont"></a>Cフォントホルダー::初期化フォント

オブジェクトを`CFontHolder`初期化します。

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>パラメーター

*フォントデック*<br/>
フォントの特性を指定するフォント記述構造体 ( [FONTDESC](/windows/win32/api/olectl/ns-olectl-fontdesc)) へのポインター。

*アンビエント*<br/>
コンテナーのアンビエント Font プロパティへのポインター。

### <a name="remarks"></a>解説

*pFontDisp アンビエント*が NULL`CFontHolder`でない場合、オブジェクトはコンテナの`IFont`アンビエント Font プロパティで使用されるインターフェイスのクローンに接続されます。

*pFontDisp アンビエント*が NULL の場合、新しい Font オブジェクトは *、pFontDesc*が指すフォント記述から、または*pFontDesc*が NULL の場合はデフォルトの説明から作成されます。

オブジェクトを構築した後、この`CFontHolder`関数を呼び出します。

## <a name="cfontholderm_pfont"></a><a name="m_pfont"></a>Cフォントホルダー::m_pFont

オブジェクトの`CFontHolder``IFont`インターフェイスへのポインター。

```
LPFONT m_pFont;
```

## <a name="cfontholderquerytextmetrics"></a><a name="querytextmetrics"></a>Cフォントホルダー::クエリテキストメトリックス

オブジェクトによって表される物理フォントに関する情報`CFontHolder`を取得します。

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>パラメーター

*lptm*<br/>
情報を受け取る[TEXTMETRIC](/windows/win32/api/wingdi/ns-wingdi-textmetricw)構造体へのポインター。

## <a name="cfontholderreleasefont"></a><a name="releasefont"></a>Cフォントホルダー::リリースフォント

この関数は、`CFontHolder``IFont`オブジェクトをそのインターフェイスから切断します。

```
void ReleaseFont();
```

## <a name="cfontholderselect"></a><a name="select"></a>Cフォントホルダー::選択

コントロールのフォントを指定したデバイス コンテキストに選択します。

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
フォントが選択されるデバイス コンテキスト。

*サイロジカル*<br/>
コントロールが描画される四角形の高さ (論理単位)。

*サイヒメトリック*<br/>
コントロールの高さ (MM_HIMETRIC単位)。

### <a name="return-value"></a>戻り値

置換されるフォントへのポインター。

### <a name="remarks"></a>解説

*サイロジカル*および*サイメトリック*パラメータの説明については[、「GetFontHandle」](#getfonthandle)を参照してください。

## <a name="cfontholdersetfont"></a><a name="setfont"></a>Cフォントホルダー::セットフォント

既存のフォントを解放し、`CFontHolder`オブジェクトをインターフェイス`IFont`に接続します。

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>パラメーター

*新しいフォント*<br/>
新しい`IFont`インターフェイスへのポインター。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cpropexchange-class.md)
