---
title: クラスの CWindowImpl |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CWindowImpl
- ATLWIN/ATL::CWindowImpl
- ATLWIN/ATL::CWindowImpl::Create
- ATLWIN/ATL::DefWindowProc
- ATLWIN/ATL::GetCurrentMessage
- ATLWIN/ATL::GetWindowProc
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::SubclassWindow
- ATLWIN/ATL::UnsubclassWindow
- ATLWIN/ATL::GetWndClassInfo
- ATLWIN/ATL::WindowProc
- ATLWIN/ATL::m_pfnSuperWindowProc
dev_langs:
- C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4884bbacd03675d00cb1a49b937265ab5faa2835
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366157"
---
# <a name="cwindowimpl-class"></a>CWindowImpl クラス
ウィンドウを作成またはサブクラス化するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 `CWindowImpl` から派生した新しいクラス。  
  
 *TBase*  
 クラスの基底クラス。 基本クラスは、既定では、 [CWindow](../../atl/reference/cwindow-class.md)です。  
  
 `TWinTraits`  
 A[特徴 (traits) クラス](../../atl/understanding-window-traits.md)ウィンドウのスタイルを定義します。 既定値は、`CControlWinTraits` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWindowImpl::Create](#create)|ウィンドウを作成します。|  
  
### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT メソッド  
  
|||  
|-|-|  
|[DefWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|  
|[GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|  
|[GetWindowProc](#getwindowproc)|現在のウィンドウ プロシージャを返します。|  
|[OnFinalMessage](#onfinalmessage)|最後のメッセージが受信された後に (通常は `WM_NCDESTROY`) 呼び出されます。|  
|[SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|  
|[UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|  
  
### <a name="static-methods"></a>静的メソッド  
  
|||  
|-|-|  
|[GetWndClassInfo](#getwndclassinfo)|静的インスタンスを返します[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)、ウィンドウ クラスの情報を管理します。|  
|[WindowProc](#windowproc)|ウィンドウに送信されるメッセージを処理します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[コンテナー内](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|  
  
## <a name="remarks"></a>コメント  
 使用することができます`CWindowImpl`を既存のウィンドウをウィンドウまたはサブクラスを作成します。 `CWindowImpl`ウィンドウ プロシージャは、適切なハンドラーにメッセージをメッセージ マップを使用します。  
  
 `CWindowImpl::Create` 管理されているウィンドウ クラスの情報に基づいてウィンドウを作成[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)です。 `CWindowImpl` 含まれています、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロ、つまり`CWndClassInfo`新しいウィンドウ クラスを登録します。 既存のウィンドウ クラスをスーパークラスにする場合からクラスを派生`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロです。 この場合、`CWndClassInfo` は、既存のクラスに基づくウィンドウ クラスを登録しますが、`CWindowImpl::WindowProc` を使用します。 例えば:  
  
 [!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  `CWndClassInfo` は、1 つのウィンドウ クラスの情報のみを管理するため、`CWindowImpl` のインスタンスによって作成された各ウィンドウは、同じウィンドウ クラスに基づきます。  
  
 `CWindowImpl` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CWindowImpl` オブジェクトにアタッチし、ウィンドウ プロシージャを `CWindowImpl::WindowProc` に変更します。 `CWindowImpl` の各インスタンスは、別のウィンドウをサブクラス化できます。  
  
> [!NOTE]
>  指定された任意の`CWindowImpl`オブジェクト、いずれかを呼び出す**作成**または`SubclassWindow`です。 同じオブジェクトで両方のメソッドを呼び出さないでください。  
  
 加え`CWindowImpl`、ATL には、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)別のオブジェクトに含まれているウィンドウを作成します。  
  
 基底クラスのデストラクター (~ **CWindowImplRoot**) により、オブジェクトが破棄される前に、ウィンドウが消えます。  
  
 `CWindowImpl` 派生した**CWindowImplBaseT**から派生した**CWindowImplRoot**から派生した**TBase**と[CMessageMap](../../atl/reference/cmessagemap-class.md)です。  
  
|詳細情報:|解決方法については、|  
|--------------------------------|---------|  
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|  
|ATL でのウィンドウの使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|  
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="create"></a>  CWindowImpl::Create  
 新しいウィンドウ クラスに基づくウィンドウを作成します。  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]親ウィンドウまたはオーナー ウィンドウへのハンドル。  
  
 `rect`  
 [in]A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ウィンドウの位置を指定する構造体。 `RECT`ポインター渡しまたは参照渡しで渡すことができます。  
  
 `szWindowName`  
 [in]ウィンドウの名前を指定します。 既定値は**NULL**です。  
  
 `dwStyle`  
 [in]ウィンドウのスタイルです。 この値は、ウィンドウの特徴 (traits) クラスが提供するスタイルと組み合わされます。 既定値は、クラスのフル コントロールのスタイルが、特徴 (traits) を示します。 使用可能な値の一覧は、次を参照してください。 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK に含まれています。  
  
 `dwExStyle`  
 [in]拡張ウィンドウ スタイルです。 この値は、ウィンドウの特徴 (traits) クラスが提供するスタイルと組み合わされます。 既定値は、クラスのフル コントロールのスタイルが、特徴 (traits) を示します。 使用可能な値の一覧は、次を参照してください。[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 `MenuOrID`  
 [in]子ウィンドウでは、ウィンドウの識別子。 最上位レベルのウィンドウのメニューは、ウィンドウのハンドルします。 既定値は**0 u**です。  
  
 `lpCreateParam`  
 [in]ウィンドウの作成データへのポインター。 詳細については、最終パラメーターの説明を参照して[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、新しく作成されたウィンドウのハンドル。 それ以外の場合、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 **作成**まだ登録されていない場合は、まず、ウィンドウ クラスを登録します。 新しく作成されたウィンドウが自動的に添付、`CWindowImpl`オブジェクト。  
  
> [!NOTE]
>  呼び出す必要はありません**作成**既にを呼び出した場合[SubclassWindow](#subclasswindow)です。  
  
 既存のウィンドウ クラスに基づいているウィンドウ クラスを使用するからクラスを派生`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロです。 既存のウィンドウ クラスのウィンドウ プロシージャ[コンテナー内](#m_pfnsuperwindowproc)です。 詳細については、次を参照してください。、 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要です。  
  
> [!NOTE]
>  値として 0 が使用する場合、`MenuOrID`パラメーター、0 u として指定する必要があります (既定値) をコンパイラ エラーを回避します。  
  
##  <a name="defwindowproc"></a>  CWindowImpl::DefWindowProc  
 によって呼び出されます[WindowProc](#windowproc)メッセージ マップで処理されないメッセージを処理します。  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```  
  
### <a name="parameters"></a>パラメーター  
 `uMsg`  
 [in]ウィンドウに送信するメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
### <a name="return-value"></a>戻り値  
 メッセージの処理の結果。  
  
### <a name="remarks"></a>コメント  
 既定では、`DefWindowProc`呼び出し、 [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571) Win32 関数で指定されたウィンドウ プロシージャにメッセージの情報を送信する[コンテナー内](#m_pfnsuperwindowproc)です。  
  
 パラメーターなしの関数は、現在のメッセージから、必要なパラメーターを自動的に取得します。  
  
##  <a name="getcurrentmessage"></a>  CWindowImpl::GetCurrentMessage  
 パッケージ化されて、現在のメッセージが返されます、`MSG`構造体。  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>戻り値  
 現在のメッセージ。  
  
##  <a name="getwindowproc"></a>  CWindowImpl::GetWindowProc  
 返します`WindowProc`、現在のウィンドウ プロシージャ。  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>戻り値  
 現在のウィンドウ プロシージャ。  
  
### <a name="remarks"></a>コメント  
 独自のウィンドウ プロシージャを置換するには、このメソッドをオーバーライドします。  
  
##  <a name="getwndclassinfo"></a>  CWindowImpl::GetWndClassInfo  
 によって呼び出されます[作成](#create)ウィンドウ クラスの情報にアクセスします。  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>戻り値  
 静的インスタンス[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)です。  
  
### <a name="remarks"></a>コメント  
 既定では、`CWindowImpl`によっては、このメソッドを取得、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロで、新しいウィンドウ クラスを指定します。  
  
 クラスを派生を既存のウィンドウ クラスをスーパークラス化、`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)をオーバーライドするマクロ`GetWndClassInfo`です。 詳細については、次を参照してください。、 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要です。  
  
 使用するだけでなく、`DECLARE_WND_CLASS`と`DECLARE_WND_SUPERCLASS`マクロをオーバーライドできます`GetWndClassInfo`独自の実装にします。  
  
##  <a name="m_pfnsuperwindowproc"></a>  CWindowImpl::m_pfnSuperWindowProc  
 によっては、ウィンドウには、次のウィンドウ プロシージャのいずれかを指します。  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>コメント  
  
|ウィンドウの種類|ウィンドウ プロシージャ|  
|--------------------|----------------------|  
|新しいウィンドウ クラスを使用して指定に基づいて、ウィンドウ、 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)マクロです。|[DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) Win32 関数。|  
|既存のクラスを使用して指定を変更するウィンドウ クラスに基づいて、ウィンドウ、 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)マクロです。|既存のウィンドウ クラスのウィンドウ プロシージャです。|  
|サブクラス化されたウィンドウです。|サブクラス化されたウィンドウの元のウィンドウ プロシージャ。|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc)に保存されているウィンドウ プロシージャに情報メッセージを送信`m_pfnSuperWindowProc`です。  
  
##  <a name="onfinalmessage"></a>  CWindowImpl::OnFinalMessage  
 最後のメッセージの受信後に呼び出されます (通常`WM_NCDESTROY`)。  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]破棄されているウィンドウへのハンドル。  
  
### <a name="remarks"></a>コメント  
 既定の実装`OnFinalMessage`、何も行われませんが、ウィンドウを破棄する前にクリーンアップを処理するには、この関数をオーバーライドできます。 ウィンドウの破棄後にオブジェクトを自動的に削除する場合は、呼び出す`delete this;`この関数にします。  
  
##  <a name="subclasswindow"></a>  CWindowImpl::SubclassWindow  
 によって識別されるウィンドウ サブクラス`hWnd`にアタッチし、`CWindowImpl`オブジェクト。  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]サブクラス化されているウィンドウ ハンドルです。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ウィンドウが正常にサブクラス化された、それ以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 サブクラス化されたウィンドウは[CWindowImpl::WindowProc](#windowproc)です。 元のウィンドウ プロシージャに保存されて[コンテナー内](#m_pfnsuperwindowproc)です。  
  
> [!NOTE]
>  呼び出す必要はありません`SubclassWindow`既にを呼び出した場合[作成](#create)です。  
  
##  <a name="unsubclasswindow"></a>  CWindowImpl::UnsubclassWindow  
 サブクラス化されたウィンドウからのデタッチ、`CWindowImpl`オブジェクトを復元元のウィンドウ プロシージャに保存されている[コンテナー内](#m_pfnsuperwindowproc)です。  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>戻り値  
 以前にサブクラス化されたウィンドウのハンドル。  
  
##  <a name="windowproc"></a>  CWindowImpl::WindowProc  
 この静的関数では、ウィンドウ プロシージャを実装します。  
  
```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]ウィンドウのハンドル。  
  
 `uMsg`  
 [in]ウィンドウに送信するメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
### <a name="return-value"></a>戻り値  
 メッセージの処理の結果。  
  
### <a name="remarks"></a>コメント  
 `WindowProc` 既定のメッセージ マップを使用して (を使用して宣言[送るに](message-map-macros-atl.md#begin_msg_map)) 適切なハンドラーへのメッセージを送信するためです。 必要に応じて、`WindowProc`呼び出し[DefWindowProc](#defwindowproc)追加のメッセージ処理のためです。 最後のメッセージが処理されない場合`WindowProc`は次の実行します。  
  
-   ウィンドウをサブクラス化できなかった場合は、解除処理を実行します。  
  
-   `m_hWnd` を消去します。  
  
-   呼び出し[OnFinalMessage](#onfinalmessage)ウィンドウが破棄される前にします。  
  
 オーバーライドできます`WindowProc`メッセージを処理するためのさまざまなメカニズムを提供します。  
  
## <a name="see-also"></a>関連項目  
 [送るに](message-map-macros-atl.md#begin_msg_map)   
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
