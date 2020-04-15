---
title: CStatic クラス
ms.date: 11/04/2016
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
ms.openlocfilehash: e5c3705c0aa2fd90e73cb54ba5a97c252ed2cf83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371643"
---
# <a name="cstatic-class"></a>CStatic クラス

Windows のスタティック コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CStatic : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cスタティック::CStatic](#cstatic)|`CStatic` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStatic::作成](#create)|Windows の静的コントロールを作成し、オブジェクトに`CStatic`アタッチします。|
|[::Dローアイテム](#drawitem)|オーナー描画の静的コントロールを描画する場合にオーバーライドします。|
|[次の値を取得します。](#getbitmap)|前に[SetBitmap](#setbitmap)で設定したビットマップのハンドルを取得します。|
|[次の項目を使用します。](#getcursor)|[SetCursor](#setcursor)で以前に設定したカーソル イメージのハンドルを取得します。|
|[CStatic::ゲテンメタファイル](#getenhmetafile)|以前に[SetEnhMetaFile](#setenhmetafile)で設定した拡張メタファイルのハンドルを取得します。|
|[CStatic::ゲットアイコン](#geticon)|前に[SetIcon](#seticon)で設定したアイコンのハンドルを取得します。|
|[CStatic::ビットマップを設定します。](#setbitmap)|静的コントロールに表示するビットマップを指定します。|
|[クスタティック::セットカーソル](#setcursor)|静的コントロールに表示するカーソル イメージを指定します。|
|[CStatic::セテンメタファイル](#setenhmetafile)|静的コントロールに表示する拡張メタファイルを指定します。|
|[CStatic::セットアイコン](#seticon)|静的コントロールに表示するアイコンを指定します。|

## <a name="remarks"></a>解説

静的コントロールは、テキスト文字列、ボックス、四角形、アイコン、カーソル、ビットマップ、または拡張メタファイルを表示します。 ラベル付け、ボックス、または他のコントロールを分離するために使用できます。 静的コントロールは通常入力を受け取らず、出力も提供しません。ただし、スタイルで作成されたマウスクリックの親SS_NOTIFY通知できます。

2 つの手順で静的コントロールを作成します。 まず、コンストラクターを呼び出して`CStatic`オブジェクトを構築し、次に[Create](#create)メンバー関数を呼び出して静的`CStatic`コントロールを作成し、オブジェクトにアタッチします。

ダイアログ ボックス内`CStatic`で (ダイアログ リソースを使用して) オブジェクト`CStatic`を作成すると、ユーザーがダイアログ ボックスを閉じると、オブジェクトは自動的に破棄されます。

ウィンドウ内にオブジェクト`CStatic`を作成する場合は、オブジェクトを破棄する必要もあります。 ウィンドウ`CStatic`内のスタック上に作成されたオブジェクトは自動的に破棄されます。 **新しい**関数を`CStatic`使用してヒープ上にオブジェクトを作成する場合は、オブジェクトの**delete**を呼び出して破棄する必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cstaticcreate"></a><a name="create"></a>CStatic::作成

Windows の静的コントロールを作成し、オブジェクトに`CStatic`アタッチします。

```
virtual BOOL Create(
    LPCTSTR lpszText,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID = 0xffff);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
コントロールに配置するテキストを指定します。 NULL の場合、テキストは表示されません。

*Dwstyle*<br/>
静的コントロールのウィンドウ スタイルを指定します。 [コントロールに静的コントロール スタイル](../../mfc/reference/styles-used-by-mfc.md#static-styles)の任意の組み合わせを適用します。

*Rect*<br/>
静的コントロールの位置とサイズを指定します。 `RECT`構造体または`CRect`オブジェクトのいずれかです。

*pParentWnd*<br/>
親ウィンドウ`CStatic`(通常はオブジェクト`CDialog`) を指定します。 NULL にすることはできません。

*nID*<br/>
静的コントロールのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

2`CStatic`つの手順でオブジェクトを作成します。 まず、コンストラクタ`CStatic`を呼び出し`Create`、次に呼び出し、 Windows 静的コントロール`CStatic`を作成してオブジェクトにアタッチします。

静的コントロールに次の[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を適用します。

- WS_CHILD常に

- WS_VISIBLE通常

- WS_DISABLEDまれ

静的コントロールでビットマップ、カーソル、アイコン、またはメタファイルを表示する場合は、次のいずれかの[静的スタイル](../../mfc/reference/styles-used-by-mfc.md#static-styles)を適用する必要があります。

- SS_BITMAP このスタイルはビットマップに使用します。

- SS_ICON このスタイルは、カーソルとアイコンに使用します。

- SS_ENHMETAFILE 拡張メタファイルにこのスタイルを使用します。

カーソル、ビットマップ、またはアイコンの場合は、次のスタイルを使用することもできます。

- SS_CENTERIMAGE 静止コントロール内のイメージを中央に配置するために使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

## <a name="cstaticcstatic"></a><a name="cstatic"></a>Cスタティック::CStatic

`CStatic` オブジェクトを構築します。

```
CStatic();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

## <a name="cstaticdrawitem"></a><a name="drawitem"></a>::Dローアイテム

オーナー描画の静的コントロールを描画するために、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
[構造体への](/windows/win32/api/winuser/ns-winuser-drawitemstruct)ポインター。 構造には、描画する項目と必要な図面のタイプに関する情報が含まれています。

### <a name="remarks"></a>解説

オーナー描画`CStatic`オブジェクト (コントロールのスタイルがSS_OWNERDRAW) の描画を実装するには、この関数をオーバーライドします。

## <a name="cstaticgetbitmap"></a><a name="getbitmap"></a>次の値を取得します。

に関連付けられている`CStatic`ビットマップのハンドルを[取得](#setbitmap)します。

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>戻り値

現在のビットマップへのハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

## <a name="cstaticgetcursor"></a><a name="getcursor"></a>次の項目を使用します。

に関連付けられている`CStatic`、以前に[SetCursor](#setcursor)で設定されたカーソルのハンドルを取得します。

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>戻り値

現在のカーソルへのハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

## <a name="cstaticgetenhmetafile"></a><a name="getenhmetafile"></a>CStatic::ゲテンメタファイル

に関連付けられている拡張メタファイルの[ハンドルを取得](#setenhmetafile)`CStatic`します。

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>戻り値

現在の拡張メタファイルへのハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

## <a name="cstaticgeticon"></a><a name="geticon"></a>CStatic::ゲットアイコン

に関連付けられている`CStatic`アイコンのハンドルを[取得](#seticon)します。

```
HICON GetIcon() const;
```

### <a name="return-value"></a>戻り値

現在のアイコンへのハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="cstaticsetbitmap"></a><a name="setbitmap"></a>CStatic::ビットマップを設定します。

新しいビットマップを静的コントロールに関連付けます。

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>パラメーター

*hビットマップ*<br/>
静的コントロールに描画されるビットマップのハンドル。

### <a name="return-value"></a>戻り値

以前に静的コントロールに関連付けられたビットマップのハンドル。

### <a name="remarks"></a>解説

ビットマップは、静的コントロールに自動的に描画されます。 既定では、左上隅に描画され、静的コントロールはビットマップのサイズにサイズ変更されます。

次のようなさまざまなウィンドウスタイルと静的コントロールスタイルを使用できます。

- SS_BITMAPこのスタイルは常にビットマップに使用します。

- SS_CENTERIMAGE 静止コントロール内のイメージを中央に配置するために使用します。 イメージが静的コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、イメージの周りの空の領域は、ビットマップの左上隅のピクセルの色で塗りつぶされます。

- MFC には、 `CBitmap`Win32 関数`LoadBitmap`を呼び出すだけでなく、ビットマップ イメージを使用する必要がある場合に使用できるクラスが用意されています。 `CBitmap`は、ある種類の GDI オブジェクトを含むが、グラフィック`CStatic`オブジェクトを`CWnd`静的コントロールとして表示するために使用されるクラスである との協力で使用されることが多い。

`CImage`は、デバイスに依存しないビットマップ (DIB) をより簡単に操作できる ATL/MFC クラスです。 詳細については[、「CImage クラス](../../atl-mfc-shared/reference/cimage-class.md)」を参照してください。

- 一般的な使用方法として`CStatic::SetBitmap`は、 または`CImage`オブジェクトの HBITMAP 演算子によって返`CBitmap`される GDI オブジェクトを指定します。 これを行うコードは、次の行のようになります。

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```

次の例では、`CStatic`ヒープに 2 つのオブジェクトを作成します。 次に、1 つを使用してシステム`CBitmap::LoadOEMBitmap`ビットマップを使用して読み`CImage::Load`込み、もう 1 つは を使用してファイルから読み込みます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

## <a name="cstaticsetcursor"></a><a name="setcursor"></a>クスタティック::セットカーソル

新しいカーソル イメージを静的コントロールに関連付けます。

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>パラメーター

*カーソル*<br/>
静的コントロールに描画されるカーソルのハンドル。

### <a name="return-value"></a>戻り値

静的コントロールに以前に関連付けられたカーソルのハンドル。

### <a name="remarks"></a>解説

カーソルは、静的コントロールに自動的に描画されます。 既定では、左上隅に描画され、静的コントロールはカーソルのサイズに合わせてサイズ変更されます。

次のようなさまざまなウィンドウスタイルと静的コントロールスタイルを使用できます。

- SS_ICON このスタイルは、常にカーソルとアイコンに使用します。

- SS_CENTERIMAGE 静的コントロールの中央に配置します。 イメージが静的コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、イメージの周囲の空の領域は、静的コントロールの背景色で塗りつぶされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

## <a name="cstaticsetenhmetafile"></a><a name="setenhmetafile"></a>CStatic::セテンメタファイル

新しい拡張メタファイル イメージを静的コントロールに関連付けます。

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>パラメーター

*ファイル*<br/>
静的コントロールに描画される拡張メタファイルのハンドル。

### <a name="return-value"></a>戻り値

以前に静的コントロールに関連付けられた拡張メタファイルのハンドル。

### <a name="remarks"></a>解説

拡張メタファイルは、静的コントロールに自動的に描画されます。 拡張メタファイルは、静的コントロールのサイズに合わせてスケーリングされます。

次のようなさまざまなウィンドウスタイルと静的コントロールスタイルを使用できます。

- SS_ENHMETAFILE このスタイルは、常に拡張メタファイルに使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

## <a name="cstaticseticon"></a><a name="seticon"></a>CStatic::セットアイコン

新しいアイコン イメージを静的コントロールに関連付けます。

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*Hicon*<br/>
静的コントロールに描画されるアイコンのハンドル。

### <a name="return-value"></a>戻り値

以前に静的コントロールに関連付けられたアイコンのハンドル。

### <a name="remarks"></a>解説

アイコンは、静的コントロールに自動的に描画されます。 既定では、左上隅に描画され、静的コントロールはアイコンのサイズにサイズ変更されます。

次のようなさまざまなウィンドウスタイルと静的コントロールスタイルを使用できます。

- SS_ICON このスタイルは、常にカーソルとアイコンに使用します。

- SS_CENTERIMAGE 静的コントロールの中央に配置します。 イメージが静的コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、イメージの周囲の空の領域は、静的コントロールの背景色で塗りつぶされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[Cコンボボックスクラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Class](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[クラス](../../mfc/reference/cdialog-class.md)
