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
ms.openlocfilehash: 622172d369818a7a503945bcd3cf064662f38266
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576710"
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
|[CStatic::CStatic](#cstatic)|`CStatic` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStatic::Create](#create)|Windows の静的コントロールを作成し、それにアタッチします、`CStatic`オブジェクト。|
|[CStatic::DrawItem](#drawitem)|オーナー描画スタティック コントロールを描画するためにオーバーライドします。|
|[CStatic::GetBitmap](#getbitmap)|以前のビットマップのハンドルを取得[SetBitmap](#setbitmap)します。|
|[CStatic::GetCursor](#getcursor)|カーソルのイメージのハンドルが以前に設定と取得[以前](#setcursor)します。|
|[CStatic::GetEnhMetaFile](#getenhmetafile)|以前拡張メタファイルのハンドルを取得[SetEnhMetaFile](#setenhmetafile)します。|
|[CStatic::GetIcon](#geticon)|以前の設定アイコンのハンドルを取得[SetIcon](#seticon)します。|
|[CStatic::SetBitmap](#setbitmap)|スタティック コントロールに表示されるビットマップを指定します。|
|[CStatic::SetCursor](#setcursor)|スタティック コントロールに表示されるカーソルのイメージを指定します。|
|[CStatic::SetEnhMetaFile](#setenhmetafile)|スタティック コントロールに表示される拡張メタファイルを指定します。|
|[CStatic::SetIcon](#seticon)|スタティック コントロールに表示されるアイコンを指定します。|

## <a name="remarks"></a>Remarks

静的コントロールでは、テキスト文字列、ボックス、四角形、アイコン、カーソル、ビットマップ、または拡張メタファイルが表示されます。 これは、ラベル付け、ボックス、またはその他のコントロールを個別に使用できます。 スタティック コントロールは通常の入力を受け取らないし、用意されていません。ただし、マウス クリックの親に通知 SS_NOTIFY スタイルで作成されて場合ことができます。

2 つの手順では、スタティック コントロールを作成します。 最初に、構築するコンス トラクターを呼び出し、`CStatic`オブジェクトを呼び出して、[作成](#create)メンバー関数は、静的コントロールを作成し、アタッチ先、`CStatic`オブジェクト。

作成する場合、 `CStatic` (ダイアログ リソースの場合) を使ってダイアログ ボックス内のオブジェクト、 `CStatic`  ダイアログ ボックスを閉じると、オブジェクトが自動的に破棄されます。

作成する場合、`CStatic`を破棄する必要がありますも、ウィンドウ内でオブジェクトします。 A`CStatic`ウィンドウ内のスタック上に作成されたオブジェクトが自動的に破棄されます。 作成する場合、`CStatic`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を終了するときに破棄するオブジェクト。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="create"></a>  CStatic::Create

Windows の静的コントロールを作成し、それにアタッチします、`CStatic`オブジェクト。

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
コントロール内に配置するテキストを指定します。 NULL の場合、テキストは表示されません。

*dwStyle*<br/>
静的コントロールのウィンドウ スタイルを指定します。 任意の組み合わせを適用[静的コントロール スタイル](../../mfc/reference/styles-used-by-mfc.md#static-styles)コントロールにします。

*rect*<br/>
スタティック コントロールのサイズと位置を指定します。 いずれかのことができます、`RECT`構造または`CRect`オブジェクト。

*pParentWnd*<br/>
指定します、`CStatic`通常親ウィンドウを`CDialog`オブジェクト。 NULL は指定できません。

*nID*<br/>
静的コントロールのコントロール ID を指定します

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築、 `CStatic` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出す`CStatic`を呼び出して`Create`、Windows の静的コントロールを作成しにアタッチする`CStatic`オブジェクト。

次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)静的コントロールに。

- WS_CHILD 常に

- WS_VISIBLE 通常

- WS_DISABLED ことはほとんどありません。

静的コントロールで、ビットマップ、カーソル、アイコン、またはメタファイルを表示しようとしている場合は、次のいずれかを適用する必要があります[静的コントロール スタイル](../../mfc/reference/styles-used-by-mfc.md#static-styles):

- SS_BITMAP は、ビットマップにこのスタイルを使用します。

- SS_ICON は、カーソル、アイコン、このスタイルを使用します。

- SS_ENHMETAFILE は、拡張メタファイルにこのスタイルを使用します。

カーソル、ビットマップ、またはアイコンは、次のスタイルを使用することがありますも。

- 静的コントロールでイメージの中央に SS_CENTERIMAGE を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

##  <a name="cstatic"></a>  CStatic::CStatic

`CStatic` オブジェクトを構築します。

```
CStatic();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

##  <a name="drawitem"></a>  CStatic::DrawItem

オーナー描画スタティック コントロールを描画するためにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
ポインターを[DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)構造体。 構造体には、描画される項目および必要な図面の種類に関する情報が含まれています。

### <a name="remarks"></a>Remarks

オーナー描画の描画を実装するには、この関数をオーバーライド`CStatic`(コントロールにスタイル SS_OWNERDRAW) オブジェクト。

##  <a name="getbitmap"></a>  CStatic::GetBitmap

以前、ビットマップのハンドルを取得[SetBitmap](#setbitmap)、つまりに関連付けられている`CStatic`します。

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>戻り値

現在のビットマップまたはビットマップが設定されていない場合は NULL へのハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="getcursor"></a>  CStatic::GetCursor

以前、カーソルのハンドルを取得[以前](#setcursor)、つまりに関連付けられている`CStatic`します。

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>戻り値

現在のカーソルまたはカーソルが設定されていない場合は NULL へのハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile

以前は、拡張メタファイルのハンドルを取得[SetEnhMetafile](#setenhmetafile)、つまりに関連付けられている`CStatic`します。

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>戻り値

現在、拡張メタファイルまたは拡張メタファイルが設定されていない場合は NULL へのハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="geticon"></a>  CStatic::GetIcon

以前、アイコンのハンドルを取得[SetIcon](#seticon)、つまりに関連付けられている`CStatic`します。

```
HICON GetIcon() const;
```

### <a name="return-value"></a>戻り値

現在のアイコン、またはアイコンが設定されていない場合は NULL へのハンドル。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

##  <a name="setbitmap"></a>  CStatic::SetBitmap

新しいビットマップをスタティック コントロールに関連付けます。

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>パラメーター

*hBitmap*<br/>
静的コントロールで描画されるビットマップのハンドル。

### <a name="return-value"></a>戻り値

静的コントロールに関連付けられたビットマップがない場合に、静的コントロール、または NULL に以前関連付けられていたビットマップ ハンドル。

### <a name="remarks"></a>Remarks

ビットマップは、静的コントロールで自動的に描画されます。 既定が左上隅に描画され、スタティック コントロールは、ビットマップのサイズにサイズ変更されます。

さまざまなウィンドウや静的コントロール スタイル、次のようを使用することができます。

- SS_BITMAP は、ビットマップを常にこのスタイルを使用します。

- 静的コントロールでイメージの中央に SS_CENTERIMAGE を使用します。 イメージが静的コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、ビットマップの左上隅にあるピクセルの色によってイメージの周囲の空白部分が入力します。

- MFC クラスを提供します。 `CBitmap`、はより呼び出すだけで、Win32 のビットマップ イメージで機能する必要があるときに使用できる`LoadBitmap`します。 `CBitmap`、連携でよく使用されて、GDI オブジェクトの 1 つの種類が含まれています`CStatic`、これは、`CWnd`グラフィック オブジェクトを静的なコントロールとして表示するために使用されるクラスです。

`CImage` ATL と MFC クラス デバイス独立ビットマップ (DIB) を簡単に操作することができます。 詳細については、次を参照してください。 [CImage クラス](../../atl-mfc-shared/reference/cimage-class.md)します。

- 一般的な使用方法は、提示する`CStatic::SetBitmap`の HBITMAP 演算子によって返される GDI オブジェクトを`CBitmap`または`CImage`オブジェクト。 これを行うコードでは、次の行に似ています。

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```
次の例では、2 つ作成されます`CStatic`ヒープのオブジェクト。 使用してシステムのビットマップを次に、`CBitmap::LoadOEMBitmap`およびその他を使用してファイルから`CImage::Load`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="setcursor"></a>  CStatic::SetCursor

新しいカーソル イメージをスタティック コントロールに関連付けます。

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>パラメーター

*hCursor*<br/>
静的コントロールを描画するカーソルのハンドル。

### <a name="return-value"></a>戻り値

静的コントロールに関連付けられたカーソルがない場合の静的コントロール、または NULL に以前関連付けられているカーソルのハンドル。

### <a name="remarks"></a>Remarks

カーソルは静的コントロールで自動的に描画されます。 既定が左上隅に描画され、スタティック コントロールは、カーソルのサイズに変更されます。

さまざまなウィンドウと、次の静的コントロール スタイルを使用することができます。

- SS_ICON はカーソル、アイコン、常にこのスタイルを使用します。

- スタティック コントロールの中央に SS_CENTERIMAGE を使用します。 イメージが静的コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、イメージの周囲の空の領域は静的コントロールの背景色で入力します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile

静的コントロールで新しい拡張メタファイル イメージに関連付けます。

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>パラメーター

*hMetaFile*<br/>
静的コントロールを描画するメタファイルのハンドル。

### <a name="return-value"></a>戻り値

関連付けられていた静的コントロール、または NULL 拡張メタファイルが静的なコントロールに関連付けられていない場合、拡張メタファイルのハンドル。

### <a name="remarks"></a>Remarks

拡張メタファイルは、静的コントロールで自動的に描画されます。 拡張メタファイルは、静的コントロールのサイズに合わせてスケーリングされます。

さまざまなウィンドウと、次の静的コントロール スタイルを使用することができます。

- SS_ENHMETAFILE 使用常にこのスタイルの拡張メタファイルをします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="seticon"></a>  CStatic::SetIcon

静的コントロールで新しいアイコンのイメージを関連付けます。

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*hIcon*<br/>
静的コントロールを描画するアイコンのハンドル。

### <a name="return-value"></a>戻り値

静的コントロールに関連付けられたアイコンがない場合の静的コントロール、または NULL に以前関連付けられているアイコンのハンドル。

### <a name="remarks"></a>Remarks

静的コントロールにアイコンが自動的に描画されます。 既定が左上隅に描画され、スタティック コントロールは、アイコンのサイズにサイズ変更されます。

さまざまなウィンドウと、次の静的コントロール スタイルを使用することができます。

- SS_ICON はカーソル、アイコン、常にこのスタイルを使用します。

- スタティック コントロールの中央に SS_CENTERIMAGE を使用します。 イメージが静的コントロールよりも大きい場合は、クリップされます。 静的コントロールよりも小さい場合、イメージの周囲の空の領域は静的コントロールの背景色で入力します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox クラス](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit クラス](../../mfc/reference/cedit-class.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar クラス](../../mfc/reference/cscrollbar-class.md)<br/>
[CDialog クラス](../../mfc/reference/cdialog-class.md)
