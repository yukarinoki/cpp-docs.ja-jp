---
title: CPrintInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 3b081b0728514c0fca2eb31462e1bcd9e91a47aa
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753012"
---
# <a name="cprintinfo-structure"></a>CPrintInfo 構造体

印刷ジョブまたは印刷プレビュー ジョブに関する情報を格納します。

## <a name="syntax"></a>構文

```
struct CPrintInfo
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ページから取得します。](#getfrompage)|印刷される最初のページの番号を返します。|
|[を見る](#getmaxpage)|文書の最後のページの番号を返します。|
|[を見る](#getminpage)|文書の最初のページの番号を返します。|
|[ページを表示します。](#getoffsetpage)|結合された DocObject 印刷ジョブで印刷される DocObject アイテムの最初のページの前にあるページ数を返します。|
|[をクリックします。](#gettopage)|最後に印刷されたページの番号を返します。|
|[を設定します。](#setmaxpage)|ドキュメントの最後のページの番号を設定します。|
|[ページを設定します。](#setminpage)|ドキュメントの最初のページの番号を設定します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[情報を提供::m_bContinuePrinting](#m_bcontinueprinting)|フレームワークが印刷ループを続行するかどうかを示すフラグを含みます。|
|[情報を m_bDirect提供します。](#m_bdirect)|ドキュメントを直接印刷するかどうかを示すフラグを含みます ([印刷] ダイアログ ボックスを表示せずに)。|
|[情報を提供::m_bDocObject](#m_bdocobject)|印刷するドキュメントが DocObject であるかどうかを示すフラグを含みます。|
|[m_bPreview](#m_bpreview)|ドキュメントがプレビューされているかどうかを示すフラグを含みます。|
|[m_dwFlags](#m_dwflags)|DocObject の印刷操作を指定します。|
|[M_lpUserData](#m_lpuserdata)|ユーザーが作成した構造体へのポインターを格納します。|
|[m_nCurPage](#m_ncurpage)|現在印刷中のページ番号を示します。|
|[m_nJobNumber](#m_njobnumber)|現在の印刷ジョブにオペレーティング システムによって割り当てられたジョブ番号を指定します。|
|[m_nNumPreviewPages](#m_nnumpreviewpages)|プレビュー ウィンドウに表示されるページ数を示します。1 または 2 のいずれか。|
|[m_nOffsetPage](#m_noffsetpage)|結合された DocObject 印刷ジョブにおける特定の DocObject の最初のページのオフセットを指定します。|
|[を設定::m_pPD](#m_ppd)|[印刷] ダイアログ`CPrintDialog`ボックスに使用するオブジェクトへのポインターを格納します。|
|[情報を提供::m_rectDraw](#m_rectdraw)|現在の有効なページ領域を定義する四角形を指定します。|
|[情報を提供::m_strPageDesc](#m_strpagedesc)|ページ番号の表示用の書式指定文字列を格納します。|

## <a name="remarks"></a>解説

`CPrintInfo`は構造体であり、基本クラスを持っていません。

フレームワークは、印刷または印刷`CPrintInfo`プレビューコマンドが選択されるたびにオブジェクトを作成し、コマンドが完了したときに破棄します。

`CPrintInfo`印刷するページの範囲や、現在印刷中のページなど、印刷ジョブの現在の状態など、印刷ジョブ全体に関する情報が含まれます。 一部の情報は、関連付けられた[CPrintDialog](../../mfc/reference/cprintdialog-class.md)オブジェクトに格納されます。このオブジェクトには、ユーザーが [印刷] ダイアログ ボックスに入力した値が含まれます。

オブジェクト`CPrintInfo`は、印刷プロセス中にフレームワークとビュー クラスの間で渡され、両者の間で情報を交換するために使用されます。 たとえば、フレームワークは、のメンバーに値を割り当てることによって、ドキュメントのどのページを印刷するかをビュー`m_nCurPage`クラスに`CPrintInfo`通知します。ビュー クラスは値を取得し、指定されたページの実際の印刷を実行します。

もう 1 つの例として、文書の長さが印刷されるまでは不明な場合があります。 このような場合は、ページが印刷されるたびに、ビュー クラスはドキュメントの末尾をテストします。 最後に達すると、ビュー クラスはのメンバー`m_bContinuePrinting``CPrintInfo`を FALSE に設定します。これにより、フレームワークは印刷ループを停止するように通知します。

`CPrintInfo`は、「関連項目」に`CView`リストされているメンバー関数によって使用されます。 Microsoft Foundation クラス ライブラリが提供する印刷アーキテクチャの詳細については、「[フレーム ウィンドウ](../../mfc/frame-windows.md)と[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)」および「[印刷](../../mfc/printing.md)と[印刷: 複数ページのドキュメント](../../mfc/multipage-documents.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`CPrintInfo`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="cprintinfogetfrompage"></a><a name="getfrompage"></a>ページから取得します。

印刷する最初のページの番号を取得します。

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>戻り値

印刷する最初のページの番号。

### <a name="remarks"></a>解説

これは、ユーザーが [印刷] ダイアログ ボックスで指定した値で、メンバーが`CPrintDialog`参照するオブジェクトに`m_pPD`格納されます。 ユーザーが値を指定していない場合、既定値はドキュメントの最初のページです。

## <a name="cprintinfogetmaxpage"></a><a name="getmaxpage"></a>を見る

ドキュメントの最後のページの番号を取得します。

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>戻り値

ドキュメントの最後のページの番号。

### <a name="remarks"></a>解説

この値は、メンバーが`CPrintDialog`参照するオブジェクトに`m_pPD`格納されます。

## <a name="cprintinfogetminpage"></a><a name="getminpage"></a>を見る

ドキュメントの最初のページの番号を取得します。

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>戻り値

ドキュメントの最初のページの番号。

### <a name="remarks"></a>解説

この値は、メンバーが`CPrintDialog`参照するオブジェクトに`m_pPD`格納されます。

## <a name="cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a>ページを表示します。

DocObject クライアントから複数の DocObject アイテムを印刷するときにオフセットを取得します。

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>戻り値

結合された DocObject 印刷ジョブで印刷される DocObject アイテムの最初のページの前にあるページ数。

### <a name="remarks"></a>解説

この値は`m_nOffsetPage`、メンバーによって参照されます。 ドキュメントの最初のページには、他のアクティブドキュメント`m_nOffsetPage`と共に DocObject として印刷されるときに、値 + 1 が付けられます。 メンバ`m_nOffsetPage`は、値が TRUE`m_bDocObject`の場合にのみ有効です。

## <a name="cprintinfogettopage"></a><a name="gettopage"></a>をクリックします。

印刷する最後のページの番号を取得します。

```
UINT GetToPage() const;
```

### <a name="return-value"></a>戻り値

印刷する最後のページの番号を指定します。

### <a name="remarks"></a>解説

これは、ユーザーが [印刷] ダイアログ ボックスで指定した値で、メンバーが`CPrintDialog`参照するオブジェクトに`m_pPD`格納されます。 ユーザーが値を指定していない場合、既定値はドキュメントの最後のページになります。

## <a name="cprintinfom_bcontinueprinting"></a><a name="m_bcontinueprinting"></a>情報を提供::m_bContinuePrinting

フレームワークが印刷ループを続行するかどうかを示すフラグを含みます。

### <a name="remarks"></a>解説

印刷時間のページ分割を行う場合は、ドキュメントの末尾に到達した後の`CView::OnPrepareDC`上書きでこのメンバーを FALSE に設定できます。 この変数は、メンバー関数を使用して印刷ジョブの先頭に文書の長さを指定した場合には、変更する`SetMaxPage`必要はありません。 メンバー`m_bContinuePrinting`は BOOL 型のパブリック変数です。

## <a name="cprintinfom_bdirect"></a><a name="m_bdirect"></a>情報を m_bDirect提供します。

フレームワークは、印刷ダイアログ ボックスが直接印刷のためにバイパスされる場合は、このメンバーを TRUE に設定します。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

通常、シェルから印刷するとき、またはコマンド ID ID_FILE_PRINT_DIRECTを使用して印刷を行うと、印刷ダイアログはバイパスされます。

通常は、このメンバーを変更しませんが、変更する場合は[、CView::DoPreparePrinting](../../mfc/reference/cview-class.md#doprepareprinting)を呼び出す前に変更[します。](../../mfc/reference/cview-class.md#onprepareprinting)

## <a name="cprintinfom_bdocobject"></a><a name="m_bdocobject"></a>情報を提供::m_bDocObject

印刷するドキュメントが DocObject であるかどうかを示すフラグを含みます。

### <a name="remarks"></a>解説

このフラグ`m_dwFlags``m_nOffsetPage`が TRUE でない場合は、データ メンバーは無効です。

## <a name="cprintinfom_bpreview"></a><a name="m_bpreview"></a>m_bPreview

ドキュメントがプレビューされているかどうかを示すフラグを含みます。

### <a name="remarks"></a>解説

これは、ユーザーが実行するコマンドに応じてフレームワークによって設定されます。 印刷プレビュー ジョブの場合、[印刷] ダイアログ ボックスは表示されません。 メンバー`m_bPreview`は BOOL 型のパブリック変数です。

## <a name="cprintinfom_dwflags"></a><a name="m_dwflags"></a>m_dwFlags

DocObject の印刷操作を指定するフラグの組み合わせが含まれています。

### <a name="remarks"></a>解説

データ メンバー`m_bDocObject`が TRUE の場合にのみ有効です。

フラグには、次の値の 1 つ以上を指定できます。

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

## <a name="cprintinfom_lpuserdata"></a><a name="m_lpuserdata"></a>M_lpUserData

ユーザーが作成した構造体へのポインターを格納します。

### <a name="remarks"></a>解説

この機能を使用して、ビュー クラスに格納しない印刷固有のデータを格納できます。 メンバー`m_lpUserData`は、LPVOID 型のパブリック変数です。

## <a name="cprintinfom_ncurpage"></a><a name="m_ncurpage"></a>m_nCurPage

現在のページの番号を格納します。

### <a name="remarks"></a>解説

フレームワークは、`CView::OnPrepareDC`ドキュメント`CView::OnPrint`の各ページを呼び出し、毎回このメンバーに異なる値を指定します。値の範囲は、返された`GetFromPage`値から、 によって`GetToPage`返される値までです。 このメンバーは、ドキュメントの`CView::OnPrepareDC`指定したページ`CView::OnPrint`をオーバーライドして印刷するときに使用します。

プレビュー モードが最初に起動されると、フレームワークはこのメンバーの値を読み取り、ドキュメントのどのページを最初にプレビューするかを決定します。 プレビュー モードに入ったときに、ドキュメント内のユーザーの`CView::OnPreparePrinting`現在の位置を維持するために、このメンバーの値をオーバーライドで設定できます。 メンバー`m_nCurPage`は UINT 型のパブリック変数です。

## <a name="cprintinfom_njobnumber"></a><a name="m_njobnumber"></a>m_nJobNumber

現在の印刷ジョブに対してオペレーティング システムによって割り当てられたジョブ番号を示します。

### <a name="remarks"></a>解説

この値は、ジョブがまだ印刷されていない場合 (つまり、`CPrintInfo`オブジェクトが新しく作成され、印刷に使用されていない場合)、またはジョブの開始中にエラーが発生した場合にSP_ERROR可能性があります。

## <a name="cprintinfom_nnumpreviewpages"></a><a name="m_nnumpreviewpages"></a>m_nNumPreviewPages

プレビュー モードで表示されるページ数を含みます。1 または 2 のいずれかです。

### <a name="remarks"></a>解説

メンバー`m_nNumPreviewPages`は UINT 型のパブリック変数です。

## <a name="cprintinfom_noffsetpage"></a><a name="m_noffsetpage"></a>m_nOffsetPage

結合された DocObject 印刷ジョブの特定の DocObject の最初のページの前にページ数を含めます。

## <a name="cprintinfom_ppd"></a><a name="m_ppd"></a>を設定::m_pPD

印刷ジョブの [`CPrintDialog`印刷] ダイアログ ボックスを表示するために使用するオブジェクトへのポインターを格納します。

### <a name="remarks"></a>解説

メンバー`m_pPD`は、 へのポインターとして宣言されたパブリック変数`CPrintDialog`です。

## <a name="cprintinfom_rectdraw"></a><a name="m_rectdraw"></a>情報を提供::m_rectDraw

ページの有効な作図領域を論理座標で指定します。

### <a name="remarks"></a>解説

のオーバーライドでこれを参照することもできます`CView::OnPrint`。 このメンバーを使用して、ヘッダーやフッターなどを印刷した後に使用できる領域を追跡できます。 メンバー`m_rectDraw`は、 型のパブリック変数`CRect`です。

## <a name="cprintinfom_strpagedesc"></a><a name="m_strpagedesc"></a>情報を提供::m_strPageDesc

印刷プレビュー中にページ番号を表示するための書式指定文字列を格納します。この文字列は、1 つの部分文字列と 2 ページ表示用の 2 つの部分文字列で構成され、それぞれ '\n' 文字で終わる 2 ページ表示用です。

### <a name="remarks"></a>解説

フレームワークは、既定値として "ページ %u\nPages %u-%u\n" を使用します。 ページ番号に異なる形式を設定する場合は、 の上書きで書式`CView::OnPreparePrinting`指定文字列を指定します。 メンバー`m_strPageDesc`は、 型のパブリック変数`CString`です。

## <a name="cprintinfosetmaxpage"></a><a name="setmaxpage"></a>を設定します。

ドキュメントの最後のページの番号を指定します。

```cpp
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>パラメーター

