---
title: CContainedWindowT クラス |Microsoft Docs
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
ms.openlocfilehash: 5e7e77238478e32fd5b45f96cdd8a86c2205eef7
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882846"
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
 新しいクラスの基本クラス。 既定の基本クラスは`CWindow`します。  
  
 *TWinTraits*  
 ウィンドウのスタイルを定義する特性クラス。 既定値は `CControlWinTraits` です。  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md)特殊化した`CContainedWindowT`します。 基底クラスまたは特性を変更する場合を使用して、`CContainedWindowT`直接します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|コンストラクターです。 メッセージ マップが含まれているウィンドウのメッセージの処理を指定するデータ メンバーを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|ウィンドウを作成します。|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|ウィンドウのウィンドウ クラスを登録します。|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|変更をメッセージ マップが含まれているウィンドウのメッセージの処理に使用します。|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|  
|[この段階](#windowproc)|(静的)コンテナー内のウィンドウに送信されるメッセージを処理します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|メッセージ マップが含まれているウィンドウのメッセージの処理を識別します。|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|新しいウィンドウ クラスの基になる既存のウィンドウ クラスの名前を指定します。|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|  
|[CContainedWindowT::m_pObject](#m_pobject)|親オブジェクトへのポインター。|  
  
## <a name="remarks"></a>Remarks  
 `CContainedWindowT` 別のオブジェクト内に含まれるウィンドウを実装します。 `CContainedWindowT`ウィンドウ プロシージャの使用を適切なハンドラーに直接メッセージを含むオブジェクトをメッセージ マップです。 構築するときに、`CContainedWindowT`オブジェクトをメッセージ マップを使用する必要がありますを指定します。  
  
 `CContainedWindowT` 既存のウィンドウ クラスをスーパークラス化して、新しいウィンドウを作成することができます。 `Create`メソッドは、まず既存のクラスに基づきますが、使用するウィンドウ クラスを登録`CContainedWindowT::WindowProc`します。 `Create` この新しいウィンドウ クラスに基づくウィンドウが作成されます。 各インスタンス`CContainedWindowT`スーパークラス別のウィンドウ クラスのことができます。  
  
 `CContainedWindowT` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CContainedWindowT` オブジェクトにアタッチし、ウィンドウ プロシージャを `CContainedWindowT::WindowProc` に変更します。 `CContainedWindowT` の各インスタンスは、別のウィンドウをサブクラス化できます。  
  
> [!NOTE]
>  指定されたいずれかの`CContainedWindowT`オブジェクト、いずれかを呼び出す`Create`または`SubclassWindow`します。 同じオブジェクトで両方のメソッドを呼び出しませんする必要があります。  
  
 使用すると、**に基づいてコントロールを追加**オプション、ATL プロジェクト ウィザードでは、ウィザードが自動的に追加、`CContainedWindowT`コントロールを実装するクラスのデータ メンバー。 次の例では、コンテナー内のウィンドウを宣言する方法を示しています。  
  
 [!code-cpp[NVC_ATL_Windowing#38](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#39](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing#40](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|詳細情報:|解決方法については、|  
|--------------------------------|---------|  
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|  
|ATL でのウィンドウの使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|  
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595)と Windows SDK の後続のトピック|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlwin.h  
  
##  <a name="ccontainedwindowt"></a>  CContainedWindowT::CContainedWindowT  
 コンス トラクターでは、データ メンバーを初期化します。  
  
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
 *lpszClassName*  
 [in]コンテナー内のウィンドウの基になる既存のウィンドウ クラスの名前。  
  
 *pObject*  
 [in]メッセージ マップを宣言する親オブジェクトへのポインター。 このオブジェクトのクラスがから派生する必要があります[CMessageMap](../../atl/reference/cmessagemap-class.md)します。  
  
 *dwMsgMapID*  
 [in]含まれているウィンドウのメッセージを処理するメッセージ マップを識別します。 既定値 0 は、指定で宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)します。 宣言された代替メッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、渡す`msgMapID`します。  
  
### <a name="remarks"></a>Remarks  
 新しいウィンドウを作成したい場合[作成](#create)の既存のウィンドウ クラスの名前を渡す必要があります、 *lpszClassName*パラメーター。 例については、次を参照してください。、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)の概要。  
  
 次の 3 つのコンス トラクターがあります。  
  
-   3 つの引数を持つコンス トラクターと通常呼ばれる 1 つです。  
  
-   2 つの引数を持つコンス トラクターからクラス名を使用する`TBase::GetWndClassName`します。  
  
-   引数なしのコンス トラクターは、後で、引数を指定する場合に使用されます。 後で呼び出すときに、ウィンドウ クラス名、メッセージ マップのオブジェクト、およびメッセージ マップの ID を指定する必要があります`Create`します。  
  
 場合、既存のウィンドウをサブクラスで[SubclassWindow](#subclasswindow)、 *lpszClassName*値は使用されません。 そのため、このパラメーターに NULL を渡すことができます。  
  
##  <a name="create"></a>  CContainedWindowT::Create  
 呼び出し[RegisterWndSuperclass](#registerwndsuperclass)は既存のクラスに基づきますが、使用するウィンドウ クラスを登録する[この段階](#windowproc)します。  
  
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
 *lpszClassName*  
 [in]コンテナー内のウィンドウの基になる既存のウィンドウ クラスの名前。  
  
 *pObject*  
 [in]メッセージ マップを宣言する親オブジェクトへのポインター。 このオブジェクトのクラスがから派生する必要があります[CMessageMap](../../atl/reference/cmessagemap-class.md)します。  
  
 *dwMsgMapID*  
 [in]含まれているウィンドウのメッセージを処理するメッセージ マップを識別します。 既定値 0 は、指定で宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)します。 宣言された代替メッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、渡す`msgMapID`します。  
  
 *hWndParent*  
 [in]親またはオーナー ウィンドウのハンドル。  
  
 *rect*  
 [in]A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ウィンドウの位置を指定する構造体。 `RECT`ポインターまたは参照によって渡すことができます。  
  
 *szWindowName*  
 [in]ウィンドウの名前を指定します。 既定値は、NULL です。  
  
 *dwStyle*  
 [in]ウィンドウのスタイル。 既定値は WS_CHILD &#124; WS_VISIBLE します。 使用可能な値の一覧は、次を参照してください。 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) Windows SDK に含まれています。  
  
 *dwExStyle*  
 [in]拡張ウィンドウ スタイル。 既定値は 0、つまり拡張スタイルはありません。 使用可能な値の一覧は、次を参照してください。 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK に含まれています。  
  
 *MenuOrID*  
 [in]子ウィンドウの場合、ウィンドウの識別子。 最上位レベルのウィンドウでは、メニューはウィンドウのハンドルします。 既定値は**0 u**します。  
  
 *lpCreateParam*  
 [in]ウィンドウの作成データへのポインター。 詳細については、最後のパラメーターの説明を参照してください。 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、新しく作成されたウィンドウを識別するハンドルそれ以外の場合は NULL です。  
  
### <a name="remarks"></a>Remarks  
 既存のウィンドウ クラス名で保存[m_lpszClassName](#m_lpszclassname)します。 `Create` この新しいクラスに基づくウィンドウが作成されます。 新しく作成されたウィンドウが自動的にアタッチ、`CContainedWindowT`オブジェクト。  
  
> [!NOTE]
>  呼び出さない`Create`既にを呼び出した場合[SubclassWindow](#subclasswindow)します。  
  
> [!NOTE]
>  値として 0 が使用する場合、 *MenuOrID*パラメーター 0 u として指定する必要があります (既定値)、コンパイラ エラーを回避するためにします。  
  
##  <a name="defwindowproc"></a>  CContainedWindowT::DefWindowProc  
 によって呼び出される[WindowProc](#windowproc)メッセージ マップで処理されないメッセージを処理します。  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 *uMsg*  
 [in]ウィンドウに送信されるメッセージ。  
  
 *wParam*  
 [in]追加のメッセージに固有の情報。  
  
 *lParam*  
 [in]追加のメッセージに固有の情報。  
  
### <a name="return-value"></a>戻り値  
 メッセージの処理の結果。  
  
### <a name="remarks"></a>Remarks  
 既定では、`DefWindowProc`呼び出し、 [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571)ウィンドウ プロシージャで指定されたメッセージの情報を送信する Win32 関数[コンテナー内](#m_pfnsuperwindowproc)します。  
  
##  <a name="getcurrentmessage"></a>  CContainedWindowT::GetCurrentMessage  
 現在のメッセージが返されます (`m_pCurrentMsg`)。  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>戻り値  
 現在のメッセージにパッケージ化、`MSG`構造体。  
  
##  <a name="m_dwmsgmapid"></a>  CContainedWindowT::m_dwMsgMapID  
 現在コンテナー内のウィンドウの使用中のメッセージ マップの識別子を保持します。  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>Remarks  
 このメッセージ マップは、親オブジェクトで宣言する必要があります。  
  
 宣言された既定のメッセージ マップ[送るに](message-map-macros-atl.md#begin_msg_map)、常に 0 で識別されます。 宣言された、代替メッセージ マップ[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、によって識別される`msgMapID`します。  
  
 `m_dwMsgMapID` コンス トラクターで初期化が、呼び出すことによって変更できます[SwitchMessageMap](#switchmessagemap)します。 例については、次を参照してください。、 [CContainedWindowT 概要](../../atl/reference/ccontainedwindowt-class.md)します。  
  
##  <a name="m_lpszclassname"></a>  CContainedWindowT::m_lpszClassName  
 既存のウィンドウ クラスの名前を指定します。  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>Remarks  
 ウィンドウを作成するときに[作成](#create)はこの既存のクラスに基づいていますが、使用する新しいウィンドウ クラスを登録[この段階](#windowproc)します。  
  
 `m_lpszClassName` コンス トラクターで初期化されます。 例については、次を参照してください。、 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の概要。  
  
##  <a name="m_pfnsuperwindowproc"></a>  CContainedWindowT::m_pfnSuperWindowProc  
 コンテナー内のウィンドウをサブクラス化すると場合、`m_pfnSuperWindowProc`ウィンドウ クラスの元のウィンドウ プロシージャを指します。  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>Remarks  
 既存のクラスを変更するウィンドウ クラスに基づくつまり含まれているウィンドウがスーパークラスの場合は、`m_pfnSuperWindowProc`既存のウィンドウ クラスのウィンドウ プロシージャを指します。  
  
 [DefWindowProc](#defwindowproc)メソッド メッセージの情報に保存されているウィンドウ プロシージャに送信する`m_pfnSuperWindowProc`します。  
  
##  <a name="m_pobject"></a>  CContainedWindowT::m_pObject  
 格納しているオブジェクトを指す、`CContainedWindowT`オブジェクト。  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>Remarks  
 派生するクラスがあります、このコンテナー [CMessageMap](../../atl/reference/cmessagemap-class.md)、コンテナー内のウィンドウで使用されるメッセージ マップを宣言します。  
  
 `m_pObject` コンス トラクターで初期化されます。 例については、次を参照してください。、 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の概要。  
  
##  <a name="registerwndsuperclass"></a>  CContainedWindowT::RegisterWndSuperclass  
 によって呼び出される[作成](#create)ウィンドウのウィンドウ クラスを登録します。  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、atom を一意に識別登録されるウィンドウ クラスそれ以外の場合、0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このウィンドウのクラスは、既存のクラスに基づきますが、使用[この段階](#windowproc)します。 既存のウィンドウ クラスの名前とウィンドウ プロシージャに保存されます[m_lpszClassName](#m_lpszclassname)と[コンテナー内](#m_pfnsuperwindowproc)、それぞれします。  
  
##  <a name="subclasswindow"></a>  CContainedWindowT::SubclassWindow  
 識別される、ウィンドウをサブクラス*hWnd*にアタッチします、`CContainedWindowT`オブジェクト。  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *hWnd*  
 [in]サブクラス化されているウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが正常にサブクラス化された場合は TRUE。それ以外の場合、FALSE です。  
  
### <a name="remarks"></a>Remarks  
 サブクラス化されたウィンドウは[この段階](#windowproc)します。 元のウィンドウ プロシージャに保存[コンテナー内](#m_pfnsuperwindowproc)します。  
  
> [!NOTE]
>  呼び出さない`SubclassWindow`既にを呼び出した場合[作成](#create)です。  
  
##  <a name="switchmessagemap"></a>  CContainedWindowT::SwitchMessageMap  
 含まれているウィンドウのメッセージの処理に使用されるどのメッセージ マップを変更します。  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwMsgMapID*  
 [in]メッセージ マップの識別子。 宣言された既定のメッセージ マップを使用する[送るに](message-map-macros-atl.md#begin_msg_map)0 を渡します。 宣言された代替メッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)、渡す`msgMapID`します。  
  
### <a name="remarks"></a>Remarks  
 メッセージ マップは、親オブジェクトで定義する必要があります。  
  
 最初に、コンス トラクターでメッセージ マップの識別子を指定します。  
  
##  <a name="unsubclasswindow"></a>  CContainedWindowT::UnsubclassWindow  
 サブクラス化されたウィンドウのデタッチ、`CContainedWindowT`オブジェクトし、元のウィンドウ プロシージャに保存されている復元[コンテナー内](#m_pfnsuperwindowproc)します。  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 *bForce*  
 [in]復元する元のウィンドウ プロシージャを強制する場合は true に設定場合でもこれのウィンドウ プロシージャ`CContainedWindowT`オブジェクトは現在アクティブではありません。 場合*bForce*この FALSE とウィンドウ プロシージャに設定されている`CContainedWindowT`オブジェクトが現在アクティブなは、元のウィンドウ プロシージャは復元されません。  
  
### <a name="return-value"></a>戻り値  
 以前にサブクラス化されたウィンドウのハンドル。 場合*bForce*この FALSE とウィンドウ プロシージャに設定されている`CContainedWindowT`オブジェクトが現在アクティブではありません、NULL が返されます。  
  
### <a name="remarks"></a>Remarks  
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
 *hWnd*  
 [in]ウィンドウのハンドル。  
  
 *uMsg*  
 [in]ウィンドウに送信されるメッセージ。  
  
 *wParam*  
 [in]追加のメッセージに固有の情報。  
  
 *lParam*  
 [in]追加のメッセージに固有の情報。  
  
### <a name="return-value"></a>戻り値  
 メッセージの処理の結果。  
  
### <a name="remarks"></a>Remarks  
 `WindowProc` 識別されるメッセージ マップにメッセージを送信[m_dwMsgMapID](#m_dwmsgmapid)します。 必要に応じて、`WindowProc`呼び出し[DefWindowProc](#defwindowproc)追加メッセージの処理。  
  
## <a name="see-also"></a>関連項目  
 [CWindow クラス](../../atl/reference/cwindow-class.md)   
 [CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap クラス](../../atl/reference/cmessagemap-class.md)   
 [送るに](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [クラスの概要](../../atl/atl-class-overview.md)
