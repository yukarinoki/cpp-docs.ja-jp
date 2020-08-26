---
title: IAtlMemMgr クラス
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
ms.openlocfilehash: a33414ec1c1b01742382150049f8e99f4a70ae34
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833427"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr クラス

このクラスは、メモリマネージャーへのインターフェイスを表します。

## <a name="syntax"></a>構文

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|名前|説明|
|-|-|
|[割当て](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[Free](#free)|メモリのブロックを解放するには、このメソッドを呼び出します。|
|[GetSize](#getsize)|割り当てられたメモリブロックのサイズを取得するには、このメソッドを呼び出します。|
|[再割り当て](#reallocate)|メモリブロックを再割り当てするには、このメソッドを呼び出します。|

## <a name="remarks"></a>解説

このインターフェイスは、 [CComHeap](../../atl/reference/ccomheap-class.md)、 [ccrtheap](../../atl/reference/ccrtheap-class.md)、 [clocalheap](../../atl/reference/clocalheap-class.md)、 [cglobalheap](../../atl/reference/cglobalheap-class.md)、または [CWin32Heap](../../atl/reference/cwin32heap-class.md)によって実装されます。

> [!NOTE]
> ローカルヒープ関数とグローバルヒープ関数は、他のメモリ管理関数よりも低速であり、多くの機能を提供するわけではありません。 そのため、新しいアプリケーションでは、 [ヒープ関数](/windows/win32/Memory/heap-functions)を使用する必要があります。 これらは、 [CWin32Heap](../../atl/reference/cwin32heap-class.md) クラスで使用できます。

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>必要条件

**ヘッダー:** atlmem. h

## <a name="iatlmemmgrallocate"></a><a name="allocate"></a> IAtlMemMgr:: Allocate

メモリ ブロックを割り当てるには、このメソッドを呼び出します。

```cpp
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

[IAtlMemMgr:: Free](#free)または[IAtlMemMgr::](#reallocate)の再割り当てを呼び出して、このメソッドによって割り当てられたメモリを解放します。

### <a name="example"></a>例

例については、「 [IAtlMemMgr の概要](../../atl/reference/iatlmemmgr-class.md)」を参照してください。

## <a name="iatlmemmgrfree"></a><a name="free"></a> IAtlMemMgr:: Free

メモリのブロックを解放するには、このメソッドを呼び出します。

```cpp
void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="remarks"></a>解説

[IAtlMemMgr:: Allocate](#allocate)または[IAtlMemMgr:: 再割り当て](#reallocate)によって取得されたメモリを解放するには、このメソッドを使用します。

### <a name="example"></a>例

例については、「 [IAtlMemMgr の概要](../../atl/reference/iatlmemmgr-class.md)」を参照してください。

## <a name="iatlmemmgrgetsize"></a><a name="getsize"></a> IAtlMemMgr:: GetSize

割り当てられたメモリブロックのサイズを取得するには、このメソッドを呼び出します。

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="return-value"></a>戻り値

メモリブロックのサイズをバイト数で返します。

### <a name="example"></a>例

例については、「 [IAtlMemMgr の概要](../../atl/reference/iatlmemmgr-class.md)」を参照してください。

## <a name="iatlmemmgrreallocate"></a><a name="reallocate"></a> IAtlMemMgr:: 再割り当て

このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。

```cpp
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*irtran-p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

*nBytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>解説

[IAtlMemMgr:: Free](#free)または[IAtlMemMgr::](#reallocate)の再割り当てを呼び出して、このメソッドによって割り当てられたメモリを解放します。

概念的には、このメソッドは既存のメモリを解放し、新しいメモリブロックを割り当てます。 実際には、既存のメモリが拡張されたり、再利用される可能性があります。

### <a name="example"></a>例

例については、「 [IAtlMemMgr の概要](../../atl/reference/iatlmemmgr-class.md)」を参照してください。

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

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a> IAxWinAmbientDispatchEx::SetAmbientDispatch

このメソッドは、ユーザー定義のインターフェイスを使用して、既定のアンビエントプロパティインターフェイスを補うために呼び出されます。

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>パラメーター

*pDispatch*<br/>
新しいインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返し、失敗した場合はエラー HRESULT を返します。

### <a name="remarks"></a>解説

`SetAmbientDispatch`新しいインターフェイスへのポインターを使用してを呼び出すと、この新しいインターフェイスは、ホストされるコントロールによって要求されたプロパティやメソッドを呼び出すために使用されます。これらのプロパティが[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)によってまだ提供されていない場合は、このインターフェイスが使用されます。

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a> IAxWinHostWindow:: AttachControl

*HWnd*で識別されるウィンドウを使用して、既存の (および以前に初期化された) コントロールをホストオブジェクトにアタッチします。

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*pUnkControl*<br/>
から `IUnknown` ホストオブジェクトにアタッチされるコントロールのインターフェイスへのポインター。

*hWnd*<br/>
からをホストするために使用するウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a> IAxWinHostWindow::CreateControl

コントロールを作成して初期化し、 *hWnd*で識別されるウィンドウでホストします。

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*lpTricsData*<br/>
から作成するコントロールを識別する文字列。 には、CLSID (中かっこを含める必要があります)、ProgID、URL、または未加工の HTML (プレフィックスは **MSHTML:**) を指定できます。

*hWnd*<br/>
からをホストするために使用するウィンドウへのハンドル。

*pStream*<br/>
からコントロールの初期化データを格納しているストリームのインターフェイスポインター。 NULL にすることができます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このウィンドウは、このインターフェイスを公開するホストオブジェクトによってサブクラス化されます。これにより、メッセージがコントロールに反映され、その他のコンテナー機能が動作するようになります。

このメソッドを呼び出すことは、 [IAxWinHostWindow:: CreateControlEx](#createcontrolex)を呼び出すことと同じです。

ライセンスされた ActiveX コントロールを作成するには、「 [IAxWinHostWindowLic:: CreateControlLic](#createcontrollicex)」を参照してください。

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a> IAxWinHostWindow::CreateControlEx

[IAxWinHostWindow:: CreateControl](#createcontrol)と同様に、ActiveX コントロールを作成して初期化し、指定したウィンドウでホストします。

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

*lpTricsData*<br/>
から作成するコントロールを識別する文字列。 CLSID (中かっこを含める必要があります)、ProgID、URL、または未加工の HTML (プレフィックスは **MSHTML:**) にすることができます。

*hWnd*<br/>
からをホストするために使用するウィンドウへのハンドル。

*pStream*<br/>
からコントロールの初期化データを格納しているストリームのインターフェイスポインター。 NULL にすることができます。

*ppUnk*<br/>
入出力 `IUnknown` 作成されたコントロールのインターフェイスを受け取るポインターのアドレス。 NULL にすることができます。

*riidAdvise*<br/>
から含まれているオブジェクトの送信インターフェイスのインターフェイス識別子。 IID_NULL できます。

*punkAdvise*<br/>
から `IUnknown` によって指定された、格納されているオブジェクトのコネクションポイントに接続するシンクオブジェクトのインターフェイスへのポインター `iidSink` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

メソッドとは異なり `CreateControl` 、では、 `CreateControlEx` 新しく作成されたコントロールへのインターフェイスポインターを受け取り、コントロールによって発生するイベントを受け取るようにイベントシンクを設定することもできます。

ライセンスされた ActiveX コントロールを作成するには、「 [IAxWinHostWindowLic:: CreateControlLicEx](#createcontrollicex)」を参照してください。

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a> IAxWinHostWindow:: QueryControl

ホストされるコントロールによって提供される、指定されたインターフェイスポインターを返します。

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
から要求されているコントロールのインターフェイスの ID。

*ppvObject*<br/>
入出力作成されたコントロールの指定されたインターフェイスを受け取るポインターのアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a> IAxWinHostWindow:: SetExternalDispatch

外部ディスパッチインターフェイスを設定します。これは、 [IDocHostUIHandlerDispatch:: GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) メソッドを介して、含まれるコントロールで使用できます。

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
からインターフェイスへのポインター `IDispatch` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a> IAxWinHostWindow:: SetExternalUIHandler

この関数を呼び出して、オブジェクトの外部 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) インターフェイスを設定し `CAxWindow` ます。

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
からインターフェイスへのポインター `IDocHostUIHandlerDispatch` 。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

この関数は、ホストのサイトに対してインターフェイスを照会するコントロール (Web ブラウザーコントロールなど) によって使用され `IDocHostUIHandlerDispatch` ます。

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a> IAxWinHostWindowLic::CreateControlLic

ライセンスされたコントロールを作成して初期化し、で識別されるウィンドウでホストし `hWnd` ます。

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>パラメーター

*bstrLic*<br/>
からコントロールのライセンスキーを格納している BSTR。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については、「 [IAxWinHostWindow:: CreateControl](#createcontrol) 」を参照してください。

このメソッドを呼び出すことは、 [IAxWinHostWindowLic:: CreateControlLicEx](#createcontrollicex)を呼び出すことと同じです。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md) 」を参照してください `IAxWinHostWindowLic::CreateControlLic` 。

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a> IAxWinHostWindowLic::CreateControlLicEx

ライセンスされた ActiveX コントロールを作成して初期化し、 [IAxWinHostWindow:: CreateControl](#createcontrol)と同様に、指定したウィンドウでホストします。

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
からコントロールのライセンスキーを格納している BSTR。

### <a name="remarks"></a>解説

残りのパラメーターと戻り値の説明については、「 [IAxWinHostWindow:: CreateControlEx](#createcontrolex) 」を参照してください。

### <a name="example"></a>例

を使用するサンプルについては、「 [ATL AXHost を使用した ActiveX コントロールのホスト](../../atl/hosting-activex-controls-using-atl-axhost.md) 」を参照してください `IAxWinHostWindowLic::CreateControlLicEx` 。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
