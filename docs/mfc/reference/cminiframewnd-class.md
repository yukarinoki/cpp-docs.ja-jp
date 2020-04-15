---
title: CMiniFrameWnd クラス
ms.date: 11/04/2016
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
ms.openlocfilehash: e9b91161f4207f4d2215d8777beade93617ddfac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319820"
---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd クラス

フローティング ツール バーの周りなどで使用される、半分の高さのフレーム ウィンドウを表します。

## <a name="syntax"></a>構文

```
class CMiniFrameWnd : public CFrameWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cミニフレームウンド::Cミニフレームウンド](#cminiframewnd)|`CMiniFrameWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cミニフレームウンド::作成](#create)|構築後`CMiniFrameWnd`にオブジェクトを作成します。|
|[Cミニフレームウンド::作成します。](#createex)|構築後`CMiniFrameWnd`に、追加オプションを使用してオブジェクトを作成します。|

## <a name="remarks"></a>解説

これらのミニフレーム ウィンドウは通常のフレーム ウィンドウと同じように動作しますが、最小化/最大化ボタンやメニューが表示されず、システム メニューをシングルクリックするだけで閉じられます。

オブジェクトを`CMiniFrameWnd`使用するには、まずオブジェクトを定義します。 次に[、Create](#create)メンバー関数を呼び出してミニフレーム ウィンドウを表示します。

オブジェクトの使用方法`CMiniFrameWnd`の詳細については、「[ドッキング ツール バーとフローティング ツール バー](../../mfc/docking-and-floating-toolbars.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cminiframewndcminiframewnd"></a><a name="cminiframewnd"></a>Cミニフレームウンド::Cミニフレームウンド

オブジェクトを`CMiniFrameWnd`構築しますが、ウィンドウは作成しません。

```
CMiniFrameWnd();
```

### <a name="remarks"></a>解説

ウィンドウを作成するには[、CMiniFrameWnd::Create](#create)を呼び出します。

## <a name="cminiframewndcreate"></a><a name="create"></a>Cミニフレームウンド::作成

Windows ミニフレーム ウィンドウを作成し、オブジェクトに`CMiniFrameWnd`アタッチします。

```
virtual BOOL Create(
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>パラメーター

*クラス名*<br/>
Windows クラスの名前を示す null で終わる文字列を指します。 クラス名は、グローバル[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)関数に登録された任意の名前にすることができます。 NULL の場合、ウィンドウ クラスはフレームワークによって登録されます。 MFC では、既定のクラスに次のスタイルと属性が提供されます。

- スタイル ビット CS_DBLCLKSを設定します。

- スタイル ビットCS_HREDRAWおよびCS_VREDRAWを設定し、ウィンドウのサイズが変更されたときにクライアント領域の内容を再描画するように指示します。

- クラス カーソルを Windows 標準IDC_ARROWに設定します。

- クラスの背景ブラシを NULL に設定して、ウィンドウの背景を消去しないようにします。

- クラス アイコンを標準の、手を振るフラグの Windows ロゴ アイコンに設定します。

- ウィンドウのサイズと位置を Windows で指定した既定のサイズと位置に設定します。

*ウィンドウ名*<br/>
ウィンドウ名を含む NULL で終わる文字列を指します。

*Dwstyle*<br/>
ウィンドウ スタイルの属性を指定します。 標準のウィンドウ スタイルと、次の特殊なスタイルの 1 つ以上を含めることができます。

- MFS_MOVEFRAME キャプションだけでなく、ウィンドウの任意の端をクリックしてミニフレーム ウィンドウを移動できます。

- MFS_4THICKFRAME ミニフレーム ウィンドウのサイズ変更を無効にします。

- MFS_SYNCACTIVEミニフレーム ウィンドウのアクティブ化を親ウィンドウのアクティブ化に同期します。

- MFS_THICKFRAME ミニフレーム ウィンドウのサイズをクライアント領域の内容のサイズに合わせて変更できます。

- MFS_BLOCKSYSMENU システム メニューとコントロール メニューへのアクセスを無効にし、キャプション (タイトル バー) の一部に変換します。

可能なウィンドウ スタイル値の詳細については[、「CWnd::Create」](../../mfc/reference/cwnd-class.md#create)を参照してください。 ミニフレーム ウィンドウに使用される一般的な組み合わせは、&#124;WS_SYSMENU&#124;WS_CAPTION&#124;WS_POPUP。

*Rect*<br/>
ウィンドウ`RECT`の必要な寸法を指定する構造体。

*pParentWnd*<br/>
親ウィンドウへのポイント。 トップレベル ウィンドウには NULL を使用します。

*nID*<br/>
ミニフレーム ウィンドウが子ウィンドウとして作成される場合は、子コントロールの識別子です。それ以外の場合は 0。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`Create`ウィンドウのクラス名とウィンドウ名を初期化し、そのスタイルと親の既定値を登録します。

## <a name="cminiframewndcreateex"></a><a name="createex"></a>Cミニフレームウンド::作成します。

`CMiniFrameWnd` オブジェクトを作成します。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    LPCTSTR lpClassName,
    LPCTSTR lpWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd = NULL,
    UINT nID = 0);
```

### <a name="parameters"></a>パラメーター

*ドウェエクススタイル*<br/>
作成する拡張スタイルを`CMiniFrameWnd`指定します。 [ウィンドウに拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)を適用します。

*クラス名*<br/>
Windows クラス[(WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw)構造体) に名前を付ける NULL で終わる文字列を指します。 クラス名は、グローバル[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)関数に登録された任意の名前、または定義済みのコントロール クラス名のいずれかです。 NULL にすることはできません。

*ウィンドウ名*<br/>
ウィンドウ名を含む NULL で終わる文字列を指します。

*Dwstyle*<br/>
ウィンドウ スタイルの属性を指定します。 使用可能な値の説明については、「[ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[CWnd::作成](../../mfc/reference/cwnd-class.md#create)」を参照してください。

*Rect*<br/>
ウィンドウのサイズと位置を、クライアント座標で指定*した pParentWnd*です。

*pParentWnd*<br/>
親ウィンドウ オブジェクトへのポイント。

*nID*<br/>
子ウィンドウの識別子。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

パラメータ`CreateEx`は、WNDCLASS、ウィンドウ スタイル、および (オプションで) ウィンドウの初期位置とサイズを指定します。 `CreateEx`ウィンドウの親 (存在する場合) と ID も指定します。

実行時`CreateEx`に、 [ [WM_GETMINMAXINFO WM_NCCREATE](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) []、[](../../mfc/reference/cwnd-class.md#onnccreate) [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、 および[WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)のメッセージがウィンドウに送信されます。

既定のメッセージ処理を拡張するには、 から`CMiniFrameWnd`クラスを派生し、新しいクラスにメッセージ マップを追加し、上記のメッセージのメンバー関数を提供します。 オーバーライド`OnCreate`(たとえば、新しいクラスに必要な初期化を実行する場合)。

`On`*派生クラス*にさらなる機能を追加するには、メッセージ メッセージ ハンドラーをさらにオーバーライドします。

WS_VISIBLEスタイルが指定されている場合、ウィンドウをアクティブにしてウィンドウを表示するために必要なすべてのメッセージがウィンドウに送信されます。 ウィンドウ スタイルでタイトル バーを指定すると *、lpszWindowName*パラメーターが指すウィンドウ タイトルがタイトル バーに表示されます。

*dwStyle*パラメーターは、[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)の任意の組み合わせにすることができます。

古いスタイルのパレット ツールボックス ウィンドウはサポートされなくなりました。 以前のバージョンの Windows で MFC アプリケーションを実行する場合は、"閉じる" ボタンが付いていない古いスタイルがサポートされていましたが、Visual C++.NET ではサポートされていません。 新しいWS_EX_TOOLWINDOWスタイルのみがサポートされるようになりました。このスタイルの詳細については、「[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)」を参照してください。

## <a name="see-also"></a>関連項目

[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)
