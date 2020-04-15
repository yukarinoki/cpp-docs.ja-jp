---
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
ms.openlocfilehash: 0fbcb47f3148b72a3155e7c17cc913d652c70c2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370080"
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
|[CMDIチャイルドウンド::CMDIチャイルドウンド](#cmdichildwnd)|`CMDIChildWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMDIチャイルドウンド::作成](#create)|オブジェクトに関連付けられた Windows MDI`CMDIChildWnd`子ウィンドウを作成します。|
|[マチチャイルドウンド::ゲットムディフレーム](#getmdiframe)|MDI クライアント ウィンドウの親 MDI フレームを返します。|
|[CMDIチャイルドウンド::MDIアクティベート](#mdiactivate)|この MDI 子ウィンドウをアクティブにします。|
|[マフィチャイルドウンド::MDIデストロイ](#mdidestroy)|この MDI 子ウィンドウを破棄します。|
|[マチチャイルドウンド::MDI最大化](#mdimaximize)|この MDI 子ウィンドウを最大化します。|
|[マシチャイルドウンド::MDI復元](#mdirestore)|この MDI 子ウィンドウを最大化または最小化されたサイズから復元します。|
|[を設定します。](#sethandles)|メニューリソースとアクセラレータリソースのハンドルを設定します。|

## <a name="remarks"></a>解説

MDI 子ウィンドウは、通常のフレーム ウィンドウとよく似ていますが、MDI 子ウィンドウはデスクトップではなく MDI フレーム ウィンドウ内に表示されます。 MDI 子ウィンドウには、独自のメニュー バーはありませんが、MDI フレーム ウィンドウのメニューを共有します。 フレームワークは、現在アクティブな MDI 子ウィンドウを表す MDI フレーム メニューを自動的に変更します。

アプリケーションに便利な MDI 子ウィンドウを作成するには、 から`CMDIChildWnd`クラスを派生させます。 派生クラスにメンバー変数を追加して、アプリケーション固有のデータを格納します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。

MDI 子ウィンドウを構築するには、次の 3 つの方法があります。

- を使用して`Create`直接構築します。

- を使用して`LoadFrame`直接構築します。

- 間接的にドキュメント テンプレートを使用して構築します。

または`LoadFrame`を`Create`呼び出す前に、C++ **new**演算子を使用して、ヒープ上にフレーム ウィンドウ オブジェクトを構築する必要があります。 呼び`Create`出す前に、フレームのアイコンとクラス スタイルを設定する[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数を使用してウィンドウ クラスを登録することもできます。

メンバー関数`Create`を使用して、フレームの作成パラメーターを即時引数として渡します。

`LoadFrame`必要な引数は`Create`よりも少なく、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、メニューなど、リソースからその既定値のほとんどを取得します。 で`LoadFrame`アクセスできるようにするには、これらすべてのリソースに同じリソース ID (IDR_MAINFRAME など) が必要です。

オブジェクトに`CMDIChildWnd`ビューとドキュメントが含まれている場合、それらはプログラマが直接作成するのではなく、フレームワークによって間接的に作成されます。 オブジェクト`CDocTemplate`は、フレームの作成、含むビューの作成、およびビューの適切なドキュメントへの接続を調整します。 コンストラクターのパラメーターは`CDocTemplate`、関連する`CRuntimeClass`3 つのクラス (ドキュメント、フレーム、ビュー) の を指定します。 オブジェクト`CRuntimeClass`は、ユーザーが指定した場合 (たとえば、ファイル新規作成コマンドまたは MDI ウィンドウ新規作成コマンドを使用して) 新しいフレームを動的に作成するために、フレームワークによって使用されます。

上記のRUNTIME_CLASS機構が正しく`CMDIChildWnd`機能するためには、派生したフレーム ウィンドウ クラスをDECLARE_DYNCREATEで宣言する必要があります。

この`CMDIChildWnd`クラスは、既定の実装の多くを`CFrameWnd`から継承します。 これらの機能の詳細なリストについては[、CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの説明を参照してください。 この`CMDIChildWnd`クラスには、次の追加機能があります。

- `CMultiDocTemplate`クラスと組み合わせて、`CMDIChildWnd`同じドキュメント テンプレートの複数のオブジェクトが同じメニューを共有し、Windows システム リソースを節約します。

- 現在アクティブな MDI 子ウィンドウ メニューは、MDI フレーム ウィンドウのメニューに完全に置き換わります。 MDI フレーム ウィンドウと共に実装される MDI 子ウィンドウ関数の詳細な例については、`CMDIFrameWnd`クラスの説明を参照してください。

C++**の delete**演算子を使用してフレーム ウィンドウを破棄しないでください。 代わりに `CWnd::DestroyWindow` を使用してください の`CFrameWnd``PostNcDestroy`実装は、ウィンドウが破棄されると C++ オブジェクトを削除します。 ユーザーがフレーム ウィンドウを閉じると、既定`OnClose`のハンドラーが`DestroyWindow`呼び出されます。

詳細については、「`CMDIChildWnd`フレーム[ウィンドウ](../../mfc/frame-windows.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMDIChildWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a>CMDIチャイルドウンド::CMDIチャイルドウンド

オブジェクトを構築するための`CMDIChildWnd`呼び出し。

```
CMDIChildWnd();
```

### <a name="remarks"></a>解説

表示`Create`ウィンドウを作成する呼び出し。

### <a name="example"></a>例

  [「CMDIChildWnd::作成](#create)」の例を参照してください。

## <a name="cmdichildwndcreate"></a><a name="create"></a>CMDIチャイルドウンド::作成

Windows MDI 子ウィンドウを作成し、`CMDIChildWnd`オブジェクトにアタッチします。

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

*クラス名*<br/>
Windows クラス[(WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)構造体) に名前を付ける NULL で終わる文字列を指します。 クラス名は[、AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数に登録された任意の名前にすることができます。 標準の場合は NULL`CMDIChildWnd`にする必要があります。

*名前をクリックします。*<br/>
ウィンドウ名を表す null で終わる文字列を指します。 タイトル バーのテキストとして使用されます。

*Dwstyle*<br/>
ウィンドウ[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)の属性を指定します。 WS_CHILDスタイルが必要です。

*Rect*<br/>
ウィンドウのサイズと位置を示します。 この`rectDefault`値を使用すると、新しい`CMDIChildWnd`.

*pParentWnd*<br/>
ウィンドウの親を指定します。 NULL の場合は、メイン アプリケーション ウィンドウが使用されます。

*pContext*<br/>
構造体を指定[します](../../mfc/reference/ccreatecontext-structure.md)。 このパラメーターは NULL にすることができます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

現在アクティブな MDI 子フレーム ウィンドウは、親フレーム ウィンドウのキャプションを決定できます。 この機能は、子フレーム ウィンドウのFWS_ADDTOTITLE スタイル ビットをオフにすることで無効になります。

フレームワークは、子ウィンドウを作成するユーザー コマンドに応答してこのメンバー関数を呼び出し、フレームワークは *、pContext*パラメーターを使用して、子ウィンドウをアプリケーションに適切に接続します。 を呼び`Create`出すとき*は、pContext*を NULL にできます。

### <a name="example"></a>例

例 1:

[!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]

### <a name="example"></a>例

例 2:

[!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]

[!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]

## <a name="cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a>マチチャイルドウンド::ゲットムディフレーム

MDI 親フレームを返します。

```
CMDIFrameWnd* GetMDIFrame();
```

### <a name="return-value"></a>戻り値

MDI 親フレーム ウィンドウへのポインター。

### <a name="remarks"></a>解説

返されるフレームは、 から削除された`CMDIChildWnd`2 つの親であり、オブジェクトを管理する MDICLIENT`CMDIChildWnd`型のウィンドウの親です。 オブジェクトの直接 MDICLIENT 親`CMDIChildWnd`を一時的な`CWnd`ポインターとして返す[GetParent](../../mfc/reference/cwnd-class.md#getparent)メンバー関数を呼び出します。

### <a name="example"></a>例

  [次](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)の例を参照してください。

## <a name="cmdichildwndmdiactivate"></a><a name="mdiactivate"></a>CMDIチャイルドウンド::MDIアクティベート

MDI フレーム ウィンドウとは独立して MDI 子ウィンドウをアクティブにします。

```
void MDIActivate();
```

### <a name="remarks"></a>解説

フレームがアクティブになると、最後にアクティブになった子ウィンドウもアクティブになります。

### <a name="example"></a>例

  [の例を](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)参照してください。

## <a name="cmdichildwndmdidestroy"></a><a name="mdidestroy"></a>マフィチャイルドウンド::MDIデストロイ

MDI 子ウィンドウを破棄するには、このメンバー関数を呼び出します。

```
void MDIDestroy();
```

### <a name="remarks"></a>解説

メンバー関数は、フレーム ウィンドウから子ウィンドウのタイトルを削除し、子ウィンドウを非アクティブにします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]

## <a name="cmdichildwndmdimaximize"></a><a name="mdimaximize"></a>マチチャイルドウンド::MDI最大化

MDI 子ウィンドウを最大化するには、このメンバー関数を呼び出します。

```
void MDIMaximize();
```

### <a name="remarks"></a>解説

子ウィンドウが最大化されると、Windows は、クライアント領域がフレーム ウィンドウのクライアント領域いっぱいに変更されます。 Windows では、子ウィンドウのコントロール メニューがフレームのメニュー バーに配置されるため、ユーザーは子ウィンドウを元に戻したり閉じたりして、子ウィンドウのタイトルをフレーム ウィンドウのタイトルに追加できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]

## <a name="cmdichildwndmdirestore"></a><a name="mdirestore"></a>マシチャイルドウンド::MDI復元

MDI 子ウィンドウを最大化または最小化されたサイズから復元します。

```
void MDIRestore();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]

## <a name="cmdichildwndsethandles"></a><a name="sethandles"></a>を設定します。

メニューリソースとアクセラレータリソースのハンドルを設定します。

```
void SetHandles(
    HMENU hMenu,
    HACCEL hAccel);
```

### <a name="parameters"></a>パラメーター

*Hmenu*<br/>
メニュー リソースのハンドル。

*ハッセル*<br/>
アクセラレータ リソースのハンドル。

### <a name="remarks"></a>解説

MDI 子ウィンドウ オブジェクトによって使用されるメニューとアクセラレータ のリソースを設定します。

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[サンプル MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル スナップVW](../../overview/visual-cpp-samples.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)
