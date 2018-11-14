---
title: CCheckListBox クラス
ms.date: 11/04/2016
f1_keywords:
- CCheckListBox
- AFXWIN/CCheckListBox
- AFXWIN/CCheckListBox::CCheckListBox
- AFXWIN/CCheckListBox::Create
- AFXWIN/CCheckListBox::DrawItem
- AFXWIN/CCheckListBox::Enable
- AFXWIN/CCheckListBox::GetCheck
- AFXWIN/CCheckListBox::GetCheckStyle
- AFXWIN/CCheckListBox::IsEnabled
- AFXWIN/CCheckListBox::MeasureItem
- AFXWIN/CCheckListBox::OnGetCheckPosition
- AFXWIN/CCheckListBox::SetCheck
- AFXWIN/CCheckListBox::SetCheckStyle
helpviewer_keywords:
- CCheckListBox [MFC], CCheckListBox
- CCheckListBox [MFC], Create
- CCheckListBox [MFC], DrawItem
- CCheckListBox [MFC], Enable
- CCheckListBox [MFC], GetCheck
- CCheckListBox [MFC], GetCheckStyle
- CCheckListBox [MFC], IsEnabled
- CCheckListBox [MFC], MeasureItem
- CCheckListBox [MFC], OnGetCheckPosition
- CCheckListBox [MFC], SetCheck
- CCheckListBox [MFC], SetCheckStyle
ms.assetid: 1dd78438-00e8-441c-b36f-9c4f9ac0d019
ms.openlocfilehash: b3bf93a876f9092d5615b75ca45fea71341d3557
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327344"
---
# <a name="cchecklistbox-class"></a>CCheckListBox クラス

Windows のチェックリスト ボックスの機能を提供します。

