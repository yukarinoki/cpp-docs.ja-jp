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
ms.openlocfilehash: fc0164b2d0046ca2d36291696dd6137a9fcef069
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447432"
---
# <a name="cstatic-class"></a>CStatic クラス

Windows のスタティック コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CStatic : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|説明|
|----------|-----------------|
|[CStatic::CStatic](#cstatic)|`CStatic` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|説明|
|----------|-----------------|
|[CStatic:: Create](#create)|Windows スタティックコントロールを作成し、`CStatic` オブジェクトにアタッチします。|
|[CStatic::D rawItem](#drawitem)|オーナー描画の静的コントロールを描画するには、をオーバーライドします。|
|[CStatic:: GetBitmap](#getbitmap)|以前に[SetBitmap](#setbitmap)で設定されたビットマップのハンドルを取得します。|
|[CStatic:: GetCursor](#getcursor)|以前に[SetCursor](#setcursor)で設定したカーソルイメージのハンドルを取得します。|
|[CStatic::GetEnhMetaFile](#getenhmetafile)|以前に[SetEnhMetaFile](#setenhmetafile)で設定された拡張メタファイルのハンドルを取得します。|
|[CStatic:: GetIcon](#geticon)|以前に[SetIcon](#seticon)で設定したアイコンのハンドルを取得します。|
|[CStatic::SetBitmap](#setbitmap)|スタティックコントロールに表示されるビットマップを指定します。|
|[CStatic::SetCursor](#setcursor)|静的コントロールに表示されるカーソルイメージを指定します。|
|[CStatic::SetEnhMetaFile](#setenhmetafile)|静的コントロールに表示される拡張メタファイルを指定します。|
|[CStatic::SetIcon](#seticon)|静的コントロールに表示するアイコンを指定します。|

## <a name="remarks"></a>コメント

静的コントロールは、テキスト文字列、ボックス、四角形、アイコン、カーソル、ビットマップ、または拡張メタファイルを表示します。 これは、他のコントロールのラベル付け、ボックス、または分離に使用できます。 静的コントロールは通常、入力を行わず、出力も行いません。ただし、SS_NOTIFY スタイルを使用して作成されている場合は、マウスクリックの親であることを通知できます。

静的コントロールを作成するには、次の2つの手順を実行します。 まず、コンストラクターを呼び出して `CStatic` オブジェクトを作成します。次に、 [create](#create) member 関数を呼び出して、静的コントロールを作成し、それを `CStatic` オブジェクトにアタッチします。

ダイアログボックス内で (ダイアログリソースを使用して) `CStatic` オブジェクトを作成すると、ユーザーがダイアログボックスを閉じたときに `CStatic` オブジェクトが自動的に破棄されます。

ウィンドウ内に `CStatic` オブジェクトを作成した場合は、それを破棄する必要がある場合もあります。 ウィンドウ内のスタック上に作成された `CStatic` オブジェクトは、自動的に破棄されます。 **新しい**関数を使用してヒープに `CStatic` オブジェクトを作成する場合は、オブジェクトに対して**delete**を呼び出して、そのオブジェクトが終了したときに破棄する必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[から派生しているのではない](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

##  <a name="create"></a>CStatic:: Create

Windows スタティックコントロールを作成し、`CStatic` オブジェクトにアタッチします。

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

*dwStyle*<br/>
静的コントロールのウィンドウスタイルを指定します。 コントロールに[静的コントロールスタイル](../../mfc/reference/styles-used-by-mfc.md#static-styles)の任意の組み合わせを適用します。

*rect*<br/>
静的コントロールの位置とサイズを指定します。 `RECT` 構造体または `CRect` オブジェクトを指定できます。

*pParentWnd*<br/>
`CStatic` 親ウィンドウ (通常は `CDialog` オブジェクト) を指定します。 NULL にすることはできません。

*nID*<br/>
スタティックコントロールのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>コメント

2つの手順で `CStatic` オブジェクトを構築します。 まず、コンストラクター `CStatic`を呼び出し、次に `Create`を呼び出します。これにより、Windows スタティックコントロールが作成され `CStatic` オブジェクトにアタッチされます。

次の[ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を静的コントロールに適用します。

- 常に WS_CHILD

- WS_VISIBLE 通常

- WS_DISABLED はまれ

静的コントロールにビットマップ、カーソル、アイコン、またはメタファイルを表示する場合は、次の[静的スタイル](../../mfc/reference/styles-used-by-mfc.md#static-styles)のいずれかを適用する必要があります。

- SS_BITMAP ビットマップにこのスタイルを使用します。

- SS_ICON カーソルとアイコンにこのスタイルを使用します。

- SS_ENHMETAFILE 拡張メタファイルにこのスタイルを使用します。

カーソル、ビットマップ、またはアイコンの場合は、次のスタイルを使用することもできます。

- SS_CENTERIMAGE 使用して、イメージをスタティックコントロールに中央揃えします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

##  <a name="cstatic"></a>CStatic::CStatic

`CStatic` オブジェクトを構築します。

```
CStatic();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

##  <a name="drawitem"></a>CStatic::D rawItem

オーナー描画の静的コントロールを描画するために、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
[DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct)構造体へのポインター。 構造体には、描画する項目と必要な描画の種類に関する情報が含まれます。

### <a name="remarks"></a>コメント

オーナー描画 `CStatic` オブジェクトの描画を実装するには、この関数をオーバーライドします (コントロールにはスタイル SS_OWNERDRAW があります)。

##  <a name="getbitmap"></a>CStatic:: GetBitmap

`CStatic`に関連付けられている、以前に[SetBitmap](#setbitmap)で設定されたビットマップのハンドルを取得します。

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>戻り値

現在のビットマップを処理するハンドル。ビットマップが設定されていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="getcursor"></a>CStatic:: GetCursor

`CStatic`に関連付けられている、以前に[SetCursor](#setcursor)が設定されていたカーソルのハンドルを取得します。

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>戻り値

現在のカーソルを処理するハンドル。カーソルが設定されていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="getenhmetafile"></a>CStatic::GetEnhMetaFile

`CStatic`に関連付けられている、以前に[SetEnhMetafile](#setenhmetafile)が設定されていた拡張メタファイルのハンドルを取得します。

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>戻り値

現在の拡張メタファイルへのハンドル。拡張メタファイルが設定されていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="geticon"></a>CStatic:: GetIcon

`CStatic`に関連付けられている、以前に[SetIcon](#seticon)で設定されたアイコンのハンドルを取得します。

```
HICON GetIcon() const;
```

### <a name="return-value"></a>戻り値

現在のアイコンを示すハンドル。アイコンが設定されていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

##  <a name="setbitmap"></a>CStatic::SetBitmap

新しいビットマップを静的コントロールに関連付けます。

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>パラメーター

*hBitmap*<br/>
静的コントロールに描画されるビットマップのハンドル。

### <a name="return-value"></a>戻り値

以前に静的コントロールに関連付けられていたビットマップのハンドル。静的コントロールに関連付けられているビットマップがない場合は NULL。

### <a name="remarks"></a>コメント

ビットマップは、自動的に静的コントロールに描画されます。 既定では、この値は左上隅に描画され、スタティックコントロールはビットマップのサイズにサイズ変更されます。

次のようなさまざまなウィンドウと静的コントロールスタイルを使用できます。

- このスタイルは、常にビットマップに使用 SS_BITMAP ます。

- SS_CENTERIMAGE 使用して、イメージをスタティックコントロールに中央揃えします。 イメージが静的コントロールより大きい場合は、クリップされます。 静的コントロールよりも小さい場合は、イメージの周囲の空白が、ビットマップの左上隅にあるピクセルの色によって塗りつぶされます。

- MFC には `CBitmap`クラスが用意されています。このクラスは、Win32 関数 `LoadBitmap`を呼び出すだけではなく、ビットマップイメージでさらに操作する必要がある場合に使用できます。 `CBitmap`には、1種類の GDI オブジェクトが含まれています。これは、`CStatic`と連携して使用されることがよくあります。これは、グラフィックオブジェクトを静的コントロールとして表示するために使用される `CWnd` クラスです。

`CImage` は、デバイスに依存しないビットマップ (DIB) をより簡単に操作できる ATL/MFC クラスです。 詳細については、「 [CImage クラス](../../atl-mfc-shared/reference/cimage-class.md)」を参照してください。

- 一般的な使用方法は、`CBitmap` または `CImage` オブジェクトの HBITMAP 演算子によって返される GDI オブジェクト `CStatic::SetBitmap` を与えることです。 これを行うコードは、次の行のようになります。

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```

次の例では、ヒープ上に2つの `CStatic` オブジェクトを作成します。 次に、`CImage::Load`を使用して、`CBitmap::LoadOEMBitmap` を使用し、もう1つをファイルから読み込んで、システムビットマップで読み込みます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="setcursor"></a>CStatic::SetCursor

新しいカーソルイメージを静的コントロールに関連付けます。

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>パラメーター

*hCursor*<br/>
静的コントロールに描画されるカーソルのハンドル。

### <a name="return-value"></a>戻り値

以前に静的コントロールに関連付けられたカーソルのハンドル。静的コントロールに関連付けられているカーソルがない場合は NULL。

### <a name="remarks"></a>コメント

カーソルは、自動的に静的コントロールに描画されます。 既定では、この値は左上隅に描画され、静的コントロールはカーソルのサイズに合わせてサイズが変更されます。

次のようなさまざまなウィンドウと静的コントロールスタイルを使用できます。

- カーソルとアイコンには、このスタイルを常に使用 SS_ICON ます。

- を静的コントロールの中央に配置するために使用 SS_CENTERIMAGE ます。 イメージが静的コントロールより大きい場合は、クリップされます。 静的コントロールより小さい場合は、イメージの周囲の空白が、静的コントロールの背景色で塗りつぶされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="setenhmetafile"></a>CStatic::SetEnhMetaFile

新しい拡張メタファイルイメージを静的コントロールに関連付けます。

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>パラメーター

*hMetaFile*<br/>
静的コントロールに描画される拡張メタファイルのハンドル。

### <a name="return-value"></a>戻り値

以前に静的コントロールに関連付けられていた拡張メタファイルのハンドル。または、拡張メタファイルが静的コントロールに関連付けられていない場合は NULL。

### <a name="remarks"></a>コメント

拡張メタファイルは、静的コントロールに自動的に描画されます。 拡張メタファイルは、静的コントロールのサイズに合わせてスケーリングされます。

次のようなさまざまなウィンドウと静的コントロールスタイルを使用できます。

- 拡張メタファイルには、このスタイルを常に使用 SS_ENHMETAFILE ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="seticon"></a>CStatic::SetIcon

新しいアイコンイメージを静的コントロールに関連付けます。

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*hIcon*<br/>
静的コントロールに描画されるアイコンのハンドル。

### <a name="return-value"></a>戻り値

以前に静的コントロールに関連付けられていたアイコンのハンドル。静的コントロールに関連付けられているアイコンがない場合は NULL。

### <a name="remarks"></a>コメント

アイコンは、静的コントロールに自動的に描画されます。 既定では、これは左上隅に描画され、静的コントロールはアイコンのサイズに合わせてサイズ変更されます。

次のようなさまざまなウィンドウと静的コントロールスタイルを使用できます。

- カーソルとアイコンには、このスタイルを常に使用 SS_ICON ます。

- を静的コントロールの中央に配置するために使用 SS_CENTERIMAGE ます。 イメージが静的コントロールより大きい場合は、クリップされます。 静的コントロールより小さい場合は、イメージの周囲の空白が、静的コントロールの背景色で塗りつぶされます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>参照

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)
