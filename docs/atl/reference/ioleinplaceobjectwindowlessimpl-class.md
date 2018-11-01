---
title: IOleInPlaceObjectWindowlessImpl クラス
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
ms.openlocfilehash: a83fbed524c55c6bc98aa25caa17b80c1e5f89f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592128"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl クラス

このクラスは実装`IUnknown`ウィンドウ メッセージを受信して、ドラッグ アンド ドロップ操作に参加するウィンドウなしのコントロールを有効にするメソッドを提供します。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生したクラス、`IOleInPlaceObjectWindowlessImpl`します。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|状況依存のヘルプを有効にします。 ATL の実装では、E_NOTIMPL を返します。|
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|装置、`IDropTarget`インプレース アクティブ、窓のないオブジェクトをドラッグ アンド ドロップのサポートのインターフェイス。 ATL の実装では、E_NOTIMPL を返します。|
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|ウィンドウ ハンドルを取得します。|
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|アクティブなインプレース コントロールを無効になります。|
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|コンテナーから一括で有効になっているウィンドウなしのコントロールへのメッセージをディスパッチします。|
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|以前に非アクティブ化されたコントロールを再アクティブ化します。 ATL の実装では、E_NOTIMPL を返します。|
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|インプレース コントロールのどの部分が表示されていることを示します。|
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|非アクティブ化し、インプレース アクティブ化をサポートするユーザー インターフェイスを削除します。|

## <a name="remarks"></a>Remarks

[IOleInPlaceObject](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceobject)インターフェイスは、再アクティブ化を管理し、インプレースの非アクティブ化を制御し、コントロールの量を表示するかを決定します。 [IOleInPlaceObjectWindowless](/windows/desktop/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless)インターフェイス ウィンドウ メッセージを受信して、ドラッグ アンド ドロップ操作に参加するウィンドウなしのコントロールを使用できます。 クラス`IOleInPlaceObjectWindowlessImpl`の既定の実装を提供します。`IOleInPlaceObject`と`IOleInPlaceObjectWindowless`実装と`IUnknown`ダンプ情報を送信することによってデバッグでのデバイスをビルドします。

**関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

##  <a name="contextsensitivehelp"></a>  IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp

E_NOTIMPL を返します。

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>Remarks

参照してください[IOleWindow::ContextSensitiveHelp](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) Windows SDK にします。

##  <a name="getdroptarget"></a>  IOleInPlaceObjectWindowlessImpl::GetDropTarget

E_NOTIMPL を返します。

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>Remarks

参照してください[IOleInPlaceObjectWindowless::GetDropTarget](/windows/desktop/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget) Windows SDK にします。

##  <a name="getwindow"></a>  IOleInPlaceObjectWindowlessImpl::GetWindow

コンテナーは、コントロールのウィンドウ ハンドルを取得するには、この関数を呼び出します。

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>Remarks

一部のコンテナーは、現在のウィンドウがある場合でも、ウィンドウなしにされているコントロールでは機能しません。 ATL の実装の場合、コントロール クラスのデータ メンバー`m_bWasOnceWindowless`が true の場合、関数は E_FAIL を返します。 の場合*phwnd*が NULL でない`GetWindow`設定\* *phwnd*コントロール クラスのデータ メンバーに`m_hWnd`S_OK を返します。

参照してください[IOleWindow::GetWindow](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-getwindow) Windows SDK にします。

##  <a name="inplacedeactivate"></a>  IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate

インプレース アクティブなコントロールを非アクティブ化するコンテナーによって呼び出されます。

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>Remarks

このメソッドは、コントロールの状態に応じて、完全または部分的な非アクティブ化を実行します。 必要に応じて、コントロールのユーザー インターフェイスが非アクティブ化し、存在する場合、コントロールのウィンドウは破棄されます。 コンテナーは、インプレース コントロールがアクティブでなくなったことが通知されます。 `IOleInPlaceUIWindow`領域の枠線し、そのメニューをネゴシエートするコンテナーによって使用されるインターフェイスを解放します。

参照してください[IOleInPlaceObject::InPlaceDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate) Windows SDK にします。

##  <a name="onwindowmessage"></a>  IOleInPlaceObjectWindowlessImpl::OnWindowMessage

コンテナーから一括で有効になっているウィンドウなしのコントロールへのメッセージをディスパッチします。

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>Remarks

参照してください[IOleInPlaceObjectWindowless::OnWindowMessage](/windows/desktop/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage) Windows SDK にします。

##  <a name="reactivateandundo"></a>  IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo

E_NOTIMPL を返します。

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>Remarks

参照してください[IOleInPlaceObject::ReactivateAndUndo](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo) Windows SDK にします。

##  <a name="setobjectrects"></a>  IOleInPlaceObjectWindowlessImpl::SetObjectRects

コントロールのサイズや位置が変更されたことを通知するために、コンテナーによって呼び出されます。

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>Remarks

コントロールの更新`m_rcPos`データ メンバーとコントロールの表示。 クリップ領域と交差するコントロールの一部のみが表示されます。 コントロールの表示が以前にクリップされる領域が削除された場合は、コントロールの完全なビューを再描画するこの関数を呼び出すことができます。

参照してください[IOleInPlaceObject::SetObjectRects](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects) Windows SDK にします。

##  <a name="uideactivate"></a>  IOleInPlaceObjectWindowlessImpl::UIDeactivate

非アクティブ化し、インプレース アクティブ化をサポートするコントロールのユーザー インターフェイスを削除します。

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>Remarks

コントロール クラスのデータ メンバーを設定`m_bUIActive`を FALSE にします。 この関数の ATL の実装は、常に S_OK を返します。

参照してください[IOleInPlaceObject::UIDeactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate) Windows SDK にします。

## <a name="see-also"></a>関連項目

[CComControl クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
