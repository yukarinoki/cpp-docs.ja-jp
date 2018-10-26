---
title: CMFCDropDownToolbarButton クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c113ce68cf609970342d69ebc03f700e17c7e2a9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064317"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton クラス

ツール バー ボタンの一種で、クリックされたときは標準ボタンと同じように動作します。 ただし、ドロップダウン ツールバーを開きます ( [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)押すし、ツール バー ボタンを押したかどうか。

## <a name="syntax"></a>構文

```
class CMFCDropDownToolbarButton : public CMFCToolBarButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|`CMFCDropDownToolbarButton` オブジェクトを構築します。|
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|現在のボタンには、別のツール バー ボタンのプロパティをコピーします。 (上書き[CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom))。|
|`CMFCDropDownToolbarButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|ドロップダウン ツール バーが表示されます。|
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|ツール バー ボタンからメニューにテキストをコピーします。 (上書き[CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton))。|
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|ドロップダウン ツール バー ボタンに関連付けられているを取得します。|
|`CMFCDropDownToolbarButton::GetThisClass`|ポインターを取得する、framework によって使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|ドロップダウン ツール バーが現在開いているかどうかを判断します。|
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|拡張された境界で、ボタンを表示できるかどうかを判断します。 (上書き[CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize))。|
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|指定したデバイス コンテキストおよびドッキング状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))。|
|`CMFCDropDownToolbarButton::OnCancelMode`|処理するためにフレームワークによって呼び出されます、 [WM_CANCELMODE](/windows/desktop/winmsg/wm-cancelmode)メッセージ。 ( `CMCToolBarButton::OnCancelMode`をオーバーライドします)。|
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd))。|
|[CMFCDropDownToolbarButton::OnClick](#onclick)|ユーザーがマウス ボタンをクリックすると、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick))。|
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|ユーザーがマウス ボタンを離したときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup))。|
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|親ツールバー領域メッセージを処理するときに、フレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp))。|
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|アプリケーションが親ツールバーのショートカット メニューを表示するときは、指定されたメニューを変更します。 (上書き[CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu))。|
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。 (上書き[CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw))。|
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|ボタンを描画するためにフレームワークによって呼び出されます、**コマンド**のウィンドウ、**カスタマイズ** ダイアログ ボックス。 (上書き[CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist))。|
|[CMFCDropDownToolbarButton::Serialize](#serialize)|アーカイブからこのオブジェクトを読み取りまたはアーカイブに書き込みます。 (上書き[CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize))。|
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|ユーザーがボタンをクリックしたときにフレームワークによって使用される既定のコマンドを設定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|ユーザーは、ドロップダウン ツールバーが表示されるまでに、ダウンのマウス ボタンを保持する必要がある時間の長さを指定します。|

## <a name="remarks"></a>Remarks

A`CMFCDropDownToolBarButton`ボタンの右下隅に小さな矢印がある点で通常のボタンは異なります。 ドロップダウン ツール バーにユーザーがボタンを選択すると、フレームワークには、最上位レベルのツール バー ボタン (右上隅にある小さな矢印の付いたボタン) 上のアイコンが表示されます。

ドロップダウン ツール バーを実装する方法については、次を参照してください。 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)します。

`CMFCDropDownToolBarButton`にオブジェクトをエクスポートできる、 [CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)オブジェクトし、ポップアップ メニューがメニュー ボタンとして表示されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdropdowntoolbar.h

##  <a name="copyfrom"></a>  CMFCDropDownToolbarButton::CopyFrom

現在のボタンには、別のツール バー ボタンのプロパティをコピーします。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]コピー元のソースボタンへの参照。

### <a name="remarks"></a>Remarks

このツール バー ボタンに別のツール バー ボタンをコピーするには、このメソッドを呼び出します。 *src*型でなければなりません`CMFCDropDownToolbarButton`します。

##  <a name="cmfcdropdowntoolbarbutton"></a>  CMFCDropDownToolbarButton::CMFCDropDownToolbarButton

`CMFCDropDownToolbarButton` オブジェクトを構築します。

