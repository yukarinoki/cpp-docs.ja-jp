---
title: CMFCDynamicLayout クラス
ms.date: 08/29/2019
f1_keywords:
- CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout
- AFXLAYOUT/CMFCDynamicLayout::AddItem
- AFXLAYOUT/CMFCDynamicLayout::Adjust
- AFXLAYOUT/CMFCDynamicLayout::Create
- AFXLAYOUT/CMFCDynamicLayout::GetHostWnd
- AFXLAYOUT/CMFCDynamicLayout::GetMinSize
- AFXLAYOUT/CMFCDynamicLayout::GetWindowRect
- AFXLAYOUT/CMFCDynamicLayout::HasItem
- AFXLAYOUT/CMFCDynamicLayout::IsEmpty
- AFXLAYOUT/CMFCDynamicLayout::LoadResource
- AFXLAYOUT/CMFCDynamicLayout::SetMinSize
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
ms.openlocfilehash: b70deca78d079c6a95db225814fdc70528e48af9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367523"
---
# <a name="cmfcdynamiclayout-class"></a>CMFCDynamicLayout クラス

ユーザーによるウィンドウ サイズの変更時に、ウィンドウのコントロールをどのように移動して、サイズを変更するかを指定します。

## <a name="syntax"></a>構文

```
class CMFCDynamicLayout : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCDynamicLayout::CMFCDynamicLayout`|`CMFCDynamicLayout` オブジェクトを構築します。|
|`CMFCDynamicLayout::~CMFCDynamicLayout`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCDynamicLayout::AddItem](#additem)|子ウィンドウ (通常はコントロール) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。|
|[CMFCDynamicLayout::Adjust](#adjust)|子ウィンドウ (通常はコントロール) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。|
|[CMFCDynamicLayout::Create](#create)|ホスト ウィンドウを格納し、検証します。|
|[CMFCDynamicLayout::GetHostWnd](#gethostwnd)|ホスト ウィンドウへのポインターを返します。|
|[CMFCDynamicLayout::GetMinSize](#getminsize)|レイアウト調整の下限のウィンドウ サイズを返します。|
|[CMFCDynamicLayout::GetWindowRect](#getwindowrect)|ウィンドウの現在のクライアント領域の長方形を取得します。|
|[CMFCDynamicLayout::HasItem](#hasitem)|子コントロールが動的レイアウトに追加されたかどうかを確認します。|
|[CMFCDynamicLayout::IsEmpty](#isempty)|動的なレイアウトに子ウィンドウが追加されていないことを確認します。|
|[CMFCDynamicLayout::LoadResource](#loadresource)|AFX_DIALOG_LAYOUT リソースから動的レイアウトを読み取り、ホスト ウィンドウにそのレイアウトを適用します。|
|静的[なCMFCダイナミックレイアウト::移動水平](#movehorizontal)|ユーザーがホスト ウィンドウのサイズを変更したときに、子コントロールが水平方向に移動する量を定義する[MoveSettings](#movesettings_structure)値を取得します。|
|静的[なCMFCダイナミックレイアウト::移動水平および垂直](#movehorizontalandvertical)|ユーザーがホスト ウィンドウのサイズを変更したときに、子コントロールが水平方向に移動する量を定義する[MoveSettings](#movesettings_structure)値を取得します。|
|静的[な CMFC ダイナミック レイアウト::移動なし](#movenone)|子コントロールのモーション (垂直または水平) を表す[MoveSettings](#movesettings_structure)値を取得します。|
|静的[な CMFC ダイナミック レイアウト::移動垂直](#movevertical)|ユーザーがホスト ウィンドウのサイズを変更するときに、子コントロールが垂直方向に移動する量を定義する[MoveSettings](#movesettings_structure)値を取得します。|
|[CMFCDynamicLayout::SetMinSize](#setminsize)|ウィンドウ サイズをレイアウト調整の下限に設定します。|
|静的[なCMFCダイナミックレイアウト::サイズ水平](#sizehorizontal)|ユーザーがホスト ウィンドウのサイズを変更したときに、子コントロールのサイズを水平方向に変更する量を定義する[SizeSettings](#sizesettings_structure)値を取得します。|
|静的[なCMFCダイナミックレイアウト::サイズ水平および垂直](#sizehorizontalandvertical)|ユーザーがホスト ウィンドウのサイズを変更したときに、子コントロールのサイズを水平方向に変更する量を定義する[SizeSettings](#sizesettings_structure)値を取得します。|
|静的[な CMFC ダイナミック レイアウト::サイズなし](#sizenone)|子コントロールのサイズの変更を表す[SizeSettings](#sizesettings_structure)値を取得します。|
|静的[なCMFCダイナミックレイアウト::サイズ垂直](#sizevertical)|ユーザーがホスト ウィンドウのサイズを変更するときに、子コントロールの垂直方向のサイズを指定する[SizeSettings](#sizesettings_structure)値を取得します。|

## <a name="nested-types"></a>入れ子にされた型

|名前|説明|
|----------|-----------------|
|[CMFCDynamicLayout::MoveSettings 構造体](#movesettings_structure)|動的レイアウトでのコントロールの移動データをカプセル化します。|
|[CMFCDynamicLayout::SizeSettings 構造体](#sizesettings_structure)|動的レイアウトでのコントロールのサイズ変更データをカプセル化します。|

## <a name="remarks"></a>解説

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxlayout.h

## <a name="cmfcdynamiclayoutadditem"></a><a name="additem"></a>をクリックしてレイアウトを変更します。

子ウィンドウ (通常はコントロール) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。

```
BOOL AddItem(
    HWND hwnd,
    MoveSettings moveSettings SizeSettings sizeSettings);

BOOL AddItem(
    int nID,
    MoveSettings moveSettings SizeSettings sizeSettings);
```

### <a name="parameters"></a>パラメーター

*Hwnd*<br/>
追加するウィンドウへのハンドル。

*nID*<br/>
追加する子コントロールの ID。

*設定を移動します。*<br/>
ウィンドウ サイズの変更に合わせてコントロールを移動する方法を記述する構造体。

*サイズ設定*<br/>
ウィンドウ サイズの変更に合わせてコントロールのサイズを変更する方法を記述する構造体。

### <a name="return-value"></a>戻り値

項目が正常に追加された場合は true。それ以外の場合は false。

### <a name="remarks"></a>解説

ホスティング ウィンドウのサイズを変更するとき、子コントロールの位置とサイズが動的に変更されます。

## <a name="cmfcdynamiclayoutadjust"></a><a name="adjust"></a>CMFC ダイナミック レイアウト::調整

子ウィンドウ (通常はコントロール) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。

```
void Adjust();
```

### <a name="remarks"></a>解説

ホスティング ウィンドウのサイズを変更するとき、子コントロールの位置とサイズが動的に変更されます。

## <a name="cmfcdynamiclayoutcreate"></a><a name="create"></a>CMFC ダイナミック レイアウト::作成

ホスト ウィンドウを格納し、検証します。

```
BOOL Create(CWnd* pHostWnd);
```

### <a name="parameters"></a>パラメーター

*pHostWnd*<br/>
ホスト ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

作成が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutgethostwnd"></a><a name="gethostwnd"></a>をクリックします。

ホスト ウィンドウへのポインターを返します。

```
CWnd* GetHostWnd();
```

### <a name="return-value"></a>戻り値

ホスト ウィンドウへのポインター。

### <a name="remarks"></a>解説

既定では、すべての子コントロールの位置はこのウィンドウに合わせて再計算されます。

## <a name="cmfcdynamiclayoutgetminsize"></a><a name="getminsize"></a>ウィンドウスダイナミックレイアウト::ゲットミンサイズ

レイアウト調整の下限のウィンドウ サイズを返します。

```
CSize GetMinSize();
```

### <a name="return-value"></a>戻り値

レイアウト調整の下限のウィンドウ サイズ。

### <a name="remarks"></a>解説

ホスティング ウィンドウのサイズ変更が行われると、子コントロールの位置とサイズが動的に変更されます。ただし、コントロールは最小サイズが決まっており、これを下回った場合にはレイアウトが調整されません。 ウィンドウ サイズをこの最小サイズよりも小さくすることは可能ですが、その場合、ウィンドウの一部がビューに表示されなくなります。

## <a name="cmfcdynamiclayoutgetwindowrect"></a><a name="getwindowrect"></a>ウィンドウのダイナミック レイアウト::取得ウィンドウの Rect

ウィンドウの現在のクライアント領域の長方形を取得します。

```
void GetHostWndRect(CRect& rect,);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
関数から制御が戻った後、このパラメーターにはレイアウト領域に外接する四角形が含まれています。 これは out パラメーターです。入力値は上書きされます。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayouthasitem"></a><a name="hasitem"></a>を表します。

子コントロールが動的レイアウトに追加されたかどうかを確認します。

```
BOOL HasItem(HWND hwnd);
```

### <a name="parameters"></a>パラメーター

*Hwnd*<br/>
コントロールのウィンドウ ハンドル。

### <a name="return-value"></a>戻り値

この項目がレイアウトに既に存在する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutisempty"></a><a name="isempty"></a>CMFC ダイナミック レイアウト::IsEmpty

動的なレイアウトに子ウィンドウが追加されていないことを確認します。

```
BOOL IsEmpty();
```

### <a name="return-value"></a>戻り値

レイアウトに項目がない場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutloadresource"></a><a name="loadresource"></a>リソースを読み込む

AFX_DIALOG_LAYOUT リソースから動的レイアウトを読み取り、ホスト ウィンドウにそのレイアウトを適用します。

```
static BOOL LoadResource(CWnd* pHostWnd,
    LPVOID lpResource,
    DWORD dwSize);
```

### <a name="parameters"></a>パラメーター

*pHostWnd*<br/>
ホスト ウィンドウへのポインター。

*リソースを指定します。*<br/>
AFX_DIALOG_LAYOUT リソースが含まれるバッファーへのポインター。

*Dwsize*<br/>
バイト単位のバッファー サイズ。

### <a name="return-value"></a>戻り値

リソースが読み込まれ、ホスト ウィンドウに適用される場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutmovehorizontal"></a><a name="movehorizontal"></a>CMFC ダイナミック レイアウト::移動水平

ユーザーがホスト ウィンドウのサイズを変更したときに、子コントロールが水平方向に移動する量を定義する[MoveSettings](#movesettings_structure)値を取得します。

```
static MoveSettings MoveHorizontal(int nRatio);
```

### <a name="parameters"></a>パラメーター

*n比率*<br/>
ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールを水平方向に移動する量をパーセンテージとして定義します。

### <a name="return-value"></a>戻り値

要求された移動率をカプセル化する[MoveSettings](#movesettings_structure)値。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutmovehorizontalandvertical"></a><a name="movehorizontalandvertical"></a>CMFC ダイナミック レイアウト::移動水平および垂直

ユーザーがホスト ウィンドウのサイズを変更したときに、子コントロールが水平方向に移動する量を定義する[MoveSettings](#movesettings_structure)値を取得します。

```
static MoveSettings MoveHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>パラメーター

*NXRatio*<br/>
ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールを水平方向に移動する量をパーセンテージとして定義します。

*nYRatio*<br/>
ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールを垂直方向に移動する量をパーセンテージとして定義します。

### <a name="return-value"></a>戻り値

要求された移動率をカプセル化する[MoveSettings](#movesettings_structure)値。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutmovenone"></a><a name="movenone"></a>CMFC ダイナミック レイアウト::ムーブノー

子コントロールのモーション (垂直または水平) を表す[MoveSettings](#movesettings_structure)値を取得します。

```
static MoveSettings MoveNone();
```

### <a name="return-value"></a>戻り値

ユーザーがホスト ウィンドウのサイズを変更しても移動しないように、コントロールを固定する[MoveSettings](#movesettings_structure)値。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutmovesettings-structure"></a><a name="movesettings_structure"></a>CMFC ダイナミック レイアウト::ムーブ設定の構造

動的レイアウトでのコントロールの移動データをカプセル化します。

```
struct CMFCDynamicLayout::MoveSettings;
```

### <a name="remarks"></a>解説

これは、`CMFCDynamicLayout` 内の入れ子にされたクラスです。

## <a name="cmfcdynamiclayoutmovesettingsishorizontal"></a>CMFC ダイナミック レイアウト::移動設定::イス水平

データの移動が 0 以外の水平方向の移動を指定しているかどうかを確認します。

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>戻り値

`MoveSettings` オブジェクトが 0 以外の水平方向の移動を指定している場合は TRUE です。

## <a name="cmfcdynamiclayoutmovesettingsisnone"></a>CMFC ダイナミック レイアウト::移動設定::IsNone

移動データが移動なしを指定しているかどうかを確認します。

```
BOOL IsNone() const
```

## <a name="return-value"></a>戻り値

`MoveSettings` オブジェクトが移動なしを指定している場合は TRUE です。

## <a name="cmfcdynamiclayoutmovesettingsisvertical"></a>CMFC ダイナミック レイアウト::移動設定::イスタティカル

データの移動が 0 以外の垂直方向の移動を指定しているかどうかを確認します。

```
BOOL IsVertical() const
```

## <a name="return-value"></a>戻り値

`MoveSettings` オブジェクトが 0 以外の垂直方向の移動を指定している場合は TRUE です。

## <a name="cmfcdynamiclayoutmovevertical"></a><a name="movevertical"></a>CMFC ダイナミック レイアウト::移動垂直

ユーザーがホスト ウィンドウのサイズを変更するときに、子コントロールが垂直方向に移動する量を定義する[MoveSettings](#movesettings_structure)値を取得します。

```
static MoveSettings MoveVertical(int nRatio);
```

### <a name="parameters"></a>パラメーター

*n比率*<br/>
ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールを垂直方向に移動する量をパーセンテージとして定義します。

### <a name="return-value"></a>戻り値

要求された移動率をカプセル化する[MoveSettings](#movesettings_structure)値。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutsetminsize"></a><a name="setminsize"></a>を組み込む

ウィンドウ サイズをレイアウト調整の下限に設定します。

```
void SetMinSize(const CSize& size);
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
レイアウト調整が可能な最小サイズ。

### <a name="remarks"></a>解説

ホスティング ウィンドウのサイズ変更が行われると、子コントロールの位置とサイズが動的に変更されます。ただし、コントロールは最小サイズが決まっており、これを下回った場合にはレイアウトが調整されません。 ウィンドウ サイズをこの最小サイズよりも小さくすることは可能ですが、その場合、ウィンドウの一部がビューに表示されなくなります。

## <a name="cmfcdynamiclayoutsizehorizontal"></a><a name="sizehorizontal"></a>CMFC ダイナミック レイアウト::サイズ水平

ユーザーがホスト ウィンドウのサイズを変更したときに、子コントロールのサイズを水平方向に変更する量を定義する[SizeSettings](#sizesettings_structure)値を取得します。

```
static SizeSettings SizeHorizontal(int nRatio);
```

### <a name="parameters"></a>パラメーター

*n比率*<br/>
ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールの水平方向のサイズを変更する量をパーセンテージとして定義します。

### <a name="return-value"></a>戻り値

要求されたサイズの比率をカプセル化するサイズ[設定](#sizesettings_structure)値。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutsizehorizontalandvertical"></a><a name="sizehorizontalandvertical"></a>CMFC ダイナミック レイアウト::サイズ水平および垂直

ユーザーがホスト ウィンドウのサイズを変更したときに、子コントロールのサイズを水平方向に変更する量を定義する[SizeSettings](#sizesettings_structure)値を取得します。

```
static SizeSettings SizeHorizontalAndVertical(int nXRatio int nYRatio);
```

### <a name="parameters"></a>パラメーター

*NXRatio*<br/>
ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールの水平方向のサイズを変更する量をパーセンテージとして定義します。

*nYRatio*<br/>
ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールの垂直方向のサイズを変更する量をパーセンテージとして定義します。

### <a name="return-value"></a>戻り値

要求されたサイズの比率をカプセル化するサイズ[設定](#sizesettings_structure)値。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutsizenone"></a><a name="sizenone"></a>CMFC ダイナミック レイアウト::サイズなし

子コントロールのサイズの変更を表す[SizeSettings](#sizesettings_structure)値を取得します。

```
static SizeSettings SizeNone();
```

### <a name="return-value"></a>戻り値

ユーザーがホスト ウィンドウのサイズを変更してもサイズが変更されないように、コントロールを特定のサイズで固定する[SizeSettings](#sizesettings_structure)値。

### <a name="remarks"></a>解説

## <a name="cmfcdynamiclayoutsizesettings-structure"></a><a name="sizesettings_structure"></a>CMFC ダイナミック レイアウト::サイズ設定の構造

動的レイアウトでのコントロールのサイズ変更データをカプセル化します。

```
struct CMFCDynamicLayout::SizeSettings;
```

### <a name="remarks"></a>解説

これは、`CMFCDynamicLayout` 内の入れ子にされたクラスです。

## <a name="cmfcdynamiclayoutsizesettingsishorizontal"></a>CMFC ダイナミック レイアウト::サイズ設定::イス水平

サイズ変更データが、0 以外の水平方向のサイズ変更枠を指定しているかどうかを確認します。

```
BOOL IsHorizontal() const
```

## <a name="return-value"></a>戻り値

`SizeSettings` オブジェクトが、0 以外の水平方向のサイズ変更枠を指定している場合は TRUE です。

## <a name="cmfcdynamiclayoutsizesettingsisnone"></a>ウィンドウスダイナミックレイアウト::サイズ設定::IsNone

サイズ変更データが、サイズ変更枠を指定していないかどうかを確認します。

```
BOOL IsNone() const
```

## <a name="return-value"></a>戻り値

`SizeSettings` オブジェクトがサイズ変更枠を指定しない場合は TRUE です。

## <a name="cmfcdynamiclayoutsizesettingsisvertical"></a>ウィンドウスダイナミックレイアウト::サイズ設定::IsVertical

サイズ変更データが、0 以外の垂直方向のサイズ変更枠を指定しているかどうかを確認します。

```
BOOL IsVertical() const
```

## <a name="return-value"></a>戻り値

`SizeSettings` オブジェクトが、0 以外の垂直方向のサイズ変更枠を指定している場合は TRUE です。

## <a name="cmfcdynamiclayoutsizevertical"></a><a name="sizevertical"></a>CMFC ダイナミック レイアウト::サイズ垂直

ユーザーがホスト ウィンドウのサイズを変更するときに、子コントロールの垂直方向のサイズを指定する[SizeSettings](#sizesettings_structure)値を取得します。

```
static SizeSettings SizeVertical(int nRatio);
```

### <a name="parameters"></a>パラメーター

*n比率*<br/>
ユーザーによってホスト ウィンドウのサイズが変更されたときに子コントロールの垂直方向のサイズを変更する量をパーセンテージとして定義します。

### <a name="return-value"></a>戻り値

要求されたサイズの比率をカプセル化するサイズ[設定](#sizesettings_structure)値。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
