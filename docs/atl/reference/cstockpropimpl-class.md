---
title: クラス
ms.date: 05/06/2019
f1_keywords:
- CStockPropImpl
- ATLCTL/ATL::CStockPropImpl
- ATLCTL/ATL::get_Appearance
- ATLCTL/ATL::get_AutoSize
- ATLCTL/ATL::get_BackColor
- ATLCTL/ATL::get_BackStyle
- ATLCTL/ATL::get_BorderColor
- ATLCTL/ATL::get_BorderStyle
- ATLCTL/ATL::get_BorderVisible
- ATLCTL/ATL::get_BorderWidth
- ATLCTL/ATL::get_Caption
- ATLCTL/ATL::get_DrawMode
- ATLCTL/ATL::get_DrawStyle
- ATLCTL/ATL::get_DrawWidth
- ATLCTL/ATL::get_Enabled
- ATLCTL/ATL::get_FillColor
- ATLCTL/ATL::get_FillStyle
- ATLCTL/ATL::get_Font
- ATLCTL/ATL::get_ForeColor
- ATLCTL/ATL::get_HWND
- ATLCTL/ATL::get_MouseIcon
- ATLCTL/ATL::get_MousePointer
- ATLCTL/ATL::get_Picture
- ATLCTL/ATL::get_ReadyState
- ATLCTL/ATL::get_TabStop
- ATLCTL/ATL::get_Text
- ATLCTL/ATL::getvalid
- ATLCTL/ATL::get_Window
- ATLCTL/ATL::put_Appearance
- ATLCTL/ATL::put_AutoSize
- ATLCTL/ATL::put_BackColor
- ATLCTL/ATL::put_BackStyle
- ATLCTL/ATL::put_BorderColor
- ATLCTL/ATL::put_BorderStyle
- ATLCTL/ATL::put_BorderVisible
- ATLCTL/ATL::put_BorderWidth
- ATLCTL/ATL::put_Caption
- ATLCTL/ATL::put_DrawMode
- ATLCTL/ATL::put_DrawStyle
- ATLCTL/ATL::put_DrawWidth
- ATLCTL/ATL::put_Enabled
- ATLCTL/ATL::put_FillColor
- ATLCTL/ATL::put_FillStyle
- ATLCTL/ATL::put_Font
- ATLCTL/ATL::put_ForeColor
- ATLCTL/ATL::put_HWND
- ATLCTL/ATL::put_MouseIcon
- ATLCTL/ATL::put_MousePointer
- ATLCTL/ATL::put_Picture
- ATLCTL/ATL::put_ReadyState
- ATLCTL/ATL::put_TabStop
- ATLCTL/ATL::put_Text
- ATLCTL/ATL::putvalid
- ATLCTL/ATL::put_Window
- ATLCTL/ATL::putref_Font
- ATLCTL/ATL::putref_MouseIcon
- ATLCTL/ATL::putref_Picture
helpviewer_keywords:
- CStockPropImpl class
- controls [ATL], stock properties
- stock properties, ATL controls
ms.assetid: 45f11d7d-6580-4a0e-872d-3bc8b836cfda
ms.openlocfilehash: 0aaeb1b6de0febfd5fc0d41cbcc7bad41c607af4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330671"
---
# <a name="cstockpropimpl-class"></a>クラス

このクラスは、ストック プロパティ値をサポートするためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <
    class T,
    class InterfaceName,
    const IID* piid = &_ATL_IIDOF(InterfaceName),
    const GUID* plibid = &CComModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0,
    class tihclass = CcomTypeInfoHolder>
class ATL_NO_VTABLE CStockPropImpl :
    public IDispatchImpl<InterfaceName, piid, plibid, wMajor, wMinor, tihclass>
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
コントロールを実装し、 から`CStockPropImpl`派生するクラス。

*インターフェイス名*<br/>
ストック プロパティを公開するデュアル インターフェイス。

*ピッド*<br/>
の IID へのポインター `InterfaceName`。

*プリビッド*<br/>
の定義を含むタイプ ライブラリの LIBID への`InterfaceName`ポインター。

*wメジャー*<br/>
タイプ ライブラリのメジャー バージョンです。 既定値は 1 です。

*wマイナー*<br/>
タイプ ライブラリのマイナー バージョンです。 既定値は 0 です。

