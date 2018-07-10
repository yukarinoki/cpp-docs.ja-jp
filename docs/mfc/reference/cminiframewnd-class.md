---
title: CMiniFrameWnd クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
dev_langs:
- C++
helpviewer_keywords:
- CMiniFrameWnd [MFC], CMiniFrameWnd
- CMiniFrameWnd [MFC], Create
- CMiniFrameWnd [MFC], CreateEx
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 766faaa50e4efead96ff72c67aee71fec2386b18
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37038587"
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
|[CMiniFrameWnd::CreateEx](#createex)|作成、`CMiniFrameWnd`作成した後 (その他のオプション) のオブジェクト。|  
  
## <a name="remarks"></a>Remarks  
 これらのミニフレーム ウィンドウを最小限に抑える最大化ボタンがないまたはメニューとする必要があるだけそれらを消去するシステム メニューをクリックする点を除いて、通常のフレーム ウィンドウと同様に動作します。  
  
 使用する、`CMiniFrameWnd`オブジェクト、まずオブジェクトを定義します。 まず、[作成](#create)ミニフレーム ウィンドウを表示するメンバー関数。  
  
 使用する方法の詳細についての`CMiniFrameWnd`、オブジェクトが、記事を参照して[ドッキング ツールバーとフローティング ツールバー](../../mfc/docking-and-floating-toolbars.md)です。  
  
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
 Windows ミニフレーム ウィンドウを作成し、それにアタッチ、`CMiniFrameWnd`オブジェクト。  
  
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
 *lpClassName*  
 Windows クラスの名前を null で終わる文字列へのポインター。 クラス名は、グローバルに登録されている任意の名前を指定できます[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)関数。 場合**NULL**、フレームワークによって、ウィンドウ クラスの登録されます。 MFC では、既定のクラスを次のスタイルと属性。  
  
-   セットのスタイル ビット**CS_DBLCLKS**、送信し、ユーザーがマウスをダブルクリックすると、ウィンドウ プロシージャへのメッセージ をダブルクリックします。  
  
-   セットのスタイル ビット**CS_HREDRAW**と**CS_VREDRAW**、ウィンドウ サイズが変更されたときに再描画されるクライアント領域の内容を送信します。  
  
-   クラスのカーソルを標準の Windows に設定**IDC_ARROW**です。  
  
-   クラスの背景ブラシが設定**NULL**ウィンドウは、背景は消去されません。  
  
-   標準 (たなびく旗) の Windows ロゴ アイコンをクラスのアイコンを設定します。  
  
-   Windows によって示される、既定のサイズと位置をウィンドウを設定します。  
  
 *lpWindowName*  
 ウィンドウの名前を表す null で終わる文字列へのポインター。  
  
 *dwStyle*  
 ウィンドウのスタイル属性を指定します。 これらは、標準のウィンドウ スタイルと 1 つ以上の次の特殊なスタイルに含めることができます。  
  
- **MFS_MOVEFRAME**ミニフレーム ウィンドウのキャプションだけでなく、ウィンドウのいずれかの端をクリックして移動するようにします。  
  
- **MFS_4THICKFRAME**ミニフレーム ウィンドウのサイズ変更を無効にします。  
  
- **返さ**親ウィンドウのアクティブ化するミニフレーム ウィンドウのアクティブ化を同期します。  
  
- **MFS_THICKFRAME**ミニフレーム ウィンドウのサイズが小さくクライアント領域の内容を許可します。  
  
- **MFS_BLOCKSYSMENU**システム メニューのコントロールのメニューへのアクセスを無効にし、キャプション (タイトル バー) の一部に変換します。  
  
 参照してください[cwnd::create](../../mfc/reference/cwnd-class.md#create)利用可能なウィンドウのスタイル値の詳細についてはします。 ミニフレーム ウィンドウで使用される一般的な組み合わせは**WS_POPUP&#124;WS_CAPTION&#124;WS_SYSMENU**です。  
  
 *rect*  
 A`RECT`構造のウィンドウの大きさを指定します。  
  
 *pParentWnd*  
 親ウィンドウへのポインター。 使用して**NULL**トップ レベル ウィンドウに対してです。  
  
 *nID*  
 これは、子コントロールの識別子である子ウィンドウとして、ミニフレーム ウィンドウを作成する場合それ以外の場合 0 を返します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 **作成**ウィンドウのクラス名とウィンドウの名前を初期化し、スタイルと親の既定値を登録します。  
  
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
 *dwExStyle*  
 拡張スタイルを指定します、`CMiniFrameWnd`作成中です。 任意の適用、[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)ウィンドウにします。  
  
 *lpClassName*  
 Windows クラスの名前を示す文字の null で終わる文字列へのポインター (、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造体)。 クラス名は、グローバルに登録されている任意の名前を指定できます[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)関数または定義済みのコントロール クラス名のいずれか。 なければなりません**NULL**です。  
  
 *lpWindowName*  
 ウィンドウの名前を表す null で終わる文字列へのポインター。  
  
 *dwStyle*  
 ウィンドウのスタイル属性を指定します。 参照してください[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[cwnd::create](../../mfc/reference/cwnd-class.md#create)使用可能な値の詳細についてはします。  
  
 *rect*  
 クライアント座標で、ウィンドウの位置とサイズ*pParentWnd*です。  
  
 *pParentWnd*  
 親ウィンドウ オブジェクトへのポインター。  
  
 *nID*  
 子ウィンドウの識別子。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>Remarks  
 `CreateEx`パラメーターを指定して、 **WNDCLASS**ウィンドウのスタイルと (必要に応じて) 初期位置、およびウィンドウのサイズ。 `CreateEx` また、ウィンドウの親 (存在する場合) と ID を指定します  
  
 ときに`CreateEx`を実行する Windows の送信、 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)メッセージ ウィンドウにします。  
  
 既定のメッセージ処理を拡張するには、派生クラスを`CMiniFrameWnd`メッセージ マップを新しいクラスに追加し、上記のメッセージのメンバー関数を提供します。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 さらにオーバーライド **で * * * メッセージ*メッセージ ハンドラーは、派生クラスに機能を追加します。  
  
 場合、 **WS_VISIBLE**スタイルが与えられると、Windows アクティブ化し、ウィンドウを表示するために必要なすべてのメッセージ ウィンドウに送信します。 ウィンドウのスタイルは、タイトル バーを指定する場合、ウィンドウのタイトルを指す、*したとき*パラメーターは、タイトル バーに表示されます。  
  
 *DwStyle*パラメーターの任意の組み合わせを指定できます[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)です。  
  
 古いスタイルのパレット [ツールボックス] ウィンドウがサポートされていません。 MFC アプリケーションを以前のバージョンの Windows で実行されているときに、"X"閉じるボタン設定されていない、旧スタイルがサポートされていましたが、Visual C .NET ではサポートされなくです。 のみ新しい`WS_EX_TOOLWINDOW`スタイルがサポートされています。 このスタイルの説明は、次を参照してください。[拡張ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)です。  
  
## <a name="see-also"></a>関連項目  
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)
