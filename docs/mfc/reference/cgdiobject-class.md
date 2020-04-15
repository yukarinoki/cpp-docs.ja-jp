---
title: CGdiObject クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 0cd7a0e0ed500ee9394b00e8906640e9f950163b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373732"
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
|[CGdi オブジェクト::CGdi オブジェクト](#cgdiobject)|`CGdiObject` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CGdi オブジェクト::アタッチ](#attach)|オブジェクトに Windows GDI オブジェクト`CGdiObject`をアタッチします。|
|[オブジェクトを作成します。](#createstockobject)|Windows の定義済みのストック ペン、ブラシ、またはフォントの 1 つを識別するハンドルを取得します。|
|[CGdiオブジェクト::Deleteオブジェクト](#deleteobject)|オブジェクトに関連付けられているすべてのシステム ストレージを`CGdiObject`解放することによって、オブジェクトにアタッチされている Windows GDI オブジェクトをメモリから削除します。|
|[CGdiオブジェクト::Dエレテテンプマップ](#deletetempmap)|によって`FromHandle`作成された一`CGdiObject`時オブジェクトを削除します。|
|[CGdiObject::Dエタッハ](#detach)|オブジェクトから Windows GDI オブジェクト`CGdiObject`をデタッチし、Windows GDI オブジェクトへのハンドルを返します。|
|[CGdi オブジェクト::ハンドルから](#fromhandle)|Windows GDI`CGdiObject`オブジェクトへのハンドルを指定したオブジェクトへのポインターを返します。|
|[オブジェクトを取得します。](#getobject)|オブジェクトにアタッチされた Windows GDI オブジェクトを記述するデータをバッファー`CGdiObject`に格納します。|
|[オブジェクトの種類](#getobjecttype)|GDI オブジェクトの型を取得します。|
|[CGdi オブジェクト::ゲットセーフハンドル](#getsafehandle)|NULL `m_hObject` **this**でない場合は NULL を返します。|
|[CGdiオブジェクト::実現していないオブジェクト](#unrealizeobject)|ブラシの原点をリセットするか、論理パレットをリセットします。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CGdi オブジェクト::演算子 !=](#operator_neq)|2 つの GDI オブジェクトが論理的に等しくないかどうかを判断します。|
|[CGdi オブジェクト::演算子 ==](#operator_eq_eq)|2 つの GDI オブジェクトが論理的に等しいかどうかを判断します。|
|[CGdi オブジェクト::オペレーター HGDIOBJ](#operator_hgdiobj)|アタッチされた Windows GDI オブジェクトのハンドルを取得します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CGdi オブジェクト::m_hObject](#m_hobject)|このオブジェクトにアタッチされた HBITMAP、HPALETTE、HRGN、HBRUSH、HPEN、または HFONT を含むハンドル。|

## <a name="remarks"></a>解説

`CGdiObject`直接作成することはありません。 代わりに、または などの`CPen`派生クラスの 1 つからオブジェクトを`CBrush`作成します。

の詳細については、「[グラフィック オブジェクト](../../mfc/graphic-objects.md)」を参照してください。 `CGdiObject`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CGdiObject`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cgdiobjectattach"></a><a name="attach"></a>CGdi オブジェクト::アタッチ

オブジェクトに Windows GDI オブジェクト`CGdiObject`をアタッチします。

```
BOOL Attach(HGDIOBJ hObject);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
Windows GDI オブジェクト (HPEN や HBRUSH など) へのハンドル。

### <a name="return-value"></a>戻り値

アタッチが成功した場合は 0 以外の値。それ以外の場合は 0。

## <a name="cgdiobjectcgdiobject"></a><a name="cgdiobject"></a>CGdi オブジェクト::CGdi オブジェクト

`CGdiObject` オブジェクトを構築します。

```
CGdiObject();
```

### <a name="remarks"></a>解説

`CGdiObject`直接作成することはありません。 代わりに、または などの`CPen`派生クラスの 1 つからオブジェクトを`Cbrush`作成します。

## <a name="cgdiobjectcreatestockobject"></a><a name="createstockobject"></a>オブジェクトを作成します。

定義済みのストック Windows GDI ペン、ブラシ、またはフォントの 1 つのハンドルを取得し、GDI オブジェクトをオブジェクトに`CGdiObject`アタッチします。

```
BOOL CreateStockObject(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
目的のストック オブジェクトの型を指定する定数。 適切な値の説明については、Windows SDK の[GetStockObject](/windows/win32/api/wingdi/nf-wingdi-getstockobject)のパラメーター *fnObject*を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ストック ペンなど`CPen`、Windows GDI オブジェクト型に対応する派生クラスのいずれかを使用して、この関数を呼び出します。

## <a name="cgdiobjectdeleteobject"></a><a name="deleteobject"></a>CGdiオブジェクト::Deleteオブジェクト

Windows GDI オブジェクトに関連付けられているすべてのシステム ストレージを解放することによって、アタッチされた Windows GDI オブジェクトをメモリから削除します。

```
BOOL DeleteObject();
```

### <a name="return-value"></a>戻り値

GDI オブジェクトが正常に削除された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

オブジェクトに`CGdiObject`関連付けられたストレージは、この呼び出しの影響を受けません。 アプリケーションは、デバイス`DeleteObject`コンテキストに`CGdiObject`現在選択されているオブジェクトを呼び出す必要があります。

パターン ブラシを削除しても、ブラシに関連付けられたビットマップは削除されません。 ビットマップは個別に削除する必要があります。

## <a name="cgdiobjectdeletetempmap"></a><a name="deletetempmap"></a>CGdiオブジェクト::Dエレテテンプマップ

`CWinApp`アイドル時ハンドラによって自動的に呼び出`DeleteTempMap`され、によって`FromHandle`作成`CGdiObject`された一時オブジェクトを削除します。

```
static void PASCAL DeleteTempMap();
```

### <a name="remarks"></a>解説

`DeleteTempMap`オブジェクトを削除する前に、一時`CGdiObject`オブジェクトにアタッチされた Windows `CGdiObject` GDI オブジェクトをデタッチします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#175](../../mfc/codesnippet/cpp/cgdiobject-class_1.cpp)]

## <a name="cgdiobjectdetach"></a><a name="detach"></a>CGdiObject::Dエタッハ

オブジェクトから Windows GDI オブジェクト`CGdiObject`をデタッチし、Windows GDI オブジェクトへのハンドルを返します。

```
HGDIOBJ Detach();
```

### <a name="return-value"></a>戻り値

デ`HANDLE`タッチされた Windows GDI オブジェクトへの A。それ以外の場合は NULL、GDI オブジェクトがアタッチされていません。

## <a name="cgdiobjectfromhandle"></a><a name="fromhandle"></a>CGdi オブジェクト::ハンドルから

Windows GDI`CGdiObject`オブジェクトへのハンドルを指定したオブジェクトへのポインターを返します。

```
static CGdiObject* PASCAL FromHandle(HGDIOBJ hObject);
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
Windows GDI オブジェクトへのハンドル。

### <a name="return-value"></a>戻り値

一時的または永続的`CGdiObject`なを指すポインター。

### <a name="remarks"></a>解説

`CGdiObject`オブジェクトが Windows GDI オブジェクトにまだアタッチされていない場合は、`CGdiObject`一時オブジェクトが作成され、アタッチされます。

この一`CGdiObject`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効で、その時点ですべての一時グラフィック オブジェクトが削除されます。 もう 1 つの言い方は、一時オブジェクトが 1 つのウィンドウ メッセージの処理中にのみ有効であるというものです。

## <a name="cgdiobjectgetobject"></a><a name="getobject"></a>オブジェクトを取得します。

指定したオブジェクトを定義するデータをバッファーに格納します。

```
int GetObject(
    int nCount,
    LPVOID lpObject) const;
```

### <a name="parameters"></a>パラメーター

*nカウント*<br/>
*lpObject*バッファにコピーするバイト数を指定します。

*オブジェクトを指定します。*<br/>
情報を受け取るユーザーが指定したバッファーへのポイント。

### <a name="return-value"></a>戻り値

取得されたバイト数。エラーが発生した場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は、次のリストに示すように、グラフィックオブジェクトのタイプに依存するデータ構造を取得します。

|Object|バッファタイプ|
|------------|-----------------|
|`CPen`|[ログペン](/windows/win32/api/Wingdi/ns-wingdi-logpen)|
|`CBrush`|[Logbrush](/windows/win32/api/wingdi/ns-wingdi-logbrush)|
|`CFont`|[Logfont](/windows/win32/api/wingdi/ns-wingdi-logfontw)|
|`CBitmap`|[ビットマップ](/windows/win32/api/wingdi/ns-wingdi-bitmap)|
|`CPalette`|WORD|
|`CRgn`|サポートされていません|

オブジェクトがオブジェクトの`CBitmap`場合は、`GetObject`ビットマップの幅、高さ、および色の書式情報のみを返します。 実際のビットは[、CBitmap::GetBitmapBits](../../mfc/reference/cbitmap-class.md#getbitmapbits)を使用して取得できます。

オブジェクトがオブジェクトの`CPalette`場合は、`GetObject`パレット内のエントリ数を指定する WORD を取得します。 この関数は、パレットを定義する[LOGPALETTE](/windows/win32/api/wingdi/ns-wingdi-logpalette)構造体を取得しません。 アプリケーションは[、CPalette::GetPaletteEntries](../../mfc/reference/cpalette-class.md#getpaletteentries)を呼び出すことによって、パレット エントリに関する情報を取得できます。

## <a name="cgdiobjectgetobjecttype"></a><a name="getobjecttype"></a>オブジェクトの種類

GDI オブジェクトの型を取得します。

```
UINT GetObjectType() const;
```

### <a name="return-value"></a>戻り値

成功した場合はオブジェクトの型。それ以外の場合は 0。 値は次のいずれかになります。

- OBJ_BITMAPビットマップ

- OBJ_BRUSHブラシ

- フォントOBJ_FONT

- OBJ_PALパレット

- OBJ_PENペン

- OBJ_EXTPEN拡張ペン

- OBJ_REGION地域

- OBJ_DCデバイス コンテキスト

- OBJ_MEMDC メモリ デバイス コンテキスト

- OBJ_METAFILEメタファイル

- OBJ_METADC メタファイル デバイス コンテキスト

- 拡張メタファイルOBJ_ENHMETAFILE

- OBJ_ENHMETADC拡張メタファイル デバイス コンテキスト

## <a name="cgdiobjectgetsafehandle"></a><a name="getsafehandle"></a>CGdi オブジェクト::ゲットセーフハンドル

NULL `m_hObject` **this**でない場合は NULL を返します。

```
HGDIOBJ GetSafeHandle() const;
```

### <a name="return-value"></a>戻り値

アタッチされた Windows GDI オブジェクトへのハンドル。オブジェクトがアタッチされていない場合は NULL。

### <a name="remarks"></a>解説

これは、汎用のハンドル インターフェイス パラダイムの一部であり、NULL がハンドルの有効な値または特殊な値である場合に便利です。

### <a name="example"></a>例

  [「CWnd::IsWindowEnabled」](../../mfc/reference/cwnd-class.md#iswindowenabled)の例を参照してください。

## <a name="cgdiobjectm_hobject"></a><a name="m_hobject"></a>CGdi オブジェクト::m_hObject

このオブジェクトにアタッチされた HBITMAP、HRGN、HBRUSH、HPEN、HPALETTE、または HFONT を含むハンドル。

```
HGDIOBJ m_hObject;
```

## <a name="cgdiobjectoperator-"></a><a name="operator_neq"></a>CGdi オブジェクト::演算子 !=

2 つの GDI オブジェクトが論理的に等しくないかどうかを判断します。

```
BOOL operator!=(const CGdiObject& obj) const;
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
既存`CGdiObject`の .

### <a name="remarks"></a>解説

左側の GDI オブジェクトが右側の GDI オブジェクトと等しくないかどうかを判断します。

## <a name="cgdiobjectoperator-"></a><a name="operator_eq_eq"></a>CGdi オブジェクト::演算子 ==

2 つの GDI オブジェクトが論理的に等しいかどうかを判断します。

```
BOOL operator==(const CGdiObject& obj) const;
```

### <a name="parameters"></a>パラメーター

*obj*<br/>
既存`CGdiObject`の .

### <a name="remarks"></a>解説

左側の GDI オブジェクトが右側の GDI オブジェクトと等しいかどうかを判断します。

## <a name="cgdiobjectoperator-hgdiobj"></a><a name="operator_hgdiobj"></a>CGdi オブジェクト::オペレーター HGDIOBJ

アタッチされた Windows GDI オブジェクトのハンドルを取得します。オブジェクトがアタッチされていない場合は NULL。

```
operator HGDIOBJ() const;
```

## <a name="cgdiobjectunrealizeobject"></a><a name="unrealizeobject"></a>CGdiオブジェクト::実現していないオブジェクト

ブラシの原点をリセットするか、論理パレットをリセットします。

```
BOOL UnrealizeObject();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

クラスのメンバー関数である間`UnrealizeObject`は、`CBrush`または`CPalette`オブジェクトでのみ呼び出す必要があります。 `CGdiObject`

オブジェクト`CBrush`の場合`UnrealizeObject`、次に選択したブラシがデバイス コンテキストにリセットされるブラシの原点をリセットするようにシステムに指示します。 オブジェクトがオブジェクトの`CPalette`場合、`UnrealizeObject`パレットが実現されていないかのように、システムにパレットを実現させます。 アプリケーションが次に指定されたパレットの[CDC::RealizePalette](../../mfc/reference/cdc-class.md#realizepalette)関数を呼び出す時、システムは論理パレットをシステム パレットに完全に再マップします。

この`UnrealizeObject`関数は、ストックオブジェクトと一緒に使用しないでください。 新`UnrealizeObject`しいブラシの原点が設定されるたびに、この関数を呼び出す必要があります[(CDC::SetBrushOrg](../../mfc/reference/cdc-class.md#setbrushorg)関数を使用)。 現在`UnrealizeObject`選択されているブラシまたは表示コンテキストの現在選択されているパレットに対して、この関数を呼び出してはなりません。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cbitmap-class.md)<br/>
[CBrush クラス](../../mfc/reference/cbrush-class.md)<br/>
[Cフォントクラス](../../mfc/reference/cfont-class.md)<br/>
[Cパレットクラス](../../mfc/reference/cpalette-class.md)<br/>
[Cペンクラス](../../mfc/reference/cpen-class.md)<br/>
[CRgn クラス](../../mfc/reference/crgn-class.md)
