---
title: CGdiObject クラス |Microsoft ドキュメント
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
ms.openlocfilehash: ba88269cf37f41cf8a594745eb2e98a57ccf64ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CGdiObject::CreateStockObject](#createstockobject)|Windows 定義済みのストック ペン、ブラシ、フォントのいずれかへのハンドルを取得します。|  
|[CGdiObject::DeleteObject](#deleteobject)|接続されている Windows GDI オブジェクトの削除、`CGdiObject`オブジェクトに関連付けられているすべてのシステムの記憶域を解放することによって、メモリからのオブジェクト。|  
|[CGdiObject::DeleteTempMap](#deletetempmap)|一時的な削除`CGdiObject`によって作成されたオブジェクト`FromHandle`です。|  
|[CGdiObject::Detach](#detach)|Windows GDI オブジェクトからのデタッチ、`CGdiObject`オブジェクトおよびハンドル Windows GDI オブジェクトを返します。|  
|[CGdiObject::FromHandle](#fromhandle)|ポインターを返します、 `CGdiObject` Windows GDI オブジェクトへのハンドルを指定されたオブジェクト。|  
|[CGdiObject::GetObject](#getobject)|接続されている Windows GDI オブジェクトを説明するデータを含むバッファーがいっぱいになった、`CGdiObject`オブジェクト。|  
|[CGdiObject::GetObjectType](#getobjecttype)|GDI オブジェクトの種類を取得します。|  
|[CGdiObject::GetSafeHandle](#getsafehandle)|返します`m_hObject`しない限り、`this`は`NULL`、後者`NULL`が返されます。|  
|[CGdiObject::UnrealizeObject](#unrealizeobject)|ブラシの原点のリセット、または論理パレットがリセットされます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::operator! =](#operator_neq)|2 つの GDI オブジェクトが等しく論理的にないかどうかを判断します。|  
|[CGdiObject::operator = =](#operator_eq_eq)|2 つの GDI オブジェクトが論理的に等しいかどうかを判断します。|  
|[CGdiObject::operator HGDIOBJ](#operator_hgdiobj)|取得、`HANDLE`アタッチされた Windows GDI オブジェクトにします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CGdiObject::m_hObject](#m_hobject)|A`HANDLE`を含む、 `HBITMAP`、 `HPALETTE`、 `HRGN`、 `HBRUSH`、 `HPEN`、または`HFONT`このオブジェクトにアタッチします。|  
  
## <a name="remarks"></a>コメント  
 作成することはありません、`CGdiObject`直接です。 代わりに、オブジェクトを作成するその派生クラスのいずれかのように`CPen`または`CBrush`です。  
  
 詳細については`CGdiObject`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)です。  
  
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
 `hObject`  
 A `HANDLE` Windows GDI オブジェクト (たとえば、`HPEN`または`HBRUSH`)。  
  
### <a name="return-value"></a>戻り値  
 添付ファイルが正常に終了した場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="cgdiobject"></a>  CGdiObject::CGdiObject  
 `CGdiObject` オブジェクトを構築します。  
  
```  
CGdiObject();
```  
  
### <a name="remarks"></a>コメント  
 作成することはありません、`CGdiObject`直接です。 代わりに、オブジェクトを作成するその派生クラスのいずれかのように`CPen`または**Cbrush**です。  
  
##  <a name="createstockobject"></a>  CGdiObject::CreateStockObject  
 定義済みのストック Windows GDI ペン、ブラシ、フォントのいずれかへのハンドルを取得しに GDI オブジェクトをアタッチ、`CGdiObject`オブジェクト。  
  
```  
BOOL CreateStockObject(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 目的のストック オブジェクトの種類を指定する定数。 パラメーターを参照*fnObject*の[GetStockObject](http://msdn.microsoft.com/library/windows/desktop/dd144925)適切な値の詳細については、Windows SDK でします。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 クラスの派生クラスのいずれかでこの関数の呼び出しなどの Windows GDI オブジェクトの種類に対応`CPen`ストック ペン用です。  
  
##  <a name="deleteobject"></a>  CGdiObject::DeleteObject  
 Windows GDI オブジェクトに関連付けられているすべてのシステムの記憶域を解放することで、メモリから、アタッチされた Windows GDI オブジェクトを削除します。  
  
```  
BOOL DeleteObject();
```  
  
### <a name="return-value"></a>戻り値  
 GDI オブジェクトが正常に削除された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関連付けられている記憶域、`CGdiObject`オブジェクトがこの呼び出しによって影響ありません。 アプリケーションを呼び出す必要がありますいない`DeleteObject`上、`CGdiObject`デバイス コンテキストに現在選択されているオブジェクト。  
  
 ブラシ パターンが削除されると、ブラシに関連付けられたビットマップは削除されません。 ビットマップは個別に削除する必要があります。  
  
##  <a name="deletetempmap"></a>  CGdiObject::DeleteTempMap  
 によって自動的に呼び出されます、`CWinApp`アイドル処理ハンドラー`DeleteTempMap`一時的な削除`CGdiObject`によって作成されたオブジェクト`FromHandle`です。  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>コメント  
 `DeleteTempMap` 一時的に接続されている Windows GDI オブジェクトをデタッチ`CGdiObject`オブジェクトを削除する前に、`CGdiObject`オブジェクト。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]  
  
##  <a name="detach"></a>  CGdiObject::Detach  
 Windows GDI オブジェクトからのデタッチ、`CGdiObject`オブジェクトおよびハンドル Windows GDI オブジェクトを返します。  
  
```  
HGDIOBJ Detach();
```  
  
### <a name="return-value"></a>戻り値  
 A`HANDLE`オブジェクト デタッチ; それ以外の場合に、Windows GDI **NULL** GDI オブジェクトがアタッチされていない場合。  
  
##  <a name="fromhandle"></a>  CGdiObject::FromHandle  
 ポインターを返します、 `CGdiObject` Windows GDI オブジェクトへのハンドルを指定されたオブジェクト。  
  
```  
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 A `HANDLE` Windows GDI オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CGdiObject`一時的または永続する可能性があります。  
  
### <a name="remarks"></a>コメント  
 場合、`CGdiObject`オブジェクトが、一時的な Windows GDI オブジェクトに既にアタッチされていない`CGdiObject`オブジェクトが作成され、接続されています。  
  
 この一時`CGdiObject`オブジェクトは、次のアプリケーションが、すべての一時的なグラフィック オブジェクトの削除時に、イベント ループのアイドル時間までのみ有効です。 言い換えると、別の方法は、1 つのウィンドウ メッセージを処理中に、一時オブジェクトが有効でのみことです。  
  
##  <a name="getobject"></a>  CGdiObject::GetObject  
 指定したオブジェクトを定義するデータをバッファーします。  
  
```  
int GetObject(
    int nCount,  
    LPVOID lpObject) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nCount`  
 コピーするバイト数を指定、`lpObject`バッファー。  
  
 `lpObject`  
 情報を受信するユーザーが指定したバッファーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 バイト数を取得します。それ以外の場合 0 の場合、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
 関数は、次の一覧に示すように、型を持つが、グラフィック オブジェクトの種類に依存するデータ構造体を取得します。  
  
|Object|バッファーの種類|  
|------------|-----------------|  
|`CPen`|[LOGPEN](../../mfc/reference/logpen-structure.md)|  
|`CBrush`|[LOGBRUSH](../../mfc/reference/logbrush-structure.md)|  
|`CFont`|[LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037)|  
|`CBitmap`|[ビットマップ](../../mfc/reference/bitmap-structure.md)|  
|`CPalette`|**WORD**|  
|`CRgn`|サポートなし|  
  
 オブジェクトがある場合、`CBitmap`オブジェクト、`GetObject`幅、高さ、およびビットマップの色の書式情報のみを返します。 実際のビットを使用して取得できる[列](../../mfc/reference/cbitmap-class.md#getbitmapbits)です。  
  
 オブジェクトがある場合、`CPalette`オブジェクト、`GetObject`取得、 **WORD**パレット内のエントリの数を指定します。 関数を取得することはありません、[保持](http://msdn.microsoft.com/library/windows/desktop/dd145040)パレットを定義する構造体。 アプリケーションが呼び出すことによってパレット エントリに関する情報を取得できます[CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries)です。  
  
##  <a name="getobjecttype"></a>  CGdiObject::GetObjectType  
 GDI オブジェクトの種類を取得します。  
  
```  
UINT GetObjectType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は、オブジェクトの種類それ以外の場合 0 を返します。 値は次のいずれかになります。  
  
- **OBJ_BITMAP**ビットマップ  
  
- **OBJ_BRUSH**ブラシ  
  
- **OBJ_FONT**フォント  
  
- **OBJ_PAL**パレット  
  
- **OBJ_PEN**ペン  
  
- **OBJ_EXTPEN**拡張ペン  
  
- **OBJ_REGION**地域  
  
- **OBJ_DC**デバイス コンテキスト  
  
- **OBJ_MEMDC**メモリ デバイス コンテキスト  
  
- **OBJ_METAFILE**メタファイル  
  
- **OBJ_METADC**メタファイル デバイス コンテキスト  
  
- **OBJ_ENHMETAFILE**拡張メタファイル  
  
- **OBJ_ENHMETADC**拡張メタファイル デバイス コンテキスト  
  
##  <a name="getsafehandle"></a>  CGdiObject::GetSafeHandle  
 返します`m_hObject`しない限り、**この**は**NULL**、後者**NULL**が返されます。  
  
```  
HGDIOBJ GetSafeHandle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A`HANDLE`にアタッチされた Windows GDI オブジェクトです。 それ以外の場合**NULL**オブジェクトがアタッチされていない場合。  
  
### <a name="remarks"></a>コメント  
 一般的なハンドル インターフェイスのパラダイムの一部であり、 **NULL**ハンドルが無効であるか特殊な値です。  
  
### <a name="example"></a>例  
  例を参照して[CWnd::IsWindowEnabled](../../mfc/reference/cwnd-class.md#iswindowenabled)です。  
  
##  <a name="m_hobject"></a>  CGdiObject::m_hObject  
 A`HANDLE`を含む、 `HBITMAP`、 **HRGN**、 `HBRUSH`、 `HPEN`、 `HPALETTE`、または**HFONT**このオブジェクトにアタッチします。  
  
```  
HGDIOBJ m_hObject;  
```  
  
##  <a name="operator_neq"></a>  CGdiObject::operator! =  
 2 つの GDI オブジェクトが等しく論理的にないかどうかを判断します。  
  
```  
BOOL operator!=(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `obj`  
 既存へのポインター`CGdiObject`です。  
  
### <a name="remarks"></a>コメント  
 左側の GDI オブジェクトが右側の GDI オブジェクトと等しくないかどうかを判断します。  
  
##  <a name="operator_eq_eq"></a>  CGdiObject::operator = =  
 2 つの GDI オブジェクトが論理的に等しいかどうかを判断します。  
  
```  
BOOL operator==(const CGdiObject& obj) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `obj`  
 既存への参照を`CGdiObject`です。  
  
### <a name="remarks"></a>コメント  
 左側の GDI オブジェクトが右側の GDI オブジェクトと等しいかどうかを判断します。  
  
##  <a name="operator_hgdiobj"></a>  CGdiObject::operator HGDIOBJ  
 取得、`HANDLE`にアタッチされた Windows GDI オブジェクトです。 それ以外の場合**NULL**オブジェクトがアタッチされていない場合。  
  
```  
operator HGDIOBJ() const;  
```  
  
##  <a name="unrealizeobject"></a>  CGdiObject::UnrealizeObject  
 ブラシの原点のリセット、または論理パレットがリセットされます。  
  
```  
BOOL UnrealizeObject();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 中に`UnrealizeObject`のメンバー関数は、`CGdiObject`クラス、それを呼び出す上でのみ`CBrush`または`CPalette`オブジェクト。  
  
 `CBrush`オブジェクト、`UnrealizeObject`次回デバイス コンテキストに選択されている指定されたブラシの原点をリセットするシステムに指示します。 オブジェクトがある場合、`CPalette`オブジェクト、`UnrealizeObject`が、既に認識していない場合と同様に、パレットを実現するシステムに指示します。 次に、アプリケーションが呼び出すとき、 [:realizepalette](../../mfc/reference/cdc-class.md#realizepalette)指定のパレットでは、システム関数では、論理パレット システム パレットを完全に再マップします。  
  
 `UnrealizeObject`関数はストック オブジェクトを使用する必要があります。 `UnrealizeObject`新しいブラシの原点が設定されているときに、関数を呼び出す必要があります (により、 [CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg)関数)。 `UnrealizeObject`現在選択されているブラシまたはディスプレイ コンテキストの現在選択されているパレットの関数を呼び出すことがない必要があります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBitmap クラス](../../mfc/reference/cbitmap-class.md)   
 [CBrush クラス](../../mfc/reference/cbrush-class.md)   
 [CFont クラス](../../mfc/reference/cfont-class.md)   
 [CPalette クラス](../../mfc/reference/cpalette-class.md)   
 [CPen クラス](../../mfc/reference/cpen-class.md)   
 [CRgn クラス](../../mfc/reference/crgn-class.md)
