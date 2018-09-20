---
title: CMDIChildWnd クラス |Microsoft Docs
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
ms.openlocfilehash: 995e0ed8dc9d04dd67cd1f4521d4550ccdad36fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390188"
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
|[CMDIChildWnd::MDIRestore](#mdirestore)|最大化または最小化されたサイズの MDI 子ウィンドウを復元します。|
|[CMDIChildWnd::SetHandles](#sethandles)|メニューとアクセラレータ リソースのハンドルを設定します。|

## <a name="remarks"></a>Remarks

デスクトップではなく、MDI フレーム ウィンドウ内に MDI 子ウィンドウが表示されますが、一般的なフレーム ウィンドウと同様、MDI 子ウィンドウを検索します。 MDI 子ウィンドウでは、独自のメニュー バーではありませんが、代わりに、MDI フレーム ウィンドウのメニューを共有します。 フレームワークでは、現在アクティブな MDI 子ウィンドウを表す MDI フレームのメニューに自動的に変更します。

アプリケーション用の便利な MDI 子ウィンドウを作成するには、派生クラスを`CMDIChildWnd`します。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

MDI 子ウィンドウを作成する 3 つの方法はあります。

- 使用して直接構築`Create`します。

- 使用して直接構築`LoadFrame`します。

- 間接的に構築ドキュメント テンプレートを使用します。

呼び出す前に`Create`または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウ オブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に`Create`ウィンドウ クラスを登録することも、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。

使用して、`Create`メンバー関数は、イミディ エイト引数フレームの作成パラメーターを渡す。

`LoadFrame` も少ない引数が必要です`Create`、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースからほとんどの既定値を取得します。 アクセスできる`LoadFrame`、これらすべてのリソースは resource ID (たとえば、IDR_MAINFRAME) が同じである必要があります。

ときに、`CMDIChildWnd`オブジェクトには、ビューやドキュメントが含まれています、これらは間接的に作成、プログラマが直接の代わりに、フレームワークによって。 `CDocTemplate`オブジェクトは、フレームの作成、コンテナーのビューの作成と適切なドキュメント ビューの接続を調整します。 パラメーター、`CDocTemplate`コンス トラクターを指定、 `CRuntimeClass` 3 つのクラスの関係 (ドキュメント、フレーム、および表示)。 A`CRuntimeClass`オブジェクトが動的に (たとえば、新しいファイルまたは MDI ウィンドウの新しいコマンドを使用して) を指定すると、ユーザーが新しいフレームを作成するために、フレームワークによって使用されます。

フレーム ウィンドウ クラスから派生した`CMDIChildWnd`RUNTIME_CLASS 機構が正常に動作する上記の順序で DECLARE_DYNCREATE で宣言する必要があります。

`CMDIChildWnd`クラスを継承から既定の実装の多く`CFrameWnd`します。 これらの機能の詳細な一覧を参照してください、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの説明。 `CMDIChildWnd`クラスには、次の追加機能。

- 組み合わせて、`CMultiDocTemplate`クラス, 複数`CMDIChildWnd`同じドキュメント テンプレートからオブジェクトが、Windows システム リソースを保存しています。 同じメニューを共有します。

- 現在アクティブな MDI 子ウィンドウのメニューが完全に MDI フレーム ウィンドウのメニューを置き換え、MDI フレーム ウィンドウのキャプションに、現在アクティブな MDI 子ウィンドウのキャプションを追加します。 MDI フレーム ウィンドウと共に実装されている MDI 子ウィンドウ関数の詳細例については、次を参照してください。、`CMDIFrameWnd`クラスの説明。

C++ を使用しないでください**削除**フレーム ウィンドウを破棄する演算子。 代わりに、`CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ のオブジェクトが削除されます。 ユーザーが既定値であるフレーム ウィンドウを閉じるときに`OnClose`ハンドラーが呼び出す`DestroyWindow`します。

詳細については`CMDIChildWnd`を参照してください[フレーム Windows](../../mfc/frame-windows.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

##  <a name="cmdichildwnd"></a>  CMDIChildWnd::CMDIChildWnd

構築への呼び出しを`CMDIChildWnd`オブジェクト。

```
CMDIChildWnd();
```

### <a name="remarks"></a>Remarks

呼び出す`Create`表示のウィンドウを作成します。

### <a name="example"></a>例

  例をご覧ください[CMDIChildWnd::Create](#create)します。

##  <a name="create"></a>  CMDIChildWnd::Create

Windows MDI 子ウィンドウを作成し、アタッチするには、このメンバー関数を呼び出して、`CMDIChildWnd`オブジェクト。

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
Windows クラスの名前を示す文字の null で終わる文字列の指す (、 [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576)構造)。 クラス名が登録されている任意の名前を指定できます、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数。 標準の NULL にする必要があります`CMDIChildWnd`します。

*したとき*<br/>
ウィンドウの名前を表す null で終わる文字列へのポインター。 タイトル バーのテキストとして使用します。

*dwStyle*<br/>
ウィンドウを指定[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)属性。 WS_CHILD スタイルが必要です。

*rect*<br/>
ウィンドウの位置とサイズが含まれています。 `rectDefault`値により、新しい位置とサイズを指定する Windows`CMDIChildWnd`します。

*pParentWnd*<br/>
ウィンドウの親を指定します。 NULL の場合、アプリケーションのメイン ウィンドウが使用されます。

*pContext*<br/>
指定します、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターは、NULL を指定できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

現在アクティブな MDI 子フレーム ウィンドウには、親フレーム ウィンドウのキャプションを判断できます。 子フレーム ウィンドウの FWS_ADDTOTITLE スタイル ビットをオフにすることでこの機能は無効です。

フレームワークが、子ウィンドウを作成するコマンドをユーザーの応答でこのメンバー関数を呼び出すと、フレームワーク、 *pContext*子ウィンドウをアプリケーションに正しく接続パラメーター。 呼び出すと`Create`、 *pContext* NULL を指定できます。

### <a name="example"></a>例

例 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>例

例 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

##  <a name="getmdiframe"></a>  CMDIChildWnd::GetMDIFrame

MDI 親フレームを返すには、この関数を呼び出します。

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>戻り値

MDI 親フレーム ウィンドウへのポインター。

### <a name="remarks"></a>Remarks

返されるフレームは 2 つの親から削除、`CMDIChildWnd`の種類を管理する [クイック ウォッチ] ウィンドウの親であると、`CMDIChildWnd`オブジェクト。 呼び出す、 [GetParent](../../mfc/reference/cwnd-class.md#getparent)を返すメンバー関数、`CMDIChildWnd`オブジェクトの直接の クイック ウォッチ親として、一時的な`CWnd`ポインター。

### <a name="example"></a>例

  例をご覧ください[CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)します。

##  <a name="mdiactivate"></a>  CMDIChildWnd::MDIActivate

MDI フレーム ウィンドウとは無関係に MDI 子ウィンドウをアクティブ化するには、このメンバー関数を呼び出します。

```
void MDIActivate();
```

### <a name="remarks"></a>Remarks

フレームがアクティブになると、子ウィンドウに最後にアクティブ化はもアクティブにします。

### <a name="example"></a>例

  例をご覧ください[CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)します。

##  <a name="mdidestroy"></a>  CMDIChildWnd::MDIDestroy

MDI 子ウィンドウを破棄するには、このメンバー関数を呼び出します。

```
void MDIDestroy();
```

### <a name="remarks"></a>Remarks

メンバー関数は、フレーム ウィンドウから子ウィンドウのタイトルを削除し、子ウィンドウを非アクティブ化します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

##  <a name="mdimaximize"></a>  CMDIChildWnd::MDIMaximize

MDI 子ウィンドウを最大化するには、このメンバー関数を呼び出します。

```
void MDIMaximize();
```

### <a name="remarks"></a>Remarks

子ウィンドウを最大化したときに Windows では、フレーム ウィンドウのクライアント領域全体のクライアント領域にサイズ変更されます。 Windows では、ユーザーが復元または子ウィンドウを閉じるようにフレームのメニュー バーで、子ウィンドウのコントロール メニューを配置し、フレーム ウィンドウのタイトルに子ウィンドウのタイトルを追加します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

##  <a name="mdirestore"></a>  CMDIChildWnd::MDIRestore

MDI 子ウィンドウを最大化または最小化されたサイズから復元するには、このメンバー関数を呼び出します。

```
void MDIRestore();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

##  <a name="sethandles"></a>  CMDIChildWnd::SetHandles

メニューとアクセラレータ リソースのハンドルを設定します。

```
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>パラメーター

*hMenu*<br/>
メニュー リソースのハンドル。

*hAccel*<br/>
アクセラレータ リソースのハンドル。

### <a name="remarks"></a>Remarks

MDI 子ウィンドウのオブジェクトによって使用されるリソースのメニューとアクセラレータのリソースを設定するには、この関数を呼び出します。

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../visual-cpp-samples.md)<br/>
[MFC のサンプルは](../../visual-cpp-samples.md)<br/>
[MFC サンプル SNAPVW](../../visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)
