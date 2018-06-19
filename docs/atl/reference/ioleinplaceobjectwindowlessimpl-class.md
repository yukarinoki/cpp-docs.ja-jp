---
title: IOleInPlaceObjectWindowlessImpl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5616258405eb8346132d32b8f7fd71d0b4794d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365003"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl クラス
このクラスは実装**IUnknown**ウィンドウなしのコントロールを使用しているウィンドウ メッセージを受信して、ドラッグ アンド ドロップ操作に参加できるようにするためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IOleInPlaceObjectWindowlessImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|状況依存のヘルプを有効にします。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|装置、`IDropTarget`サポートをドラッグ アンド ドロップをインプレースで、ウィンドウなしのアクティブなオブジェクトのインターフェイスです。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|ウィンドウ ハンドルを取得します。|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|アクティブなインプレースでコントロールを無効になります。|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|インプレースで有効になっているウィンドウなしのコントロールをコンテナーからのメッセージをディスパッチします。|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|以前非アクティブ化されたコントロールを再アクティブ化します。 ATL の実装を返します**E_NOTIMPL**です。|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|インプレースでコントロールのどの部分が表示されていることを示します。|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|非アクティブ化し、インプレース アクティブ化をサポートするユーザー インターフェイスを削除します。|  
  
## <a name="remarks"></a>コメント  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646)インターフェイスは、再アクティブ化を管理し、インプレースでの非アクティブ化を制御し、コントロールの量を表示するかを決定します。 [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304)インターフェイス ウィンドウなしのコントロールを使用しているウィンドウ メッセージを受信して、ドラッグ アンド ドロップ操作に参加を有効にします。 クラス`IOleInPlaceObjectWindowlessImpl`の既定の実装を提供`IOleInPlaceObject`と`IOleInPlaceObjectWindowless`を実装して**IUnknown**ダンプ情報を送信することによってデバッグ デバイスを構築します。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>  IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 返します**E_NOTIMPL**です。  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) Windows SDK にします。  
  
##  <a name="getdroptarget"></a>  IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 返します**E_NOTIMPL**です。  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) Windows SDK にします。  
  
##  <a name="getwindow"></a>  IOleInPlaceObjectWindowlessImpl::GetWindow  
 コンテナーは、コントロールのウィンドウ ハンドルを取得するには、この関数を呼び出します。  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>コメント  
 コンテナーをいくつかは、現在のウィンドウがある場合でも、ウィンドウなしされているコントロールでは機能しません。 ATL の実装では場合、コントロール クラスのデータ メンバー`m_bWasOnceWindowless`は**TRUE**、関数を返します**E_FAIL**です。 それ以外の場合*phwnd*は**NULL**、`GetWindow`設定\* *phwnd*コントロール クラスのデータ メンバーに`m_hWnd`を返しますと`S_OK`.  
  
 参照してください[IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) Windows SDK にします。  
  
##  <a name="inplacedeactivate"></a>  IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 インプレース アクティブなコントロールを非アクティブ化するコンテナーによって呼び出されます。  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コントロールの状態によっては、完全または部分的な非アクティブ化を実行します。 必要に応じて、コントロールのユーザー インターフェイスが非アクティブ化し、存在する場合、コントロールのウィンドウは破棄されます。 コンテナーは、インプレース コントロールがアクティブでなくなったことが通知されます。 **埋め込み**領域の枠線し、そのメニューをネゴシエートするコンテナーによって使用されるインターフェイスを解放します。  
  
 参照してください[IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) Windows SDK にします。  
  
##  <a name="onwindowmessage"></a>  IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 インプレースで有効になっているウィンドウなしのコントロールをコンテナーからのメッセージをディスパッチします。  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) Windows SDK にします。  
  
##  <a name="reactivateandundo"></a>  IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 返します**E_NOTIMPL**です。  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) Windows SDK にします。  
  
##  <a name="setobjectrects"></a>  IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 コントロールのサイズや位置が変更されたことを通知するために、コンテナーによって呼び出されます。  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>コメント  
 コントロールの更新`m_rcPos`データ メンバーとコントロールの表示。 クリップ領域と交差するコントロールの一部のみが表示されます。 コントロールの表示が以前にクリップされる領域が削除された場合は、コントロールの完全なビューを再描画するこの関数を呼び出すことができます。  
  
 参照してください[IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) Windows SDK にします。  
  
##  <a name="uideactivate"></a>  IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 非アクティブ化し、インプレース アクティブ化をサポートするコントロールのユーザー インターフェイスを削除します。  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>コメント  
 コントロール クラスのデータ メンバーを設定`m_bUIActive`に**FALSE**です。 ATL の実装のこの関数が常に返される`S_OK`です。  
  
 参照してください[IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) Windows SDK にします。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
