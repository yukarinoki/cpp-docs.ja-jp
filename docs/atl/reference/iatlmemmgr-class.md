---
title: IAtlMemMgr クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b772a548054cd9d829356436afe53748c215c193
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078921"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr クラス

このクラスは、メモリ マネージャーへのインターフェイスを表します。

## <a name="syntax"></a>構文

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[割り当てる](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|
|[無料](#free)|メモリのブロックを解放するには、このメソッドを呼び出します。|
|[GetSize](#getsize)|割り当てられたメモリ ブロックのサイズを取得するには、このメソッドを呼び出します。|
|[再割り当てください。](#reallocate)|メモリのブロックを再割り当てするには、このメソッドを呼び出します。|

## <a name="remarks"></a>Remarks

このインターフェイスによって実装されます[CComHeap](../../atl/reference/ccomheap-class.md)、 [CCRTHeap](../../atl/reference/ccrtheap-class.md)、 [CLocalHeap](../../atl/reference/clocalheap-class.md)、 [CGlobalHeap](../../atl/reference/cglobalheap-class.md)、または[CWin32Heap](../../atl/reference/cwin32heap-class.md).

> [!NOTE]
>  ローカルとグローバルのヒープ関数では、他のメモリ管理関数よりも低速で、多くの機能を提供しません。 そのため、新しいアプリケーションを使用する必要があります、[ヒープ関数](/windows/desktop/Memory/heap-functions)します。 これらで使用できる、 [CWin32Heap](../../atl/reference/cwin32heap-class.md)クラス。

## <a name="example"></a>例

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>要件

**ヘッダー:** atlmem.h

##  <a name="allocate"></a>  IAtlMemMgr::Allocate

メモリ ブロックを割り当てるには、このメソッドを呼び出します。

```
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*nBytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>Remarks

呼び出す[IAtlMemMgr::Free](#free)または[IAtlMemMgr::Reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。

### <a name="example"></a>例

例については、次を参照してください。、 [IAtlMemMgr 概要](../../atl/reference/iatlmemmgr-class.md)します。

##  <a name="free"></a>  IAtlMemMgr::Free

メモリのブロックを解放するには、このメソッドを呼び出します。

```
void Free(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="remarks"></a>Remarks

このメソッドを使用して取得したメモリを解放[IAtlMemMgr::Allocate](#allocate)または[IAtlMemMgr::Reallocate](#reallocate)します。

### <a name="example"></a>例

例については、次を参照してください。、 [IAtlMemMgr 概要](../../atl/reference/iatlmemmgr-class.md)します。

##  <a name="getsize"></a>  IAtlMemMgr::GetSize

割り当てられたメモリ ブロックのサイズを取得するには、このメソッドを呼び出します。

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

### <a name="return-value"></a>戻り値

メモリ ブロックのサイズをバイト単位で返します。

### <a name="example"></a>例

例については、次を参照してください。、 [IAtlMemMgr 概要](../../atl/reference/iatlmemmgr-class.md)します。

##  <a name="reallocate"></a>  IAtlMemMgr::Reallocate

このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。

```
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>パラメーター

*p*<br/>
このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。

*nBytes*<br/>
新しいメモリ ブロック内の要求されたバイト数。

### <a name="return-value"></a>戻り値

新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。

### <a name="remarks"></a>Remarks

呼び出す[IAtlMemMgr::Free](#free)または[IAtlMemMgr::Reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。

概念的にはこのメソッドは、既存のメモリを解放し、新しいメモリ ブロックを割り当てます。 実際には、既存のメモリを拡張またはそれ以外の場合に再利用する可能性があります。

### <a name="example"></a>例

例については、次を参照してください。、 [IAtlMemMgr 概要](../../atl/reference/iatlmemmgr-class.md)します。

##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu

`AllowContextMenu`プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>パラメーター

*pbAllowContextMenu*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値に VARIANT_TRUE を使用します。

##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI

`AllowShowUI`プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>パラメーター

*pbAllowShowUI*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として VARIANT_FALSE を使用します。

##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation

`AllowWindowlessActivation`プロパティは、コンテナーでウィンドウなしのアクティベーションを許可するかどうかを指定します。

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>パラメーター

*pbAllowWindowless*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値に VARIANT_TRUE を使用します。

##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor

`BackColor`プロパティをコンテナーのアンビエント背景色を指定します。

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>パラメーター

*pclrBackground*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、COLOR_BTNFACE または COLOR_WINDOW を (ホスト ウィンドウの親がダイアログ ボックスかどうか) に応じて、このプロパティの既定値として使用します。

##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault

`DisplayAsDefault` アンビエント プロパティを調べるかどうかは、既定のコントロールのコントロールを許可します。

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>パラメーター

*pbDisplayAsDefault*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として VARIANT_FALSE を使用します。

##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`プロパティは、ダブルクリックに応答で実行される操作を指定します。

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>パラメーター

*pdwDocHostDoubleClickFlags*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として DOCHOSTUIDBLCLK_DEFAULT を使用します。

##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags

`DocHostFlags`プロパティが、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>パラメーター

*pdwDocHostFlags*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として DOCHOSTUIFLAG_NO3DBORDER を使用します。

##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font

`Font`プロパティは、コンテナーのアンビエント フォントを指定します。

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
[out]アドレス、`IFontDisp`インターフェイス ポインターがこのプロパティの現在の値を受信するために使用します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として既定の GUI フォントまたはシステム フォントを使用します。

##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor

`ForeColor`プロパティをコンテナーのアンビエント前景色を指定します。

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>パラメーター

*pclrForeground*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値としてシステム ウィンドウのテキストの色を使用します。

##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID

`LocaleID`プロパティをコンテナーのアンビエント ロケール ID を指定します。

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>パラメーター

*plcidLocaleID*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として、ユーザーの既定のロケールを使用します。

この方法では、アンビエント LocalID を見つけることができます、つまり、プログラムの LocaleID コントロールで使用されています。 ロケール Id がわかれば、リソース ファイルまたはサテライト DLL からなどロケール固有のキャプションを読み込むためのコード、エラー メッセージのテキストを呼び出すことができます。

##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect

`MessageReflect`アンビエント プロパティは、コンテナーがホストされているコントロールへのメッセージを反映するかどうかを指定します。

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>パラメーター

*pbMessageReflect*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値に VARIANT_TRUE を使用します。

##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath

`OptionKeyPath`プロパティをユーザー設定をレジストリ キーのパスを指定します。

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>パラメーター

*pbstrOptionKeyPath*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles

`ShowGrabHandles`アンビエント プロパティでは、コントロールを調べるかどうかは、グラブ ハンドルを描画、自体する必要があります。

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>パラメーター

*pbShowGrabHandles*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

常に ATL ホスト オブジェクト実装では、このプロパティの値として VARIANT_FALSE を返します。

##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching

`ShowHatching`アンビエント プロパティでは、コントロールを調べるかどうかハッチ自体を描画する必要があります。

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>パラメーター

*pbShowHatching*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

常に ATL ホスト オブジェクト実装では、このプロパティの値として VARIANT_FALSE を返します。

##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode

`UserMode`プロパティをコンテナーのアンビエント ユーザー モードを指定します。

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>パラメーター

*pbUserMode*<br/>
[out]このプロパティの現在の値を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値に VARIANT_TRUE を使用します。

##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu

`AllowContextMenu`プロパティは、ホストされるコントロールが、独自のコンテキスト メニューを表示できるかどうかを指定します。

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>パラメーター

*bAllowContextMenu*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値に VARIANT_TRUE を使用します。

##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI

`AllowShowUI`プロパティは、ホストされるコントロールが、独自のユーザー インターフェイスを表示できるかどうかを指定します。

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>パラメーター

*bAllowShowUI*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として VARIANT_FALSE を使用します。

##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation

`AllowWindowlessActivation`プロパティは、コンテナーでウィンドウなしのアクティベーションを許可するかどうかを指定します。

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>パラメーター

*bAllowWindowless*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値に VARIANT_TRUE を使用します。

##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor

`BackColor`プロパティをコンテナーのアンビエント背景色を指定します。

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>パラメーター

*clrBackground*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、COLOR_BTNFACE または COLOR_WINDOW を (ホスト ウィンドウの親がダイアログ ボックスかどうか) に応じて、このプロパティの既定値として使用します。

##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault

`DisplayAsDefault` アンビエント プロパティを調べるかどうかは、既定のコントロールのコントロールを許可します。

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>パラメーター

*bDisplayAsDefault*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として VARIANT_FALSE を使用します。

##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`プロパティは、ダブルクリックに応答で実行される操作を指定します。

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>パラメーター

*dwDocHostDoubleClickFlags*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として DOCHOSTUIDBLCLK_DEFAULT を使用します。

##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags

`DocHostFlags`プロパティが、そのホスト オブジェクトのユーザー インターフェイス機能を指定します。

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>パラメーター

*dwDocHostFlags*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として DOCHOSTUIFLAG_NO3DBORDER を使用します。

##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font

`Font`プロパティは、コンテナーのアンビエント フォントを指定します。

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として既定の GUI フォントまたはシステム フォントを使用します。

##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor

`ForeColor`プロパティをコンテナーのアンビエント前景色を指定します。

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>パラメーター

*clrForeground*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値としてシステム ウィンドウのテキストの色を使用します。

##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID

`LocaleID`プロパティをコンテナーのアンビエント ロケール ID を指定します。

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>パラメーター

*lcidLocaleID*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値として、ユーザーの既定のロケールを使用します。

##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect

`MessageReflect`アンビエント プロパティは、コンテナーがホストされているコントロールへのメッセージを反映するかどうかを指定します。

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>パラメーター

*bMessageReflect*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値に VARIANT_TRUE を使用します。

##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath

`OptionKeyPath`プロパティをユーザー設定をレジストリ キーのパスを指定します。

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>パラメーター

*bstrOptionKeyPath*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode

`UserMode`プロパティをコンテナーのアンビエント ユーザー モードを指定します。

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>パラメーター

*bUserMode*<br/>
[in]このプロパティの新しい値。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

ATL のホスト オブジェクトの実装では、このプロパティの既定値に VARIANT_TRUE を使用します。

##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch

このメソッドはユーザー定義のインターフェイスを持つ既定のアンビエント プロパティのインターフェイスを補完します。

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>パラメーター

*pDispatch*<br/>
新しいインターフェイスへのポインター。

### <a name="return-value"></a>戻り値

成功した場合、S_OK または失敗時にエラーの hresult 値を返します。

### <a name="remarks"></a>Remarks

ときに`SetAmbientDispatch`と呼びますプロパティまたはメソッドがホストされるコントロールから求められる呼び出しに、この新しいインターフェイスを使用では、新しいインターフェイスへのポインター、— でこれらのプロパティが既に提供されていない場合[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).

##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl

識別されるウィンドウを使用して、そのホスト オブジェクトを既存の (および前に初期化された) コントロールをアタッチします*hWnd*します。

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>パラメーター

*pUnkControl*<br/>
[in]ポインター、`IUnknown`ホスト オブジェクトにアタッチされるコントロールのインターフェイス。

*hWnd*<br/>
[in]ホストするために使用するウィンドウへのハンドル。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="createcontrol"></a>  については

コントロールを作成し、初期化して、識別されるウィンドウでホスト*hWnd*します。

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>パラメーター

*lpTricsData*<br/>
[in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) の CLSID、ProgID、URL、または生の HTML にすることができます (付いて**MSHTML:**)。

*hWnd*<br/>
[in]ホストするために使用するウィンドウへのハンドル。

*pStream*<br/>
[in]コントロールの初期化データを含むストリームのインターフェイス ポインター。 NULL にすることができます。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

このウィンドウは、メッセージをコントロールに反映されることができ、その他のコンテナーの機能は動作できるように、このインターフェイスを公開するホスト オブジェクトをサブクラス化されます。

このメソッドを呼び出すには、[詳細](#createcontrolex)します。

ライセンスされた ActiveX コントロールを作成するを参照してください。 [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex)します。

##  <a name="createcontrolex"></a>  詳細

ActiveX コントロールを作成、初期化、および指定したウィンドウでホスト[については](#createcontrol)します。

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
[in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) の CLSID、ProgID、URL、または生の HTML にすることができます (付いて**MSHTML:**)。

*hWnd*<br/>
[in]ホストするために使用するウィンドウへのハンドル。

*pStream*<br/>
[in]コントロールの初期化データを含むストリームのインターフェイス ポインター。 NULL にすることができます。

*ppUnk*<br/>
[out]受信するポインターのアドレス、`IUnknown`作成されたコントロールのインターフェイス。 NULL にすることができます。

*riidAdvise*<br/>
[in]送信のインターフェイスに含まれるオブジェクトのインターフェイスの識別子です。 Iid_ をすることができます。

*punkAdvise*<br/>
[in]ポインター、`IUnknown`で指定された、含まれるオブジェクトの接続ポイントに接続されているシンク オブジェクトのインターフェイス`iidSink`します。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

異なり、`CreateControl`メソッド、`CreateControlEx`新しく作成されたコントロールへのインターフェイス ポインターを受け取るし、コントロールによって発生したイベントを受信するために、イベント シンクをセットアップすることもできます。

ライセンスされた ActiveX コントロールを作成するを参照してください。[呼び出し](#createcontrollicex)します。

##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl

ホストされるコントロールによって提供される指定されたインターフェイス ポインターを返します。

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```

### <a name="parameters"></a>パラメーター

*riid*<br/>
[in]要求されているコントロールのインターフェイスの ID。

*ppvObject*<br/>
[out]作成されたコントロールの指定したインターフェイスを受信するポインターのアドレス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch

格納されているコントロールを使用できる外部のディスパッチ インターフェイスの設定、 [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md)メソッド。

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
[in]ポインター、`IDispatch`インターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler

外部を設定するには、この関数を呼び出す[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)のためのインターフェイス、`CAxWindow`オブジェクト。

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>パラメーター

*pDisp*<br/>
[in]ポインター、`IDocHostUIHandlerDispatch`インターフェイス。

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>Remarks

この関数は、ホストのサイト (Web ブラウザー コントロール) などのコントロールで使用、`IDocHostUIHandlerDispatch`インターフェイス。

##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic

ライセンス付きコントロールを作成し、それを初期化しで識別されるウィンドウでホスト`hWnd`します。

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>パラメーター

*bstrLic*<br/>
[in]コントロールのライセンス キーを含む BSTR です。

### <a name="remarks"></a>Remarks

参照してください[については](#createcontrol)の残りのパラメーターと戻り値の説明。

このメソッドを呼び出すには、[呼び出し](#createcontrollicex)

### <a name="example"></a>例

参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`IAxWinHostWindowLic::CreateControlLic`します。

##  <a name="createcontrollicex"></a>  呼び出し

ライセンスされた ActiveX コントロールを作成し、それを初期化し、指定したウィンドウでホスト[については](#createcontrol)します。

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
[in]コントロールのライセンス キーを含む BSTR です。

### <a name="remarks"></a>Remarks

参照してください[詳細](#createcontrolex)の残りのパラメーターと戻り値の説明。

### <a name="example"></a>例

参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`IAxWinHostWindowLic::CreateControlLicEx`します。

## <a name="see-also"></a>関連項目

[クラスの概要](../../atl/atl-class-overview.md)
