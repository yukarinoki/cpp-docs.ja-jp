---
description: '詳細情報: CMDIChildWnd クラス'
title: CMDIChildWnd クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 4e9bf936cbb4f07401e8d54c56516f8846f2fc0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336697"
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
|[CMDIChildWnd:: CMDIChildWnd](#cmdichildwnd)|`CMDIChildWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMDIChildWnd:: Create](#create)|オブジェクトに関連付けられた Windows MDI 子ウィンドウを作成し `CMDIChildWnd` ます。|
|[CMDIChildWnd:: GetMDIFrame](#getmdiframe)|MDI クライアントウィンドウの親 MDI フレームを返します。|
|[CMDIChildWnd:: MDIActivate](#mdiactivate)|この MDI 子ウィンドウをアクティブにします。|
|[CMDIChildWnd:: MDIDestroy](#mdidestroy)|この MDI 子ウィンドウを破棄します。|
|[CMDIChildWnd:: MDIMaximize](#mdimaximize)|この MDI 子ウィンドウを最大化します。|
|[CMDIChildWnd:: MDIRestore](#mdirestore)|この MDI 子ウィンドウを最大化または最小化されたサイズから復元します。|
|[CMDIChildWnd:: SetHandles](#sethandles)|メニューとアクセラレータのリソースのハンドルを設定します。|

## <a name="remarks"></a>解説

Mdi 子ウィンドウは、一般的なフレームウィンドウのように見えますが、mdi 子ウィンドウは、デスクトップではなく MDI フレームウィンドウ内に表示される点が異なります。 MDI 子ウィンドウには独自のメニューバーはありませんが、代わりに MDI フレームウィンドウのメニューが共有されます。 現在アクティブな MDI 子ウィンドウを表すように、フレームワークによって MDI フレームメニューが自動的に変更されます。

アプリケーションに便利な MDI 子ウィンドウを作成するには、からクラスを派生させ `CMDIChildWnd` ます。 アプリケーションに固有のデータを格納するために、派生クラスにメンバー変数を追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

MDI 子ウィンドウを構築するには、次の3つの方法があります。

- を使用して直接作成 `Create` します。

- を使用して直接作成 `LoadFrame` します。

- ドキュメントテンプレートを使用して間接的に構築します。

またはを呼び出す前に、 `Create` `LoadFrame` C++ の演算子を使用して、ヒープ上にフレームウィンドウオブジェクトを構築する必要があり **`new`** ます。 を呼び出す前に、 `Create` ウィンドウクラスを [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) グローバル関数に登録して、フレームのアイコンとクラススタイルを設定することもできます。

メンバー関数を使用し `Create` て、フレームの作成パラメーターをイミディエイト引数として渡します。

`LoadFrame` に必要な引数がより少なく `Create` 、代わりに、フレームのキャプション、アイコン、アクセラレータテーブル、メニューなど、リソースからほとんどの既定値を取得します。 によってアクセスできるようにするには `LoadFrame` 、これらすべてのリソースが同じリソース ID を持つ必要があります (たとえば、IDR_MAINFRAME)。

オブジェクトに `CMDIChildWnd` ビューとドキュメントが含まれている場合は、プログラマが直接作成するのではなく、フレームワークによって間接的に作成されます。 オブジェクトは、 `CDocTemplate` フレームの作成、含まれるビューの作成、および適切なドキュメントへのビューの接続を調整します。 コンストラクターのパラメーターは、 `CDocTemplate` 関連する `CRuntimeClass` 3 つのクラス (ドキュメント、フレーム、およびビュー) のを指定します。 `CRuntimeClass`オブジェクトは、ユーザーが指定したときに新しいフレームを動的に作成するために、フレームワークによって使用されます (たとえば、File new コマンドや MDI Window new コマンドを使用します)。

上の RUNTIME_CLASS 機構を正しく動作させるには、から派生したフレームウィンドウクラスを `CMDIChildWnd` DECLARE_DYNCREATE で宣言する必要があります。

クラスは、 `CMDIChildWnd` の既定の実装の多くを継承 `CFrameWnd` します。 これらの機能の詳細な一覧については、 [CFrameWnd](../../mfc/reference/cframewnd-class.md) クラスの説明を参照してください。 クラスには `CMDIChildWnd` 、次の追加機能があります。

- クラスと共に `CMultiDocTemplate` 、 `CMDIChildWnd` 同じドキュメントテンプレートの複数のオブジェクトが同じメニューを共有し、Windows システムリソースを保存します。

- 現在アクティブな MDI 子ウィンドウメニューは、MDI フレームウィンドウのメニューを完全に置き換えるもので、現在アクティブな MDI 子ウィンドウのキャプションが MDI フレームウィンドウのキャプションに追加されます。 MDI フレームウィンドウと共に実装される MDI 子ウィンドウ関数のその他の例については、クラスの説明を参照してください `CMDIFrameWnd` 。

C++ の演算子を使用して **`delete`** フレームウィンドウを破棄しないでください。 代わりに、`CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装は、 `PostNcDestroy` ウィンドウが破棄されたときに C++ オブジェクトを削除します。 ユーザーがフレームウィンドウを閉じると、既定の `OnClose` ハンドラーはを呼び出し `DestroyWindow` ます。

の詳細につい `CMDIChildWnd` ては、「 [フレームウィンドウ](../../mfc/frame-windows.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a> CMDIChildWnd:: CMDIChildWnd

を呼び出して、 `CMDIChildWnd` オブジェクトを構築します。

```
CMDIChildWnd();
```

### <a name="remarks"></a>解説

`Create`を呼び出して、表示されるウィンドウを作成します。

### <a name="example"></a>例

  [CMDIChildWnd:: Create](#create)の例を参照してください。

## <a name="cmdichildwndcreate"></a><a name="create"></a> CMDIChildWnd:: Create

このメンバー関数を呼び出して、Windows MDI 子ウィンドウを作成し、オブジェクトにアタッチし `CMDIChildWnd` ます。

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

*lpszClassName*<br/>
Windows クラス ( [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 構造体) に名前を指定する null で終わる文字列を指します。 クラス名には、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) グローバル関数に登録されている任意の名前を指定できます。 標準の場合は NULL にする必要があり `CMDIChildWnd` ます。

*lpszWindowName*<br/>
ウィンドウ名を表す null で終わる文字列を指します。 タイトルバーのテキストとして使用されます。

*dwStyle*<br/>
ウィンドウ [スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles) 属性を指定します。 WS_CHILD スタイルが必要です。

*rect*<br/>
ウィンドウのサイズと位置を格納します。 この `rectDefault` 値により、Windows は新しいのサイズと位置を指定でき `CMDIChildWnd` ます。

*pParentWnd*<br/>
ウィンドウの親を指定します。 NULL の場合、メインアプリケーションウィンドウが使用されます。

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体を指定します。 このパラメーターは、NULL でもかまいません。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

現在アクティブな MDI 子フレームウィンドウでは、親フレームウィンドウのキャプションを確認できます。 この機能は、子フレームウィンドウの FWS_ADDTOTITLE スタイルビットをオフにすると無効になります。

フレームワークは、ユーザーコマンドに応答してこのメンバー関数を呼び出し、子ウィンドウを作成します。フレームワークは、 *pContext* パラメーターを使用して、子ウィンドウをアプリケーションに適切に接続します。 を呼び出すと `Create` 、 *PCONTEXT* を NULL にすることができます。

### <a name="example"></a>例

例 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>例

例 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

## <a name="cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a> CMDIChildWnd:: GetMDIFrame

MDI 親フレームを返すには、この関数を呼び出します。

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>戻り値

MDI 親フレームウィンドウへのポインター。

### <a name="remarks"></a>解説

返されるフレームはから削除された2つの親であり、 `CMDIChildWnd` オブジェクトを管理する MDICLIENT 型のウィンドウの親です `CMDIChildWnd` 。 [](../../mfc/reference/cwnd-class.md#getparent) `CMDIChildWnd` オブジェクトのイミディエイト MDICLIENT parent を一時ポインターとして返すには、GetParent メンバー関数を呼び出し `CWnd` ます。

### <a name="example"></a>例

  [CMDIFrameWnd:: MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)の例を参照してください。

## <a name="cmdichildwndmdiactivate"></a><a name="mdiactivate"></a> CMDIChildWnd:: MDIActivate

Mdi フレームウィンドウとは別に MDI 子ウィンドウをアクティブにするには、このメンバー関数を呼び出します。

```cpp
void MDIActivate();
```

### <a name="remarks"></a>解説

フレームがアクティブになると、最後にアクティブ化された子ウィンドウもアクティブになります。

### <a name="example"></a>例

  [CMDIFrameWnd:: GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)の例を参照してください。

## <a name="cmdichildwndmdidestroy"></a><a name="mdidestroy"></a> CMDIChildWnd:: MDIDestroy

このメンバー関数を呼び出して、MDI 子ウィンドウを破棄します。

```cpp
void MDIDestroy();
```

### <a name="remarks"></a>解説

このメンバー関数は、フレームウィンドウから子ウィンドウのタイトルを削除し、子ウィンドウを非アクティブにします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

## <a name="cmdichildwndmdimaximize"></a><a name="mdimaximize"></a> CMDIChildWnd:: MDIMaximize

MDI 子ウィンドウを最大化するには、このメンバー関数を呼び出します。

```cpp
void MDIMaximize();
```

### <a name="remarks"></a>解説

子ウィンドウが最大化されると、クライアント領域がフレームウィンドウのクライアント領域に収まるように、ウィンドウのサイズが変更されます。 Windows では、子ウィンドウのコントロールメニューをフレームのメニューバーに配置して、ユーザーが子ウィンドウを復元または閉じ、子ウィンドウのタイトルをフレームウィンドウのタイトルに追加できるようにします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

## <a name="cmdichildwndmdirestore"></a><a name="mdirestore"></a> CMDIChildWnd:: MDIRestore

このメンバー関数を呼び出して、最大化または最小化されたサイズから MDI 子ウィンドウを復元します。

```cpp
void MDIRestore();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

## <a name="cmdichildwndsethandles"></a><a name="sethandles"></a> CMDIChildWnd:: SetHandles

メニューとアクセラレータのリソースのハンドルを設定します。

```cpp
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>パラメーター

*hMenu*<br/>
メニューリソースのハンドル。

*hAccel*<br/>
アクセラレータリソースのハンドル。

### <a name="remarks"></a>解説

MDI 子ウィンドウオブジェクトによって使用されるメニューおよびアクセラレータリソースを設定するには、この関数を呼び出します。

## <a name="see-also"></a>関連項目

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)