```
CMFCDropDownToolbarButton();

CMFCDropDownToolbarButton(
    LPCTSTR lpszName,
    CMFCDropDownToolBar* pToolBar);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
[in]ボタンの既定のテキスト。

*pToolBar*<br/>
[in]ポインター、`CMFCDropDownToolBar`ユーザーがボタンを押したときに表示されるオブジェクト。

### <a name="remarks"></a>Remarks

コンス トラクターの 2 番目のオーバー ロードからにコピー ドロップダウン ボタンの最初のボタン、ツールバーを*pToolBar*を指定します。

ドロップダウン ツール バー ボタンが通常、ツールバーの最近使用したボタンのテキストを使用する*pToolBar*を指定します。 指定されたテキストを使用して*lpszName*ボタンがメニュー ボタンに変換またはが表示されます、**コマンド**のタブ、**カスタマイズ** ダイアログ ボックス。 詳細については、**カスタマイズ**ダイアログ ボックスを参照してください[CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)します。

### <a name="example"></a>例

次の例のオブジェクトを構築する方法、`CMFCDropDownToolbarButton`クラス。 このコード スニペットの一部、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]

##  <a name="dropdowntoolbar"></a>  CMFCDropDownToolbarButton::DropDownToolbar

ドロップダウン ツール バーが表示されます。

```
BOOL DropDownToolbar(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]フレームのドロップ ダウン、またはドロップダウン ツール バー ボタンの親ウィンドウを使用して NULL の親ウィンドウ。

### <a name="return-value"></a>戻り値

メソッドが成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

[CMFCDropDownToolbarButton::OnClick](#onclick)メソッドを押すし、ツール バー ボタンを押したときに、ドロップダウン ツールバーを開くには、このメソッドを呼び出します。

このメソッドを使用して、ドロップダウン ツールバーを作成し、 [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create)メソッド。 親ツールバーが垂直方向に、ドッキングされている場合は、このメソッドは配置ドロップダウン ツール バー適合しているかに応じて、親ツールバーの左側または右側にあるのいずれか。 それ以外の場合、このメソッドは、親ツールバーの下のドロップダウン ツール バーを配置します。

このメソッドは失敗*我が物*が NULL で、ドロップダウン ツール バー ボタンには、親ウィンドウはありません。

##  <a name="exporttomenubutton"></a>  CMFCDropDownToolbarButton::ExportToMenuButton

ツール バー ボタンからメニューにテキストをコピーします。

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>パラメーター

*メニュー ボタン*<br/>
[in]ターゲットのメニュー ボタンへの参照。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>Remarks

このメソッドは、基本クラスの実装を呼び出します ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) し、このボタンの各ツールバーのメニュー項目を含むポップアップ メニュー ターゲット メニュー ボタンを追加します。 このメソッドは、ポップアップ メニューにサブメニューを追加しません。

このメソッドは失敗、親ツールバー `m_pToolBar`、null または基本クラスの実装が FALSE を返します。

##  <a name="getdropdowntoolbar"></a>  CMFCDropDownToolbarButton::GetDropDownToolBar

ドロップダウン ツール バー ボタンに関連付けられているを取得します。

```
CMFCToolBar* GetDropDownToolBar() const;
```

### <a name="return-value"></a>戻り値

ドロップダウン ツール バー ボタンに関連付けられています。

### <a name="remarks"></a>Remarks

このメソッドが戻る、`m_pToolBar`データ メンバー。

##  <a name="isdropdown"></a>  CMFCDropDownToolbarButton::IsDropDown

ドロップダウン ツール バーが現在開いているかどうかを判断します。

```
BOOL IsDropDown() const;
```

### <a name="return-value"></a>戻り値

ドロップダウン ツール バーが現在開いている場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

フレームワークを使用して、ドロップダウン ツールバーを開き、 [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)メソッド。 フレームワークは、ユーザーがドロップダウン ツール バーの非クライアント領域でマウスの左ボタンを押したときにドロップダウン ツール バーを閉じます。

##  <a name="isextrasize"></a>  CMFCDropDownToolbarButton::IsExtraSize

拡張された境界で、ボタンを表示できるかどうかを判断します。

```
virtual BOOL IsExtraSize() const;
```

### <a name="return-value"></a>戻り値

ツール バー ボタンは、拡張された境界で表示できる場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

罫線の拡張の詳細については、次を参照してください。 [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize)します。

##  <a name="m_uishowbardelay"></a>  CMFCDropDownToolbarButton::m_uiShowBarDelay

ユーザーは、ドロップダウン ツールバーが表示されるまでに、ダウンのマウス ボタンを保持する必要がある時間の長さを指定します。

```
static UINT m_uiShowBarDelay;
```

### <a name="remarks"></a>Remarks

