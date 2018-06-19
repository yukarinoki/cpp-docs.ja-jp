---
title: IAxWinAmbientDispatch インターフェイス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d082faf4c25f76fd7a98cc897760adc424ffb49e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366329"
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch インターフェイス
このインターフェイスは、ホストされるコントロールまたはコンテナーの特性を指定するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
interface IAxWinAmbientDispatch : IDispatch
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[get_AllowContextMenu](#get_allowcontextmenu)|**ショートカット メニューの表示**プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。|  
|[get_AllowShowUI](#get_allowshowui)|**AllowShowUI**プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。|  
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|**AllowWindowlessActivation**プロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。|  
|[get_BackColor](#get_backcolor)|`BackColor`プロパティは、コンテナーのアンビエント背景色を指定します。|  
|[get_DisplayAsDefault](#get_displayasdefault)|**DisplayAsDefault**アンビエント プロパティを調べるかどうか、既定のコントロールを制御できるようにします。|  
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|**DocHostDoubleClickFlags**プロパティは、処理を実行するダブルクリックに応答する操作を指定します。|  
|[get_DocHostFlags](#get_dochostflags)|**DocHostFlags**プロパティが、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。|  
|[get_Font](#get_font)|**フォント**プロパティは、コンテナーのアンビエント フォントを指定します。|  
|[get_ForeColor](#get_forecolor)|`ForeColor`プロパティは、コンテナーのアンビエント前景色を指定します。|  
|[get_LocaleID](#get_localeid)|**LocaleID**プロパティは、コンテナーのアンビエント ロケール ID を指定します。|  
|[get_MessageReflect](#get_messagereflect)|**MessageReflect**アンビエント プロパティは、コンテナーがホストされるコントロールへのメッセージを反映するかどうかを指定します。|  
|[get_OptionKeyPath](#get_optionkeypath)|**OptionKeyPath**プロパティは、ユーザー設定をレジストリ キーのパスを指定します。|  
|[get_ShowGrabHandles](#get_showgrabhandles)|**ShowGrabHandles**アンビエント プロパティがかどうかにする必要があります自体を使用して描画グラブ ハンドル検索するコントロールを使用します。|  
|[get_ShowHatching](#get_showhatching)|**ShowHatching**アンビエント プロパティでは、コントロールを調べるかどうかハッチ自体を描画する必要があります。|  
|[get_UserMode](#get_usermode)|**UserMode**プロパティは、コンテナーのアンビエント ユーザー モードを指定します。|  
|[put_AllowContextMenu](#put_allowcontextmenu)|**ショートカット メニューの表示**プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。|  
|[put_AllowShowUI](#put_allowshowui)|**AllowShowUI**プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。|  
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|**AllowWindowlessActivation**プロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。|  
|[put_BackColor](#put_backcolor)|`BackColor`プロパティは、コンテナーのアンビエント背景色を指定します。|  
|[put_DisplayAsDefault](#put_displayasdefault)|**DisplayAsDefault**アンビエント プロパティを調べるかどうか、既定のコントロールを制御できるようにします。|  
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|**DocHostDoubleClickFlags**プロパティは、処理を実行するダブルクリックに応答する操作を指定します。|  
|[put_DocHostFlags](#put_dochostflags)|**DocHostFlags**プロパティが、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。|  
|[put_Font](#put_font)|**フォント**プロパティは、コンテナーのアンビエント フォントを指定します。|  
|[put_ForeColor](#put_forecolor)|`ForeColor`プロパティは、コンテナーのアンビエント前景色を指定します。|  
|[put_LocaleID](#put_localeid)|**LocaleID**プロパティは、コンテナーのアンビエント ロケール ID を指定します。|  
|[put_MessageReflect](#put_messagereflect)|**MessageReflect**アンビエント プロパティは、コンテナーがホストされるコントロールへのメッセージを反映するかどうかを指定します。|  
|[put_OptionKeyPath](#put_optionkeypath)|**OptionKeyPath**プロパティは、ユーザー設定をレジストリ キーのパスを指定します。|  
|[put_UserMode](#put_usermode)|**UserMode**プロパティは、コンテナーのアンビエント ユーザー モードを指定します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、ATL の ActiveX コントロールをホストしているオブジェクトによって公開されます。 ホストされるコントロールに使用可能なアンビエント プロパティを設定するか、コンテナーの動作の他の側面を指定する、このインターフェイスでメソッドを呼び出します。 提供されるプロパティを補足する`IAxWinAmbientDispatch`を使用して[IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)です。  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx)をに関する型情報を読み込んでみます`IAxWinAmbientDispatch`と`IAxWinAmbientDispatchEx`コードが含まれるタイプ ライブラリからです。  
  
 ATL90.dll にリンクする場合は**AXHost**が DLL にタイプ ライブラリから型情報を読み込みます。  
  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)詳細についてはします。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次の表に示すようにさまざまな形式で使用できます。  
  
|定義の型|ファイル|  
|---------------------|----------|  
|IDL|atliface.idl|  
|タイプ ライブラリ|ATL.dll|  
|C++|atliface.h (ATLBase.h にも含まれます)|  
  
##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu  
 **ショートカット メニューの表示**プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbAllowContextMenu*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI  
 **AllowShowUI**プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbAllowShowUI*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**VARIANT_FALSE**としてこのプロパティの既定値です。  
  
##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 **AllowWindowlessActivation**プロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbAllowWindowless*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor  
 `BackColor`プロパティは、コンテナーのアンビエント背景色を指定します。  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrBackground*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**COLOR_BTNFACE**または**COLOR_WINDOW** (かどうかに応じて、ホスト ウィンドウの親ダイアログか) には、このプロパティの既定値として。  
  
##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault  
 **DisplayAsDefault**アンビエント プロパティを調べるかどうか、既定のコントロールを制御できるようにします。  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbDisplayAsDefault*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**VARIANT_FALSE**としてこのプロパティの既定値です。  
  
##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags**プロパティは、処理を実行するダブルクリックに応答する操作を指定します。  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *pdwDocHostDoubleClickFlags*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**DOCHOSTUIDBLCLK_DEFAULT**としてこのプロパティの既定値です。  
  
##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags  
 **DocHostFlags**プロパティが、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *pdwDocHostFlags*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**DOCHOSTUIFLAG_NO3DBORDER**としてこのプロパティの既定値です。  
  
##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font  
 **フォント**プロパティは、コンテナーのアンビエント フォントを指定します。  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 [out]アドレス、**この**インターフェイス ポインターがこのプロパティの現在の値を受信するために使用します。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装は、このプロパティの既定値として既定の GUI フォントやシステム フォントを使用します。  
  
##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor  
 `ForeColor`プロパティは、コンテナーのアンビエント前景色を指定します。  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>パラメーター  
 *pclrForeground*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装では、このプロパティの既定値としてシステム ウィンドウのテキストの色を使用します。  
  
##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID  
 **LocaleID**プロパティは、コンテナーのアンビエント ロケール ID を指定します。  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>パラメーター  
 *plcidLocaleID*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装では、このプロパティの既定値として、ユーザーの既定のロケールを使用します。  
  
 このメソッドを使用してアンビエント LocalID を検出することができます、つまり、プログラムのロケール Id、コントロールが使用されています。 ロケール Id がわかれば、リソース ファイルまたはサテライト DLL からなどを読み込むコードをロケール固有のキャプション、エラー メッセージ テキストを呼び出すことができます。  
  
##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect  
 **MessageReflect**アンビエント プロパティは、コンテナーがホストされるコントロールへのメッセージを反映するかどうかを指定します。  
  
```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbMessageReflect*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath  
 **OptionKeyPath**プロパティは、ユーザー設定をレジストリ キーのパスを指定します。  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbstrOptionKeyPath*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles  
 **ShowGrabHandles**アンビエント プロパティがかどうかにする必要があります自体を使用して描画グラブ ハンドル検索するコントロールを使用します。  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbShowGrabHandles*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクト実装は、常に**VARIANT_FALSE**としてこのプロパティの値。  
  
##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching  
 **ShowHatching**アンビエント プロパティでは、コントロールを調べるかどうかハッチ自体を描画する必要があります。  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbShowHatching*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL ホスト オブジェクト実装は、常に**VARIANT_FALSE**としてこのプロパティの値。  
  
##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode  
 **UserMode**プロパティは、コンテナーのアンビエント ユーザー モードを指定します。  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>パラメーター  
 *pbUserMode*  
 [out]このプロパティの現在の値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu  
 **ショートカット メニューの表示**プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAllowContextMenu*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI  
 **AllowShowUI**プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAllowShowUI*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**VARIANT_FALSE**としてこのプロパティの既定値です。  
  
##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 **AllowWindowlessActivation**プロパティは、コンテナーがウィンドウなしのアクティベーションを許可するかどうかを指定します。  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAllowWindowless*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor  
 `BackColor`プロパティは、コンテナーのアンビエント背景色を指定します。  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrBackground*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**COLOR_BTNFACE**または**COLOR_WINDOW** (かどうかに応じて、ホスト ウィンドウの親ダイアログか) には、このプロパティの既定値として。  
  
##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault  
 **DisplayAsDefault**アンビエント プロパティを調べるかどうか、既定のコントロールを制御できるようにします。  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `bDisplayAsDefault`  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**VARIANT_FALSE**としてこのプロパティの既定値です。  
  
##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags**プロパティは、処理を実行するダブルクリックに応答する操作を指定します。  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDocHostDoubleClickFlags*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**DOCHOSTUIDBLCLK_DEFAULT**としてこのプロパティの既定値です。  
  
##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags  
 **DocHostFlags**プロパティが、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwDocHostFlags*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して**DOCHOSTUIFLAG_NO3DBORDER**としてこのプロパティの既定値です。  
  
##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font  
 **フォント**プロパティは、コンテナーのアンビエント フォントを指定します。  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFont`  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装は、このプロパティの既定値として既定の GUI フォントやシステム フォントを使用します。  
  
##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor  
 `ForeColor`プロパティは、コンテナーのアンビエント前景色を指定します。  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrForeground*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装では、このプロパティの既定値としてシステム ウィンドウのテキストの色を使用します。  
  
##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID  
 **LocaleID**プロパティは、コンテナーのアンビエント ロケール ID を指定します。  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>パラメーター  
 *lcidLocaleID*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装では、このプロパティの既定値として、ユーザーの既定のロケールを使用します。  
  
##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect  
 **MessageReflect**アンビエント プロパティは、コンテナーがホストされるコントロールへのメッセージを反映するかどうかを指定します。  
  
```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```  
  
### <a name="parameters"></a>パラメーター  
 `bMessageReflect`  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath  
 **OptionKeyPath**プロパティは、ユーザー設定をレジストリ キーのパスを指定します。  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>パラメーター  
 *bstrOptionKeyPath*  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode  
 **UserMode**プロパティは、コンテナーのアンビエント ユーザー モードを指定します。  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `bUserMode`  
 [in]このプロパティの新しい値。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 ATL のホスト オブジェクトの実装を使用して`VARIANT_TRUE`としてこのプロパティの既定値です。  
  
## <a name="see-also"></a>関連項目  
 [IAxWinAmbientDispatchEx インターフェイス](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow インターフェイス](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









