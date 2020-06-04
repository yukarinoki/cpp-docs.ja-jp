---
title: クラスを確認する
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
ms.openlocfilehash: dc0e80e80d61104a4d8cb5f1cfd4e26a64c42249
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752744"
---
# <a name="cchecklistbox-class"></a>クラスを確認する

Windows のチェックリスト ボックスの機能を提供します。

## <a name="syntax"></a>構文

```
class CCheckListBox : public CListBox
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCheck リストボックス::Cチェックリストボックス](#cchecklistbox)|`CCheckListBox` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCheck リストボックス::作成](#create)|Windows チェックリスト ボックスを作成し、オブジェクトに`CCheckListBox`アタッチします。|
|[リストボックス::Dローアイテム](#drawitem)|オーナー描画リスト ボックスの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。|
|[Cチェックリストボックス::有効にする](#enable)|チェックリスト ボックス項目を有効または無効にします。|
|[リストボックス::ゲットチェック](#getcheck)|項目のチェック ボックスの状態を取得します。|
|[リストボックス::ゲットチェックスタイル](#getcheckstyle)|コントロールのチェック ボックスのスタイルを取得します。|
|[リストボックス::IsEnabled](#isenabled)|項目が有効かどうかを判断します。|
|[Cチェックリストボックス::メジャーアイテム](#measureitem)|オーナー描画スタイルを持つリスト ボックスが作成されるときに、フレームワークによって呼び出されます。|
|[リストボックス::オンゲットチェックポジション](#ongetcheckposition)|アイテムのチェック ボックスの位置を取得するために、フレームワークによって呼び出されます。|
|[リストボックス::セットチェック](#setcheck)|項目のチェック ボックスの状態を設定します。|
|[Cチェックリストボックス::セットチェックスタイル](#setcheckstyle)|コントロールのチェック ボックスのスタイルを設定します。|

## <a name="remarks"></a>解説

"チェックリスト ボックス" には、ファイル名などの項目の一覧が表示されます。 リスト内の各項目の横には、ユーザーがチェックまたはオフにできるチェック ボックスがあります。

`CCheckListBox`は、リストにテキスト文字列以外の数が含まれているため、オーナー描画コントロールに対してのみ使用されます。 最も簡単なチェックリスト ボックスにはテキスト文字列とチェック ボックスが含まれていますが、テキストを用意する必要はありません。 たとえば、小さいビットマップのリストを、各項目の横にチェック ボックスを付けて表示できます。

独自のチェックリスト ボックスを作成するには、 から`CCheckListBox`独自のクラスを派生させる必要があります。 独自のクラスを派生させるには、派生クラスのコンストラクタを記述してから、`Create`を呼び出します。

リスト ボックスから親に送信される Windows 通知メッセージ (通常[は CDialog](../../mfc/reference/cdialog-class.md)から派生したクラス) を処理する場合は、メッセージ マップ エントリとメッセージ ハンドラー メンバー関数を各メッセージの親クラスに追加します。

各メッセージ マップ エントリは、次の形式をとります。

**オン\_**_通知_**(** _id_,_メンバFxn_ **)**

通知`id`を送信するコントロールの子ウィンドウ ID を指定`memberFxn`し、通知を処理するために記述した親メンバー関数の名前を指定します。

親の関数プロトタイプは次のとおりです。

`afx_msg void memberFxn();`

特に関連するメッセージ マップ エントリは 1`CCheckListBox`つだけです ([ただし、CListBox](../../mfc/reference/clistbox-class.md)のメッセージ マップ エントリも参照してください)。

- ON_CLBN_CHKCHANGE ユーザーがアイテムのチェックボックスの状態を変更しました。

チェックリスト ボックスが既定のチェックリスト ボックス (既定のサイズのチェック ボックスがそれぞれ左側にある文字列の一覧) の場合は、既定の[CCheckListBox::DrawItem](#drawitem)を使用してチェックリスト ボックスを描画できます。 それ以外の場合は[、C リスト ボックス::比較項目](../../mfc/reference/clistbox-class.md#compareitem)関数と[CCheckListBox::DrawItem](#drawitem)関数と[CCheckListBox::メジャーアイテム関数をオーバーライドする](#measureitem)必要があります。

チェックリスト ボックスは、ダイアログ テンプレートから作成することも、コード内で直接作成することもできます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CCheckListBox`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cchecklistboxcchecklistbox"></a><a name="cchecklistbox"></a>CCheck リストボックス::Cチェックリストボックス

`CCheckListBox` オブジェクトを構築します。

```
CCheckListBox();
```

### <a name="remarks"></a>解説