## <a name="syntax"></a>構文

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[サンプル](#cchecklistbox)|`CCheckListBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCheckListBox::Create](#create)|Windows チェックリスト ボックスを作成し、それにアタッチ、`CCheckListBox`オブジェクト。|
|[Cchecklistbox:](#drawitem)|ビジュアルな部分のオーナー描画リスト ボックスが変更されたときにフレームワークによって呼び出されます。|
|[CCheckListBox::Enable](#enable)|有効またはチェックリスト ボックスの項目を無効にします。|
|[CCheckListBox::GetCheck](#getcheck)|項目のチェック ボックスの状態を取得します。|
|[CCheckListBox::GetCheckStyle](#getcheckstyle)|コントロールのチェック ボックスのスタイルを取得します。|
|[CCheckListBox::IsEnabled](#isenabled)|項目が有効になっているかどうかを判断します。|
|[CCheckListBox::MeasureItem](#measureitem)|オーナー描画スタイルでリスト ボックスが作成されるときに、フレームワークによって呼び出されます。|
|[CCheckListBox::OnGetCheckPosition](#ongetcheckposition)|項目のチェック ボックスの位置を取得するためにフレームワークによって呼び出されます。|
|[CCheckListBox::SetCheck](#setcheck)|項目のチェック ボックスの状態を設定します。|
|[CCheckListBox::SetCheckStyle](#setcheckstyle)|コントロールのチェック ボックスのスタイルを設定します。|

## <a name="remarks"></a>Remarks

「チェックリスト ボックス」には、ファイル名などの項目の一覧が表示されます。 リスト内の各項目は、ユーザーはオンまたはオフにすることの横にあるチェック ボックスが。

`CCheckListBox` オーナー描画コントロールに対してのみは複数のテキスト文字列の一覧が含まれています。 簡単に言うと、チェックリスト ボックスには、テキスト文字列と、チェック ボックスが含まれていますが、すべてのテキストを持つ必要はありません。 たとえば、小型のビットマップと各アイテムの横のチェック ボックスの一覧がある可能性があります。

独自チェックリスト ボックスを作成するには、独自のクラスから派生する必要があります`CCheckListBox`します。 派生クラスのコンス トラクターを作成、独自のクラスを派生する呼び出します`Create`します。

リスト ボックスからその親に送信される Windows 通知メッセージを処理する場合 (通常はから派生したクラス[CDialog](../../mfc/reference/cdialog-class.md))、親クラスに各メッセージをメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を追加します。

各メッセージ マップ エントリは、次の形式をとります。

**ON\_**_通知_ **(** _id_、 _memberFxn_ **)**

場所`id`通知を送信するコントロールの子ウィンドウ ID を指定および`memberFxn`通知を処理するために記述した親メンバー関数の名前を指定します。

親の関数のプロトタイプは次のとおりです。

`afx_msg void memberFxn();`

関連する 1 つだけのメッセージ マップ エントリがある`CCheckListBox`(メッセージ マップ エントリも参照してください。 ただし[CListBox](../../mfc/reference/clistbox-class.md))。

- ON_CLBN_CHKCHANGE ユーザーには、項目のチェック ボックスをオンの状態が変更されました。

既定値を使用するには、チェックリスト ボックスが既定のチェックリスト ボックス (文字列をそれぞれの左側に既定のサイズのチェック ボックスの一覧) の場合は、 [cchecklistbox:](#drawitem)チェックリスト ボックスを描画するためにします。 それ以外の場合、オーバーライドする必要があります、 [CListBox::CompareItem](../../mfc/reference/clistbox-class.md#compareitem)関数と[cchecklistbox:](#drawitem)と[CCheckListBox::MeasureItem](#measureitem)関数。

チェックリスト ボックスは、ダイアログ テンプレートから、またはコードで直接作成できます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cchecklistbox"></a>  サンプル

`CCheckListBox` オブジェクトを構築します。

```
CCheckListBox();
```

### <a name="remarks"></a>Remarks

構築する、 `CCheckListBox` 2 つのステップ内のオブジェクト。 最初から派生したクラスを定義`CCheckListBox`、呼び出して`Create`、Windows のチェックリスト ボックスを初期化しにアタッチする`CCheckListBox`オブジェクト。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

##  <a name="create"></a>  CCheckListBox::Create

Windows チェックリスト ボックスを作成し、それにアタッチ、`CCheckListBox`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
チェックリスト ボックスのスタイルを指定します。 LBS_HASSTRINGS と LBS_OWNERDRAWFIXED (リスト内のすべての項目は高さが同じ) または LBS_OWNERDRAWVARIABLE をスタイルとして使用することがあります (リスト内の項目は異なる高さの)。 このスタイルは、その他と組み合わせることができます[リスト ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)LBS_USETABSTOPS を除きます。

*rect*<br/>
チェックリスト ボックスのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。

*pParentWnd*<br/>
チェックリスト ボックスの親ウィンドウを指定します (通常、`CDialog`オブジェクト)。 NULL は指定できません。

*nID*<br/>
チェックリスト ボックスのコントロール ID を指定します

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築する、 `CCheckListBox` 2 つのステップ内のオブジェクト。 派生したクラスを最初に、定義`CcheckListBox`を呼び出して`Create`、Windows のチェックリスト ボックスを初期化しにアタッチする`CCheckListBox`します。 参照してください[サンプル](#cchecklistbox)サンプルについては、します。

ときに`Create`実行されると、Windows の送信、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)チェックリスト ボックス コントロールへのメッセージ。

既定でこれらのメッセージが処理されます、 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate)、 [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)、 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数`CWnd`基本クラス。 既定のメッセージ処理を拡張するには、メッセージ マップを追加、上書き、前のメッセージ ハンドラー メンバー関数、派生クラス。 オーバーライド`OnCreate`、たとえば、新しいクラスに必要な初期化を実行します。

次の適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)チェックリスト ボックス コントロールに。

- WS_CHILD 常に

- WS_VISIBLE 通常

- WS_DISABLED ことはほとんどありません。

- WS_VSCROLL に垂直スクロール バーを追加します。

- WS_HSCROLL に水平スクロール バーを追加します。

- WS_GROUP コントロールをグループ化

- WS_TABSTOP にこのコントロールにタブ移動を許可します。

##  <a name="drawitem"></a>  Cchecklistbox:

ビジュアルな部分のオーナー描画のチェックリスト ボックスが変更されたときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
Long ポインター、 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md)のために必要な図面の種類に関する情報を含む構造体。

### <a name="remarks"></a>Remarks

`itemAction`と`itemState`のメンバー、`DRAWITEMSTRUCT`構造を実行する描画の動作を定義します。

既定では、この関数は、左側に既定のサイズのチェック ボックスに文字列ごとの一覧から成る既定 チェック ボックスの一覧を描画します。 チェック ボックスの一覧のサイズは、いずれかで指定された[作成](#create)です。

チェックリスト ボックスの文字列ではないリスト、変数の高さのアイテム、または、左上にいないチェック ボックスなど、既定ではないオーナー描画チェックリスト ボックスの描画を実装するには、このメンバー関数をオーバーライドします。 アプリケーションで提供されるディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバー関数の終了前にします。

チェックリスト ボックス スタイルでチェックリスト ボックスの項目はすべて同じ高さではない場合、(で指定されている`Create`) する必要があります * * して、一定をオーバーライドする必要があります、 [MeasureItem](#measureitem)関数。

##  <a name="enable"></a>  CCheckListBox::Enable

この関数では、有効またはチェックリスト ボックスの項目を無効にします。

```
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
チェックリスト ボックスの項目のインデックスを有効にします。

*bEnabled*<br/>
項目が有効になっているかどうかを指定します。

##  <a name="getcheck"></a>  CCheckListBox::GetCheck

指定されたチェック ボックスの状態を取得します。

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス内のチェック ボックスの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定されたチェック ボックスの状態。 次の表では、使用可能な値を示します。

|[値]|説明|
|-----------|-----------------|
|BST_CHECKED|チェック ボックスをオンします。|
|設定されています。|チェック ボックスはチェックされません。|
|BST_INDETERMINATE|チェック ボックスの状態は不確定です。|

##  <a name="getcheckstyle"></a>  CCheckListBox::GetCheckStyle

チェックリスト ボックスのスタイルを取得するには、この関数を呼び出します。

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>戻り値

コントロールのチェック ボックスのスタイル。

### <a name="remarks"></a>Remarks

利用可能な方法については、次を参照してください。[有効なスタイル](#setcheckstyle)します。

##  <a name="isenabled"></a>  CCheckListBox::IsEnabled

項目が有効になっているかどうかを判断するには、この関数を呼び出します。

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目のインデックス。

### <a name="return-value"></a>戻り値

0 以外の場合は、項目が有効な場合それ以外の場合 0 を返します。

##  <a name="measureitem"></a>  CCheckListBox::MeasureItem

既定以外のスタイルでチェックリスト ボックスが作成されるときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpMeasureItemStruct*<br/>
Long ポインター、 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md)構造体。

### <a name="remarks"></a>Remarks

既定では、このメンバー関数は何もしません。 このメンバー関数をオーバーライドし、入力、`MEASUREITEMSTRUCT`チェックリスト ボックス アイテムのディメンションの Windows に通知する構造体。 チェックリスト ボックスが作成された場合、 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)リスト ボックス内の各項目のスタイル、フレームワークの呼び出し、このメンバー関数。 それ以外の場合、このメンバーは、1 回だけ呼び出されます。

##  <a name="ongetcheckposition"></a>  CCheckListBox::OnGetCheckPosition

フレームワークは、項目のチェック ボックスのサイズと位置を取得するには、この関数を呼び出します。

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>パラメーター

*rectItem*<br/>
位置となるリスト アイテムのサイズ。

*rectCheckBox*<br/>
既定の位置とサイズの項目のチェック ボックスをオンします。

### <a name="return-value"></a>戻り値

位置とサイズの項目のチェック ボックスをオンします。

### <a name="remarks"></a>Remarks

既定の位置とサイズのチェック ボックスのみ既定の実装を返します (`rectCheckBox`)。 既定では、チェック ボックスをアイテムの左上隅に配置され、標準のチェック ボックスのサイズします。 場合、右側のチェック ボックスまたは拡大または縮小のチェック ボックスの位置である可能性があります。 このような場合は、オーバーライド`OnGetCheckPosition`チェック ボックスの位置とサイズ内に項目を変更します。

##  <a name="setcheck"></a>  CCheckListBox::SetCheck

指定されたチェック ボックスの状態を設定します。

```
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックス内のチェック ボックスの 0 から始まるインデックス。

*確認してください。*<br/>
指定されたチェック ボックスのボタンの状態。 使用可能な値は、「解説」を参照してください。

### <a name="remarks"></a>Remarks

次の表に指定できる値の一覧、*を確認してください*パラメーター。

|[値]|説明|
|-----------|-----------------|
|BST_CHECKED|指定されたチェック ボックスを選択します。|
|設定されています。|指定されたチェック ボックスをオフにします。|
|BST_INDETERMINATE|不確定なを指定のチェック ボックスの状態を設定します。<br /><br /> この状態は、チェック ボックスのスタイルが BS_AUTO3STATE または BS_3STATE 場合にのみ使用します。 詳細については、次を参照してください。[ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)します。|

##  <a name="setcheckstyle"></a>  CCheckListBox::SetCheckStyle

チェックリスト ボックスのチェック ボックスのスタイルを設定するには、この関数を呼び出します。

```
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
チェックリスト ボックスのチェック ボックスのスタイルを決定します。

### <a name="remarks"></a>Remarks

有効なスタイルは次のとおりです。

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

これらのスタイルについては、次を参照してください。[ボタンのスタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)します。

## <a name="see-also"></a>関連項目

[MFC サンプル TSTCON](../../visual-cpp-samples.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)
