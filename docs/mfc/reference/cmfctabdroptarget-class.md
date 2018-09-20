---
title: CMFCTabDropTarget クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f4951da1f6407dae1d31d92724bbcc80e677616
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442436"
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget クラス

タブ コントロールと OLE ライブラリ間の通信機構を提供します。

## <a name="syntax"></a>構文

```
class CMFCTabDropTarget : public COleDropTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|`CMFCTabDropTarget::CMFCTabDropTarget`|既定のコンストラクター|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|ユーザーがタブ ウィンドウにオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter))。|
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|ユーザーがフォーカスを持つタブ ウィンドウ以外でオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave))。|
|[CMFCTabDropTarget::OnDragOver](#ondragover)|ユーザーは、フォーカスのあるタブ ウィンドウの上にオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover))。|
|[CMFCTabDropTarget::OnDropEx](#ondropex)|ユーザーがドラッグ操作の最後にマウス ボタンを離したときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex))。|
|[CMFCTabDropTarget::Register](#register)|OLE ドラッグ アンド ドロップ操作のターゲットにすることができますを 1 つとして、コントロールを登録します。|

### <a name="remarks"></a>Remarks

このクラスをドラッグ アンド ドロップのサポートを提供する、`CMFCBaseTabCtrl`クラス。 使用して、アプリケーションが OLE ライブラリを初期化する場合、 [AfxOleInit](ole-initialization.md#afxoleinit)関数、`CMFCBaseTabCtrl`オブジェクトがドラッグ アンド ドロップ操作に対して自身を登録します。

`CMFCTabDropTarget`クラスは、カーソルの下では、ドラッグ操作が行われるアクティブなタブのことで、基底クラスを拡張します。 ドラッグ アンド ドロップ操作の詳細については、次を参照してください。[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)します。

## <a name="example"></a>例

`CMFCTabDropTarget` オブジェクトを構築して、その `Register` メソッドを使用する方法を、次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleDropTarget](../../mfc/reference/coledroptarget-class.md)

[CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxbasetabctrl.h

##  <a name="ondragenter"></a>  CMFCTabDropTarget::OnDragEnter

ユーザーがタブ ウィンドウにオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。

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
|*我が物*|[in]使用されていません。|
|*pDataObject*|[in]ユーザーがドラッグされるオブジェクトへのポインター。|
|*ドロップ*|[in]修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせ: MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。|
|*ポイント*|[in]クライアント座標でのカーソルの位置。|

### <a name="return-value"></a>戻り値

によって指定された場所にドロップが発生した場合に発生する影響*ポイント*します。 次の 1 つ以上を指定できます。

- せず

- DROPEFFECT_COPY

- 行った

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Remarks

このメソッドは、カスタマイズ モードで、ツールバーのフレームワークがないか、クリップボード データ形式をご利用いただけませんせずを返します。 呼び出し元の結果を返しますそれ以外の場合、`CMFCBaseTabCtrl::OnDragEnter`指定されたパラメーターを使用します。

カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)します。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)します。

##  <a name="ondragleave"></a>  CMFCTabDropTarget::OnDragLeave

ユーザーがフォーカスを持つタブ ウィンドウ以外でオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*我が物*|[in]使用されていません。|

### <a name="remarks"></a>Remarks

このメソッドは、`CMFCBaseTabCtrl::OnDragLeave`ドラッグ操作を実行するメソッド。

##  <a name="ondragover"></a>  CMFCTabDropTarget::OnDragOver

ユーザーは、フォーカスのあるタブ ウィンドウの上にオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。

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
|*我が物*|[in]使用されていません。|
|*pDataObject*|[in]ユーザーがドラッグされるオブジェクトへのポインター。|
|*ドロップ*|[in]修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせ: MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。|
|*ポイント*|[in]クライアント座標でマウス ポインターの位置。|

### <a name="return-value"></a>戻り値

によって指定された場所にドロップが発生した場合に発生する影響*ポイント*します。 次の 1 つ以上を指定できます。

- せず

- DROPEFFECT_COPY

- 行った

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Remarks

このメソッドでは、ドラッグ操作が行われるアクティブなカーソルの下にあるタブで行います。 カスタマイズ モードで、ツールバーのフレームワークがないか、クリップボード データ形式は使用できません、せずが返されます。 呼び出し元の結果を返しますそれ以外の場合、`CMFCBaseTabCtrl::OnDragOver`指定されたパラメーターを使用します。

カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)します。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)します。

##  <a name="ondropex"></a>  CMFCTabDropTarget::OnDropEx

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
|*我が物*|[in]使用されていません。|
|*pDataObject*|[in]ユーザーがドラッグされるオブジェクトへのポインター。|
|*dropEffect*|[in]既定のドロップ操作。|
|*ドロップダウン リスト*|[in]使用されていません。|
|*ポイント*|[in]クライアント座標でマウス ポインターの位置。|

### <a name="return-value"></a>戻り値

結果として得られるドロップ効果。 次の 1 つ以上を指定できます。

- せず

- DROPEFFECT_COPY

- 行った

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Remarks

このメソッドを呼び出す`CMFCBaseTabCtrl::OnDrop`ツールバー フレームワークは、カスタマイズ モードでは、クリップボード データ形式が利用できる場合。 場合に呼び出し`CMFCBaseTabCtrl::OnDrop`返します 0 以外の値、このメソッドで指定された既定のドロップ効果の返します*dropEffect*します。 それ以外の場合、このメソッドは、せずを返します。 ドロップ効果の詳細については、次を参照してください。 [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex)します。

カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)します。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)します。

##  <a name="register"></a>  CMFCTabDropTarget::Register

OLE ドラッグ アンド ドロップ操作のターゲットにすることができますを 1 つとして、コントロールを登録します。

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*pOwner*|[in]ドロップ先として登録するタブ コントロール。|

### <a name="return-value"></a>戻り値

登録が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドを呼び出す[COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register)ドラッグ アンド ドロップ操作のコントロールを登録します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)



