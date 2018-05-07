---
title: CMDIChildWnd クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e27551c04be5d6e985c6e7829f11f94d0aafeba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd クラス
ウィンドウ管理用のメンバーも含めて、Windows のマルチ ドキュメント インターフェイス (MDI: multiple document interface) の子ウィンドウの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|`CMDIChildWnd` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|関連付けられている Windows MDI 子ウィンドウを作成、`CMDIChildWnd`オブジェクト。|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|親 MDI クライアント ウィンドウの MDI フレームを返します。|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|MDI 子ウィンドウをアクティブにします。|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|MDI 子ウィンドウを破棄します。|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|MDI 子ウィンドウを最大化します。|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|MDI 子ウィンドウを最大化または最小化されているサイズから復元します。|  
|[CMDIChildWnd::SetHandles](#sethandles)|メニューとアクセラレータのリソースに対するハンドルを設定します。|  
  
## <a name="remarks"></a>コメント  
 MDI 子ウィンドウがデスクトップ上ではなく、MDI フレーム ウィンドウ内に表示する点を除いて、一般的なフレーム ウィンドウと同様、MDI 子ウィンドウを検索します。 MDI 子ウィンドウでは、独自のメニュー バーではありませんが、代わりに、MDI フレーム ウィンドウのメニューを共有します。 フレームワークは、現在アクティブな MDI 子ウィンドウを表すため MDI フレームのメニューを自動的に変更します。  
  
 アプリケーションに役立ちます MDI 子ウィンドウを作成するには、派生クラスを`CMDIChildWnd`です。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 MDI 子ウィンドウを構築するための 3 つの方法があります。  
  
-   使用して直接構築**作成**です。  
  
-   使用して直接構築`LoadFrame`です。  
  
-   間接的に構築ドキュメント テンプレートを使用します。  
  
 呼び出す前に**作成**または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウ オブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に**作成**でウィンドウ クラスを登録することも、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。  
  
 使用して、**作成**引数を渡す、フレームの作成パラメーターとして直接のメンバー関数。  
  
 `LoadFrame` も少ない引数を必要と**作成**、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースからほとんどの既定値を取得します。 によってアクセスされる`LoadFrame`、これらすべてのリソースが同じリソース ID を持つ必要があります (たとえば、 **IDR_MAINFRAME**)。  
  
 ときに、`CMDIChildWnd`オブジェクトには、ビューやドキュメントが含まれています、によって作成されるない直接の代わりに、プログラマが直接のフレームワークです。 `CDocTemplate`オブジェクトは、フレームの作成、コンテナーのビューの作成と適切なドキュメント ビューの接続を統制します。 パラメーター、`CDocTemplate`コンス トラクターを指定して、 `CRuntimeClass` 3 つのクラスの関係 (ドキュメント、フレーム、および表示)。 A`CRuntimeClass`オブジェクトを動的に (たとえば、ファイルの新規作成 コマンドまたは MDI ウィンドウの新しいコマンドを使用して) を指定すると、ユーザーが新しいフレームを作成する、フレームワークによって使用されます。  
  
 フレーム ウィンドウ クラスから派生`CMDIChildWnd`で宣言する必要があります`DECLARE_DYNCREATE`上記の順序で`RUNTIME_CLASS`正常に動作するためのメカニズムです。  
  
 `CMDIChildWnd`クラスを継承から既定の実装の大部分`CFrameWnd`です。 これらの機能の詳細な一覧を参照してください、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの説明。 `CMDIChildWnd`クラスには次の追加機能。  
  
-   組み合わせて、`CMultiDocTemplate`クラス, 複数`CMDIChildWnd`同じドキュメント テンプレートからのオブジェクトが同じメニュー、Windows システム リソースが節約を共有します。  
  
-   現在アクティブな MDI 子ウィンドウのメニューが完全に MDI フレーム ウィンドウのメニューを置き換え、MDI フレーム ウィンドウのキャプションに現在アクティブな MDI 子ウィンドウのキャプションを追加します。 MDI フレーム ウィンドウと共にに実装されている MDI 子ウィンドウ関数の詳細な例については、次を参照してください。、`CMDIFrameWnd`クラスの説明。  
  
 C++ を使用しないでください**削除**フレーム ウィンドウを破棄する演算子です。 代わりに、`CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ オブジェクトが削除されます。 ユーザーが既定値であるフレーム ウィンドウを閉じたとき`OnClose`ハンドラーを呼び出す`DestroyWindow`です。  
  
 詳細については`CMDIChildWnd`を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cmdichildwnd"></a>  CMDIChildWnd::CMDIChildWnd  
 構築するために呼び出し、`CMDIChildWnd`オブジェクト。  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す**作成**表示ウィンドウを作成します。  
  
### <a name="example"></a>例  
  例を参照して[CMDIChildWnd::Create](#create)です。  
  
##  <a name="create"></a>  CMDIChildWnd::Create  
 Windows MDI 子ウィンドウを作成しにアタッチするには、このメンバー関数を呼び出す、`CMDIChildWnd`オブジェクト。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CMDIFrameWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 Windows クラスの名前を示す文字の null で終わる文字列へのポインター (、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造体)。 クラス名に登録されている任意の名前を指定できます、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数。 必要があります**NULL**標準の`CMDIChildWnd`します。  
  
 `lpszWindowName`  
 ウィンドウの名前を表す文字の null で終わる文字列へのポインター。 タイトル バーのテキストとして使用します。  
  
 `dwStyle`  
 ウィンドウを指定[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)属性。 **WS_CHILD**スタイルが必要です。  
  
 `rect`  
 ウィンドウの位置とサイズが含まれています。 `rectDefault`値により、新しい位置とサイズを指定する Windows`CMDIChildWnd`です。  
  
 `pParentWnd`  
 ウィンドウの親を指定します。 場合**NULL**アプリケーションのメイン ウィンドウを使用します。  
  
 `pContext`  
 指定します、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターを指定できます**NULL**です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 現在アクティブな MDI 子フレーム ウィンドウには、親フレーム ウィンドウのキャプションを判断できます。 この機能はオフになっている、 **FWS_ADDTOTITLE**子フレーム ウィンドウのスタイル ビットです。  
  
 フレームワークでは、このメンバー関数を呼び出して子ウィンドウを作成するコマンドをユーザーに応答してフレームワークを使用して、`pContext`子ウィンドウをアプリケーションに正しく接続するパラメーターです。 呼び出すと**作成**、`pContext`できます**NULL**です。  
  
### <a name="example"></a>例  
 例 1:  
  
 [!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>例  
 例 2:  
  
 [!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="getmdiframe"></a>  CMDIChildWnd::GetMDIFrame  
 この関数では、MDI 親フレームを返します。  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>戻り値  
 MDI 親フレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 返されたフレームは、2 つの親から削除された、`CMDIChildWnd`型のウィンドウの親であると**MDICLIENT**を管理する、`CMDIChildWnd`オブジェクト。 呼び出す、 [GetParent](../../mfc/reference/cwnd-class.md#getparent)を返すメンバー関数、`CMDIChildWnd`オブジェクトの即時**MDICLIENT**一時と親`CWnd`ポインター。  
  
### <a name="example"></a>例  
  例を参照して[CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)です。  
  
##  <a name="mdiactivate"></a>  CMDIChildWnd::MDIActivate  
 MDI フレーム ウィンドウとは無関係に MDI 子ウィンドウをアクティブ化するには、このメンバー関数を呼び出します。  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>コメント  
 フレームがアクティブになったときにもアクティブにされた子ウィンドウをアクティブ化されます。  
  
### <a name="example"></a>例  
  例を参照して[CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)です。  
  
##  <a name="mdidestroy"></a>  CMDIChildWnd::MDIDestroy  
 MDI 子ウィンドウを破棄するには、このメンバー関数を呼び出します。  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、フレーム ウィンドウから子ウィンドウのタイトルを削除し、子ウィンドウを非アクティブ化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="mdimaximize"></a>  CMDIChildWnd::MDIMaximize  
 MDI 子ウィンドウを最大化するには、このメンバー関数を呼び出します。  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>コメント  
 子ウィンドウを最大表示しているときに Windows では、そのクライアント領域のフレーム ウィンドウのクライアント領域を塗りつぶすにサイズ変更します。 Windows では、ユーザーが復元または子ウィンドウを閉じるようにフレームのメニュー バーで子ウィンドウのコントロールのメニューを配置し、フレーム ウィンドウのタイトルに子ウィンドウのタイトルを追加します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="mdirestore"></a>  CMDIChildWnd::MDIRestore  
 MDI 子ウィンドウを最大化または最小化されているサイズから復元するには、このメンバー関数を呼び出します。  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="sethandles"></a>  CMDIChildWnd::SetHandles  
 メニューとアクセラレータのリソースに対するハンドルを設定します。  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMenu`  
 メニュー リソースのハンドル。  
  
 `hAccel`  
 アクセラレータ リソースのハンドル。  
  
### <a name="remarks"></a>コメント  
 MDI 子ウィンドウのオブジェクトによって使用されているメニューとアクセラレータのリソースを設定するには、この関数を呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [MFC サンプルは](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)
