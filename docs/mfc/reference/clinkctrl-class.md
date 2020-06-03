---
title: CLinkCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
helpviewer_keywords:
- CLinkCtrl [MFC], CLinkCtrl
- CLinkCtrl [MFC], Create
- CLinkCtrl [MFC], CreateEx
- CLinkCtrl [MFC], GetIdealHeight
- CLinkCtrl [MFC], GetIdealSize
- CLinkCtrl [MFC], GetItem
- CLinkCtrl [MFC], GetItemID
- CLinkCtrl [MFC], GetItemState
- CLinkCtrl [MFC], GetItemUrl
- CLinkCtrl [MFC], HitTest
- CLinkCtrl [MFC], SetItem
- CLinkCtrl [MFC], SetItemID
- CLinkCtrl [MFC], SetItemState
- CLinkCtrl [MFC], SetItemUrl
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
ms.openlocfilehash: aa1f630b448c60a0eeb6a905ed6eef6f84a2ff8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372249"
---
# <a name="clinkctrl-class"></a>CLinkCtrl クラス

Windows コモン SysLink コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CLinkCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次のリンク::CリンクCtrl](#clinkctrl)|`CLinkCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クリックキー::作成](#create)|リンク コントロールを作成し、`CLinkCtrl`オブジェクトにアタッチします。|
|[クリンクCtrl::作成Ex](#createex)|拡張スタイルを持つリンク コントロールを作成し、オブジェクト`CLinkCtrl`にアタッチします。|
|[次の値を取得します。](#getidealheight)|リンク コントロールの理想的な高さを取得します。|
|[次の値を取得します。](#getidealsize)|リンクの指定された幅に応じて、現在のリンク コントロールのリンク テキストの優先高さを計算します。|
|[次の項目を取得します。](#getitem)|リンク コントロール項目の状態と属性を取得します。|
|[次の項目 ID を取得します。](#getitemid)|リンク コントロールアイテムの ID を取得します。|
|[をクリックします。](#getitemstate)|リンク コントロール項目の状態を取得します。|
|[次の項目を取得します。](#getitemurl)|リンク コントロール アイテムによって表される URL を取得します。|
|[クリックキー::ヒットテスト](#hittest)|指定したリンクをユーザーがクリックしたかどうかを判断します。|
|[次の項目を選択します。](#setitem)|リンク コントロール アイテムの状態と属性を設定します。|
|[をクリックします。](#setitemid)|リンク コントロール アイテムの ID を設定します。|
|[をクリックします。](#setitemstate)|リンク コントロール項目の状態を設定します。|
|[次の項目を選択します。](#setitemurl)|リンク コントロール アイテムによって表される URL を設定します。|

## <a name="remarks"></a>解説

"リンク コントロール" は、ハイパーテキスト リンクをウィンドウに埋め込む便利な方法です。 実際のコントロールは、マークアップテキストをレンダリングし、ユーザーが埋め込みリンクをクリックしたときに適切なアプリケーションを起動するウィンドウです。 複数のリンクは 1 つのコントロール内でサポートされ、0 から始まるインデックスからアクセスできます。

このコントロール (および`CLinkCtrl`クラス) は、Windows XP 以降で実行されているプログラムでのみ使用できます。

詳細については、Windows SDK[の「SysLink コントロール](/windows/win32/Controls/syslink-overview)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CLinkCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="clinkctrlclinkctrl"></a><a name="clinkctrl"></a>次のリンク::CリンクCtrl

`CLinkCtrl` オブジェクトを構築します。

```
CLinkCtrl();
```

## <a name="clinkctrlcreate"></a><a name="create"></a>クリックキー::作成

リンク コントロールを作成し、`CLinkCtrl`オブジェクトにアタッチします。

```
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*マークアップ*<br/>
表示するマークアップ されたテキストを含む、0 で終わる文字列へのポインター。 詳細については、 [SysLink コントロールの概要](/windows/win32/Controls/syslink-overview)のトピックの「マークアップとリンク アクセス」を参照してください。

*Dwstyle*<br/>
リンク コントロールのスタイルを指定します。 コントロール スタイルの任意の組み合わせを適用します。 詳細については、「 の[一般的なコントロール スタイル](/windows/win32/Controls/common-control-styles)」`Windows SDK`を参照してください。

*Rect*<br/>
リンク コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
リンク コントロールの親ウィンドウを指定します。 NULL にすることはできません。

*nID*<br/>
リンク コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトは`CLinkCtrl`2 つの手順で作成します。 まず、コンストラクタを呼び出し`Create`、次に`CLinkCtrl`を呼び出します。 コントロールで拡張ウィンドウ スタイルを使用する場合は、代わりに[CLinkCtrl::CreateEx](#createex)を呼び出`Create`します。

メソッドの 2`Create`番目の形式は非推奨です。 パラメーターを指定する最初の形式*を*使用します。

### <a name="example"></a>例

2 つのリンク コントロールにアクセスするために`m_Link1`使用`m_Link2`される 2 つの変数を定義するコード例を次に示します。

[!code-cpp[NVC_MFC_CLinkCtrl_s1#2](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]

### <a name="example"></a>例

次のコード例では、別のリンク コントロールの場所に基づいてリンク コントロールを作成します。 リソース ローダーは、アプリケーションの起動時に最初のリンク コントロールを作成します。 アプリケーションが OnInitDialog メソッドを入力すると、最初のリンク コントロールの位置を基準にして、2 番目のリンク コントロールが作成されます。 次に、2 番目のリンク コントロールのサイズを、表示されるテキストに合わせて変更します。

[!code-cpp[NVC_MFC_CLinkCtrl_s1#1](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]

## <a name="clinkctrlcreateex"></a><a name="createex"></a>クリンクCtrl::作成Ex

拡張スタイルを持つリンク コントロールを作成し、オブジェクト`CLinkCtrl`にアタッチします。

```
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);

virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```

### <a name="parameters"></a>パラメーター

*マークアップ*<br/>
表示するマークアップ されたテキストを含む、0 で終わる文字列へのポインター。 詳細については、 [SysLink コントロールの概要](/windows/win32/Controls/syslink-overview)のトピックの「マークアップとリンク アクセス」を参照してください。

*ドウェエクススタイル*<br/>
リンク コントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の*DwExStyle*パラメーター[を](/windows/win32/api/winuser/nf-winuser-createwindowexw)参照してください。

*Dwstyle*<br/>
リンク コントロールのスタイルを指定します。 コントロール スタイルの任意の組み合わせを適用します。 詳細については、Windows SDK[の「コモン コントロール スタイル](/windows/win32/Controls/common-control-styles)」を参照してください。

*Rect*<br/>
リンク コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
リンク コントロールの親ウィンドウを指定します。 NULL にすることはできません。

*nID*<br/>
リンク コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

拡張`CreateEx`Windows スタイル定数を適用するには[、[作成]](#create)の代わりに使用します。

メソッドの 2`CreateEx`番目の形式は非推奨です。 パラメーターを指定する最初の形式*を*使用します。

## <a name="clinkctrlgetidealheight"></a><a name="getidealheight"></a>次の値を取得します。

リンク コントロールの理想的な高さを取得します。

```
int GetIdealHeight() const;
```

### <a name="return-value"></a>戻り値

コントロールの理想的な高さ (ピクセル単位)。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[LM_GETIDEALHEIGHT](/windows/win32/Controls/lm-getidealheight)の動作を実装します。

## <a name="clinkctrlgetidealsize"></a><a name="getidealsize"></a>次の値を取得します。

リンクの指定された幅に応じて、現在のリンク コントロールのリンク テキストの優先高さを計算します。

```
int GetIdealSize(
    int cxMaxWidth,
    SIZE* pSize) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*最大幅*|[in]リンクの最大幅 (ピクセル単位)。|
|[アウト]\**サイズ*|Windows[サイズ](/windows/win32/api/windef/ns-windef-size)構造体へのポインター。 このメソッドが返されるときに、*cy*`SIZE`構造体の cy メンバーには *、cxMaxWidth*で指定されたリンク テキスト幅に最適なリンク テキストの高さが含まれています。 構造体の*cx*メンバーには、実際に必要なリンク テキストの幅が含まれています。|

### <a name="return-value"></a>戻り値

リンク テキストの推奨される高さ (ピクセル単位)。 戻り値は、`SIZE`構造体の*cy*メンバーの値と同じです。

### <a name="remarks"></a>解説

`GetIdealSize`メソッドの例については[、「CLinkCtrl::Create」](#create)の例を参照してください。

このメソッドは、Windows SDK で説明されている[LM_GETIDEALSIZE](/windows/win32/Controls/lm-getidealsize)メッセージを送信します。

## <a name="clinkctrlgetitem"></a><a name="getitem"></a>次の項目を取得します。

リンク コントロール項目の状態と属性を取得します。

```
BOOL GetItem(PLITEM pItem) const;
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
項目情報を受け取る[LITEM](/windows/win32/api/commctrl/ns-commctrl-litem)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[LM_GETITEM](/windows/win32/Controls/lm-getitem)の動作を実装します。

## <a name="clinkctrlgetitemid"></a><a name="getitemid"></a>次の項目 ID を取得します。

リンク コントロールアイテムの ID を取得します。

```
BOOL GetItemID(
    int iLink,
    CString& strID) const;

BOOL GetItemID(
    int iLink,
    LPWSTR szID,
    UINT cchID) const;
```

### <a name="parameters"></a>パラメーター

*アイリンク*<br/>
リンク コントロール項目のインデックス。

*strID*<br/>
指定した項目の ID を含む[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト。

*szID*<br/>
指定された項目の ID を含む null で終わる文字列。

*cchID*<br/>
*szID*バッファーのサイズ (文字数)。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

> [!NOTE]
> この関数は *、szID または strID*のバッファーが MAX_LINKID_TEXT より小さい場合にも FALSE を返します。

### <a name="remarks"></a>解説

特定のリンク コントロール 項目の ID を取得します。 詳細については、Windows SDK の Win32 メッセージ[LM_GETITEM](/windows/win32/Controls/lm-getitem)を参照してください。

## <a name="clinkctrlgetitemstate"></a><a name="getitemstate"></a>をクリックします。

リンク コントロール項目の状態を取得します。

```
BOOL GetItemState(
    int iLink,
    UINT* pnState,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;
```

### <a name="parameters"></a>パラメーター

*アイリンク*<br/>
リンク コントロール項目のインデックス。

*プンステート*<br/>
指定した状態項目の値。

*ステートマスク*<br/>
取得する状態項目を記述するフラグの組み合わせ。 値のリストについては[、LITEM](/windows/win32/api/commctrl/ns-commctrl-litem)構造体のメンバー`state`の説明を参照してください。 許可される項目は、 で`state`許可されているものと同じです。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

特定のリンク コントロール項目の指定された状態項目の値を取得します。 詳細については、Windows SDK の Win32 メッセージ[LM_GETITEM](/windows/win32/Controls/lm-getitem)を参照してください。

## <a name="clinkctrlgetitemurl"></a><a name="getitemurl"></a>次の項目を取得します。

リンク コントロール アイテムによって表される URL を取得します。

```
BOOL GetItemUrl(
    int iLink,
    CString& strUrl) const;

BOOL GetItemUrl(
    int iLink,
    LPWSTR szUrl,
    UINT cchUrl) const;
```

### <a name="parameters"></a>パラメーター

*アイリンク*<br/>
リンク コントロール項目のインデックス。

*ストルUrl*<br/>
指定されたアイテムによって表される URL を含む[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクト

*スズUrl*<br/>
指定されたアイテムによって表される URL を含む null で終わる文字列

*cchUrl*<br/>
*szURL*バッファーのサイズ (文字数)。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

> [!NOTE]
> この関数は *、szUrl または strUrl*のバッファーがMAX_LINKID_TEXTより小さい場合にも FALSE を返します。

### <a name="remarks"></a>解説

指定したリンク コントロール アイテムで表される URL を取得します。 詳細については、Windows SDK の Win32 メッセージ[LM_GETITEM](/windows/win32/Controls/lm-getitem)を参照してください。

## <a name="clinkctrlhittest"></a><a name="hittest"></a>クリックキー::ヒットテスト

指定したリンクをユーザーがクリックしたかどうかを判断します。

```
BOOL HitTest(PLHITTESTINFO phti) const;
```

### <a name="parameters"></a>パラメーター

*フティ*<br/>
ユーザーがクリック`LHITTESTINFO`したリンクに関する情報を含む構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[LM_HITTEST](/windows/win32/Controls/lm-hittest)の動作を実装します。

## <a name="clinkctrlsetitem"></a><a name="setitem"></a>次の項目を選択します。

リンク コントロール アイテムの状態と属性を設定します。

```
BOOL SetItem(PLITEM pItem);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
設定する情報を含む[LITEM](/windows/win32/api/commctrl/ns-commctrl-litem)構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[LM_SETITEM](/windows/win32/Controls/lm-setitem)の動作を実装します。

## <a name="clinkctrlsetitemid"></a><a name="setitemid"></a>をクリックします。

リンク コントロールアイテムの ID を取得します。

```
BOOL SetItemID(
    int iLink,
    LPCWSTR szID);
```

### <a name="parameters"></a>パラメーター

*アイリンク*<br/>
リンク コントロール項目のインデックス。

*szID*<br/>
指定された項目の ID を含む null で終わる文字列。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

特定のリンク コントロール アイテムの ID を設定します。 詳細については、Windows SDK の Win32 メッセージ[LM_SETITEM](/windows/win32/Controls/lm-setitem)を参照してください。

## <a name="clinkctrlsetitemstate"></a><a name="setitemstate"></a>をクリックします。

リンク コントロール項目の状態を取得します。

```
BOOL SetItemState(
    int iLink,
    UINT state,
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```

### <a name="parameters"></a>パラメーター

*アイリンク*<br/>
リンク コントロール項目のインデックス。

*プンステート*<br/>
設定されている指定された状態項目の値。

*ステートマスク*<br/>
設定されている状態項目を記述するフラグの組み合わせ。 値のリストについては[、LITEM](/windows/win32/api/commctrl/ns-commctrl-litem)構造体のメンバー`state`の説明を参照してください。 許可される項目は、 で`state`許可されているものと同じです。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

特定のリンク コントロール アイテムの指定された状態項目の値を設定します。 詳細については、Windows SDK の Win32 メッセージ[LM_SETITEM](/windows/win32/Controls/lm-setitem)を参照してください。

## <a name="clinkctrlsetitemurl"></a><a name="setitemurl"></a>次の項目を選択します。

リンク コントロール アイテムによって表される URL を設定します。

```
BOOL SetItemUrl(
    int iLink,
    LPCWSTR szUrl);
```

### <a name="parameters"></a>パラメーター

*アイリンク*<br/>
リンク コントロール項目のインデックス。

*スズUrl*<br/>
指定されたアイテムによって表される URL を含む null で終わる文字列

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

指定したリンク コントロール アイテムで表される URL を設定します。 詳細については、Windows SDK の Win32 メッセージ[LM_SETITEM](/windows/win32/Controls/lm-setitem)を参照してください。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)
