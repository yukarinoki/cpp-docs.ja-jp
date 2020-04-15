---
title: インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
ms.openlocfilehash: 6a4f5322d957b1e978bd123db3b4796be6b300da
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330010"
---
# <a name="iaxwinambientdispatch-interface"></a>インターフェイス

このインターフェイスには、ホストされたコントロールまたはコンテナーの特性を指定するメソッドが用意されています。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|プロパティ`AllowContextMenu`は、ホストされたコントロールが独自のコンテキスト メニューを表示できるかどうかを指定します。|
|[get_AllowShowUI](#get_allowshowui)|この`AllowShowUI`プロパティは、ホストされたコントロールが独自のユーザー インターフェイスを表示できるかどうかを指定します。|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|この`AllowWindowlessActivation`プロパティは、コンテナーがウィンドウなしのアクティブ化を許可するかどうかを指定します。|
|[get_BackColor](#get_backcolor)|プロパティ`BackColor`は、コンテナーのアンビエント背景色を指定します。|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault`は、コントロールが既定のコントロールかどうかを調べることができるアンビエント プロパティです。|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|この`DocHostDoubleClickFlags`プロパティは、ダブルクリックに応答して実行する操作を指定します。|
|[get_DocHostFlags](#get_dochostflags)|プロパティ`DocHostFlags`は、ホスト オブジェクトのユーザー インターフェイス機能を指定します。|
|[get_Font](#get_font)|プロパティ`Font`は、コンテナーのアンビエント フォントを指定します。|
|[get_ForeColor](#get_forecolor)|プロパティ`ForeColor`は、コンテナーのアンビエント前景色を指定します。|
|[get_LocaleID](#get_localeid)|プロパティ`LocaleID`は、コンテナーのアンビエント ロケール ID を指定します。|
|[get_MessageReflect](#get_messagereflect)|アン`MessageReflect`ビエント プロパティは、コンテナーがホストされたコントロールにメッセージを反映するかどうかを指定します。|
|[get_OptionKeyPath](#get_optionkeypath)|プロパティ`OptionKeyPath`は、ユーザー設定へのレジストリ キーパスを指定します。|
|[get_ShowGrabHandles](#get_showgrabhandles)|`ShowGrabHandles`アンビエント プロパティを使用すると、コントロールは、グラブ ハンドルを使用して描画する必要があるかどうかを調べることができます。|
|[get_ShowHatching](#get_showhatching)|`ShowHatching`アンビエント プロパティを使用すると、コントロールが自身をハッチングして描画する必要があるかどうかを調べることができます。|
|[get_UserMode](#get_usermode)|プロパティ`UserMode`は、コンテナーのアンビエント ユーザー モードを指定します。|
|[put_AllowContextMenu](#put_allowcontextmenu)|プロパティ`AllowContextMenu`は、ホストされたコントロールが独自のコンテキスト メニューを表示できるかどうかを指定します。|
|[put_AllowShowUI](#put_allowshowui)|この`AllowShowUI`プロパティは、ホストされたコントロールが独自のユーザー インターフェイスを表示できるかどうかを指定します。|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|この`AllowWindowlessActivation`プロパティは、コンテナーがウィンドウなしのアクティブ化を許可するかどうかを指定します。|
|[put_BackColor](#put_backcolor)|プロパティ`BackColor`は、コンテナーのアンビエント背景色を指定します。|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault`は、コントロールが既定のコントロールかどうかを調べることができるアンビエント プロパティです。|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|この`DocHostDoubleClickFlags`プロパティは、ダブルクリックに応答して実行する操作を指定します。|
|[put_DocHostFlags](#put_dochostflags)|プロパティ`DocHostFlags`は、ホスト オブジェクトのユーザー インターフェイス機能を指定します。|
|[put_Font](#put_font)|プロパティ`Font`は、コンテナーのアンビエント フォントを指定します。|
|[put_ForeColor](#put_forecolor)|プロパティ`ForeColor`は、コンテナーのアンビエント前景色を指定します。|
|[put_LocaleID](#put_localeid)|プロパティ`LocaleID`は、コンテナーのアンビエント ロケール ID を指定します。|
|[put_MessageReflect](#put_messagereflect)|アン`MessageReflect`ビエント プロパティは、コンテナーがホストされたコントロールにメッセージを反映するかどうかを指定します。|
|[put_OptionKeyPath](#put_optionkeypath)|プロパティ`OptionKeyPath`は、ユーザー設定へのレジストリ キーパスを指定します。|
|[put_UserMode](#put_usermode)|プロパティ`UserMode`は、コンテナーのアンビエント ユーザー モードを指定します。|

## <a name="remarks"></a>解説

このインターフェイスは、ATL の ActiveX コントロールホスト オブジェクトによって公開されます。 このインターフェイスのメソッドを呼び出して、ホストされたコントロールで使用できるアンビエント プロパティを設定したり、コンテナーの動作の他の側面を指定したりします。 によって`IAxWinAmbientDispatch`提供されるプロパティを補足するには[、IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)を使用します。

<xref:System.Windows.Forms.AxHost>コードを含む typelib `IAxWinAmbientDispatch` `IAxWinAmbientDispatchEx`に関する型情報と、そのコードを含む typelib から型情報を読み込もうとします。

ATL90.dll にリンクしている場合 **、AXHost**はタイプライブラリから DLL に型情報を読み込みます。

詳細については[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照してください。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次の表に示すように、さまざまな形式で使用できます。

|定義タイプ|ファイル|
|---------------------|----------|
|Idl|アトリファス.idl|
|タイプ ライブラリ|ATL.dll|
|C++|atliface.h (ATLBase.h にも含まれています)|

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a>IAxWinアンビエントディスパッチ::get_AllowContextMenu

プロパティ`AllowContextMenu`は、ホストされたコントロールが独自のコンテキスト メニューを表示できるかどうかを指定します。

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>パラメーター

*メニューを許可します。*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_TRUEが使用されます。

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a>IAxWinアンビエントディスパッチ::get_AllowShowUI

この`AllowShowUI`プロパティは、ホストされたコントロールが独自のユーザー インターフェイスを表示できるかどうかを指定します。

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>パラメーター

*表示を許可します。*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_FALSEが使用されます。

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a>IAxWinアンビエントディスパッチ::get_AllowWindowlessActivation

この`AllowWindowlessActivation`プロパティは、コンテナーがウィンドウなしのアクティブ化を許可するかどうかを指定します。

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>パラメーター

*ウィンドウレスを許可する*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_TRUEが使用されます。

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a>IAxWinアンビエントディスパッチ::get_BackColor

プロパティ`BackColor`は、コンテナーのアンビエント背景色を指定します。

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>パラメーター

*バックグラウンド*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値として COLOR_BTNFACE またはCOLOR_WINDOWを使用します (ホスト ウィンドウの親がダイアログかどうかによって異なります)。

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a>IAxWinアンビエントディスパッチ::get_DisplayAsDefault

`DisplayAsDefault`は、コントロールが既定のコントロールかどうかを調べることができるアンビエント プロパティです。

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>パラメーター

*デフォルトで表示します。*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_FALSEが使用されます。

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a>IAxWinアンビエントディスパッチ::get_DocHostDoubleClickFlags

この`DocHostDoubleClickFlags`プロパティは、ダブルクリックに応答して実行する操作を指定します。

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>パラメーター

*ダブルクリックフラグ*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてDOCHOSTUIDBLCLK_DEFAULTを使用します。

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a>IAxWinアンビエントディスパッチ::get_DocHostFlags

プロパティ`DocHostFlags`は、ホスト オブジェクトのユーザー インターフェイス機能を指定します。

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてDOCHOSTUIFLAG_NO3DBORDERを使用します。

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a>IAxWinアンビエントディスパッチ::get_Font

プロパティ`Font`は、コンテナーのアンビエント フォントを指定します。

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
[アウト]このプロパティの現在`IFontDisp`の値を受け取るために使用されるインターフェイス ポインターのアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、デフォルトの GUI フォントまたはシステム フォントをこのプロパティの既定値として使用します。

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a>IAxWinアンビエントディスパッチ::get_ForeColor

プロパティ`ForeColor`は、コンテナーのアンビエント前景色を指定します。

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>パラメーター

*前景*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてシステム ウィンドウのテキストの色を使用します。

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a>IAxWinアンビエントディスパッチ::get_LocaleID

プロパティ`LocaleID`は、コンテナーのアンビエント ロケール ID を指定します。

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>パラメーター

*グループを指定します。*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてユーザーの既定のロケールを使用します。

このメソッドを使用すると、アンビエント ローカル ID、つまりコントロールが使用されているプログラムのロケール ID を検出できます。 LocaleID がわかっている場合は、ロケール固有のキャプションやエラー メッセージ テキストなどをリソース ファイルまたはサテライト DLL から読み込むコードを呼び出すことができます。

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a>IAxWinアンビエントディスパッチ::get_MessageReflect

アン`MessageReflect`ビエント プロパティは、コンテナーがホストされたコントロールにメッセージを反映するかどうかを指定します。

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>パラメーター

*メッセージを反映*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_TRUEが使用されます。

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a>IAxWinアンビエントディスパッチ::get_OptionKeyPath

プロパティ`OptionKeyPath`は、ユーザー設定へのレジストリ キーパスを指定します。

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>パラメーター

*キーパス*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a>IAxWinアンビエントディスパッチ::get_ShowGrabHandles

`ShowGrabHandles`アンビエント プロパティを使用すると、コントロールは、グラブ ハンドルを使用して描画する必要があるかどうかを調べることができます。

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>パラメーター

*グラブハンドルを表示します。*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装は、常にこのプロパティの値としてVARIANT_FALSEを返します。

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a>IAxWinアンビエントディスパッチ::get_ShowHatching

`ShowHatching`アンビエント プロパティを使用すると、コントロールが自身をハッチングして描画する必要があるかどうかを調べることができます。

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>パラメーター

*ハッチリングを表示する*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装は、常にこのプロパティの値としてVARIANT_FALSEを返します。

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a>IAxWinアンビエントディスパッチ::get_UserMode

プロパティ`UserMode`は、コンテナーのアンビエント ユーザー モードを指定します。

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>パラメーター

*モード*<br/>
[アウト]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_TRUEが使用されます。

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a>IAxWin アンビエントディスパッチ::pを使用します。

プロパティ`AllowContextMenu`は、ホストされたコントロールが独自のコンテキスト メニューを表示できるかどうかを指定します。

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>パラメーター

*メニューをクリックします。*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_TRUEが使用されます。

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a>IAxWin アンビエントディスパッチ::pを許可します。

この`AllowShowUI`プロパティは、ホストされたコントロールが独自のユーザー インターフェイスを表示できるかどうかを指定します。

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>パラメーター

*を表示します。*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_FALSEが使用されます。

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a>IAxWin アンビエントディスパッチ::pを許可するウィンドウなしのアクティブ化

この`AllowWindowlessActivation`プロパティは、コンテナーがウィンドウなしのアクティブ化を許可するかどうかを指定します。

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>パラメーター

*ウィンドウレスを許可する*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_TRUEが使用されます。

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a>IAxWin アンビエントディスパッチ::p

プロパティ`BackColor`は、コンテナーのアンビエント背景色を指定します。

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>パラメーター

*clrBackground*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値として COLOR_BTNFACE またはCOLOR_WINDOWを使用します (ホスト ウィンドウの親がダイアログかどうかによって異なります)。

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a>IAxWin アンビエントディスパッチ::pを使用します。

`DisplayAsDefault`は、コントロールが既定のコントロールかどうかを調べることができるアンビエント プロパティです。

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>パラメーター

*既定の表示*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_FALSEが使用されます。

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a>IAxWin アンビエントディスパッチ::p

この`DocHostDoubleClickFlags`プロパティは、ダブルクリックに応答して実行する操作を指定します。

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>パラメーター

*ダブルクリックフラグ*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてDOCHOSTUIDBLCLK_DEFAULTを使用します。

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a>IAxWin アンビエントディスパッチ::p

プロパティ`DocHostFlags`は、ホスト オブジェクトのユーザー インターフェイス機能を指定します。

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>パラメーター

*フラグ*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてDOCHOSTUIFLAG_NO3DBORDERを使用します。

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a>IAxWin アンビエントディスパッチ::p

プロパティ`Font`は、コンテナーのアンビエント フォントを指定します。

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、デフォルトの GUI フォントまたはシステム フォントをこのプロパティの既定値として使用します。

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a>IAxWin アンビエントディスパッチ::p

プロパティ`ForeColor`は、コンテナーのアンビエント前景色を指定します。

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>パラメーター

*clrフォアグラウンド*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてシステム ウィンドウのテキストの色を使用します。

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a>IAxWin アンビエントディスパッチ::put_ロケールID

プロパティ`LocaleID`は、コンテナーのアンビエント ロケール ID を指定します。

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>パラメーター

*ロケールID*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてユーザーの既定のロケールを使用します。

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a>IAxWin アンビエントディスパッチ::pを使用してメッセージを返す

アン`MessageReflect`ビエント プロパティは、コンテナーがホストされたコントロールにメッセージを反映するかどうかを指定します。

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>パラメーター

*メッセージを反映する*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_TRUEが使用されます。

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a>IAxWin アンビエントディスパッチ::pを使用します。

プロパティ`OptionKeyPath`は、ユーザー設定へのレジストリ キーパスを指定します。

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>パラメーター

*キーパス*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a>IAxWin アンビエントディスパッチ::p

プロパティ`UserMode`は、コンテナーのアンビエント ユーザー モードを指定します。

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>パラメーター

*モード*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホスト オブジェクトの実装では、このプロパティの既定値としてVARIANT_TRUEが使用されます。

## <a name="see-also"></a>関連項目

[インターフェイス](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[インターフェイス](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[ウィンドウ::クエリホスト](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
