---
title: CReBar クラス
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: c1379d1ef8effea0df564da1b43769bb9a11435d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363931"
---
# <a name="crebar-class"></a>CReBar クラス

Rebar コントロールのレイアウト、永続性、および状態に関する情報を提供するコントロール バーです。

## <a name="syntax"></a>構文

```
class CReBar : public CControlBar
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[クレバー::追加バー](#addbar)|帯をリバーに追加します。|
|[CReBar::作成](#create)|Rebar コントロールを作成し、オブジェクトに`CReBar`アタッチします。|
|[クレバー::ゲットバーCtrl](#getrebarctrl)|基になるコモン コントロールに直接アクセスできるようにします。|

## <a name="remarks"></a>解説

Rebar オブジェクトには、編集ボックス、ツールバー、リスト ボックスなど、さまざまな子ウィンドウ (通常は他のコントロール) を含めることができます。 Rebar オブジェクトは、指定されたビットマップ上に子ウィンドウを表示できます。 アプリケーションで Rebar のサイズを自動的に変更したり、ユーザーがグリップ バーをクリックまたはドラッグして、手動で Rebar のサイズを変更したりできます。

![RebarMenu の例](../../mfc/reference/media/vc4sc61.gif "RebarMenu の例")

## <a name="rebar-control"></a>リバー コントロール

rebar オブジェクトは、ツールバー オブジェクトと同様に動作します。 Rebar は、クリック アンド ドラッグ機構を使用してバンドのサイズを変更します。 Rebar コントロールには 1 つまたは複数のバンドを含めることができ、各バンドはグリッパー バー、ビットマップ、テキスト ラベル、および子ウィンドウの任意の組み合わせを持ちます。 ただし、バンドに複数の子ウィンドウを含めることはできません。

`CReBar`は、その実装を提供するために[CReBarCtrl](../../mfc/reference/crebarctrl-class.md)クラスを使用します。 コントロールのカスタマイズ オプションを利用するには[、GetReBarCtrl](#getrebarctrl)を使用して Rebar コントロールにアクセスできます。 Rebar コントロールの詳細については、を`CReBarCtrl`参照してください。 RebarCtrl の使用の詳細については[、「ReBarCtrl](../../mfc/using-crebarctrl.md)の使用」を参照してください。

> [!CAUTION]
> Rebar コントロール オブジェクトと Rebar コントロール オブジェクトは、MFC コントロール バーのドッキングをサポートしていません。 呼`CRebar::EnableDocking`び出された場合、アプリケーションはアサートします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[コントロールバー](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="crebaraddbar"></a><a name="addbar"></a>クレバー::追加バー

このメンバー関数を呼び出して、帯を Rebar に追加します。

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>パラメーター

*pバー*<br/>
Rebar に`CWnd`挿入される子ウィンドウであるオブジェクトへのポインター。 参照されるオブジェクトには、WS_CHILDが必要です。

*lpszText*<br/>
Rebar に表示するテキストを含む文字列へのポインター。 既定では NULL です。 *lpszText*に含まれるテキストは子ウィンドウの一部ではありません。それは、筋の上にあります。

*pbmp*<br/>
Rebar の`CBitmap`背景に表示されるオブジェクトへのポインター。 既定では NULL です。

*Dwstyle*<br/>
Rebar に適用するスタイルを含む DWORD。 バンド`fStyle`スタイルの完全なリストについては、Win32 構造体[REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow)の関数の説明を参照してください。

*clrFore*<br/>
REBAR の前景色を表す COLORREF 値。

*clrバック*<br/>
REBAR の背景色を表す COLORREF 値。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

## <a name="crebarcreate"></a><a name="create"></a>CReBar::作成

このメンバー関数を呼び出して、Rebar を作成します。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ウィンドウがステータス`CWnd`バーの親であるオブジェクトへのポインター。 通常、フレーム ウィンドウ。

*スタイル*<br/>
Rebar コントロールのスタイル。 既定では、RBS_BANDBORDERSは、Rebar コントロール内の隣接するバンドを分離するために狭い線を表示します。 スタイルの一覧については、Windows SDK の[「Rebar コントロール](/windows/win32/Controls/rebar-control-styles)スタイル」を参照してください。

*Dwstyle*<br/>
Rebar ウィンドウスタイル。

*nID*<br/>
rebar の子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [「CReBar::AddBar」](#addbar)の例を参照してください。

## <a name="crebargetrebarctrl"></a><a name="getrebarctrl"></a>クレバー::ゲットバーCtrl

このメンバー関数は、基になるコモン コントロールに直接アクセスできます。

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>戻り値

[オブジェクト](../../mfc/reference/crebarctrl-class.md)への参照。

### <a name="remarks"></a>解説

Rebar のカスタマイズ時に Windows rebar コモン コントロールの機能を利用するには、このメンバー関数を呼び出します。 を呼び`GetReBarCtrl`出すと、オブジェクトに参照オブジェクトが`CReBarCtrl`返されるため、いずれかのメンバー関数を使用できます。

Rebar をカスタマイズ`CReBarCtrl`する方法の詳細については、「 [CReBarCtrl](../../mfc/using-crebarctrl.md)の使用 」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