*ティクラス*<br/>
*T*の型情報を管理するために使用されるクラス。既定値は です`CComTypeInfoHolder`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|[get_Appearance](#get_appearance)|フラットまたは 3D など、コントロールで使用されるペイント スタイルを取得します。|
|[get_AutoSize](#get_autosize)|コントロールを他のサイズにできないかどうかを示すフラグの状態を取得します。|
|[get_BackColor](#get_backcolor)|コントロールの背景色を取得します。|
|[get_BackStyle](#get_backstyle)|コントロールの背景スタイルを透明または不透明にします。|
|[get_BorderColor](#get_bordercolor)|コントロールの境界線の色を取得します。|
|[get_BorderStyle](#get_borderstyle)|コントロールの境界線スタイルを取得します。|
|[get_BorderVisible](#get_bordervisible)|コントロールの境界線が表示されているかどうかを示すフラグの状態を取得します。|
|[get_BorderWidth](#get_borderwidth)|コントロールの境界線の幅 (ピクセル単位) を取得します。|
|[get_Caption](#get_caption)|オブジェクトのキャプションに指定されたテキストを取得します。|
|[get_DrawMode](#get_drawmode)|コントロールの描画モード (XOR ペンや反転色など) を取得します。|
|[get_DrawStyle](#get_drawstyle)|このメソッドは、コントロールの描画スタイル (実線、破線、点線など) を取得します。|
|[get_DrawWidth](#get_drawwidth)|コントロールの描画メソッドで使用される描画幅 (ピクセル単位) を取得します。|
|[get_Enabled](#get_enabled)|コントロールが有効かどうかを示すフラグの状態を取得します。|
|[get_FillColor](#get_fillcolor)|コントロールの塗りつぶしの色を取得します。|
|[get_FillStyle](#get_fillstyle)|このメソッドは、コントロールの塗りつぶしスタイル (塗りつぶし、透明、またはクロス ハッチングなど) を取得します。|
|[get_Font](#get_font)|コントロールのフォント プロパティへのポインターを取得します。|
|[get_ForeColor](#get_forecolor)|コントロールの前景色を取得します。|
|[get_HWND](#get_hwnd)|コントロールに関連付けられているウィンドウ ハンドルを取得します。|
|[get_MouseIcon](#get_mouseicon)|マウスがコントロール上にあるときに表示されるグラフィックス (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを取得します。|
|[get_MousePointer](#get_mousepointer)|マウスがコントロールの上にあるときに表示されるマウス ポインターの種類 (矢印、十字、砂時計など) を取得します。|
|[get_Picture](#get_picture)|表示するグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティへのポインターを取得します。|
|[get_ReadyState](#get_readystate)|たとえば、読み込みや読み込みなど、コントロールの準備完了状態を取得します。|
|[get_TabStop](#get_tabstop)|コントロールがタブ ストップかどうかを示すフラグを取得します。|
|[get_Text](#get_text)|コントロールと共に表示されるテキストを取得します。|
|[有効な取得](#get_valid)|コントロールが有効かどうかを示すフラグの状態を取得します。|
|[get_Window](#get_window)|コントロールに関連付けられているウィンドウ ハンドルを取得します。 同一 C[ストックプロップインプル::get_HWND.](#get_hwnd)|
|[put_Appearance](#put_appearance)|フラットまたは 3D など、コントロールで使用されるペイント スタイルを設定します。|
|[put_AutoSize](#put_autosize)|コントロールを他のサイズにできないかどうかを示すフラグの値を設定します。|
|[put_BackColor](#put_backcolor)|コントロールの背景色を設定します。|
|[put_BackStyle](#put_backstyle)|コントロールの背景スタイルを設定します。|
|[put_BorderColor](#put_bordercolor)|コントロールの境界線の色を設定します。|
|[put_BorderStyle](#put_borderstyle)|コントロールの境界線スタイルを設定します。|
|[put_BorderVisible](#put_bordervisible)|コントロールの境界線が表示されているかどうかを示すフラグの値を設定します。|
|[put_BorderWidth](#put_borderwidth)|コントロールの境界線の幅を設定します。|
|[put_Caption](#put_caption)|コントロールと共に表示するテキストを設定します。|
|[put_DrawMode](#put_drawmode)|コントロールの描画モード (XOR ペンや反転色など) を設定します。|
|[put_DrawStyle](#put_drawstyle)|このメソッドは、コントロールの描画スタイル (塗りつぶし、破線、点線など) を設定します。|
|[put_DrawWidth](#put_drawwidth)|コントロールの描画メソッドで使用される幅 (ピクセル単位) を設定します。|
|[put_Enabled](#put_enabled)|コントロールが有効かどうかを示すフラグを設定します。|
|[put_FillColor](#put_fillcolor)|コントロールの塗りつぶしの色を設定します。|
|[put_FillStyle](#put_fillstyle)|このメソッドは、コントロールの塗りつぶしスタイル (塗りつぶし、透明、またはクロス ハッチングなど) を設定します。|
|[put_Font](#put_font)|コントロールのフォント プロパティを設定します。|
|[put_ForeColor](#put_forecolor)|コントロールの前景色を設定します。|
|[put_HWND](#put_hwnd)|このメソッドはE_FAILを返します。|
|[put_MouseIcon](#put_mouseicon)|マウスがコントロール上にあるときに表示されるグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを設定します。|
|[put_MousePointer](#put_mousepointer)|マウスがコントロールの上にあるときに表示されるマウス ポインタの種類 (矢印、十字、砂時計など) を設定します。|
|[put_Picture](#put_picture)|表示するグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを設定します。|
|[put_ReadyState](#put_readystate)|このメソッドを呼び出して、読み込みや読み込みなど、コントロールの準備完了状態を設定します。|
|[put_TabStop](#put_tabstop)|コントロールがタブ ストップかどうかを示すフラグの値を設定します。|
|[put_Text](#put_text)|コントロールと共に表示されるテキストを設定します。|
|[プット有効](#put_valid)|コントロールが有効かどうかを示すフラグを設定します。|
|[put_Window](#put_window)|このメソッドは[、E_FAILを返す CStockPropImpl::put_HWND](#put_hwnd)を呼び出します。|
|[putref_Font](#putref_font)|コントロールのフォント プロパティを参照カウントで設定します。|
|[putref_MouseIcon](#putref_mouseicon)|マウスがコントロール上にあるときに表示されるグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを参照カウントで設定します。|
|[putref_Picture](#putref_picture)|表示されるグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを参照カウントで設定します。|

## <a name="remarks"></a>解説

`CStockPropImpl`は、各ストック プロパティの**put**メソッドと**get**メソッドを提供します。 これらのメソッドは、プロパティが変更されたときに、各プロパティに関連付けられたデータ メンバーを設定または取得し、コンテナーに通知および同期するために必要なコードを提供します。

Visual Studio では、ウィザードを使用してストック プロパティをサポートしています。 コントロールにストック プロパティを追加する方法の詳細については、「 ATL チュートリアル 」を[参照してください。](../../atl/active-template-library-atl-tutorial.md)

下位互換性を保`CStockPropImpl`つために、それぞれ`get_Window``put_Window`と を呼`get_HWND`び`put_HWND`出すだけのメソッドとを公開します。 HWND は`put_HWND`読み取り専用プロパティでなければならないため、戻り値の既定の実装はE_FAIL。

次のプロパティには **、putref**実装もあります。

- フォント

- マウスアイコン

- 写真

同じ 3 つのストック プロパティでは、対応するデータ`CComPtr`メンバが型であるか、代入演算子によって正しいインターフェイス参照カウントを提供する他のクラスである必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

`T`

[I ディスパッチインプラ](../../atl/reference/idispatchimpl-class.md)

`CStockPropImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="cstockpropimplget_appearance"></a><a name="get_appearance"></a>Cストックプロップインプル::get_Appearance

フラットまたは 3D など、コントロールで使用されるペイント スタイルを取得します。

```
HRESULT STDMETHODCALLTYPE get_Appearance(SHORT pnAppearance);
```

### <a name="parameters"></a>パラメーター

*外観*<br/>
コントロールの描画スタイルを受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_autosize"></a><a name="get_autosize"></a>Cストックプロップインプル::get_AutoSize

コントロールを他のサイズにできないかどうかを示すフラグの状態を取得します。

```
HRESULT STDMETHODCALLTYPE get_Autosize(VARIANT_BOOL* pbAutoSize);
```

### <a name="parameters"></a>パラメーター

*pb 自動サイズ*<br/>
フラグの状態を受け取る変数。 TRUE は、コントロールが他のサイズにできないことを示します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_backcolor"></a><a name="get_backcolor"></a>Cストックプロップインプル::get_BackColor

コントロールの背景色を取得します。

```
HRESULT STDMETHODCALLTYPE get_BackColor(OLE_COLOR* pclrBackColor);
```

### <a name="parameters"></a>パラメーター

*カラー*<br/>
コントロールの背景色を受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_backstyle"></a><a name="get_backstyle"></a>Cストックプロップインプル::get_BackStyle

コントロールの背景スタイルを透明または不透明にします。

```
HRESULT STDMETHODCALLTYPE get_BackStyle(LONG* pnBackStyle);
```

### <a name="parameters"></a>パラメーター

*バックスタイル*<br/>
コントロールの背景スタイルを受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_bordercolor"></a><a name="get_bordercolor"></a>Cストックプロップインプル::get_BorderColor

コントロールの境界線の色を取得します。

```
HRESULT STDMETHODCALLTYPE get_BorderColor(OLE_COLOR* pclrBorderColor);
```

### <a name="parameters"></a>パラメーター

*色*<br/>
コントロールの境界線の色を受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_borderstyle"></a><a name="get_borderstyle"></a>Cストックプロップインプル::get_BorderStyle

コントロールの境界線スタイルを取得します。

```
HRESULT STDMETHODCALLTYPE get_BorderStyle(LONG* pnBorderStyle);
```

### <a name="parameters"></a>パラメーター

*境界線スタイル*<br/>
コントロールの境界線スタイルを受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_bordervisible"></a><a name="get_bordervisible"></a>Cストックプロップインプル::get_BorderVisible

コントロールの境界線が表示されているかどうかを示すフラグの状態を取得します。

```
HRESULT STDMETHODCALLTYPE get_BorderVisible(VARIANT_BOOL* pbBorderVisible);
```

### <a name="parameters"></a>パラメーター

*pbボーダービジブル*<br/>
フラグの状態を受け取る変数。 TRUE は、コントロールの境界線が表示されることを示します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_borderwidth"></a><a name="get_borderwidth"></a>Cストックプロップインプル::get_BorderWidth

コントロールの境界線の幅を取得します。

```
HRESULT STDMETHODCALLTYPE get_BorderWidth(LONG* pnBorderWidth);
```

### <a name="parameters"></a>パラメーター

*境界線の幅*<br/>
コントロールの境界線の幅を受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_caption"></a><a name="get_caption"></a>Cストックプロップインプル::get_Caption

オブジェクトのキャプションに指定されたテキストを取得します。

```
HRESULT STDMETHODCALLTYPE get_Caption(BSTR* pbstrCaption);
```

### <a name="parameters"></a>パラメーター

*キャプション*<br/>
コントロールと共に表示されるテキスト。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_drawmode"></a><a name="get_drawmode"></a>Cストックプロップインプル::get_DrawMode

コントロールの描画モード (XOR ペンや反転色など) を取得します。

```
HRESULT STDMETHODCALLTYPE get_DrawMode(LONG* pnDrawMode);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
コントロールの描画モードを受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_drawstyle"></a><a name="get_drawstyle"></a>Cストックプロップインプル::get_DrawStyle

このメソッドは、コントロールの描画スタイル (実線、破線、点線など) を取得します。

```
HRESULT STDMETHODCALLTYPE get_DrawStyle(LONG* pnDrawStyle);
```

### <a name="parameters"></a>パラメーター

*スタイルを描画します。*<br/>
コントロールの描画スタイルを受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_drawwidth"></a><a name="get_drawwidth"></a>Cストックプロップインプル::get_DrawWidth

コントロールの描画メソッドで使用される描画幅 (ピクセル単位) を取得します。

```
HRESULT STDMETHODCALLTYPE get_DrawWidth(LONG* pnDrawWidth);
```

### <a name="parameters"></a>パラメーター

*幅*<br/>
コントロールの幅の値をピクセル単位で受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_enabled"></a><a name="get_enabled"></a>Cストックプロップインプル::get_Enabled

コントロールが有効かどうかを示すフラグの状態を取得します。

```
HRESULT STDMETHODCALLTYPE get_Enabled(VARIANT_BOOL* pbEnabled);
```

### <a name="parameters"></a>パラメーター

*pb有効*<br/>
フラグの状態を受け取る変数。 TRUE は、コントロールが有効であることを示します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_fillcolor"></a><a name="get_fillcolor"></a>Cストックプロップインプル::get_FillColor

コントロールの塗りつぶしの色を取得します。

```
HRESULT STDMETHODCALLTYPE get_FillColor(OLE_COLOR* pclrFillColor);
```

### <a name="parameters"></a>パラメーター

*色を塗り潰す*<br/>
コントロールの塗りつぶしの色を受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_fillstyle"></a><a name="get_fillstyle"></a>Cストックプロップインプル::get_FillStyle

このメソッドは、コントロールの塗りつぶしスタイル (塗りつぶし、透明、ハッチングなど) を取得します。

```
HRESULT STDMETHODCALLTYPE get_FillStyle(LONG* pnFillStyle);
```

### <a name="parameters"></a>パラメーター

*スタイル*<br/>
コントロールの塗りつぶしスタイルを受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_font"></a><a name="get_font"></a>Cストックプロップインプル::get_Font

コントロールのフォント プロパティへのポインターを取得します。

```
HRESULT STDMETHODCALLTYPE get_Font(IFontDisp** ppFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
コントロールのフォント プロパティへのポインターを受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_forecolor"></a><a name="get_forecolor"></a>Cストックプロップインプル::get_ForeColor

コントロールの前景色を取得します。

```
HRESULT STDMETHODCALLTYPE get_ForeColor(OLE_COLOR* pclrForeColor);
```

### <a name="parameters"></a>パラメーター

*カラー*<br/>
コントロールの前景色を受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_hwnd"></a><a name="get_hwnd"></a>Cストックプロップインプル::get_HWND

コントロールに関連付けられているウィンドウ ハンドルを取得します。

```
HRESULT STDMETHODCALLTYPE get_HWND(LONG_PTR* phWnd);
```

### <a name="parameters"></a>パラメーター

*phWnd*<br/>
コントロールに関連付けられているウィンドウ ハンドル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_mouseicon"></a><a name="get_mouseicon"></a>Cストックプロップインプル::get_MouseIcon

マウスがコントロール上にあるときに表示されるグラフィックス (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを取得します。

```
HRESULT STDMETHODCALLTYPE get_MouseIcon(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>パラメーター

*写真*<br/>
グラフィックのピクチャ プロパティへのポインターを受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_mousepointer"></a><a name="get_mousepointer"></a>Cストックプロップインプル::get_MousePointer

マウスがコントロールの上にあるときに表示されるマウス ポインターの種類 (矢印、十字、砂時計など) を取得します。

```
HRESULT STDMETHODCALLTYPE get_MousePointer(LONG* pnMousePointer);
```

### <a name="parameters"></a>パラメーター

*マウスポインタ*<br/>
マウス ポインターの型を受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_picture"></a><a name="get_picture"></a>Cストックプロップインプル::get_Picture

表示するグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティへのポインターを取得します。

```
HRESULT STDMETHODCALLTYPE get_Picture(IPictureDisp** ppPicture);
```

### <a name="parameters"></a>パラメーター

*写真*<br/>
ピクチャのプロパティへのポインターを受け取る変数。 詳細については[、IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp)を参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_readystate"></a><a name="get_readystate"></a>Cストックプロップインプル::get_ReadyState

たとえば、読み込みや読み込みなど、コントロールの準備完了状態を取得します。

```
HRESULT STDMETHODCALLTYPE get_ReadyState(LONG* pnReadyState);
```

### <a name="parameters"></a>パラメーター

*状態を確認します。*<br/>
コントロールの準備完了状態を受け取る変数。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_tabstop"></a><a name="get_tabstop"></a>Cストックプロップインプル::get_TabStop

コントロールがタブ ストップかどうかを示すフラグの状態を取得します。

```
HRESULT STDMETHODCALLTYPE get_TabStop(VARIANT_BOOL* pbTabStop);
```

### <a name="parameters"></a>パラメーター

*タブストップ*<br/>
フラグの状態を受け取る変数。 TRUE は、コントロールがタブ ストップであることを示します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_text"></a><a name="get_text"></a>Cストックプロップインプル::get_Text

コントロールと共に表示されるテキストを取得します。

```
HRESULT STDMETHODCALLTYPE get_Text(BSTR* pbstrText);
```

### <a name="parameters"></a>パラメーター

*テキスト*<br/>
コントロールと共に表示されるテキスト。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplgetvalid"></a><a name="get_valid"></a>Cストックプロップインプル::ゲット有効

コントロールが有効かどうかを示すフラグの状態を取得します。

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL* pbValid);
```

### <a name="parameters"></a>パラメーター

*pbValid*<br/>
フラグの状態を受け取る変数。 TRUE は、コントロールが有効であることを示します。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplget_window"></a><a name="get_window"></a>Cストックプロップインプル::get_Window

コントロールに関連付けられているウィンドウ ハンドルを取得します。 同一 C[ストックプロップインプル::get_HWND.](#get_hwnd)

```
HRESULT STDMETHODCALLTYPE get_Window(LONG_PTR* phWnd);
```

### <a name="parameters"></a>パラメーター

*phWnd*<br/>
コントロールに関連付けられているウィンドウ ハンドル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_appearance"></a><a name="put_appearance"></a>外観:p

フラットまたは 3D など、コントロールで使用されるペイント スタイルを設定します。

```
HRESULT STDMETHODCALLTYPE put_Appearance(SHORT nAppearance);
```

### <a name="parameters"></a>パラメーター

*n外観*<br/>
コントロールで使用する新しい描画スタイル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_autosize"></a><a name="put_autosize"></a>クストルプロプル::p

コントロールを他のサイズにできないかどうかを示すフラグの値を設定します。

```
HRESULT STDMETHODCALLTYPE put_AutoSize(VARIANT_BOOL bAutoSize,);
```

### <a name="parameters"></a>パラメーター

*b 自動サイズ*<br/>
コントロールが他のサイズにできない場合は TRUE。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_backcolor"></a><a name="put_backcolor"></a>Cストックプロップインプル::pット_バックカラー

コントロールの背景色を設定します。

```
HRESULT STDMETHODCALLTYPE put_BackColor(OLE_COLOR clrBackColor);
```

### <a name="parameters"></a>パラメーター

*コールバックカラー*<br/>
新しいコントロールの背景色。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_backstyle"></a><a name="put_backstyle"></a>Cストックプロップインプル::pット_バックスタイル

コントロールの背景スタイルを設定します。

```
HRESULT STDMETHODCALLTYPE put_BackStyle(LONG nBackStyle);
```

### <a name="parameters"></a>パラメーター

*nバックスタイル*<br/>
新しいコントロールの背景スタイル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_bordercolor"></a><a name="put_bordercolor"></a>コストプロップルプル::pット_ボーダーカラー

コントロールの境界線の色を設定します。

```
HRESULT STDMETHODCALLTYPE put_BorderColor(OLE_COLOR clrBorderColor);
```

### <a name="parameters"></a>パラメーター

*境界線の色*<br/>
新しい境界線の色。 OLE_COLORデータ型は、内部的に 32 ビットの長整数として表されます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_borderstyle"></a><a name="put_borderstyle"></a>Cストックプロップインプル::pット_ボーダースタイル

コントロールの境界線スタイルを設定します。

```
HRESULT STDMETHODCALLTYPE put_BorderStyle(LONG nBorderStyle);
```

### <a name="parameters"></a>パラメーター

*ボーダースタイル*<br/>
新しい境界線スタイル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_bordervisible"></a><a name="put_bordervisible"></a>を見 :pる

コントロールの境界線が表示されているかどうかを示すフラグの値を設定します。

```
HRESULT STDMETHODCALLTYPE put_BorderVisible(VARIANT_BOOL bBorderVisible);
```

### <a name="parameters"></a>パラメーター

*bボーダービジブル*<br/>
境界線を表示する場合は TRUE。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_borderwidth"></a><a name="put_borderwidth"></a>:p

コントロールの境界線の幅を設定します。

```
HRESULT STDMETHODCALLTYPE put_BorderWidth(LONG nBorderWidth);
```

### <a name="parameters"></a>パラメーター

*境界線幅*<br/>
コントロールの境界線の新しい幅。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_caption"></a><a name="put_caption"></a>キャプション:p

コントロールと共に表示するテキストを設定します。

```
HRESULT STDMETHODCALLTYPE put_Caption(BSTR bstrCaption);
```

### <a name="parameters"></a>パラメーター

*キャプション*<br/>
コントロールと共に表示されるテキスト。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_drawmode"></a><a name="put_drawmode"></a>:pを引き出します。

コントロールの描画モード (XOR ペンや反転色など) を設定します。

```
HRESULT STDMETHODCALLTYPE put_DrawMode(LONG nDrawMode);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
コントロールの新しい描画モード。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_drawstyle"></a><a name="put_drawstyle"></a>:pを引き出すスタイル

このメソッドは、コントロールの描画スタイル (塗りつぶし、破線、点線など) を設定します。

```
HRESULT STDMETHODCALLTYPE put_DrawStyle(LONG pnDrawStyle);
```

### <a name="parameters"></a>パラメーター

*ヌドロースタイル*<br/>
コントロールの新しい描画スタイル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_drawwidth"></a><a name="put_drawwidth"></a>:p幅を引き出す

コントロールの描画メソッドで使用される幅 (ピクセル単位) を設定します。

```
HRESULT STDMETHODCALLTYPE put_DrawWidth(LONG nDrawWidth);
```

### <a name="parameters"></a>パラメーター

*幅を広げます。*<br/>
コントロールの描画メソッドで使用される新しい幅。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_enabled"></a><a name="put_enabled"></a>クストルプロビト::pを有効にしました

コントロールが有効かどうかを示すフラグの値を設定します。

```
HRESULT STDMETHODCALLTYPE put_Enabled(VARIANT_BOOL bEnabled);
```

### <a name="parameters"></a>パラメーター

*b有効*<br/>
コントロールが有効になっている場合は TRUE。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_fillcolor"></a><a name="put_fillcolor"></a>:pを塗り潰し色

コントロールの塗りつぶしの色を設定します。

```
HRESULT STDMETHODCALLTYPE put_FillColor(OLE_COLOR clrFillColor);
```

### <a name="parameters"></a>パラメーター

*カラー*<br/>
コントロールの新しい塗りつぶしの色。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_fillstyle"></a><a name="put_fillstyle"></a>Cストックプロップインプル::pット_フィルスタイル

このメソッドは、コントロールの塗りつぶしスタイル (塗りつぶし、透明、またはクロス ハッチングなど) を設定します。

```
HRESULT STDMETHODCALLTYPE put_FillStyle(LONG nFillStyle);
```

### <a name="parameters"></a>パラメーター

*エンフィルスタイル*<br/>
コントロールの新しい塗りつぶしスタイル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_font"></a><a name="put_font"></a>次の値を:p。フォント

コントロールのフォント プロパティを設定します。

```
HRESULT STDMETHODCALLTYPE put_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
コントロールのフォント プロパティへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_forecolor"></a><a name="put_forecolor"></a>Cストックプロップインプル::p

コントロールの前景色を設定します。

```
HRESULT STDMETHODCALLTYPE put_ForeColor(OLE_COLOR clrForeColor);
```

### <a name="parameters"></a>パラメーター

*カラー*<br/>
コントロールの新しい前景色。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_hwnd"></a><a name="put_hwnd"></a>Cストックプロップインプル::pット_HWND

このメソッドはE_FAILを返します。

```
HRESULT STDMETHODCALLTYPE put_HWND(LONG_PTR /* hWnd */);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
予約済み。

### <a name="return-value"></a>戻り値

E_FAILを返します。

### <a name="remarks"></a>解説

ウィンドウ ハンドルは読み取り専用の値です。

## <a name="cstockpropimplput_mouseicon"></a><a name="put_mouseicon"></a>Cストックプロップインプル::pット_マウスアイコン

マウスがコントロール上にあるときに表示されるグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを設定します。

```
HRESULT STDMETHODCALLTYPE put_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>パラメーター

*写真*<br/>
グラフィックのピクチャ プロパティへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_mousepointer"></a><a name="put_mousepointer"></a>:pをクリックします。

マウスがコントロールの上にあるときに表示されるマウス ポインタの種類 (矢印、十字、砂時計など) を設定します。

```
HRESULT STDMETHODCALLTYPE put_MousePointer(LONG nMousePointer);
```

### <a name="parameters"></a>パラメーター

*マウスポインタ*<br/>
マウス ポインターの種類。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_picture"></a><a name="put_picture"></a>Cストックプロップインプル::pット_ピクチャー

表示するグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを設定します。

```
HRESULT STDMETHODCALLTYPE put_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>パラメーター

*写真*<br/>
ピクチャのプロパティへのポインター。 詳細については[、IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp)を参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_readystate"></a><a name="put_readystate"></a>Cストックプロップインプル::pユタ州_レディステート

このメソッドを呼び出して、読み込みや読み込みなど、コントロールの準備完了状態を設定します。

```
HRESULT STDMETHODCALLTYPE put_ReadyState(LONG nReadyState);
```

### <a name="parameters"></a>パラメーター

*準備完了状態*<br/>
コントロールの準備完了状態。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_tabstop"></a><a name="put_tabstop"></a>クストルプロプル::pユタ_タブストップ

コントロールがタブ ストップかどうかを示すフラグを設定します。

```
HRESULT STDMETHODCALLTYPE put_TabStop(VARIANT_BOOL bTabStop);
```

### <a name="parameters"></a>パラメーター

*bタブストップ*<br/>
コントロールがタブ ストップの場合は TRUE。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_text"></a><a name="put_text"></a>テキストを:p

コントロールと共に表示されるテキストを設定します。

```
HRESULT STDMETHODCALLTYPE put_Text(BSTR bstrText);
```

### <a name="parameters"></a>パラメーター

*テキスト*<br/>
コントロールと共に表示されるテキスト。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplputvalid"></a><a name="put_valid"></a>クストルププロップル::p有効

コントロールが有効かどうかを示すフラグを設定します。

```
HRESULT STDMETHODCALLTYPE getvalid(VARIANT_BOOL bValid);
```

### <a name="parameters"></a>パラメーター

*bValid*<br/>
コントロールが有効な場合は TRUE。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cstockpropimplput_window"></a><a name="put_window"></a>ウィンドウ:p

このメソッドは[、E_FAILを返す CStockPropImpl::put_HWND](#put_hwnd)を呼び出します。

```
HRESULT STDMETHODCALLTYPE put_Window(LONG_PTR hWnd);
```

### <a name="parameters"></a>パラメーター

*hWnd*<br/>
ウィンドウ ハンドル。

### <a name="return-value"></a>戻り値

E_FAILを返します。

### <a name="remarks"></a>解説

ウィンドウ ハンドルは読み取り専用の値です。

## <a name="cstockpropimplputref_font"></a><a name="putref_font"></a>次の値を:p

コントロールのフォント プロパティを参照カウントで設定します。

```
HRESULT STDMETHODCALLTYPE putref_Font(IFontDisp* pFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
コントロールのフォント プロパティへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[CStockPropImpl::put_Font](#put_font)と同じですが、参照カウントを持つ。

## <a name="cstockpropimplputref_mouseicon"></a><a name="putref_mouseicon"></a>Cストックプロップインプル::pトレフ_マウスアイコン

マウスがコントロール上にあるときに表示されるグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを参照カウントで設定します。

```
HRESULT STDMETHODCALLTYPE putref_MouseIcon(IPictureDisp* pPicture);
```

### <a name="parameters"></a>パラメーター

*写真*<br/>
グラフィックのピクチャ プロパティへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

参照カウントを持つ[CStockPropImpl::put_マウスアイコン](#put_mouseicon)と同じです。

## <a name="cstockpropimplputref_picture"></a><a name="putref_picture"></a>Cストックプロップインプル::pトレフ_ピクチャー

表示されるグラフィック (アイコン、ビットマップ、またはメタファイル) のピクチャ プロパティを参照カウントで設定します。

```
HRESULT STDMETHODCALLTYPE putref_Picture(IPictureDisp* pPicture);
```

### <a name="parameters"></a>パラメーター

*写真*<br/>
ピクチャのプロパティへのポインター。 詳細については[、IPictureDisp](/windows/win32/api/ocidl/nn-ocidl-ipicturedisp)を参照してください。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[CStockPropImpl::put_Picture](#put_picture)と同じですが、参照カウントを持つ。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)<br/>
[クラスをディスパッチインプラ](../../atl/reference/idispatchimpl-class.md)
