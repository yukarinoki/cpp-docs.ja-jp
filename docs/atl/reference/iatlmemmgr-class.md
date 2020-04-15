---
title: イアトルメムグラムクラス
ms.date: 11/04/2016
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
ms.openlocfilehash: c296c9de79c305d0f7d2f135f250d181d3cd667a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330064"
---
# <a name="iatlmemmgr-class"></a>イアトルメムグラムクラス

このクラスは、メモリ マネージャへのインターフェイスを表します。

## <a name="syntax"></a>構文

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[割り当てる](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[Free](#free)|メモリ ブロックを解放します。|
|[GetSize](#getsize)|割り当てられたメモリ ブロックのサイズを取得します。|
|[再割り当て](#reallocate)|メモリ ブロックを再割り当てします。|

## <a name="remarks"></a>解説

このインターフェイスは[、CCom ヒープ](../../atl/reference/ccomheap-class.md) [、CCRT](../../atl/reference/ccrtheap-class.md)ヒープ[、C ローカル ヒープ](../../atl/reference/clocalheap-class.md)[、CGlobal ヒープ](../../atl/reference/cglobalheap-class.md)、または[CWin32 ヒープ](../../atl/reference/cwin32heap-class.md)によって実装されます。

> [!NOTE]
> ローカル ヒープ関数とグローバル ヒープ関数は、他のメモリ管理機能よりも低速であり、多くの機能を提供しません。 したがって、新しいアプリケーションでは[ヒープ関数](/windows/win32/Memory/heap-functions)を使用する必要があります。 これらは[CWin32Heap](../../atl/reference/cwin32heap-class.md)クラスで使用できます。

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** atlmem.h

## <a name="iatlmemmgrallocate"></a><a name="allocate"></a>イアットルメムグラムグラム::割り当て

メモリ ブロックを割り当てるには、このメソッドを呼び出します。

```
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*Nbytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

呼び出し[IAtlMemgr::Free](#free)または[IAtlMemmgr::この](#reallocate)メソッドによって割り当てられたメモリを解放するために再割り当てします。

### <a name="example"></a>例

例については、「 [IAtlMemmgr の概要](../../atl/reference/iatlmemmgr-class.md)」を参照してください。

## <a name="iatlmemmgrfree"></a><a name="free"></a>IAtlMemgr::無料

メモリ ブロックを解放します。

```
void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="remarks"></a>解説

このメソッドを使用して[、IAtlMemgr によって取得されたメモリを解放します。:割り当て](#allocate)または[IAtlMemmgr::再割り当て](#reallocate).

### <a name="example"></a>例

例については、「 [IAtlMemmgr の概要](../../atl/reference/iatlmemmgr-class.md)」を参照してください。

## <a name="iatlmemmgrgetsize"></a><a name="getsize"></a>イアットルメムグラムグラム::ゲットサイズ

割り当てられたメモリ ブロックのサイズを取得します。

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="return-value"></a>戻り値

メモリ ブロックのサイズをバイト単位で返します。

### <a name="example"></a>例

例については、「 [IAtlMemmgr の概要](../../atl/reference/iatlmemmgr-class.md)」を参照してください。

## <a name="iatlmemmgrreallocate"></a><a name="reallocate"></a>IAtlMemmgr::再割り当て

このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。

```
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*P*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

*Nbytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

呼び出し[IAtlMemgr::Free](#free)または[IAtlMemmgr::この](#reallocate)メソッドによって割り当てられたメモリを解放するために再割り当てします。

概念的には、このメソッドは既存のメモリを解放し、新しいメモリ ブロックを割り当てます。 実際には、既存のメモリを拡張したり、再利用したりすることがあります。

### <a name="example"></a>例

例については、「 [IAtlMemmgr の概要](../../atl/reference/iatlmemmgr-class.md)」を参照してください。

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

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a>IAxWin アンビエントディスパッチエックス::設定アンビエントディスパッチ

このメソッドは、既定のアンビエント プロパティ インターフェイスをユーザー定義インターフェイスで補完するために呼び出されます。

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>パラメーター

*ディスパッチ*<br/>
新しいインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

新`SetAmbientDispatch`しいインターフェイスへのポインターを使用して呼び出されると、この新しいインターフェイスは、ホストされたコントロールによって求められるプロパティまたはメソッドを呼び出すために使用[されます。](../../atl/reference/iaxwinambientdispatch-interface.md)

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a>ウィンドウ::コントロールをアタッチします。

*hWnd*で識別されるウィンドウを使用して、既存の (および以前に初期化された) コントロールをホスト オブジェクトにアタッチします。

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*コントロールを確認する*<br/>
[in]ホスト オブジェクトに`IUnknown`アタッチされるコントロールのインターフェイスへのポインター。

*hWnd*<br/>
[in]ホストに使用するウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a>ウィンドウ::コントロールの作成

コントロールを作成し、初期化し *、hWnd*で識別されるウィンドウでホストします。

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*データ*<br/>
[in]作成するコントロールを識別する文字列。 CLSID (中かっこを含める必要があります)、ProgID、URL、または生の HTML **(MSHTML:** の接頭辞) を指定できます。

*hWnd*<br/>
[in]ホストに使用するウィンドウへのハンドル。

*pストリーム*<br/>
[in]コントロールの初期化データを含むストリームのインターフェイス ポインター。 NULL にすることができます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このウィンドウは、メッセージをコントロールに反映できるように、このインターフェイスを公開するホスト オブジェクトによってサブクラス化され、他のコンテナー機能が機能します。

このメソッドを呼び出すことは、呼び出す[の](#createcontrolex)と同じです。

ライセンスを取得した ActiveX コントロールを作成するには[、「IAxWinHostWindowLic::CreateControlLic](#createcontrollicex)」を参照してください。

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a>ウィンドウ::コントロールエクスを作成します。

ActiveX コントロールを作成し、初期化し、指定したウィンドウで[ホストします。](#createcontrol)

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>パラメーター

*データ*<br/>
[in]作成するコントロールを識別する文字列。 CLSID (中かっこを含める必要があります)、ProgID、URL、または生の HTML (プレフィックスは**MSHTML:**) です。

*hWnd*<br/>
[in]ホストに使用するウィンドウへのハンドル。

*pストリーム*<br/>
[in]コントロールの初期化データを含むストリームのインターフェイス ポインター。 NULL にすることができます。

*ppUnk*<br/>
[アウト]作成されたコントロールのインターフェイスを`IUnknown`受け取るポインターのアドレス。 NULL にすることができます。

*リドアドバイス*<br/>
[in]含まれているオブジェクトの発信インターフェイスのインターフェイス識別子。 IID_NULLすることができます。

*パンクアドバイス*<br/>
[in]で`iidSink`指定された格納`IUnknown`されているオブジェクトの接続ポイントに接続されるシンク オブジェクトのインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

`CreateControl`メソッドとは異`CreateControlEx`なり、新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクを設定することもできます。

ライセンスを取得した ActiveX コントロールを作成するには[、「IAxWinHostWindowLic::CreateControlLicEx](#createcontrollicex)」を参照してください。

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a>ウィンドウ::クエリコントロール

ホストされたコントロールによって提供される指定されたインターフェイス ポインターを返します。

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
[in]要求されているコントロールのインターフェイスの ID。

*オブジェクト*<br/>
[アウト]作成されたコントロールの指定されたインターフェイスを受け取るポインターのアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a>ウィンドウ::外部ディスパッチを設定します。

メソッドを通じて含まれるコントロールに使用できる外部ディスパッチ インターフェイス[を](../../atl/reference/idochostuihandlerdispatch-interface.md)設定します。

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
[in]`IDispatch`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a>ウィンドウ::外部UIハンドラを設定します。

オブジェクトの外部[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)インターフェイスを設定するには、`CAxWindow`この関数を呼び出します。

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
[in]`IDocHostUIHandlerDispatch`インターフェイスへのポインター。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

この関数は、ホストのサイトにインターフェイスを照会するコントロール (Web ブラウザー コントロールなど)`IDocHostUIHandlerDispatch`によって使用されます。

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a>をクリックします。

ライセンスされたコントロールを作成し、初期化し、 で`hWnd`識別されるウィンドウでホストします。

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>パラメーター

*bstrLic*<br/>
[in]コントロールのライセンス キーを含む BSTR。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については[、IAxWinHostWindow::CreateControl](#createcontrol)を参照してください。

このメソッドを呼び出すことは、呼び出しと同等[です。](#createcontrollicex)

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`IAxWinHostWindowLic::CreateControlLic`してください。

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a>をクリックします。

ライセンスを受けた ActiveX コントロールを作成し、初期化し、指定されたウィンドウで[ホストします。](#createcontrol)

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>パラメーター

*bstrLic*<br/>
[in]コントロールのライセンス キーを含む BSTR。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については[、IAxWinHostWindow::CreateControlEx](#createcontrolex)を参照してください。

### <a name="example"></a>例

を使用するサンプルについては[、ATL AXHost を使用した ActiveX コントロールのホスティング](../../atl/hosting-activex-controls-using-atl-axhost.md)を参照`IAxWinHostWindowLic::CreateControlLicEx`してください。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
