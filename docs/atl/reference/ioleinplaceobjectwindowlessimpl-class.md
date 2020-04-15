---
title: ウィンドウレスプルクラス
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
ms.openlocfilehash: b0438692161f38445eb7cbed54edcc8a0ba8c0d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326580"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>ウィンドウレスプルクラス

このクラスは、`IUnknown`ウィンドウなしのコントロールがウィンドウ メッセージを受信し、ドラッグ アンド ドロップ操作に参加できるようにするメソッドを実装および提供します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
から派生したクラス`IOleInPlaceObjectWindowlessImpl`。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ウィンドウレスインプル::コンテキスト依存ヘルプ](#contextsensitivehelp)|状況依存のヘルプを有効にします。 ATL の実装はE_NOTIMPL返します。|
|[ウィンドウレスインプル::GetDropTarget](#getdroptarget)|ドラッグ`IDropTarget`アンド ドロップをサポートするウィンドウなしのアクティブなオブジェクトのインターフェイスを提供します。 ATL の実装はE_NOTIMPL返します。|
|[ウィンドウレスインプル::Getウィンドウ](#getwindow)|ウィンドウ ハンドルを取得します。|
|[ウィンドウレスインプル::インプレイス非アクティブ化](#inplacedeactivate)|アクティブなインプレース コントロールを非アクティブにします。|
|[ウィンドウレスインプル::オンウィンドウメッセージ](#onwindowmessage)|コンテナーから、インプレース アクティブなウィンドウなしのコントロールにメッセージをディスパッチします。|
|[ウィンドウレスインプル::再アクティブ化と元に戻す](#reactivateandundo)|以前に非アクティブ化したコントロールを再アクティブ化します。 ATL の実装はE_NOTIMPL返します。|
|[ウィンドウレスインプル::セットオブジェクトレクト](#setobjectrects)|インプレース コントロールの表示部分を示します。|
|[ウィンドウレスインプル::UI非アクティブ化](#uideactivate)|インプレース アクティベーションをサポートするユーザー インターフェイスを非アクティブ化および削除します。|

## <a name="remarks"></a>解説

[IOleInPlaceObject](/windows/win32/api/oleidl/nn-oleidl-ioleinplaceobject)インターフェイスは、インプレース コントロールの再アクティブ化と非アクティブ化を管理し、コントロールの表示する量を決定します。 インターフェイス[を](/windows/win32/api/ocidl/nn-ocidl-ioleinplaceobjectwindowless)使用すると、ウィンドウなしのコントロールでウィンドウ メッセージを受信し、ドラッグ アンド ドロップ操作に参加できます。 クラス`IOleInPlaceObjectWindowlessImpl`は、デバッグ ビルド`IOleInPlaceObject`で`IOleInPlaceObjectWindowless`ダンプ デバイス`IUnknown`に情報を送信することにより、およびの既定の実装と実装を提供します。

**関連記事** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md), [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>継承階層

`IOleInPlaceObjectWindowless`

`IOleInPlaceObjectWindowlessImpl`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlctl.h

## <a name="ioleinplaceobjectwindowlessimplcontextsensitivehelp"></a><a name="contextsensitivehelp"></a>ウィンドウレスインプル::コンテキスト依存ヘルプ

E_NOTIMPL を返します。

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="remarks"></a>解説

Windows SDK[の「IOle ウィンドウ::コンテキストセンシティブヘルプ](/windows/win32/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp)」を参照してください。

## <a name="ioleinplaceobjectwindowlessimplgetdroptarget"></a><a name="getdroptarget"></a>ウィンドウレスインプル::GetDropTarget

E_NOTIMPL を返します。

```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```

### <a name="remarks"></a>解説

ウィンドウ[レスを参照してください](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-getdroptarget)。

## <a name="ioleinplaceobjectwindowlessimplgetwindow"></a><a name="getwindow"></a>ウィンドウレスインプル::Getウィンドウ

コンテナーは、コントロールのウィンドウ ハンドルを取得するには、この関数を呼び出します。

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>解説

一部のコンテナーは、ウィンドウがウィンドウに設定されている場合でも、ウィンドウなしのコントロールでは動作しません。 ATL の実装では、コントロール クラスのデータ メンバー`m_bWasOnceWindowless`が TRUE の場合、関数はE_FAIL返します。 それ以外の場合は *、phwnd* `GetWindow`が\*NULL でない場合 *、phwnd*を`m_hWnd`コントロール クラスのデータ メンバーに設定し、S_OK返します。

Windows SDK[の「IOle ウィンドウ::ウィンドウを取得](/windows/win32/api/oleidl/nf-oleidl-iolewindow-getwindow)する」を参照してください。

## <a name="ioleinplaceobjectwindowlessimplinplacedeactivate"></a><a name="inplacedeactivate"></a>ウィンドウレスインプル::インプレイス非アクティブ化

コンテナーによって呼び出され、インプレース アクティブ コントロールを非アクティブ化します。

```
HRESULT InPlaceDeactivate(HWND* phwnd);
```

### <a name="remarks"></a>解説

このメソッドは、コントロールの状態に応じて、完全または部分的な非アクティブ化を実行します。 必要に応じて、コントロールのユーザー インターフェイスが非アクティブ化され、コントロールのウィンドウが破棄されます。 コンテナーには、コントロールがアクティブでなくなったことが通知されます。 メニュー`IOleInPlaceUIWindow`と境界領域をネゴシエートするためにコンテナーが使用するインターフェイスが解放されます。

Windows SDK[の「IOleInPlace オブジェクト::インプレース非アクティブ化](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-inplacedeactivate)」を参照してください。

## <a name="ioleinplaceobjectwindowlessimplonwindowmessage"></a><a name="onwindowmessage"></a>ウィンドウレスインプル::オンウィンドウメッセージ

コンテナーから、インプレース アクティブなウィンドウなしのコントロールにメッセージをディスパッチします。

```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```

### <a name="remarks"></a>解説

ウィンドウ SDK[の「ウィンドウレス:オンウィンドウメッセージ](/windows/win32/api/ocidl/nf-ocidl-ioleinplaceobjectwindowless-onwindowmessage)」を参照してください。

## <a name="ioleinplaceobjectwindowlessimplreactivateandundo"></a><a name="reactivateandundo"></a>ウィンドウレスインプル::再アクティブ化と元に戻す

E_NOTIMPL を返します。

```
HRESULT ReactivateAndUndo();
```

### <a name="remarks"></a>解説

Windows SDK[の「IOleInPlace オブジェクト::再アクティブ化と元に戻す](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-reactivateandundo)」を参照してください。

## <a name="ioleinplaceobjectwindowlessimplsetobjectrects"></a><a name="setobjectrects"></a>ウィンドウレスインプル::セットオブジェクトレクト

コントロールのサイズや位置が変更されたことを通知するために、コンテナーによって呼び出されます。

```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```

### <a name="remarks"></a>解説

コントロールの`m_rcPos`データ メンバーとコントロールの表示を更新します。 クリップ領域と交差するコントロールの部分のみが表示されます。 コントロールの表示が以前にクリップされていたが、クリッピングが削除されている場合は、この関数を呼び出してコントロールの完全なビューを再描画できます。

次[を参照してください](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-setobjectrects)。

## <a name="ioleinplaceobjectwindowlessimpluideactivate"></a><a name="uideactivate"></a>ウィンドウレスインプル::UI非アクティブ化

インプレース アクティブ化をサポートするコントロールのユーザー インターフェイスを非アクティブ化および削除します。

```
HRESULT UIDeactivate();
```

### <a name="remarks"></a>解説

コントロール クラスのデータ メンバー`m_bUIActive`を FALSE に設定します。 この関数の ATL 実装は常にS_OK返します。

Windows SDK[の「IOleInPlace オブジェクト::UIDeactivate」](/windows/win32/api/oleidl/nf-oleidl-ioleinplaceobject-uideactivate)を参照してください。

## <a name="see-also"></a>関連項目

[CCom コントロール クラス](../../atl/reference/ccomcontrol-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
