---
description: '詳細情報: CReBar クラス'
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
ms.openlocfilehash: 138add510b76f21f5776f809b1551eb35d554d68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343128"
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
|[CReBar:: AddBar](#addbar)|バンドを rebar に追加します。|
|[CReBar:: Create](#create)|Rebar コントロールを作成し、オブジェクトにアタッチし `CReBar` ます。|
|[CReBar:: GetReBarCtrl](#getrebarctrl)|基になるコモンコントロールに直接アクセスできるようにします。|

## <a name="remarks"></a>解説

Rebar オブジェクトには、さまざまな子ウィンドウを含めることができます。通常は、エディットボックス、ツールバー、リストボックスなどの他のコントロールが含まれます。 Rebar オブジェクトは、指定されたビットマップ上に子ウィンドウを表示できます。 アプリケーションで rebar のサイズを自動的に変更したり、ユーザーがグリップバーをクリックまたはドラッグして rebar のサイズを手動で変更したりできます。

![RebarMenu の例](../../mfc/reference/media/vc4sc61.gif "RebarMenu の例")

## <a name="rebar-control"></a>Rebar コントロール

Rebar オブジェクトは、toolbar オブジェクトと同様に動作します。 Rebar は、クリックアンドドラッグでバンドのサイズを変更します。 Rebar コントロールには、1つまたは複数のバンドを含めることができます。各バンドには、グリップバー、ビットマップ、テキストラベル、および子ウィンドウが任意に組み合わされています。 ただし、バンドには複数の子ウィンドウを含めることはできません。

`CReBar` は、 [Crebarctrl](../../mfc/reference/crebarctrl-class.md) クラスを使用して実装を提供します。 [GetReBarCtrl](#getrebarctrl)を使用して rebar コントロールにアクセスし、コントロールのカスタマイズオプションを利用することができます。 Rebar コントロールの詳細については、「」を参照してください `CReBarCtrl` 。 Rebar コントロールの使用方法の詳細については、「 [CReBarCtrl の使用](../../mfc/using-crebarctrl.md)」を参照してください。

> [!CAUTION]
> Rebar および rebar コントロールオブジェクトは、MFC コントロールバーのドッキングをサポートしていません。 `CRebar::EnableDocking`が呼び出されると、アプリケーションはをアサートします。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

## <a name="crebaraddbar"></a><a name="addbar"></a> CReBar:: AddBar

バンドを rebar に追加するには、このメンバー関数を呼び出します。

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

*pBar*<br/>
`CWnd`Rebar に挿入される子ウィンドウであるオブジェクトへのポインター。 参照されるオブジェクトには、WS_CHILD が必要です。

*lpszText*<br/>
Rebar に表示されるテキストを含む文字列へのポインター。 既定では NULL です。 *LpszText* に含まれるテキストは、子ウィンドウの一部ではありません。これは rebar 自体にあります。

*.pbmp*<br/>
`CBitmap`Rebar の背景に表示されるオブジェクトへのポインター。 既定では NULL です。

*dwStyle*<br/>
Rebar に適用するスタイルを含む DWORD です。 `fStyle`バンドスタイルの完全な一覧については、Win32 構造体の関数の説明[REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow)を参照してください。

*clrFore*<br/>
Rebar の前景色を表す COLORREF 値。

*clrBack*<br/>
Rebar の背景色を表す COLORREF 値。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

## <a name="crebarcreate"></a><a name="create"></a> CReBar:: Create

Rebar を作成するには、このメンバー関数を呼び出します。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
`CWnd`Windows ウィンドウがステータスバーの親であるオブジェクトへのポインター。 通常はフレームウィンドウです。

*dwCtrlStyle*<br/>
Rebar コントロールスタイル。 既定では、RBS_BANDBORDERS は、rebar コントロール内の隣接するバンドを区切るための細い線を表示します。 スタイルの一覧については、「Windows SDK の [Rebar コントロールスタイル](/windows/win32/Controls/rebar-control-styles) 」を参照してください。

*dwStyle*<br/>
Rebar ウィンドウスタイル。

*nID*<br/>
Rebar の子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [CReBar:: AddBar](#addbar)の例を参照してください。

## <a name="crebargetrebarctrl"></a><a name="getrebarctrl"></a> CReBar:: GetReBarCtrl

このメンバー関数は、基になるコモンコントロールに直接アクセスできるようにします。

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>戻り値

[Crebarctrl](../../mfc/reference/crebarctrl-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

このメンバー関数を呼び出して、rebar をカスタマイズするときの Windows rebar コモンコントロールの機能を利用します。 を呼び出すと `GetReBarCtrl` 、オブジェクトへの参照オブジェクトが返され `CReBarCtrl` ます。これにより、いずれかのメンバー関数を使用できるようになります。

を使用した rebar のカスタマイズの詳細について `CReBarCtrl` は、「 [CReBarCtrl の使用](../../mfc/using-crebarctrl.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