遅延時間はミリ秒単位で測定されます。 既定値は 500 です。 別の遅延を設定するには、この共有のデータ メンバーの値を変更します。

##  <a name="oncalculatesize"></a>  CMFCDropDownToolbarButton::OnCalculateSize

指定したデバイス コンテキストおよびドッキング状態のボタンのサイズを計算するためにフレームワークによって呼び出されます。

```
virtual SIZE OnCalculateSize(
    CDC* pDC,
    const CSize& sizeDefault,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*sizeDefault*<br/>
[in]ボタンの既定のサイズ。

*bHorz*<br/>
[in]親ツールバーのドッキング状態。 このパラメーターは、ツールバーが垂直方向にドッキングされている場合は、ツールバーが水平方向にドッキングされているかがフローティングする場合は TRUE または FALSE です。

### <a name="return-value"></a>戻り値

A `SIZE` (ピクセル単位)、ボタンの大きさを格納する構造体。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize))、ボタンのサイズの水平方向にドロップダウン矢印の幅を追加します。

##  <a name="onchangeparentwnd"></a>  CMFCDropDownToolbarButton::OnChangeParentWnd

新しいツールバーにボタンが挿入されたときに、フレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
[in]新しい親ウィンドウです。

### <a name="remarks"></a>Remarks

このメソッドは、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) をテキスト ラベルをオフにして ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) と設定、 [CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext)と[CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton)データ メンバーを FALSE にします。

##  <a name="onclick"></a>  CMFCDropDownToolbarButton::OnClick

ユーザーがマウス ボタンをクリックすると、フレームワークによって呼び出されます。

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]ツール バー ボタンの親ウィンドウ。

*bDelay*<br/>
[in]TRUE の場合、メッセージは、遅延時間で処理する必要があります。

### <a name="return-value"></a>戻り値

ボタンをクリックしてメッセージを処理する場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)、ドロップダウン ツールバーの状態を更新しています。

ユーザーは、ツール バー ボタンをクリックすると、このメソッドで指定した時間の長さが待機するタイマーを作成、 [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)データ メンバーとし、を使用して、ドロップダウンリストが開きますツールバー[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)メソッド。 このメソッドは、ユーザーがツール バー ボタンがクリックして 2 回目のドロップダウン ツール バーを閉じます。

##  <a name="onclickup"></a>  CMFCDropDownToolbarButton::OnClickUp

ユーザーがマウス ボタンを離したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnClickUp();
```

### <a name="return-value"></a>戻り値

ボタンをクリックしてメッセージを処理する場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張[CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup)、ドロップダウン ツールバーの状態を更新しています。

このメソッドは、アクティブである場合、ドロップダウン ツールバー タイマーを停止します。 開いている場合は、ドロップダウン ツールバーを閉じます。

ドロップダウン ツール バーとツールバーのドロップダウン リストのタイマーの詳細については、次を参照してください。 [CMFCDropDownToolbarButton::OnClick](#onclick)します。

##  <a name="oncontexthelp"></a>  CMFCDropDownToolbarButton::OnContextHelp

親ツールバー領域メッセージを処理するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnContextHelp(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]ツール バー ボタンの親ウィンドウ。

### <a name="return-value"></a>戻り値

ボタンは、ヘルプ メッセージを処理する場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) 呼び出すことによって、 [CMFCDropDownToolbarButton::OnClick](#onclick)メソッド*bDelay*を FALSE に設定します。 このメソッドによって返される値を返します[CMFCDropDownToolbarButton::OnClick](#onclick)します。

領域のメッセージの詳細については、次を参照してください。 [TN028: 状況依存ヘルプ サポート](../../mfc/tn028-context-sensitive-help-support.md)します。

##  <a name="oncustomizemenu"></a>  CMFCDropDownToolbarButton::OnCustomizeMenu

アプリケーションが親ツールバーのショートカット メニューを表示するときは、指定されたメニューを変更します。

```
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```

### <a name="parameters"></a>パラメーター

*pMenu*<br/>
[in]カスタマイズするメニュー。

### <a name="return-value"></a>戻り値

このメソッドは、TRUE を返します。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) を次のメニュー項目を無効にします。

- **ボタン イメージのコピー**

- **ボタンの外観**

- **イメージ**

- **[テキスト]**

- **イメージとテキスト**

フレームワークは、カスタマイズ モードで表示されるショートカット メニューを変更するには、このメソッドをオーバーライドします。

