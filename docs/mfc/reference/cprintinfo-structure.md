---
description: '詳細については、次を参照してください: CPrintInfo 構造体'
title: CPrintInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 355bcf2f04b32756ae16147465054e945d70cf78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343389"
---
# <a name="cprintinfo-structure"></a>CPrintInfo 構造体

印刷ジョブまたは印刷プレビュージョブに関する情報を格納します。

## <a name="syntax"></a>構文

```
struct CPrintInfo
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CPrintInfo:: GetFromPage](#getfrompage)|印刷される最初のページの番号を返します。|
|[CPrintInfo:: GetMaxPage](#getmaxpage)|ドキュメントの最後のページの番号を返します。|
|[CPrintInfo:: GetMinPage](#getminpage)|ドキュメントの最初のページの番号を返します。|
|[CPrintInfo:: GetOffsetPage](#getoffsetpage)|結合された DocObject print ジョブで印刷される DocObject 項目の最初のページの前のページ数を返します。|
|[CPrintInfo:: GetToPage](#gettopage)|印刷されている最後のページの番号を返します。|
|[CPrintInfo:: SetMaxPage](#setmaxpage)|ドキュメントの最後のページの番号を設定します。|
|[CPrintInfo:: SetMinPage](#setminpage)|ドキュメントの最初のページの番号を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CPrintInfo:: m_bContinuePrinting](#m_bcontinueprinting)|フレームワークで印刷ループを続行するかどうかを示すフラグが含まれています。|
|[CPrintInfo:: m_bDirect](#m_bdirect)|ドキュメントが直接印刷されている ([印刷] ダイアログボックスを表示しない) かどうかを示すフラグが含まれています。|
|[CPrintInfo:: m_bDocObject](#m_bdocobject)|印刷されるドキュメントが DocObject であるかどうかを示すフラグが含まれています。|
|[CPrintInfo:: m_bPreview](#m_bpreview)|ドキュメントがプレビューされているかどうかを示すフラグが含まれています。|
|[CPrintInfo:: m_dwFlags](#m_dwflags)|DocObject 印刷操作を指定します。|
|[CPrintInfo:: m_lpUserData](#m_lpuserdata)|ユーザーが作成した構造体へのポインターを格納します。|
|[CPrintInfo:: m_nCurPage](#m_ncurpage)|現在印刷されているページの番号を識別します。|
|[CPrintInfo:: m_nJobNumber](#m_njobnumber)|現在の印刷ジョブに対してオペレーティングシステムによって割り当てられたジョブ番号を指定します。|
|[CPrintInfo:: m_nNumPreviewPages](#m_nnumpreviewpages)|プレビューウィンドウに表示されるページ数を識別します。1または2のいずれかです。|
|[CPrintInfo:: m_nOffsetPage](#m_noffsetpage)|結合された DocObject print ジョブ内の特定の DocObject の最初のページのオフセットを指定します。|
|[CPrintInfo:: m_pPD](#m_ppd)|`CPrintDialog`[印刷] ダイアログボックスに使用するオブジェクトへのポインターを格納します。|
|[CPrintInfo:: m_rectDraw](#m_rectdraw)|現在使用可能なページ領域を定義する四角形を指定します。|
|[CPrintInfo:: m_strPageDesc](#m_strpagedesc)|ページ番号表示の書式文字列が含まれています。|

## <a name="remarks"></a>解説

`CPrintInfo` は構造体であり、基本クラスを持っていません。

フレームワークは、 `CPrintInfo` 印刷または印刷プレビューコマンドが選択されるたびにのオブジェクトを作成し、コマンドの完了時に破棄します。

`CPrintInfo` 印刷するページの範囲や、現在印刷中のページなど、印刷ジョブの現在の状態など、印刷ジョブ全体に関する情報を格納します。 一部の情報は、関連付けられた [CPrintDialog](../../mfc/reference/cprintdialog-class.md) オブジェクトに格納されます。このオブジェクトには、ユーザーが [印刷] ダイアログボックスに入力した値が含まれています。

`CPrintInfo`オブジェクトは、印刷処理中にフレームワークとビュークラスの間で渡され、2つの間で情報を交換するために使用されます。 たとえば、フレームワークは、のメンバーに値を割り当てることによって、印刷するドキュメントのページをビュークラスに通知します `m_nCurPage` `CPrintInfo` 。ビュークラスは、値を取得し、指定されたページの実際の印刷を実行します。

別の例として、ドキュメントの長さが印刷されるまでわからない場合があります。 この場合、ビュークラスは、ページが印刷されるたびにドキュメントの末尾をテストします。 End に達すると、ビュークラスによってのメンバーが FALSE に設定されます。これにより、 `m_bContinuePrinting` `CPrintInfo` 出力ループを停止するようにフレームワークに通知されます。

`CPrintInfo` は、「参照」に記載されているのメンバー関数によって使用され `CView` ます。 Microsoft Foundation Class ライブラリによって提供される印刷アーキテクチャの詳細については、「 [フレームウィンドウ](../../mfc/frame-windows.md) 」と「 [ドキュメント/ビューアーキテクチャ](../../mfc/document-view-architecture.md) 」、および「 [印刷](../../mfc/printing.md) と [印刷: マルチページドキュメント](../../mfc/multipage-documents.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CPrintInfo`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

