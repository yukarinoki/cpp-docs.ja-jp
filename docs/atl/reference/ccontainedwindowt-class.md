---
title: CContainedWindowT クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
dev_langs:
- C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f3f90e23eed3bd1eba80bbf90fe73de45eb7cfa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366485"
---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT クラス
このクラスは、別のオブジェクト内に含まれるウィンドウを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>パラメーター  
 *TBase*  
 新しいクラスの基本クラスです。 既定の基本クラスは`CWindow`します。  
  
 `TWinTraits`  
 ウィンドウのスタイルを定義する特徴 (traits) クラス。 既定値は、`CControlWinTraits` です。  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md)の特殊化`CContainedWindowT`です。 基底クラスまたは特徴 (traits) を変更する場合を使用して`CContainedWindowT`直接です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|コンストラクターです。 指定するメッセージ マップが含まれているウィンドウのメッセージを処理するデータ メンバーを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|ウィンドウを作成します。|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|ウィンドウのウィンドウ クラスを登録します。|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|変更するメッセージ マップが含まれているウィンドウのメッセージを処理するために使用します。|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|  
|[この段階](#windowproc)|(静的)コンテナー内のウィンドウに送信されたメッセージを処理します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|どのメッセージ マップが含まれているウィンドウのメッセージの処理を識別します。|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|新しいウィンドウ クラスの基になる既存のウィンドウ クラスの名前を指定します。|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|  
|[CContainedWindowT::m_pObject](#m_pobject)|親オブジェクトへのポインター。|  
  
## <a name="remarks"></a>コメント  
 `CContainedWindowT` 別のオブジェクト内に含まれるウィンドウを実装します。 `CContainedWindowT`適切なハンドラーに直接メッセージを含んでいるオブジェクトのマップに、メッセージ ウィンドウ プロシージャの使用方法です。 構築するときに、`CContainedWindowT`オブジェクトをどのメッセージ マップを使用する必要がありますを指定します。  
  
 `CContainedWindowT` 使用すると、既存のウィンドウ クラスをスーパークラス化して、新しいウィンドウを作成できます。 **作成**メソッドは、まず既存のクラスに基づきますが、使用するウィンドウ クラスを登録`CContainedWindowT::WindowProc`です。 **作成**し、この新しいウィンドウ クラスに基づくウィンドウを作成します。 各インスタンス`CContainedWindowT`スーパークラス別のウィンドウ クラスのことができます。  
  
 `CContainedWindowT` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CContainedWindowT` オブジェクトにアタッチし、ウィンドウ プロシージャを `CContainedWindowT::WindowProc` に変更します。 `CContainedWindowT` の各インスタンスは、別のウィンドウをサブクラス化できます。  
  
> [!NOTE]
>  指定された任意の`CContainedWindowT`オブジェクト、いずれかを呼び出す**作成**または`SubclassWindow`です。 同じオブジェクトで両方のメソッドを呼び出しません必要があります。  
  
 使用すると、**に基づいてコントロールを追加**ウィザードが自動的に追加オプション、ATL プロジェクト ウィザードで、`CContainedWindowT`コントロールを実装するクラスのデータ メンバーです。 次の例では、コンテナー内のウィンドウを宣言する方法を示しています。  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|詳細情報:|解決方法については、|  
|--------------------------------|---------|  
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|  
|ATL でのウィンドウの使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|  
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595)と Windows SDK のそれ以降のトピック|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="ccontainedwindowt"></a>  CContainedWindowT::CContainedWindowT  
 コンス トラクターは、データ メンバーを初期化します。  
  
```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```     
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 [in]コンテナー内のウィンドウの基になる既存のウィンドウ クラスの名前。  
  
 `pObject`  
 [in]メッセージ マップを宣言する親オブジェクトへのポインター。 このオブジェクトのクラスから派生しなければなりません[CMessageMap](../../atl/reference/cmessagemap-class.md)です。  
  
 `dwMsgMapID`  
 [in]含まれているウィンドウのメッセージを処理するメッセージ マップを識別します。 既定値は 0 を指定で宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)です。 宣言された代替のメッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、渡す`msgMapID`です。  
  
### <a name="remarks"></a>コメント  
 新しいウィンドウを作成する場合[作成](#create)の既存のウィンドウ クラスの名前を渡す必要があります、`lpszClassName`パラメーター。 例については、次を参照してください。、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)の概要です。  
  
 次の 3 つのコンス トラクターがあります。  
  
-   3 つの引数を持つコンス トラクターと通常呼ばれる 1 つです。  
  
-   2 つの引数を持つコンス トラクターからクラス名を使用して**トラクター**です。  
  
-   引数なしのコンス トラクターは後で、引数を指定する場合に使用されます。 呼び出すと、ウィンドウ クラス名、メッセージ マップのオブジェクト、およびメッセージ マップの ID を指定する必要があります**作成**です。  
  
 場合、既存のウィンドウをサブクラスを通じて[SubclassWindow](#subclasswindow)、`lpszClassName`値は使用されません。 ため、渡すことができます**NULL**このパラメーターにします。  
  
##  <a name="create"></a>  CContainedWindowT::Create  
 呼び出し[RegisterWndSuperclass](#registerwndsuperclass)は既存のクラスに基づいていますが、使用するウィンドウ クラスを登録する[この段階](#windowproc)です。  
  
```
HWND Create(  
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 [in]コンテナー内のウィンドウの基になる既存のウィンドウ クラスの名前。  
  
 `pObject`  
 [in]メッセージ マップを宣言する親オブジェクトへのポインター。 このオブジェクトのクラスから派生しなければなりません[CMessageMap](../../atl/reference/cmessagemap-class.md)です。  
  
 `dwMsgMapID`  
 [in]含まれているウィンドウのメッセージを処理するメッセージ マップを識別します。 既定値は 0 を指定で宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)です。 宣言された代替のメッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、渡す`msgMapID`です。  
  
 `hWndParent`  
 [in]親ウィンドウまたはオーナー ウィンドウへのハンドル。  
  
 `rect`  
 [in]A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ウィンドウの位置を指定する構造体。 `RECT`ポインター渡しまたは参照渡しで渡すことができます。  
  
 `szWindowName`  
 [in]ウィンドウの名前を指定します。 既定値は**NULL**です。  
  
 `dwStyle`  
 [in]ウィンドウのスタイルです。 既定値は**WS_CHILD &#124; WS_VISIBLE**です。 使用可能な値の一覧は、次を参照してください。 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK に含まれています。  
  
 `dwExStyle`  
 [in]拡張ウィンドウ スタイルです。 既定値は、0、拡張スタイルれないことを意味します。 使用可能な値の一覧は、次を参照してください。[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK に含まれています。  
  
 `MenuOrID`  
 [in]子ウィンドウでは、ウィンドウの識別子。 最上位レベルのウィンドウのメニューは、ウィンドウのハンドルします。 既定値は**0 u**です。  
  
 `lpCreateParam`  
 [in]ウィンドウの作成データへのポインター。 詳細については、最終パラメーターの説明を参照して[について](http://msdn.microsoft.com/library/windows/desktop/ms632680)です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、新しく作成されたウィンドウへのハンドルそれ以外の場合、 **NULL**です。  
  
### <a name="remarks"></a>コメント  
 既存のウィンドウ クラス名に保存[m_lpszClassName](#m_lpszclassname)です。 **作成**し、この新しいクラスに基づくウィンドウを作成します。 新しく作成されたウィンドウが自動的に添付、`CContainedWindowT`オブジェクト。  
  
> [!NOTE]
>  呼び出す必要はありません**作成**既にを呼び出した場合[SubclassWindow](#subclasswindow)です。  
  
> [!NOTE]
>  値として 0 が使用する場合、`MenuOrID`パラメーター、0 u として指定する必要があります (既定値) をコンパイラ エラーを回避します。  
  
##  <a name="defwindowproc"></a>  CContainedWindowT::DefWindowProc  
 によって呼び出されます[WindowProc](#windowproc)メッセージ マップで処理されないメッセージを処理します。  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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
  
##  <a name="getcurrentmessage"></a>  CContainedWindowT::GetCurrentMessage  
 現在のメッセージが返されます ( **m_pCurrentMsg**)。  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>戻り値  
 現在のメッセージ内にパッケージ化、`MSG`構造体。  
  
##  <a name="m_dwmsgmapid"></a>  CContainedWindowT::m_dwMsgMapID  
 コンテナー内のウィンドウの現在使用されているメッセージ マップの識別子を保持します。  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>コメント  
 このメッセージ マップは、親オブジェクトで宣言されなければなりません。  
  
 宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)、常に 0 で識別されます。 宣言された、代替のメッセージ マップ[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、によって識別される`msgMapID`です。  
  
 `m_dwMsgMapID` まずコンス トラクターによって初期化し、呼び出すことにより変更できます[SwitchMessageMap](#switchmessagemap)です。 例については、次を参照してください。、 [「](../../atl/reference/ccontainedwindowt-class.md)です。  
  
##  <a name="m_lpszclassname"></a>  CContainedWindowT::m_lpszClassName  
 既存のウィンドウ クラスの名前を指定します。  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウを作成するときに[作成](#create)この既存クラスに基づきますが、使用する新しいウィンドウ クラスを登録[この段階](#windowproc)です。  
  
 `m_lpszClassName` コンス トラクターによって初期化されます。 例については、次を参照してください。、 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の概要です。  
  
##  <a name="m_pfnsuperwindowproc"></a>  CContainedWindowT::m_pfnSuperWindowProc  
 コンテナー内のウィンドウがサブクラス化される場合`m_pfnSuperWindowProc`ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>コメント  
 コンテナー内のウィンドウがスーパークラスの場合は、つまりは、ウィンドウ クラスに基づいて、既存のクラスを変更する`m_pfnSuperWindowProc`既存のウィンドウ クラスのウィンドウ プロシージャをポイントします。  
  
 [DefWindowProc](#defwindowproc)メソッドに保存されているウィンドウ プロシージャにメッセージの情報を送信する`m_pfnSuperWindowProc`です。  
  
##  <a name="m_pobject"></a>  CContainedWindowT::m_pObject  
 含むオブジェクトを指す、`CContainedWindowT`オブジェクト。  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>コメント  
 派生クラスが、このコンテナー [CMessageMap](../../atl/reference/cmessagemap-class.md)、コンテナー内のウィンドウで使用されるメッセージ マップを宣言します。  
  
 `m_pObject` コンス トラクターによって初期化されます。 例については、次を参照してください。、 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の概要です。  
  
##  <a name="registerwndsuperclass"></a>  CContainedWindowT::RegisterWndSuperclass  
 によって呼び出されます[作成](#create)コンテナー内のウィンドウのウィンドウ クラスを登録します。  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、atom 一意に識別する; 登録されているウィンドウ クラスそれ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 このウィンドウ クラスは、既存のクラスに基づきますが、使用[この段階](#windowproc)です。 既存のウィンドウ クラスの名前とウィンドウ プロシージャに保存されます[m_lpszClassName](#m_lpszclassname)と[コンテナー内](#m_pfnsuperwindowproc)、それぞれします。  
  
##  <a name="subclasswindow"></a>  CContainedWindowT::SubclassWindow  
 によって識別されるウィンドウ サブクラス`hWnd`にアタッチし、`CContainedWindowT`オブジェクト。  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]サブクラス化されているウィンドウ ハンドルです。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ウィンドウが正常にサブクラス化された、それ以外の場合は**FALSE**です。  
  
### <a name="remarks"></a>コメント  
 サブクラス化されたウィンドウは[この段階](#windowproc)です。 元のウィンドウ プロシージャに保存されて[コンテナー内](#m_pfnsuperwindowproc)です。  
  
> [!NOTE]
>  呼び出す必要はありません`SubclassWindow`既にを呼び出した場合[作成](#create)です。  
  
##  <a name="switchmessagemap"></a>  CContainedWindowT::SwitchMessageMap  
 含まれているウィンドウのメッセージの処理に使用される、メッセージ マップを変更します。  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMsgMapID`  
 [in]メッセージ マップの識別子。 宣言された既定のメッセージ マップを使用する[送るに](message-map-macros-atl.md#begin_msg_map)0 を渡します。 宣言された代替のメッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、渡す`msgMapID`です。  
  
### <a name="remarks"></a>コメント  
 メッセージ マップは、親オブジェクトで定義する必要があります。  
  
 最初に、コンス トラクターでメッセージ マップの識別子を指定します。  
  
##  <a name="unsubclasswindow"></a>  CContainedWindowT::UnsubclassWindow  
 サブクラス化されたウィンドウからのデタッチ、`CContainedWindowT`オブジェクトを復元元のウィンドウ プロシージャに保存されている[コンテナー内](#m_pfnsuperwindowproc)です。  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bForce`  
 [in]設定**TRUE**を復元する元のウィンドウ プロシージャを強制的に場合でもこれのウィンドウ プロシージャ`CContainedWindowT`オブジェクトが現在アクティブではありません。 場合`bForce`に設定されている**FALSE**およびこれのウィンドウ プロシージャ`CContainedWindowT`オブジェクトが現在アクティブなは、元のウィンドウ プロシージャは復元されません。  
  
### <a name="return-value"></a>戻り値  
 以前にサブクラス化されたウィンドウのハンドル。 場合`bForce`に設定されている**FALSE**およびこれのウィンドウ プロシージャ`CContainedWindowT`オブジェクトが現在アクティブでない、返します**NULL**です。  
  
### <a name="remarks"></a>コメント  
 ウィンドウが破棄される前に、元のウィンドウ プロシージャを復元する場合にのみ、このメソッドを使用します。 それ以外の場合、 [WindowProc](#windowproc)ウィンドウが破棄されるときに、これは自動的にします。  
  
##  <a name="windowproc"></a>  この段階  
 この静的メソッドでは、ウィンドウ プロシージャを実装します。  
  
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
 `WindowProc` によって識別されるメッセージ マップにメッセージを送ります[m_dwMsgMapID](#m_dwmsgmapid)です。 必要に応じて、`WindowProc`呼び出し[DefWindowProc](#defwindowproc)追加のメッセージ処理のためです。  
  
## <a name="see-also"></a>関連項目  
 [CWindow クラス](../../atl/reference/cwindow-class.md)   
 [CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap クラス](../../atl/reference/cmessagemap-class.md)   
 [送るに](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [クラスの概要](../../atl/atl-class-overview.md)