オブジェクトは`CCheckListBox`2 つの手順で作成します。 まず、 から`CCheckListBox`派生したクラスを定義`Create`してから、 を呼び出します`CCheckListBox`。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#60](../../mfc/codesnippet/cpp/cchecklistbox-class_1.cpp)]

## <a name="cchecklistboxcreate"></a><a name="create"></a>CCheck リストボックス::作成

Windows チェックリスト ボックスを作成し、オブジェクトに`CCheckListBox`アタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
チェックリスト ボックスのスタイルを指定します。 スタイルは、LBS_HASSTRINGSLBS_OWNERDRAWFIXED (リスト内のすべての項目が同じ高さ) またはLBS_OWNERDRAWVARIABLE (リスト内の項目は、さまざまな高さ) である必要があります。 このスタイルは、LBS_USETABSTOPS以外の他[のリスト ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)と組み合わせることができます。

*Rect*<br/>
チェックリスト ボックスのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
チェックリスト ボックスの親ウィンドウ (通常はオブジェクト`CDialog`) を指定します。 NULL にすることはできません。

*nID*<br/>
チェックリスト ボックスのコントロール ID を指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

オブジェクトは`CCheckListBox`2 つの手順で作成します。 まず、 から`CcheckListBox`派生したクラスを定義し`Create`、 を呼び出し、Windows チェックリスト ボックスを`CCheckListBox`初期化して にアタッチします。 サンプル[については、「CCheckListBox::CCheckListBox」](#cchecklistbox)を参照してください。

実行時`Create`に、 windows は[WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)のメッセージをチェックリスト ボックス コントロールに送信します。

これらのメッセージは、`CWnd`既定では、基本クラスの[OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate) [、OnCreate、OnNcCalcSize](../../mfc/reference/cwnd-class.md#oncreate)、および[OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)メンバー関数によって処理されます。 [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize) 既定のメッセージ処理を拡張するには、派生クラスにメッセージ マップを追加し、上記のメッセージ ハンドラー メンバー関数をオーバーライドします。 オーバーライド`OnCreate`(たとえば、新しいクラスに必要な初期化を実行する場合)。

チェックリスト ボックス コントロールに次の[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)を適用します。

- WS_CHILD常に

- WS_VISIBLE通常

- WS_DISABLEDまれ

- WS_VSCROLL垂直スクロール バーを追加するには

- WS_HSCROLL 水平スクロール バーを追加するには

- WS_GROUP グループ コントロールへ

- WS_TABSTOP このコントロールへのタブ移動を許可するには

## <a name="cchecklistboxdrawitem"></a><a name="drawitem"></a>リストボックス::Dローアイテム

オーナー描画のチェックリスト ボックスの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
必要な描画の種類に関する情報を含む[DRAWITEMSTRUCT 構造体](/windows/win32/api/winuser/ns-winuser-drawitemstruct)への長いポインター。

### <a name="remarks"></a>解説

`itemAction`構造体の`itemState`および`DRAWITEMSTRUCT`メンバーは、実行する描画アクションを定義します。

デフォルトでは、この関数は、文字列のリストから成るデフォルトのチェックボックスリストを、それぞれデフォルトサイズのチェックボックスを左側に描画します。 チェックボックスリストのサイズは[、作成](#create)で指定したサイズです。

文字列ではないリストを持つチェックリスト ボックス、可変高さ項目、左側にないチェック ボックスなど、既定ではないオーナー描画チェックリスト ボックスの描画を実装するには、このメンバー関数をオーバーライドします。 アプリケーションは、このメンバー関数の終了前に *、lpDrawItemStruct*で提供される表示コンテキストに選択されているすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

チェックリスト ボックスの項目がすべて同じ高さでない場合は、 で`Create`指定したチェックリスト ボックス スタイルを**LBS_OWNERVARIABLE**する[MeasureItem](#measureitem)必要があります。

## <a name="cchecklistboxenable"></a><a name="enable"></a>Cチェックリストボックス::有効にする

チェックリスト ボックス項目を有効または無効にします。

```cpp
void Enable(
    int nIndex,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
有効にするチェックリスト ボックス項目のインデックス。

*b有効*<br/>
項目が有効か無効かを指定します。

## <a name="cchecklistboxgetcheck"></a><a name="getcheck"></a>リストボックス::ゲットチェック

指定されたチェック ボックスの状態を取得します。

```
int GetCheck(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックスに含まれるチェック ボックスの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定されたチェック ボックスの状態。 次の表に、使用できる値を示します。

|値|説明|
|-----------|-----------------|
|BST_CHECKED|チェック ボックスはオンです。|
|BST_UNCHECKED|チェック ボックスはオンになっていません。|
|BST_INDETERMINATE|チェック ボックスの状態は不確定です。|

## <a name="cchecklistboxgetcheckstyle"></a><a name="getcheckstyle"></a>リストボックス::ゲットチェックスタイル

チェックリスト ボックスのスタイルを取得します。

```
UINT GetCheckStyle();
```

### <a name="return-value"></a>戻り値

コントロールのチェック ボックスのスタイル。

### <a name="remarks"></a>解説

可能なスタイルの詳細については、「 [SetCheckStyle](#setcheckstyle)」を参照してください。

## <a name="cchecklistboxisenabled"></a><a name="isenabled"></a>リストボックス::IsEnabled

アイテムが有効かどうかを調べます。

```
BOOL IsEnabled(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
項目のインデックス。

### <a name="return-value"></a>戻り値

項目が有効な場合は 0 以外。それ以外の場合は 0。

## <a name="cchecklistboxmeasureitem"></a><a name="measureitem"></a>Cチェックリストボックス::メジャーアイテム

既定以外のスタイルのチェックリスト ボックスが作成されたときに、フレームワークによって呼び出されます。

```
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```

### <a name="parameters"></a>パラメーター

*クラス*<br/>
[構造体への](/windows/win32/api/winuser/ns-winuser-measureitemstruct)長いポインター。

### <a name="remarks"></a>解説

既定では、このメンバー関数は何も実行しません。 このメンバー関数をオーバーライドし、チェックリスト`MEASUREITEMSTRUCT`ボックス項目のサイズを Windows に通知する構造を入力します。 [LBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)スタイルでチェックリスト ボックスを作成すると、フレームワークはリスト ボックス内の各項目に対してこのメンバー関数を呼び出します。 それ以外の場合、このメンバーは 1 回だけ呼び出されます。

## <a name="cchecklistboxongetcheckposition"></a><a name="ongetcheckposition"></a>リストボックス::オンゲットチェックポジション

フレームワークは、この関数を呼び出して、項目内のチェック ボックスの位置とサイズを取得します。

```
virtual CRect OnGetCheckPosition(
    CRect rectItem,
    CRect rectCheckBox);
```

### <a name="parameters"></a>パラメーター

*レクトアイテム*<br/>
リスト アイテムの位置とサイズ。

*レクトチェックボックス*<br/>
項目のチェック ボックスの既定の位置とサイズ。

### <a name="return-value"></a>戻り値

項目のチェック ボックスの位置とサイズ。

### <a name="remarks"></a>解説

既定の実装では、チェック ボックス ( )`rectCheckBox`の既定の位置とサイズのみが返されます。 既定では、チェック ボックスは項目の左上隅に配置され、標準のチェック ボックス サイズになります。 右側のチェック ボックスが必要な場合や、チェック ボックスを大きくまたは小さくする場合があります。 このような場合は、項目`OnGetCheckPosition`内のチェックボックスの位置とサイズを変更するようにオーバーライドします。

## <a name="cchecklistboxsetcheck"></a><a name="setcheck"></a>リストボックス::セットチェック

指定されたチェック ボックスの状態を設定します。

```cpp
void SetCheck(
    int nIndex,
    int nCheck);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
リスト ボックスに含まれるチェック ボックスの 0 から始まるインデックス。

*nチェック*<br/>
指定されたチェック ボックスのボタンの状態。 可能な値については、「解説」を参照してください。

### <a name="remarks"></a>解説

次の表は *、nCheck*パラメーターの値を示しています。

|値|説明|
|-----------|-----------------|
|BST_CHECKED|指定したチェック ボックスをオンにします。|
|BST_UNCHECKED|指定したチェック ボックスをオフにします。|
|BST_INDETERMINATE|指定されたチェック ボックスの状態を不確定に設定します。<br /><br /> この状態は、チェック ボックス スタイルがBS_AUTO3STATEまたはBS_3STATEの場合にのみ使用できます。 詳細については、「ボタン[スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)」を参照してください。|

## <a name="cchecklistboxsetcheckstyle"></a><a name="setcheckstyle"></a>Cチェックリストボックス::セットチェックスタイル

チェックリスト ボックスのチェック ボックスのスタイルを設定します。

```cpp
void SetCheckStyle(UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nStyle*<br/>
チェックリスト ボックスのチェック ボックスのスタイルを指定します。

### <a name="remarks"></a>解説

有効なスタイルは次のとおりです。

- BS_CHECKBOX

- BS_AUTOCHECKBOX

- BS_AUTO3STATE

- BS_3STATE

これらのスタイルの詳細については、「[ボタン スタイル](../../mfc/reference/styles-used-by-mfc.md#button-styles)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CListBox クラス](../../mfc/reference/clistbox-class.md)