## <a name="cprintinfogetfrompage"></a><a name="getfrompage"></a> CPrintInfo:: GetFromPage

印刷される最初のページの番号を取得するには、この関数を呼び出します。

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>戻り値

印刷される最初のページの番号。

### <a name="remarks"></a>解説

これは、ユーザーが [印刷] ダイアログボックスで指定した値で、 `CPrintDialog` メンバーによって参照されるオブジェクトに格納され `m_pPD` ます。 ユーザーが値を指定していない場合、既定値はドキュメントの最初のページになります。

## <a name="cprintinfogetmaxpage"></a><a name="getmaxpage"></a> CPrintInfo:: GetMaxPage

ドキュメントの最後のページの番号を取得します。

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>戻り値

ドキュメントの最後のページ番号。

### <a name="remarks"></a>解説

この値は `CPrintDialog` 、メンバーによって参照されるオブジェクトに格納され `m_pPD` ます。

## <a name="cprintinfogetminpage"></a><a name="getminpage"></a> CPrintInfo:: GetMinPage

ドキュメントの最初のページの番号を取得します。

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>戻り値

ドキュメントの最初のページの番号。

### <a name="remarks"></a>解説

この値は `CPrintDialog` 、メンバーによって参照されるオブジェクトに格納され `m_pPD` ます。

## <a name="cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a> CPrintInfo:: GetOffsetPage

DocObject クライアントから複数の DocObject アイテムを印刷するときに、この関数を呼び出してオフセットを取得します。

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>戻り値

結合された DocObject 印刷ジョブで印刷される DocObject 項目の最初のページの前のページ数。

### <a name="remarks"></a>解説

この値は、メンバーによって参照され `m_nOffsetPage` ます。 ドキュメントの最初のページには、 `m_nOffsetPage` 他のアクティブなドキュメントを DocObject として印刷すると、値 + 1 が付けられます。 `m_nOffsetPage`メンバーは、値が TRUE の場合にのみ有効です `m_bDocObject` 。

## <a name="cprintinfogettopage"></a><a name="gettopage"></a> CPrintInfo:: GetToPage

印刷する最後のページの番号を取得するには、この関数を呼び出します。

```
UINT GetToPage() const;
```

### <a name="return-value"></a>戻り値

印刷する最後のページの番号。

### <a name="remarks"></a>解説

これは、ユーザーが [印刷] ダイアログボックスで指定した値で、 `CPrintDialog` メンバーによって参照されるオブジェクトに格納され `m_pPD` ます。 ユーザーが値を指定していない場合、既定値はドキュメントの最後のページです。

## <a name="cprintinfom_bcontinueprinting"></a><a name="m_bcontinueprinting"></a> CPrintInfo:: m_bContinuePrinting

フレームワークで印刷ループを続行するかどうかを示すフラグが含まれています。

