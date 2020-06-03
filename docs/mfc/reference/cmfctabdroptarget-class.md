---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
ms.openlocfilehash: 83432fdb90fe28214fb1faaf843556deb2f44750
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367354"
---
# <a name="cmfctabdroptarget-class"></a>クラス

タブ コントロールと OLE ライブラリ間の通信メカニズムを提供します。

## <a name="syntax"></a>構文

```
class CMFCTabDropTarget : public COleDropTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CMFCTabDropTarget::CMFCTabDropTarget`|既定のコンストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[CMFCタブドロップターゲット::オンドラグエンター](#ondragenter)|ユーザーがオブジェクトをタブ ウィンドウにドラッグしたときに、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/coledroptarget-class.md#ondragenter)|
|[CMFCタブドロップターゲット::オンドラグリーブ](#ondragleave)|ユーザーがフォーカスのあるタブ ウィンドウの外にオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/coledroptarget-class.md#ondragleave)|
|[CMFCタブドロップターゲット::オンドラッグオーバー](#ondragover)|ユーザーがフォーカスのあるタブ ウィンドウにオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 ([オーバーライドします: :オンドラッグオーバー](../../mfc/reference/coledroptarget-class.md#ondragover).)|
|[をクリックします。](#ondropex)|ユーザーがドラッグ操作の最後にマウス ボタンを離したときに、フレームワークによって呼び出されます。 (上書き[COleDropターゲット::オンドロップエックス](../../mfc/reference/coledroptarget-class.md#ondropex).)|
|[登録](#register)|OLE ドラッグ アンド ドロップ操作の対象となるコントロールとしてコントロールを登録します。|

### <a name="remarks"></a>解説

このクラスは、クラスにドラッグ アンド ドロップ`CMFCBaseTabCtrl`のサポートを提供します。 [AfxOleInit](ole-initialization.md#afxoleinit)関数を使用してアプリケーションが OLE ライブラリを初期化`CMFCBaseTabCtrl`する場合、オブジェクトはドラッグ アンド ドロップ操作に対して自身を登録します。

この`CMFCTabDropTarget`クラスは、ドラッグ操作が行われたときにカーソルの下にあるタブをアクティブにすることで、基本クラスを拡張します。 ドラッグ アンド ドロップ操作の詳細については、「 [OLE ドラッグ アンド ドロップ](../../mfc/drag-and-drop-ole.md)」を参照してください。

## <a name="example"></a>例

`CMFCTabDropTarget` オブジェクトを構築して、その `Register` メソッドを使用する方法を、次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleDropTarget](../../mfc/reference/coledroptarget-class.md)

[をクリックします。](../../mfc/reference/cmfctabdroptarget-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxbasetabctrl.h

## <a name="cmfctabdroptargetondragenter"></a><a name="ondragenter"></a>CMFCタブドロップターゲット::オンドラグエンター

ユーザーがオブジェクトをタブ ウィンドウにドラッグしたときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Pwnd*|[in]未使用。|
|*オブジェクト*|[in]ユーザーがドラッグするオブジェクトへのポインター。|
|*州*|[in]修飾子キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。|
|*ポイント*|[in]クライアント座標でのカーソルの位置。|

### <a name="return-value"></a>戻り値

ポイントで指定された位置でドロップが*発生した場合*に生じる効果。 次の 1 つ以上を指定できます。

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>解説

このメソッドは、ツールバー フレームワークがカスタマイズ モードでない場合、またはクリップボードのデータ形式が使用できない場合に、DROPEFFECT_NONEを返します。 それ以外の場合は、指定された`CMFCBaseTabCtrl::OnDragEnter`パラメーターを使用して呼び出した結果を返します。

カスタマイズ モードの詳細については[、「CMFC ツール バー::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)」を参照してください。 クリップボード データ形式の詳細については[、「COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)」を参照してください。

## <a name="cmfctabdroptargetondragleave"></a><a name="ondragleave"></a>CMFCタブドロップターゲット::オンドラグリーブ

ユーザーがフォーカスのあるタブ ウィンドウの外にオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Pwnd*|[in]未使用。|

### <a name="remarks"></a>解説

このメソッドは、`CMFCBaseTabCtrl::OnDragLeave`ドラッグ操作を実行するメソッドを呼び出します。

## <a name="cmfctabdroptargetondragover"></a><a name="ondragover"></a>CMFCタブドロップターゲット::オンドラッグオーバー

ユーザーがフォーカスのあるタブ ウィンドウにオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Pwnd*|[in]未使用。|
|*オブジェクト*|[in]ユーザーがドラッグするオブジェクトへのポインター。|
|*州*|[in]修飾子キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。|
|*ポイント*|[in]クライアント座標でのマウス ポインターの位置。|

### <a name="return-value"></a>戻り値

ポイントで指定された位置でドロップが*発生した場合*に生じる効果。 次の 1 つ以上を指定できます。

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>解説

このメソッドは、ドラッグ操作が行われたときにカーソルの下にあるタブをアクティブにします。 ツール バー フレームワークがカスタマイズ モードでない場合、またはクリップボードのデータ形式が使用できない場合は、DROPEFFECT_NONEを返します。 それ以外の場合は、指定された`CMFCBaseTabCtrl::OnDragOver`パラメーターを使用して呼び出した結果を返します。

カスタマイズ モードの詳細については[、「CMFC ツール バー::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)」を参照してください。 クリップボード データ形式の詳細については[、「COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)」を参照してください。

## <a name="cmfctabdroptargetondropex"></a><a name="ondropex"></a>をクリックします。

ユーザーがドラッグ操作の最後にマウス ボタンを離したときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*Pwnd*|[in]未使用。|
|*オブジェクト*|[in]ユーザーがドラッグするオブジェクトへのポインター。|
|*ドロップエフェクト*|[in]既定のドロップ操作。|
|*ドロップリスト*|[in]未使用。|
|*ポイント*|[in]クライアント座標でのマウス ポインターの位置。|

### <a name="return-value"></a>戻り値

結果のドロップ効果。 次の 1 つ以上を指定できます。

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>解説

このメソッドは`CMFCBaseTabCtrl::OnDrop`、ツール バー フレームワークがカスタマイズ モードで、クリップボード データ形式が使用可能な場合に呼び出します。 呼び出し`CMFCBaseTabCtrl::OnDrop`が 0 以外の値を返す場合、このメソッドは*dropEffect*で指定された既定のドロップ効果を返します。 それ以外の場合、このメソッドはDROPEFFECT_NONEを返します。 ドロップ効果の詳細については[、「COleDropTarget::OnDropEx」](../../mfc/reference/coledroptarget-class.md#ondropex)を参照してください。

カスタマイズ モードの詳細については[、「CMFC ツール バー::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)」を参照してください。 クリップボード データ形式の詳細については[、「COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)」を参照してください。

## <a name="cmfctabdroptargetregister"></a><a name="register"></a>登録

OLE ドラッグ アンド ドロップ操作の対象となるコントロールとしてコントロールを登録します。

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*所有者*|[in]ドロップ ターゲットとして登録するタブ コントロール。|

### <a name="return-value"></a>戻り値

登録が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、ドラッグ アンド ドロップ操作用のコントロールを登録するために[COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register)を呼び出します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[OLE のドラッグ アンド ドロップ](../../mfc/drag-and-drop-ole.md)
