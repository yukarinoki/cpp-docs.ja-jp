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
ms.openlocfilehash: 623ce5da46716e3f9a562862fc0375fb8704bb21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182213"
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
|[CFontHolder::GetDisplayString](#getdisplaystring)|コンテナーのプロパティ ブラウザーに表示される文字列を取得します。|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|フォントを返します`IDispatch`インターフェイス。|
|[CFontHolder::GetFontHandle](#getfonthandle)|Windows フォントへのハンドルを返します。|
|[CFontHolder::InitializeFont](#initializefont)|初期化します、`CFontHolder`オブジェクト。|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|フォント関連の情報を取得します。|
|[CFontHolder::ReleaseFont](#releasefont)|切断、`CFontHolder`オブジェクトから、`IFont`と`IFontNotification`インターフェイス。|
|[CFontHolder::Select](#select)|デバイス コンテキストには、フォント リソースを選択します。|
|[CFontHolder::SetFont](#setfont)|接続、`CFontHolder`オブジェクトを`IFont`インターフェイス。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CFontHolder::m_pFont](#m_pfont)|ポインター、`CFontHolder`オブジェクトの`IFont`インターフェイス。|

## <a name="remarks"></a>Remarks

`CFontHolder` 基本クラスはありません。

コントロールのカスタム フォント プロパティを実装するのにには、このクラスを使用します。 このようなプロパティを作成する方法の詳細については、記事を参照してください。 [ActiveX コントロール。フォントを使用して](../../mfc/mfc-activex-controls-using-fonts.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`CFontHolder`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxctl.h

##  <a name="cfontholder"></a>  CFontHolder::CFontHolder

`CFontHolder` オブジェクトを構築します。

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>パラメーター

*pNotify*<br/>
フォントへのポインター`IPropertyNotifySink`インターフェイス。

### <a name="remarks"></a>Remarks

呼び出す必要があります`InitializeFont`を使用する前に、結果のオブジェクトを初期化します。

##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString

コンテナーのプロパティ ブラウザーで表示可能な文字列を取得します。

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>パラメーター

*strValue*<br/>
参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)表示文字列を保持します。

### <a name="return-value"></a>戻り値

文字列が正常に取得される場合は 0 以外。それ以外の場合 0 を返します。

##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch

フォントのディスパッチ インターフェイスへのポインターを取得するには、この関数を呼び出します。

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>戻り値

ポインター、`CFontHolder`オブジェクトの`IFontDisp`インターフェイス。 呼び出しを関数に注意してください。`GetFontDispatch`呼び出す必要があります`IUnknown::Release`使い終わったときにこのインターフェイス ポインター。

### <a name="remarks"></a>Remarks

呼び出す`InitializeFont`呼び出す前に`GetFontDispatch`します。

##  <a name="getfonthandle"></a>  CFontHolder::GetFontHandle

Windows フォントへのハンドルを取得するには、この関数を呼び出します。

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>パラメーター

*cyLogical*<br/>
論理ユニットは、コントロールを描画する四角形の高さ。

*cyHimetric*<br/>
寸法は、コントロールの高さ。

### <a name="return-value"></a>戻り値

フォント オブジェクトを識別するハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

比率*cyLogical*と*cyHimetric*寸法で表されるフォントのポイント サイズの論理単位で、適切な表示サイズを計算するために使用します。

表示サイズ = ( *cyLogical* / *cyHimetric*) フォントのサイズ

パラメーターなしのバージョンは、画面の適切なサイズ、フォントへのハンドルを返します。

##  <a name="initializefont"></a>  CFontHolder::InitializeFont

初期化します、`CFontHolder`オブジェクト。

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>パラメーター

*pFontDesc*<br/>
フォントの説明の構造体へのポインター ( [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc)) フォントの特性を指定します。

*pFontDispAmbient*<br/>
コンテナーのアンビエント フォント プロパティへのポインター。

### <a name="remarks"></a>Remarks

場合*pFontDispAmbient*が NULL でない、`CFontHolder`の複製にオブジェクトが接続されている、`IFont`コンテナーのアンビエント フォント プロパティによって使用されるインターフェイス。

場合*pFontDispAmbient*が NULL の場合は、新しいフォント オブジェクトを作成のいずれかによって示されるフォントの説明から*pFontDesc*または、 *pFontDesc*既定値から NULL の場合は、説明します。

構築の後にこの関数を呼び出し、`CFontHolder`オブジェクト。

##  <a name="m_pfont"></a>  CFontHolder::m_pFont

ポインター、`CFontHolder`オブジェクトの`IFont`インターフェイス。

```
LPFONT m_pFont;
```

##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics

によって表される物理フォントに関する情報を取得、`CFontHolder`オブジェクト。

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>パラメーター

*lptm*<br/>
ポインターを[受け取る](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica)情報を受け取る構造体。

##  <a name="releasefont"></a>  CFontHolder::ReleaseFont

この関数は切断、`CFontHolder`オブジェクトからその`IFont`インターフェイス。

```
void ReleaseFont();
```

##  <a name="select"></a>  CFontHolder::Select

指定したデバイス コンテキストをコントロールのフォントを選択するには、この関数を呼び出します。

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
フォントの選択先デバイス コンテキスト。

*cyLogical*<br/>
論理ユニットは、コントロールを描画する四角形の高さ。

*cyHimetric*<br/>
寸法は、コントロールの高さ。

### <a name="return-value"></a>戻り値

置き換えられるフォントへのポインター。

### <a name="remarks"></a>Remarks

参照してください[GetFontHandle](#getfonthandle)の詳細については、 *cyLogical*と*cyHimetric*パラメーター。

##  <a name="setfont"></a>  CFontHolder::SetFont

任意の既存のフォントを解放し、接続、`CFontHolder`オブジェクトを`IFont`インターフェイス。

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>パラメーター

*pNewFont*<br/>
新しいポインター`IFont`インターフェイス。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[CPropExchange クラス](../../mfc/reference/cpropexchange-class.md)