### <a name="remarks"></a>解説

印刷時の改ページ位置の自動修正を実行している場合は、ドキュメントの末尾に達したときにのオーバーライドで、このメンバーを FALSE に設定でき `CView::OnPrepareDC` ます。 メンバー関数を使用して印刷ジョブの開始時にドキュメントの長さを指定している場合は、この変数を変更する必要はありません `SetMaxPage` 。 メンバーは、 `m_bContinuePrinting` BOOL 型のパブリック変数です。

## <a name="cprintinfom_bdirect"></a><a name="m_bdirect"></a> CPrintInfo:: m_bDirect

[印刷] ダイアログボックスが直接印刷のためにバイパスされる場合、フレームワークはこのメンバーを TRUE に設定します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

通常、[印刷] ダイアログは、シェルから印刷するとき、またはコマンド ID ID_FILE_PRINT_DIRECT を使用して印刷を行うときにバイパスされます。

通常、このメンバーは変更しませんが、変更する場合は、cview: [: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)のオーバーライドで[Cview::D oPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting)を呼び出す前に変更してください。

## <a name="cprintinfom_bdocobject"></a><a name="m_bdocobject"></a> CPrintInfo:: m_bDocObject

印刷されるドキュメントが DocObject であるかどうかを示すフラグが含まれています。

### <a name="remarks"></a>解説

データメンバー `m_dwFlags` と `m_nOffsetPage` は、このフラグが TRUE でない限り無効です。

## <a name="cprintinfom_bpreview"></a><a name="m_bpreview"></a> CPrintInfo:: m_bPreview

ドキュメントがプレビューされているかどうかを示すフラグが含まれています。

### <a name="remarks"></a>解説

これは、ユーザーが実行したコマンドに応じて、フレームワークによって設定されます。 印刷プレビュージョブの場合、[印刷] ダイアログボックスは表示されません。 メンバーは、 `m_bPreview` BOOL 型のパブリック変数です。

## <a name="cprintinfom_dwflags"></a><a name="m_dwflags"></a> CPrintInfo:: m_dwFlags

DocObject 印刷操作を指定するフラグの組み合わせが含まれています。

### <a name="remarks"></a>解説

データメンバー `m_bDocObject` が TRUE の場合にのみ有効です。

フラグには、次の値の1つ以上を指定できます。

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

## <a name="cprintinfom_lpuserdata"></a><a name="m_lpuserdata"></a> CPrintInfo:: m_lpUserData

ユーザーが作成した構造体へのポインターを格納します。

### <a name="remarks"></a>解説

これを使用すると、ビュークラスに格納しない印刷固有のデータを格納できます。 `m_lpUserData`メンバーは、LPVOID 型のパブリック変数です。

## <a name="cprintinfom_ncurpage"></a><a name="m_ncurpage"></a> CPrintInfo:: m_nCurPage

現在のページの番号を格納します。

### <a name="remarks"></a>解説

フレームワークは、 `CView::OnPrepareDC` `CView::OnPrint` ドキュメントの各ページに対してとを1回呼び出し、このメンバーに対して毎回異なる値を指定します。値は、によって返される値から、に `GetFromPage` よって返される値までの範囲です `GetToPage` 。 このメンバーをおよびのオーバーライドで使用して、 `CView::OnPrepareDC` `CView::OnPrint` 指定したドキュメントのページを印刷します。

プレビューモードが最初に呼び出されたときに、フレームワークはこのメンバーの値を読み取って、ドキュメントのどのページを最初にプレビューするかを決定します。 のオーバーライドでこのメンバーの値を設定して、 `CView::OnPreparePrinting` プレビューモードに入るときにドキュメント内のユーザーの現在の位置を維持することができます。 メンバーは、 `m_nCurPage` UINT 型のパブリック変数です。

## <a name="cprintinfom_njobnumber"></a><a name="m_njobnumber"></a> CPrintInfo:: m_nJobNumber

現在の印刷ジョブに対してオペレーティングシステムによって割り当てられたジョブ番号を示します。

### <a name="remarks"></a>解説

