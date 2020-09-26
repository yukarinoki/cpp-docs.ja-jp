---
title: IAxWinAmbientDispatch インターフェイス
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
ms.openlocfilehash: dbd682451ca5499aef4b16b3b51feba8411bdd12
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "91352961"
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch インターフェイス

このインターフェイスは、ホストされるコントロールまたはコンテナーの特性を指定するためのメソッドを提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|プロパティは、ホストされる `AllowContextMenu` コントロールが独自のコンテキストメニューを表示できるかどうかを指定します。|
|[get_AllowShowUI](#get_allowshowui)|プロパティは、ホストされる `AllowShowUI` コントロールが独自のユーザーインターフェイスを表示できるかどうかを指定します。|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|プロパティは、 `AllowWindowlessActivation` コンテナーがウィンドウなしでのアクティブ化を許可するかどうかを指定します。|
|[get_BackColor](#get_backcolor)|プロパティは、 `BackColor` コンテナーのアンビエント背景色を指定します。|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault` は、コントロールが既定のコントロールであるかどうかを調べることができるアンビエントプロパティです。|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|プロパティは、 `DocHostDoubleClickFlags` ダブルクリックに応答して実行される操作を指定します。|
|[get_DocHostFlags](#get_dochostflags)|プロパティは、 `DocHostFlags` ホストオブジェクトのユーザーインターフェイス機能を指定します。|
|[get_Font](#get_font)|プロパティは、 `Font` コンテナーのアンビエントフォントを指定します。|
|[get_ForeColor](#get_forecolor)|プロパティは、 `ForeColor` コンテナーのアンビエント前景色を指定します。|
|[get_LocaleID](#get_localeid)|プロパティは、 `LocaleID` コンテナーのアンビエントロケール ID を指定します。|
|[get_MessageReflect](#get_messagereflect)|`MessageReflect`アンビエントプロパティは、コンテナーがホストされるコントロールにメッセージを反映するかどうかを指定します。|
|[get_OptionKeyPath](#get_optionkeypath)|プロパティは、 `OptionKeyPath` ユーザー設定へのレジストリキーのパスを指定します。|
|[get_ShowGrabHandles](#get_showgrabhandles)|アンビエントプロパティを使用する `ShowGrabHandles` と、コントロールはグラブハンドルを使用して描画する必要があるかどうかを確認できます。|
|[get_ShowHatching](#get_showhatching)|`ShowHatching`アンビエントプロパティを使用すると、コントロールでハッチを描画する必要があるかどうかを確認できます。|
|[get_UserMode](#get_usermode)|プロパティは、 `UserMode` コンテナーのアンビエントユーザーモードを指定します。|
|[put_AllowContextMenu](#put_allowcontextmenu)|プロパティは、ホストされる `AllowContextMenu` コントロールが独自のコンテキストメニューを表示できるかどうかを指定します。|
|[put_AllowShowUI](#put_allowshowui)|プロパティは、ホストされる `AllowShowUI` コントロールが独自のユーザーインターフェイスを表示できるかどうかを指定します。|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|プロパティは、 `AllowWindowlessActivation` コンテナーがウィンドウなしでのアクティブ化を許可するかどうかを指定します。|
|[put_BackColor](#put_backcolor)|プロパティは、 `BackColor` コンテナーのアンビエント背景色を指定します。|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault` は、コントロールが既定のコントロールであるかどうかを調べることができるアンビエントプロパティです。|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|プロパティは、 `DocHostDoubleClickFlags` ダブルクリックに応答して実行される操作を指定します。|
|[put_DocHostFlags](#put_dochostflags)|プロパティは、 `DocHostFlags` ホストオブジェクトのユーザーインターフェイス機能を指定します。|
|[put_Font](#put_font)|プロパティは、 `Font` コンテナーのアンビエントフォントを指定します。|
|[put_ForeColor](#put_forecolor)|プロパティは、 `ForeColor` コンテナーのアンビエント前景色を指定します。|
|[put_LocaleID](#put_localeid)|プロパティは、 `LocaleID` コンテナーのアンビエントロケール ID を指定します。|
|[put_MessageReflect](#put_messagereflect)|`MessageReflect`アンビエントプロパティは、コンテナーがホストされるコントロールにメッセージを反映するかどうかを指定します。|
|[put_OptionKeyPath](#put_optionkeypath)|プロパティは、 `OptionKeyPath` ユーザー設定へのレジストリキーのパスを指定します。|
|[put_UserMode](#put_usermode)|プロパティは、 `UserMode` コンテナーのアンビエントユーザーモードを指定します。|

## <a name="remarks"></a>解説

このインターフェイスは、ATL の ActiveX コントロールのホストオブジェクトによって公開されます。 このインターフェイスのメソッドを呼び出して、ホストされるコントロールで使用できるアンビエントプロパティを設定するか、コンテナーの動作の他の側面を指定します。 によって提供されるプロパティを補完するには `IAxWinAmbientDispatch` 、 [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)を使用します。

<xref:System.Windows.Forms.AxHost> は、コードを含む typelib に関する型情報の読み込みを試み `IAxWinAmbientDispatch` `IAxWinAmbientDispatchEx` ます。

ATL90.dll にリンクしている場合、 **AXHost** は DLL 内の typelib から型情報を読み込みます。

詳細については、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 」を参照してください。

## <a name="requirements"></a>必要条件

このインターフェイスの定義は、次の表に示すように、さまざまな形式で使用できます。

|定義の種類|ファイル|
|---------------------|----------|
|IDL|atliface|
|タイプライブラリ|ATL.dll|
|C++|atliface (ATLBase. h にも含まれる)|

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a> IAxWinAmbientDispatch:: get_AllowContextMenu

プロパティは、ホストされる `AllowContextMenu` コントロールが独自のコンテキストメニューを表示できるかどうかを指定します。

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>パラメーター

*pbAllowContextMenu*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_TRUE が使用されます。

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a> IAxWinAmbientDispatch:: get_AllowShowUI

プロパティは、ホストされる `AllowShowUI` コントロールが独自のユーザーインターフェイスを表示できるかどうかを指定します。

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>パラメーター

*pbAllowShowUI*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_FALSE が使用されます。

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a> IAxWinAmbientDispatch:: get_AllowWindowlessActivation

プロパティは、 `AllowWindowlessActivation` コンテナーがウィンドウなしでのアクティブ化を許可するかどうかを指定します。

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>パラメーター

*pbAllowWindowless*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_TRUE が使用されます。

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a> IAxWinAmbientDispatch:: get_BackColor

プロパティは、 `BackColor` コンテナーのアンビエント背景色を指定します。

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>パラメーター

*pclrBackground*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として COLOR_BTNFACE または COLOR_WINDOW を使用します (ホストウィンドウの親がダイアログであるかどうかによって異なります)。

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a> IAxWinAmbientDispatch:: get_DisplayAsDefault

`DisplayAsDefault` は、コントロールが既定のコントロールであるかどうかを調べることができるアンビエントプロパティです。

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>パラメーター

*pbDisplayAsDefault*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_FALSE が使用されます。

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a> IAxWinAmbientDispatch:: get_DocHostDoubleClickFlags

プロパティは、 `DocHostDoubleClickFlags` ダブルクリックに応答して実行される操作を指定します。

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>パラメーター

*pdwDocHostDoubleClickFlags*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として DOCHOSTUIDBLCLK_DEFAULT が使用されます。

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a> IAxWinAmbientDispatch:: get_DocHostFlags

プロパティは、 `DocHostFlags` ホストオブジェクトのユーザーインターフェイス機能を指定します。

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>パラメーター

*pdwDocHostFlags*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として DOCHOSTUIFLAG_NO3DBORDER が使用されます。

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a> IAxWinAmbientDispatch:: get_Font

プロパティは、 `Font` コンテナーのアンビエントフォントを指定します。

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
入出力 `IFontDisp` このプロパティの現在の値を受け取るために使用されるインターフェイスポインターのアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として既定の GUI フォントまたはシステムフォントを使用します。

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a> IAxWinAmbientDispatch:: get_ForeColor

プロパティは、 `ForeColor` コンテナーのアンビエント前景色を指定します。

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>パラメーター

*pclrForeground*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値としてシステムウィンドウテキストの色が使用されます。

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a> IAxWinAmbientDispatch:: get_LocaleID

プロパティは、 `LocaleID` コンテナーのアンビエントロケール ID を指定します。

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>パラメーター

*plcidLocaleID*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値としてユーザーの既定のロケールを使用します。

このメソッドを使用すると、アンビエント LocalID (コントロールが使用されているプログラムの LocaleID) を見つけることができます。 LocaleID がわかれば、コードを呼び出して、リソースファイルまたはサテライト DLL からロケール固有のキャプション、エラーメッセージテキストなどを読み込むことができます。

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a> IAxWinAmbientDispatch:: get_MessageReflect

`MessageReflect`アンビエントプロパティは、コンテナーがホストされるコントロールにメッセージを反映するかどうかを指定します。

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>パラメーター

*pbMessageReflect*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_TRUE が使用されます。

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a> IAxWinAmbientDispatch:: get_OptionKeyPath

プロパティは、 `OptionKeyPath` ユーザー設定へのレジストリキーのパスを指定します。

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>パラメーター

*pbstrOptionKeyPath*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a> IAxWinAmbientDispatch:: get_ShowGrabHandles

アンビエントプロパティを使用する `ShowGrabHandles` と、コントロールはグラブハンドルを使用して描画する必要があるかどうかを確認できます。

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>パラメーター

*pbShowGrabHandles*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装は、常にこのプロパティの値として VARIANT_FALSE を返します。

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a> IAxWinAmbientDispatch:: get_ShowHatching

`ShowHatching`アンビエントプロパティを使用すると、コントロールでハッチを描画する必要があるかどうかを確認できます。

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>パラメーター

*このように*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装は、常にこのプロパティの値として VARIANT_FALSE を返します。

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a> IAxWinAmbientDispatch:: get_UserMode

プロパティは、 `UserMode` コンテナーのアンビエントユーザーモードを指定します。

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>パラメーター

*pbUserMode*<br/>
入出力このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_TRUE が使用されます。

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a> IAxWinAmbientDispatch::p ut_AllowContextMenu

プロパティは、ホストされる `AllowContextMenu` コントロールが独自のコンテキストメニューを表示できるかどうかを指定します。

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>パラメーター

*bAllowContextMenu*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_TRUE が使用されます。

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a> IAxWinAmbientDispatch::p ut_AllowShowUI

プロパティは、ホストされる `AllowShowUI` コントロールが独自のユーザーインターフェイスを表示できるかどうかを指定します。

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>パラメーター

*bAllowShowUI*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_FALSE が使用されます。

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a> IAxWinAmbientDispatch::p ut_AllowWindowlessActivation

プロパティは、 `AllowWindowlessActivation` コンテナーがウィンドウなしでのアクティブ化を許可するかどうかを指定します。

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>パラメーター

*bAllowWindowless*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_TRUE が使用されます。

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a> IAxWinAmbientDispatch::p ut_BackColor

プロパティは、 `BackColor` コンテナーのアンビエント背景色を指定します。

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>パラメーター

*clrBackground*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として COLOR_BTNFACE または COLOR_WINDOW を使用します (ホストウィンドウの親がダイアログであるかどうかによって異なります)。

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a> IAxWinAmbientDispatch::p ut_DisplayAsDefault

`DisplayAsDefault` は、コントロールが既定のコントロールであるかどうかを調べることができるアンビエントプロパティです。

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>パラメーター

*bDisplayAsDefault*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_FALSE が使用されます。

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a> IAxWinAmbientDispatch::p ut_DocHostDoubleClickFlags

プロパティは、 `DocHostDoubleClickFlags` ダブルクリックに応答して実行される操作を指定します。

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>パラメーター

*dwDocHostDoubleClickFlags*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として DOCHOSTUIDBLCLK_DEFAULT が使用されます。

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a> IAxWinAmbientDispatch::p ut_DocHostFlags

プロパティは、 `DocHostFlags` ホストオブジェクトのユーザーインターフェイス機能を指定します。

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>パラメーター

*Dwdoチョーク Stflags*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として DOCHOSTUIFLAG_NO3DBORDER が使用されます。

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a> IAxWinAmbientDispatch::p ut_Font

プロパティは、 `Font` コンテナーのアンビエントフォントを指定します。

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として既定の GUI フォントまたはシステムフォントを使用します。

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a> IAxWinAmbientDispatch::p ut_ForeColor

プロパティは、 `ForeColor` コンテナーのアンビエント前景色を指定します。

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>パラメーター

*clrForeground*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値としてシステムウィンドウテキストの色が使用されます。

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a> IAxWinAmbientDispatch::p ut_LocaleID

プロパティは、 `LocaleID` コンテナーのアンビエントロケール ID を指定します。

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>パラメーター

*lcidLocaleID*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値としてユーザーの既定のロケールを使用します。

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a> IAxWinAmbientDispatch::p ut_MessageReflect

`MessageReflect`アンビエントプロパティは、コンテナーがホストされるコントロールにメッセージを反映するかどうかを指定します。

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>パラメーター

*bMessageReflect*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_TRUE が使用されます。

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a> IAxWinAmbientDispatch::p ut_OptionKeyPath

プロパティは、 `OptionKeyPath` ユーザー設定へのレジストリキーのパスを指定します。

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>パラメーター

*bstrOptionKeyPath*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a> IAxWinAmbientDispatch::p ut_UserMode

プロパティは、 `UserMode` コンテナーのアンビエントユーザーモードを指定します。

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>パラメーター

*bUserMode*<br/>
からこのプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

ATL ホストオブジェクトの実装では、このプロパティの既定値として VARIANT_TRUE が使用されます。

## <a name="see-also"></a>関連項目

[IAxWinAmbientDispatchEx インターフェイス](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[IAxWinHostWindow インターフェイス](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow:: QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)
