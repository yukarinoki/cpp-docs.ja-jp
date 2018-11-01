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
ms.openlocfilehash: f16a8cd21fe724c44a1ed648f29e42cb5d00dcd1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663307"
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
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|`CMiniFrameWnd` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[には](#create)|作成、`CMiniFrameWnd`構築後のオブジェクト。|
|[CMiniFrameWnd::CreateEx](#createex)|作成、`CMiniFrameWnd`構築後 (その他のオプション) を含むオブジェクト。|

## <a name="remarks"></a>Remarks

これらのミニフレーム ウィンドウは、点が異なりますを最小化/最大化ボタンがないか、メニューおよびするがシステム メニューを閉じるには、1 回のクリックだけが通常のフレーム ウィンドウと同様に動作します。

使用する、`CMiniFrameWnd`オブジェクト、最初のオブジェクトを定義します。 呼び出して、[作成](#create)ミニフレーム ウィンドウを表示するメンバー関数。

使用する方法の詳細についての`CMiniFrameWnd`オブジェクトは、記事をご覧ください。[ドッキングとフローティング ツールバー](../../mfc/docking-and-floating-toolbars.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

`CMiniFrameWnd`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cminiframewnd"></a>  CMiniFrameWnd::CMiniFrameWnd

構築、`CMiniFrameWnd`オブジェクトは、ウィンドウを作成しません。

```
CMiniFrameWnd();
```

### <a name="remarks"></a>Remarks

ウィンドウを作成するには[には](#create)します。

##  <a name="create"></a>  には

Windows のミニフレーム ウィンドウを作成しにアタッチします、`CMiniFrameWnd`オブジェクト。

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

*lpClassName*<br/>
Windows クラスの名前を示す文字の null で終わる文字列を指します。 クラス名はグローバルに登録されている任意の名前を指定できます[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)関数。 NULL の場合、ウィンドウ クラスは、フレームワークによってが登録されます。 MFC で既定のクラスは、次のスタイルと属性。

- セットのスタイルのビット CS_DBLCLKS、送信、ユーザーがマウスをダブルクリックしたときにウィンドウ プロシージャへのメッセージをダブルクリックします。

- ウィンドウ サイズが変更されたときに再描画されるクライアント領域の内容を直接 CS_HREDRAW と CS_VREDRAW、スタイルのビットを設定します。

- Windows 標準 IDC_ARROW クラス カーソルに設定します。

- ウィンドウはその背景を消去されませんので、NULL にクラスの背景ブラシを設定します。

- クラスのアイコンを手を振るフラグの標準の Windows ロゴのアイコンに設定します。

- Windows で示されている既定のサイズと位置に、ウィンドウを設定します。

*lpWindowName*<br/>
ウィンドウの名前を含む null で終わる文字列へのポインター。

*dwStyle*<br/>
ウィンドウのスタイル属性を指定します。 これらは、標準のウィンドウ スタイルと 1 つ以上の次の特殊なスタイルを含めることができます。

- MFS_MOVEFRAME により、ミニフレーム ウィンドウ キャプションだけでなく、ウィンドウの端をクリックして移動します。

- ミニフレーム ウィンドウのサイズ変更 MFS_4THICKFRAME を無効にします。

- 返さでは、親ウィンドウのアクティブ化するミニフレーム ウィンドウのアクティブ化を同期します。

- MFS_THICKFRAME により、ミニフレーム ウィンドウのクライアント領域の内容のような小さいサイズを使用できます。

- システム メニューと、[コントロール] メニューへのアクセスの MFS_BLOCKSYSMENU を無効にされ、キャプション (タイトル バー) の一部に変換します。

参照してください[cwnd::create](../../mfc/reference/cwnd-class.md#create)の利用可能なウィンドウ スタイル値の説明。 ミニフレーム ウィンドウを使用する一般的な組み合わせが WS_POPUP&#124;WS_CAPTION&#124;WS_SYSMENU します。

*rect*<br/>
A`RECT`構造は、ウィンドウの大きさを指定します。

*pParentWnd*<br/>
親ウィンドウへのポインター。 トップ レベル ウィンドウに対して NULL を使用します。

*nID*<br/>
これは、子コントロールの識別子を子ウィンドウとして、ミニフレーム ウィンドウが作成される場合それ以外の場合 0 を返します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

`Create` ウィンドウのクラス名とウィンドウの名前を初期化し、そのスタイルと親の既定値を登録します。

##  <a name="createex"></a>  CMiniFrameWnd::CreateEx

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

*dwExStyle*<br/>
拡張スタイルを指定します、`CMiniFrameWnd`作成中です。 任意の適用、[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)ウィンドウにします。

*lpClassName*<br/>
Windows クラスの名前を示す文字の null で終わる文字列の指す (、 [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576)構造)。 クラス名はグローバルに登録されている任意の名前を指定できます[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)関数またはそのいずれかの定義済みのコントロール クラス名。 NULL は指定できません。

*lpWindowName*<br/>
ウィンドウの名前を含む null で終わる文字列へのポインター。

*dwStyle*<br/>
ウィンドウのスタイル属性を指定します。 参照してください[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[cwnd::create](../../mfc/reference/cwnd-class.md#create)の使用可能な値の説明。

*rect*<br/>
クライアント座標で、ウィンドウの位置とサイズ*pParentWnd*します。

*pParentWnd*<br/>
親ウィンドウ オブジェクトへのポインター。

*nID*<br/>
子ウィンドウの識別子。

### <a name="return-value"></a>戻り値

成功した場合、true を返します。

### <a name="remarks"></a>Remarks

`CreateEx` WNDCLASS、ウィンドウ スタイル、および (必要に応じて) 初期位置、およびウィンドウのサイズを指定します。 `CreateEx` また、ウィンドウの親 (ある場合) と ID を指定します

ときに`CreateEx`実行されると、Windows の送信、 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)メッセージは、ウィンドウに表示します。

既定のメッセージ処理を拡張するには、派生クラスを`CMiniFrameWnd`メッセージ マップを新しいクラスに追加し、上記のメッセージのメンバー関数を提供します。 オーバーライド`OnCreate`、たとえば、新しいクラスに必要な初期化を実行します。

さらにオーバーライド`On`*メッセージ*メッセージ ハンドラーは、派生クラスに機能を追加します。

WS_VISIBLE スタイルを指定すると、Windows はアクティブ化し、ウィンドウを表示するために必要なすべてのメッセージをウィンドウに送信します。 ウィンドウのスタイルは、タイトル バーを指定する場合、ウィンドウのタイトルが指す、*したとき*パラメーターは、タイトル バーに表示されます。

*DwStyle*パラメーターの任意の組み合わせを指定できます[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)します。

古いスタイル パレットのツールボックス ウィンドウがサポートされていません。 以前のバージョンの Windows では、MFC アプリケーションを実行するときに、"X"の閉じるボタンを設定されていない、以前のスタイルがサポートされていましたが、Visual C .NET でサポートされて不要になった。 新しい WS_EX_TOOLWINDOW スタイルのみがサポートされるようになりました。このスタイルの説明は、次を参照してください。[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)します。

## <a name="see-also"></a>関連項目

[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)