*最大ページ*<br/>
ドキュメントの最後のページの番号。

### <a name="remarks"></a>解説

この値は、メンバーが`CPrintDialog`参照するオブジェクトに`m_pPD`格納されます。 ドキュメントの長さが印刷前にわかっている場合は、`CView::OnPreparePrinting`のオーバーライドからこの関数を呼び出します。 ドキュメントの長さが [印刷] ダイアログ ボックスでユーザーが指定した設定に依存する場合は、`CView::OnBeginPrinting`の上書きからこの関数を呼び出します。 印刷されるまでドキュメントの長さがわからない場合は、そのメンバーを`m_bContinuePrinting`使用して印刷ループを制御します。

### <a name="example"></a>例

  [「CView::OnPrepare印刷](../../mfc/reference/cview-class.md#onprepareprinting)」の例を参照してください。

## <a name="cprintinfosetminpage"></a><a name="setminpage"></a>ページを設定します。

ドキュメントの最初のページの番号を指定します。

```cpp
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>パラメーター

*ページ*<br/>
ドキュメントの最初のページの番号。

### <a name="remarks"></a>解説

ページ番号は通常 1 から始まります。 この値は、メンバーが`CPrintDialog`参照するオブジェクトに`m_pPD`格納されます。

## <a name="see-also"></a>関連項目

[MFC サンプル ディブルック](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[Cビュー::オンエンドプリント](../../mfc/reference/cview-class.md#onendprinting)<br/>
[プレビュー::オンエンドプリントプレビュー](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[Cビュー::オン準備DC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[Cビュー::準備印刷中](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[Cビュー::オンプリント](../../mfc/reference/cview-class.md#onprint)
