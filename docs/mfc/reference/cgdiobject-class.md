---
title: CGdiObject クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGdiObject
- AFXWIN/CGdiObject
- AFXWIN/CGdiObject::CGdiObject
- AFXWIN/CGdiObject::Attach
- AFXWIN/CGdiObject::CreateStockObject
- AFXWIN/CGdiObject::DeleteObject
- AFXWIN/CGdiObject::DeleteTempMap
- AFXWIN/CGdiObject::Detach
- AFXWIN/CGdiObject::FromHandle
- AFXWIN/CGdiObject::GetObject
- AFXWIN/CGdiObject::GetObjectType
- AFXWIN/CGdiObject::GetSafeHandle
- AFXWIN/CGdiObject::UnrealizeObject
- AFXWIN/CGdiObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CGdiObject [MFC], CGdiObject
- CGdiObject [MFC], Attach
- CGdiObject [MFC], CreateStockObject
- CGdiObject [MFC], DeleteObject
- CGdiObject [MFC], DeleteTempMap
- CGdiObject [MFC], Detach
- CGdiObject [MFC], FromHandle
- CGdiObject [MFC], GetObject
- CGdiObject [MFC], GetObjectType
- CGdiObject [MFC], GetSafeHandle
- CGdiObject [MFC], UnrealizeObject
- CGdiObject [MFC], m_hObject
ms.assetid: 1cba3ba5-3d49-4e43-8293-209299f2f6f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e72c7ea788085f25dc2a4ec1b2f8682df9e20b25
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209128"
---
# <a name="cgdiobject-class"></a>CGdiObject クラス
ビットマップ、領域、ブラシ、ペン、パレット、フォントなどの Windows のさまざまな種類のグラフィックス デバイス インターフェイス (GDI) の基底クラスを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CGdiObject : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::CGdiObject](#cgdiobject)|`CGdiObject` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::Attach](#attach)|Windows GDI オブジェクトをアタッチ、`CGdiObject`オブジェクト。|  
|[CGdiObject::CreateStockObject](#createstockobject)|Windows の定義済みのストック ペン、ブラシ、またはフォントのいずれかを識別するハンドルを取得します。|  
|[CGdiObject::DeleteObject](#deleteobject)|Windows GDI オブジェクトにアタッチされて削除、`CGdiObject`オブジェクトに関連付けられているすべてのシステムの記憶域を解放することによって、メモリからオブジェクト。|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|一時的な削除`CGdiObject`によって作成されたオブジェクト`FromHandle`します。|  
|[CGdiObject::Detach](#detach)|Windows GDI オブジェクトからデタッチする`CGdiObject`オブジェクトし、Windows GDI オブジェクトへのハンドルを返します。|  
|[CGdiObject::FromHandle](#fromhandle)|ポインターを返します、 `CGdiObject` Windows GDI オブジェクトを識別するハンドルを指定したオブジェクト。|  
|[CGdiObject::GetObject](#getobject)|アタッチされている Windows GDI オブジェクトを説明するデータを使用して、バッファーを塗りつぶし、`CGdiObject`オブジェクト。|  
|[CGdiObject::GetObjectType](#getobjecttype)|GDI オブジェクトの型を取得します。|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|返します`m_hObject`しない限り、**この**が null の場合、大文字と小文字の NULL が返されます。|  
|[CGdiObject::UnrealizeObject](#unrealizeobject)|ブラシの原点にリセットまたは論理パレットをリセットします。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|2 つの GDI オブジェクトが等しく論理的にないかどうかを決定します。|  
|[CGdiObject::operator = =](#operator_eq_eq)|2 つの GDI オブジェクトが論理的に等しいかどうかを決定します。|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|アタッチされている Windows GDI オブジェクトを識別するハンドルを取得します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|HBITMAP、HPALETTE、HRGN、HBRUSH、HPEN、または HFONT ハンドルは、このオブジェクトにアタッチします。|  
  
## <a name="remarks"></a>Remarks  
 作成することはありません、`CGdiObject`直接します。 代わりに、オブジェクトを作成するその派生クラスのいずれかからなど`CPen`または`CBrush`します。  
  
 詳細については`CGdiObject`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGdiObject`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="attach"></a>  CGdiObject::Attach  
 Windows GDI オブジェクトをアタッチ、`CGdiObject`オブジェクト。  
  
```  
BOOL Attach(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 *hObject*  
 Windows GDI オブジェクト (たとえば、HPEN または HBRUSH) へのハンドル。  
  
### <a name="return-value"></a>戻り値  
 添付ファイルが成功した場合、0 以外の場合それ以外の場合 0 を返します。  
  
##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject  
 `CGdiObject` オブジェクトを構築します。  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>Remarks  
 作成することはありません、`CGdiObject`直接します。 代わりに、オブジェクトを作成するその派生クラスのいずれかからなど`CPen`または`Cbrush`します。  
  
##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject  
 定義済みのストック Windows GDI ペン、ブラシ、フォントのいずれかを識別するハンドルを取得し、GDI オブジェクトを`CGdiObject`オブジェクト。  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIndex*  
 目的のストック オブジェクトの種類を指定する定数。 パラメーターを*fnObject*の[GetStockObject](/windows/desktop/api/wingdi/nf-wingdi-getstockobject) Windows sdk の適切な値の説明。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 クラスの派生クラスのいずれかでこの関数の呼び出しなどの Windows GDI オブジェクトの種類に対応`CPen`の株価のペン。  
  
##  <a name="deleteobject"></a>  CGdiObject::DeleteObject  
 Windows GDI オブジェクトに関連付けられたすべてのシステムの記憶域を解放して、メモリからアタッチされている Windows GDI オブジェクトを削除します。  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>戻り値  
 GDI オブジェクトが正常に削除された場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 関連付けられている記憶域、`CGdiObject`オブジェクトがこの呼び出しによって影響ありません。 アプリケーションは呼び出さないでください`DeleteObject`上、`CGdiObject`デバイス コンテキストに現在選択されているオブジェクト。  
  
 ブラシのパターンが削除されると、ブラシに関連付けられたビットマップは削除されません。 ビットマップは個別に削除する必要があります。  
  
##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap  
 によって自動的と呼ばれる、`CWinApp`アイドル処理ハンドラー、`DeleteTempMap`一時を削除します`CGdiObject`によって作成されたオブジェクト`FromHandle`します。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Remarks  
 `DeleteTempMap` 一時的に接続されている Windows GDI オブジェクトをデタッチ`CGdiObject`オブジェクトを削除する前に、`CGdiObject`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>  CGdiObject::Detach  
 Windows GDI オブジェクトからデタッチする`CGdiObject`オブジェクトし、Windows GDI オブジェクトへのハンドルを返します。  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>戻り値  
 A `HANDLE` Windows gdi オブジェクトをデタッチ; GDI オブジェクトがアタッチされていない場合は NULL それ以外の場合。  
  
##  <a name="fromhandle"></a>  CGdiObject::FromHandle  
 ポインターを返します、 `CGdiObject` Windows GDI オブジェクトを識別するハンドルを指定したオブジェクト。  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 *hObject*  
 Windows GDI オブジェクトへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CGdiObject`一時的または永続的があります。  
  
### <a name="remarks"></a>Remarks  
 場合、`CGdiObject`オブジェクトが一時的なである Windows GDI オブジェクトに既にアタッチされていない`CGdiObject`オブジェクトを作成し、接続されています。  
  
 この一時`CGdiObject`オブジェクトは、次回、アプリケーションがあるすべての一時的なグラフィック オブジェクトを削除する時点で、イベント ループでのアイドル時間までのみ有効です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に一時オブジェクトが有効でのみことです。  
  
##  <a name="getobject"></a>  CGdiObject::GetObject  
 指定したオブジェクトを定義するデータをバッファーします。  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *nCount*  
 コピーするバイト数を指定します、 *lpObject*バッファー。  
  
 *lpObject*  
 情報を受信するユーザー指定のバッファーを指します。  
  
### <a name="return-value"></a>戻り値  
 バイトの数を取得します。それ以外の場合のエラーが 0 の場合に発生します。  
  
### <a name="remarks"></a>Remarks  
 関数は、次の一覧に示すように型を持つは、グラフィック オブジェクトの種類によって異なります。 データ構造体を取得します。  
  
|Object|バッファーの種類|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](/windows/desktop/api/wingdi/ns-wingdi-taglogfonta)|  
|`CBitmap`|[ビットマップ](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|WORD|  
|`CRgn`|サポートなし|  
  
 オブジェクトの場合、`CBitmap`オブジェクト、`GetObject`幅、高さ、およびビットマップの色の書式情報のみを返します。 使用して取得できる実際のビット[列](../../mfc/reference/cbitmap-class.md#getbitmapbits)します。  
  
 オブジェクトの場合、`CPalette`オブジェクト、`GetObject`パレットのエントリの数を指定する単語を取得します。 関数を取得することはありません、[保持](/windows/desktop/api/wingdi/ns-wingdi-taglogpalette)パレットを定義する構造体。 アプリケーションが呼び出すことによってパレット エントリに関する情報を取得できる[CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries)します。  
  
##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType  
 GDI オブジェクトの型を取得します。  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は、オブジェクトの種類それ以外の場合 0 を返します。 値は次のいずれかになります。  
  
- OBJ_BITMAP ビットマップ  
  
- OBJ_BRUSH ブラシ  
  
- OBJ_FONT フォント  
  
- OBJ_PAL パレット  
  
- OBJ_PEN ペン  
  
- ペンの OBJ_EXTPEN 拡張  
  
- OBJ_REGION リージョン  
  
- OBJ_DC デバイス コンテキスト  
  
- OBJ_MEMDC メモリ デバイス コンテキスト  
  
- OBJ_METAFILE メタファイル  
  
- OBJ_METADC メタファイル デバイス コンテキスト  
  
- OBJ_ENHMETAFILE 拡張メタファイル  
  
- OBJ_ENHMETADC 拡張メタファイル デバイス コンテキスト  
  
##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle  
 返します`m_hObject`しない限り、**この**が null の場合、大文字と小文字の NULL が返されます。  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 接続されている Windows GDI オブジェクトを識別するハンドルオブジェクトがアタッチされていない場合は NULL それ以外の場合です。  
  
### <a name="remarks"></a>Remarks  
 一般的なハンドルのインターフェイスのパラダイムの一部でありこのハンドルが無効であるか、特殊な値は NULL は場合に便利です。  
  
### <a name="example"></a>例  
  例をご覧ください[CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled)します。  
  
##  <a name="m_hobject"></a>  CGdiObject::m_hObject  
 HBITMAP、HRGN、HBRUSH、HPEN、HPALETTE、または HFONT ハンドルは、このオブジェクトにアタッチします。  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>  CGdiObject::operator! =  
 2 つの GDI オブジェクトが等しく論理的にないかどうかを決定します。  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *obj*  
 既存へのポインター`CGdiObject`します。  
  
### <a name="remarks"></a>Remarks  
 左側にある GDI オブジェクトが右側にある GDI オブジェクトと等しくないかどうかを決定します。  
  
##  <a name="operator_eq_eq"></a>  CGdiObject::operator = =  
 2 つの GDI オブジェクトが論理的に等しいかどうかを決定します。  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *obj*  
 既存への参照を`CGdiObject`します。  
  
### <a name="remarks"></a>Remarks  
 左側にある GDI オブジェクトが右側にある、GDI オブジェクトと等しいかどうかを判断します。  
  
##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ  
 接続されている Windows GDI オブジェクトを識別するハンドルを取得します。オブジェクトがアタッチされていない場合は NULL それ以外の場合です。  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>  CGdiObject::UnrealizeObject  
 ブラシの原点にリセットまたは論理パレットをリセットします。  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 中に`UnrealizeObject`のメンバー関数は、`CGdiObject`クラス、それを呼び出すだけで`CBrush`または`CPalette`オブジェクト。  
  
 `CBrush`オブジェクト、`UnrealizeObject`は、デバイス コンテキストに選択されているときに、指定されたブラシの原点をリセットするようにします。 オブジェクトの場合、`CPalette`オブジェクト、`UnrealizeObject`いた、以前認識していない場合と同様に、パレットを実現するシステムに指示します。 呼び出して、次回、 [:realizepalette](../../mfc/reference/cdc-class.md#realizepalette)関数の指定のパレットでは、システムの場合は、システム パレットにある論理パレットを完全に再マップします。  
  
 `UnrealizeObject`ストック オブジェクトと関数を使用する必要があります。 `UnrealizeObject`新しいブラシの原点が設定されている場合、関数を呼び出す必要があります (によって、 [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg)関数)。 `UnrealizeObject`現在選択されているブラシまたはディスプレイ コンテキストの現在選択されているパレットの関数を呼び出すことがない必要があります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBitmap クラス](../../mfc/reference/cbitmap-class.md)   
 [CBrush クラス](../../mfc/reference/cbrush-class.md)   
 [CFont クラス](../../mfc/reference/cfont-class.md)   
 [CPalette クラス](../../mfc/reference/cpalette-class.md)   
 [CPen クラス](../../mfc/reference/cpen-class.md)   
 [CRgn クラス](../../mfc/reference/crgn-class.md)