この値は、ジョブがまだ印刷されていない場合 (つまり、 `CPrintInfo` オブジェクトが新しく構築されていて、まだ印刷に使用されていない場合)、またはジョブの開始中にエラーが発生した場合に SP_ERROR ます。

## <a name="cprintinfom_nnumpreviewpages"></a><a name="m_nnumpreviewpages"></a> CPrintInfo:: m_nNumPreviewPages

プレビューモードで表示されるページ数を含みます。1または2のいずれかを指定できます。

### <a name="remarks"></a>解説

メンバーは、 `m_nNumPreviewPages` UINT 型のパブリック変数です。

## <a name="cprintinfom_noffsetpage"></a><a name="m_noffsetpage"></a> CPrintInfo:: m_nOffsetPage

結合された DocObject print ジョブ内の特定の DocObject の最初のページの前のページ数を含みます。

## <a name="cprintinfom_ppd"></a><a name="m_ppd"></a> CPrintInfo:: m_pPD

`CPrintDialog`印刷ジョブの [印刷] ダイアログボックスを表示するために使用するオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

`m_pPD`メンバーは、へのポインターとして宣言されたパブリック変数です `CPrintDialog` 。

## <a name="cprintinfom_rectdraw"></a><a name="m_rectdraw"></a> CPrintInfo:: m_rectDraw

ページの使用可能な描画領域を論理座標で指定します。

### <a name="remarks"></a>解説

のオーバーライドでこれを参照することもでき `CView::OnPrint` ます。 このメンバーを使用すると、ヘッダーやフッターなどを印刷した後に使用できる領域を追跡できます。 `m_rectDraw`メンバーは型のパブリック変数です `CRect` 。

## <a name="cprintinfom_strpagedesc"></a><a name="m_strpagedesc"></a> CPrintInfo:: m_strPageDesc

印刷プレビュー中にページ番号を表示するために使用される書式設定文字列が含まれています。この文字列は2つの部分文字列で構成されます。1ページ表示の場合は1つ、2ページ表示の場合は1つであり、それぞれ ' \n ' 文字で終了します。

### <a name="remarks"></a>解説

フレームワークでは、"ページ% U\n ページ%%u\n" が既定値として使用されます。 ページ番号に別の形式を使用する場合は、のオーバーライドで書式設定文字列を指定し `CView::OnPreparePrinting` ます。 `m_strPageDesc`メンバーは型のパブリック変数です `CString` 。

## <a name="cprintinfosetmaxpage"></a><a name="setmaxpage"></a> CPrintInfo:: SetMaxPage

ドキュメントの最後のページの番号を指定します。

```cpp
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>パラメーター

*nMaxPage*<br/>
ドキュメントの最後のページ番号。

### <a name="remarks"></a>解説

この値は `CPrintDialog` 、メンバーによって参照されるオブジェクトに格納され `m_pPD` ます。 ドキュメントが印刷される前にその長さがわかっている場合は、のオーバーライドからこの関数を呼び出し `CView::OnPreparePrinting` ます。 ドキュメントの長さが、[印刷] ダイアログボックスでユーザーが指定した設定に依存している場合は、のオーバーライドからこの関数を呼び出し `CView::OnBeginPrinting` ます。 ドキュメントの長さが印刷されるまでわからない場合は、メンバーを使用して `m_bContinuePrinting` 印刷ループを制御します。

### <a name="example"></a>例

  [CView:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)の例を参照してください。

## <a name="cprintinfosetminpage"></a><a name="setminpage"></a> CPrintInfo:: SetMinPage

ドキュメントの最初のページの番号を指定します。

```cpp
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>パラメーター

*nMinPage*<br/>
ドキュメントの最初のページの番号。

### <a name="remarks"></a>解説

通常、ページ番号は1から始まります。 この値は `CPrintDialog` 、メンバーによって参照されるオブジェクトに格納され `m_pPD` ます。

## <a name="see-also"></a>関連項目

[MFC のサンプル DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView:: OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView:: OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView:: OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView:: OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView:: OnPrint](../../mfc/reference/cview-class.md#onprint)