##  <a name="ondraw"></a>  CMFCDropDownToolbarButton::OnDraw

指定したスタイルとオプションを使用して、ボタンを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz = TRUE,
    BOOL bCustomizeMode = FALSE,
    BOOL bHighlight = FALSE,
    BOOL bDrawBorder = TRUE,
    BOOL bGrayDisabledButtons = TRUE);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*rect*<br/>
[in]ボタンの外接する四角形。

*pImages*<br/>
[in]ボタンに関連付けられているツール バー イメージのコレクション。

*bHorz*<br/>
[in]親ツールバーのドッキング状態。 ボタンが垂直方向にドッキングされているとき、ボタンを水平方向および FALSE はドッキング時に、このパラメーターは TRUE です。

*bCustomizeMode*<br/>
[in]ツールバーのカスタマイズ モードであるかどうかを指定します。 ツールバーは、ツールバーはカスタマイズ モードでないときにカスタマイズ モードと FALSE であるとき、このパラメーターは TRUE です。

*bHighlight*<br/>
[in]ボタンが強調表示されているかどうかを指定します。 このパラメーターは、ボタンが強調表示されていない場合は、ボタンが強調表示されている場合に TRUE と FALSE です。

*bDrawBorder*<br/>
[in]ボタンの境界線を表示する必要があるかどうかを指定します。 このパラメーターは、TRUE は、ボタンから、ボタンが境界線が表示されない場合に、境界線を FALSE を表示する必要があります。

*bGrayDisabledButtons*<br/>
[in]無効なボタンの影を付けるか、無効なイメージのコレクションを使用するかどうかを指定します。 このメソッドは、無効なイメージのコレクションを使用する必要がありますと、無効になっているボタンを網掛けと FALSE をする場合、このパラメーターは TRUE です。

### <a name="remarks"></a>Remarks

ツールバーのボタンの描画をカスタマイズするには、このメソッドをオーバーライドします。

##  <a name="ondrawoncustomizelist"></a>  CMFCDropDownToolbarButton::OnDrawOnCustomizeList

ボタンを描画するためにフレームワークによって呼び出されます、**コマンド**のウィンドウ、**カスタマイズ** ダイアログ ボックス。

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*rect*<br/>
[in]ボタンの外接する四角形。

*bSelected*<br/>
[in]ボタンが選択されているかどうか。 このパラメーターが TRUE の場合、ボタンが選択されます。 このパラメーターが FALSE の場合、ボタンが選択されていません。

### <a name="return-value"></a>戻り値

指定したデバイス コンテキストにあるボタンのピクセル単位の幅。

### <a name="remarks"></a>Remarks

このメソッドは、カスタマイズ ダイアログ ボックス (**コマンド** タブ)、ボタンがオーナー描画リスト ボックスに表示するために必要な場合。

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) ボタンの名前を変更すると、ボタンのテキスト ラベル (つまりの値に、 *lpszName*パラメーターをコンス トラクターに渡されます)。

##  <a name="serialize"></a>  CMFCDropDownToolbarButton::Serialize

アーカイブからこのオブジェクトを読み取りまたはアーカイブに書き込みます。

```
virtual void Serialize(CArchive& ar);
```

### <a name="parameters"></a>パラメーター

*ar*<br/>
[in]`CArchive`元またはシリアル化するオブジェクト。

### <a name="remarks"></a>Remarks

このメソッドが基底クラスの実装を拡張 ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) 親ツールバーのリソース ID をシリアル化しています。 アーカイブの読み込み時に ([場合](../../mfc/reference/carchive-class.md#isloading)0 以外の値を返します)、このメソッドは、設定、`m_pToolBar`データ メンバーをシリアル化されたリソース ID を含むツールバー

##  <a name="setdefaultcommand"></a>  CMFCDropDownToolbarButton::SetDefaultCommand

ユーザーがボタンをクリックしたときにフレームワークによって使用される既定のコマンドを設定します。

```
void SetDefaultCommand(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*uiCmd*<br/>
[in]既定のコマンドの ID。

### <a name="remarks"></a>Remarks

ユーザーがボタンをクリックしたときに、framework が実行される既定のコマンドを指定するには、このメソッドを呼び出します。 指定されたコマンド ID を持つ項目*uiCmd*親ドロップダウン ツールバーに配置する必要があります。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)<br/>
[CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarMenuButton クラス](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)

