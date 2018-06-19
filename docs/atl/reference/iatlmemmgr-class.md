---
title: クラスの |Microsoft ドキュメント
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
ms.openlocfilehash: 35cc685c06eaa3992ec8444cfc5d99f2191145a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366209"
---
# <a name="iatlmemmgr-class"></a>クラス
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
|[無料](#free)|このメソッドを呼び出してメモリ ブロックを解放します。|  
|[GetSize](#getsize)|割り当てられたメモリ ブロックのサイズを取得するには、このメソッドを呼び出します。|  
|[再割り当てします](#reallocate)|メモリ ブロックを再割り当てするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスはによって実装[CComHeap](../../atl/reference/ccomheap-class.md)、 [CCRTHeap](../../atl/reference/ccrtheap-class.md)、 [CLocalHeap](../../atl/reference/clocalheap-class.md)、 [CGlobalHeap](../../atl/reference/cglobalheap-class.md)、または[CWin32Heap](../../atl/reference/cwin32heap-class.md).  
  
> [!NOTE]
>  Local と global のヒープ関数は、他のメモリ管理機能よりも低速おりに多くの機能は提供されません。 したがって、新しいアプリケーションを使用する必要があります、[ヒープ関数](http://msdn.microsoft.com/library/windows/desktop/aa366711)です。 これらで使用できる、 [CWin32Heap](../../atl/reference/cwin32heap-class.md)クラスです。  
  
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
 `nBytes`  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[IAtlMemMgr::Free](#free)または[IAtlMemMgr::Reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
### <a name="example"></a>例  
 例については、次を参照してください。、 [、概要](../../atl/reference/iatlmemmgr-class.md)です。  
  
##  <a name="free"></a>  IAtlMemMgr::Free  
 このメソッドを呼び出してメモリ ブロックを解放します。  
  
```
void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドによって取得されるメモリを解放を使用して[IAtlMemMgr::Allocate](#allocate)または[IAtlMemMgr::Reallocate](#reallocate)です。  
  
### <a name="example"></a>例  
 例については、次を参照してください。、 [、概要](../../atl/reference/iatlmemmgr-class.md)です。  
  
##  <a name="getsize"></a>  IAtlMemMgr::GetSize  
 割り当てられたメモリ ブロックのサイズを取得するには、このメソッドを呼び出します。  
  
```
size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メモリ ブロックのサイズをバイト単位で返します。  
  
### <a name="example"></a>例  
 例については、次を参照してください。、 [、概要](../../atl/reference/iatlmemmgr-class.md)です。  
  
##  <a name="reallocate"></a>  IAtlMemMgr::Reallocate  
 このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。  
  
```
void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
 `nBytes`  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[IAtlMemMgr::Free](#free)または[IAtlMemMgr::Reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 概念的にはこのメソッドは、既存のメモリを解放し、新しいメモリ ブロックを割り当てます。 実際には、既存のメモリを拡張またはそれ以外の場合に再利用する可能性があります。  
  
### <a name="example"></a>例  
 例については、次を参照してください。、 [、概要](../../atl/reference/iatlmemmgr-class.md)です。  
  
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
  
##  <a name="setambientdispatch"></a>  IAxWinAmbientDispatchEx::SetAmbientDispatch  
 ユーザー定義のインターフェイスを持つ既定のアンビエント プロパティ インターフェイスを補完する、このメソッドが呼び出されます。  
  
```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 *pDispatch*  
 新しいインターフェイスへのポインター。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 ときに`SetAmbientDispatch`が呼び出された任意のプロパティまたはメソッドのホストされるコントロールから求められる呼び出しに、この新しいインターフェイスを使用で新しいインターフェイスへのポインター、— でそれらのプロパティは既に提供されない場合[IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md).  
  
##  <a name="attachcontrol"></a>  IAxWinHostWindow::AttachControl  
 識別されるウィンドウを使用して、そのホスト オブジェクトを既存の (および前に初期化された) のコントロールを結び付けます`hWnd`です。  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pUnkControl*  
 [in]ポインター、 **IUnknown**そのホスト オブジェクトにアタッチされているコントロールのインターフェイスです。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="createcontrol"></a>  については  
 コントロールを作成し、初期化してによって識別されるウィンドウでホスト`hWnd`です。  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpTricsData`  
 [in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) の CLSID、ProgID、URL、または生の HTML を指定できます (付きます**MSHTML:**)。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
 `pStream`  
 [in]コントロールの初期化データを格納しているストリームのインターフェイス ポインター。 指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 このウィンドウは、メッセージがコントロールに反映させることができ、その他のコンテナーの機能が動作できるように、このインターフェイスを公開する、そのホスト オブジェクトをサブクラス化されます。  
  
 このメソッドの呼び出しは呼び出すことと同じ[詳細](#createcontrolex)です。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。 [IAxWinHostWindowLic::CreateControlLic](#createcontrollicex)です。  
  
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
 `lpTricsData`  
 [in]作成するコントロールを識別する文字列。 (中かっこを含める必要があります) の CLSID、ProgID、URL、または生の HTML を指定できます (付いて**MSHTML:**)。  
  
 `hWnd`  
 [in]ホストするために使用するウィンドウへのハンドル。  
  
 `pStream`  
 [in]コントロールの初期化データを格納しているストリームのインターフェイス ポインター。 指定できます**NULL**です。  
  
 `ppUnk`  
 [out]受信するポインターのアドレス、 **IUnknown**に作成されたコントロールのインターフェイスです。 指定できます**NULL**です。  
  
 *riidAdvise*  
 [in]含まれるオブジェクト上の発信インターフェイスのインターフェイスの識別子です。 指定できます**iid_ に**です。  
  
 *punkAdvise*  
 [in]ポインター、 **IUnknown**で指定されたコンテナー内のオブジェクトの接続ポイントに接続するシンク オブジェクトのインターフェイス`iidSink`です。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 異なり、`CreateControl`メソッド、`CreateControlEx`を新しく作成されたコントロールへのインターフェイス ポインターを受け取り、コントロールによって発生したイベントを受信するイベント シンクをセットアップすることもできます。  
  
 ライセンスされた ActiveX コントロールを作成するを参照してください。[呼び出し](#createcontrollicex)です。  
  
##  <a name="querycontrol"></a>  IAxWinHostWindow::QueryControl  
 ホストされるコントロールによって提供される、指定されたインターフェイス ポインターを返します。  
  
```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `riid`  
 [in]要求されているコントロールのインターフェイスの ID。  
  
 `ppvObject`  
 [out]作成されたコントロールの指定されたインターフェイスを受信するポインターのアドレス。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="setexternaldispatch"></a>  IAxWinHostWindow::SetExternalDispatch  
 を通じて、含まれているコントロールがある外部のディスパッチ インターフェイスの設定、 [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md)メソッドです。  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 [in]ポインター、`IDispatch`インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
##  <a name="setexternaluihandler"></a>  IAxWinHostWindow::SetExternalUIHandler  
 外部を設定するには、この関数を呼び出す[IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md)のためのインターフェイス、`CAxWindow`オブジェクト。  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDisp`  
 [in]ポインター、 **IDocHostUIHandlerDispatch**インターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 この関数が、ホストのサイト (Web ブラウザー コントロールで) などのコントロールで使用される、`IDocHostUIHandlerDispatch`インターフェイスです。  
  
##  <a name="createcontrollic"></a>  IAxWinHostWindowLic::CreateControlLic  
 ライセンスされたコントロールを作成、初期化して、およびで識別されるウィンドウでホスト`hWnd`です。  
  
```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```  
  
### <a name="parameters"></a>パラメーター  
 `bstrLic`  
 [in]コントロールのライセンス キーを含む BSTR です。  
  
### <a name="remarks"></a>コメント  
 参照してください[については](#createcontrol)残りのパラメーターと戻り値の詳細についてはします。  
  
 このメソッドの呼び出しは呼び出すことと同じ[呼び出し](#createcontrollicex)  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`IAxWinHostWindowLic::CreateControlLic`します。  
  
##  <a name="createcontrollicex"></a>  呼び出し  
 ライセンスされた ActiveX コントロールを作成、初期化、および指定したウィンドウでホスト[については](#createcontrol)します。  
  
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
 `bstrLic`  
 [in]コントロールのライセンス キーを含む BSTR です。  
  
### <a name="remarks"></a>コメント  
 参照してください[詳細](#createcontrolex)残りのパラメーターと戻り値の詳細についてはします。  
  
### <a name="example"></a>例  
 参照してください[ActiveX コントロール ATL を使用しての AXHost をホストしている](../../atl/hosting-activex-controls-using-atl-axhost.md)を使用するサンプルの`IAxWinHostWindowLic::CreateControlLicEx`します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
