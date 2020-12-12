---
description: '詳細情報: CBitmapButton クラス'
title: CBitmapButton クラス
ms.date: 11/04/2016
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
helpviewer_keywords:
- CBitmapButton [MFC], CBitmapButton
- CBitmapButton [MFC], AutoLoad
- CBitmapButton [MFC], LoadBitmaps
- CBitmapButton [MFC], SizeToContent
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
ms.openlocfilehash: 93d114dce87aba4643af427f3726a5ffab004b77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122708"
---
# <a name="cbitmapbutton-class"></a>CBitmapButton クラス

ラベルがテキストではなくビットマップ イメージのプッシュ ボタン コントロールを作成します。

## <a name="syntax"></a>構文

```
class CBitmapButton : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CBitmapButton:: CBitmapButton](#cbitmapbutton)|`CBitmapButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CBitmapButton:: 自動読み込み](#autoload)|ダイアログボックスのボタンをクラスのオブジェクトと関連付け `CBitmapButton` 、ビットマップを名前で読み込み、ビットマップに合わせてボタンのサイズを調整します。|
|[CBitmapButton:: LoadBitmaps](#loadbitmaps)|アプリケーションのリソースファイルから1つまたは複数の名前付きビットマップリソースを読み込み、オブジェクトにビットマップをアタッチすることによって、オブジェクトを初期化します。|
|[CBitmapButton:: SizeToContent](#sizetocontent)|ビットマップに合わせてボタンのサイズを調整します。|

## <a name="remarks"></a>解説

`CBitmapButton` オブジェクトには、最大4つのビットマップが含まれています。これには、ボタンが想定しているさまざまな状態のイメージが含まれています。たとえば、up (または normal)、down (または selected)、フォーカス、および無効になります。 最初のビットマップのみが必要です。他のオプションは省略可能です。

ビットマップボタンのイメージには、イメージの周りとイメージ自体の境界線が含まれます。 境界線は、通常、ボタンの状態を示す部分を再生します。 たとえば、フォーカスされた状態のビットマップは、通常、アップ状態のビットマップに似ていますが、境界線または境界線の枠線から破線の四角形が埋め込まれています。 無効な状態のビットマップは、通常、アップ状態のビットマップに似ていますが、コントラストは低くなります (淡色表示またはグレー表示のメニューの選択など)。

これらのビットマップは任意のサイズにすることができますが、すべてが up 状態のビットマップと同じサイズであるかのように扱われます。

さまざまなアプリケーションでは、ビットマップイメージのさまざまな組み合わせが必要になります。

|上へ|[下へ]|フォーカスされている|無効|Application|
|--------|----------|-------------|--------------|-----------------|
|×||||Bitmap|
|×|×|||WS_TABSTOP スタイルのないボタン|
|×|×|×|×|すべての状態のダイアログボタン|
|×|×|×||WS_TABSTOP スタイルのダイアログボタン|

ビットマップボタンコントロールを作成する場合は、BS_OWNERDRAW スタイルを設定して、ボタンがオーナー描画であることを指定します。 これにより、Windows がボタンの WM_MEASUREITEM と WM_DRAWITEM メッセージを送信するようになります。フレームワークは、これらのメッセージを処理し、ボタンの外観を管理します。

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>ウィンドウのクライアント領域にビットマップボタンコントロールを作成するには

1. ボタン用に 1 ~ 4 個のビットマップイメージを作成します。

1. [Cbitmapbutton](#cbitmapbutton)オブジェクトを構築します。

1. [Create](../../mfc/reference/cbutton-class.md#create)関数を呼び出して、Windows のボタンコントロールを作成し、それをオブジェクトにアタッチし `CBitmapButton` ます。

1. [Load](#loadbitmaps) bitmap メンバー関数を呼び出して、ビットマップボタンの構築後にビットマップリソースを読み込みます。

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>ビットマップボタンコントロールをダイアログボックスに追加するには

1. ボタン用に 1 ~ 4 個のビットマップイメージを作成します。

1. ビットマップボタンを配置するオーナー描画ボタンを持つダイアログテンプレートを作成します。 テンプレート内のボタンのサイズは関係ありません。

1. ボタンのキャプションを "MYIMAGE" などの値に設定し、IDC_MYIMAGE などのボタンのシンボルを定義します。

1. アプリケーションのリソーススクリプトで、ボタン用に作成された各イメージを、手順 3. のボタンキャプションに使用する文字列に "U"、"D"、"F"、"X" (up、down、フォーカス、および無効) のいずれかの文字を追加して作成した ID を付けます。 たとえば、ボタンのキャプション "MYIMAGE" の場合、Id は "MYIMAGEU"、"MYIMAGE"、"MYIMAGEF"、"MYIMAGE" のようになります。 ビットマップの ID を二重引用符で囲んで指定 **する必要があり** ます。 そうしないと、リソースエディターによってリソースに整数が割り当てられ、イメージの読み込み時に MFC は失敗します。

1. アプリケーションのダイアログクラス (から派生) で `CDialog` 、 `CBitmapButton` メンバーオブジェクトを追加します。

1. `CDialog`オブジェクトの [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)ルーチンで、オブジェクトの自動読み込み関数を呼び出し `CBitmapButton` ます。その際、ボタンのコントロール ID とオブジェクトのポインターをパラメーターとして使用し [](#autoload) `CDialog` **`this`** ます。

ビットマップボタンコントロールによって親 (通常はから派生するクラス) にビットマップボタンコントロールによって送信された BN_CLICKED などの Windows 通知メッセージを処理する場合は `CDialog` 、 `CDialog` 各メッセージのメッセージマップエントリとメッセージハンドラーメンバー関数を、派生オブジェクトに追加します。 オブジェクトによって送信される通知 `CBitmapButton` は、 [CButton](../../mfc/reference/cbutton-class.md) オブジェクトによって送信される通知と同じです。

クラスの [CToolBar](../../mfc/reference/ctoolbar-class.md) は、ビットマップボタンに別のアプローチを取ります。

の詳細につい `CBitmapButton` ては、「 [コントロール](../../mfc/controls-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>要件

**ヘッダー:** afxext.h

## <a name="cbitmapbuttonautoload"></a><a name="autoload"></a> CBitmapButton:: 自動読み込み

ダイアログボックスのボタンをクラスのオブジェクトと関連付け `CBitmapButton` 、ビットマップを名前で読み込み、ビットマップに合わせてボタンのサイズを調整します。

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
ボタンのコントロール ID。

*pParent*<br/>
ボタンを所有するオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

関数を使用し `AutoLoad` て、ダイアログボックスのオーナー描画ボタンをビットマップボタンとして初期化します。 この関数を使用する手順については、クラスの解説を参照して `CBitmapButton` ください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

## <a name="cbitmapbuttoncbitmapbutton"></a><a name="cbitmapbutton"></a> CBitmapButton:: CBitmapButton

`CBitmapButton` オブジェクトを作成します。

```
CBitmapButton();
```

### <a name="remarks"></a>解説

C++ オブジェクトを作成した後 `CBitmapButton` 、 [CButton:: create](../../mfc/reference/cbutton-class.md#create) を呼び出して、Windows ボタンコントロールを作成し、それをオブジェクトにアタッチし `CBitmapButton` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

## <a name="cbitmapbuttonloadbitmaps"></a><a name="loadbitmaps"></a> CBitmapButton:: LoadBitmaps

この関数は、リソース名または ID 番号で識別されるビットマップイメージを読み込む場合、または、 `AutoLoad` ダイアログボックスの一部ではないビットマップボタンを作成する場合などに使用します。

```
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,
    LPCTSTR lpszBitmapResourceSel = NULL,
    LPCTSTR lpszBitmapResourceFocus = NULL,
    LPCTSTR lpszBitmapResourceDisabled = NULL);

BOOL LoadBitmaps(
    UINT nIDBitmapResource,
    UINT nIDBitmapResourceSel = 0,
    UINT nIDBitmapResourceFocus = 0,
    UINT nIDBitmapResourceDisabled = 0);
```

### <a name="parameters"></a>パラメーター

*lpszBitmapResource*<br/>
ビットマップボタンの normal または "up" 状態のビットマップの名前を含む、null で終わる文字列を指します。 必須。

*lpszBitmapResourceSel*<br/>
ビットマップボタンの選択された状態または "down" 状態のビットマップの名前を含む、null で終わる文字列を指します。 NULL の場合もあります。

*lpszBitmapResourceFocus*<br/>
ビットマップボタンのフォーカス状態のビットマップの名前を含む、null で終わる文字列を指します。 NULL の場合もあります。

*lpszBitmapResourceDisabled*<br/>
ビットマップボタンの無効状態のビットマップの名前を含む、null で終わる文字列を指します。 NULL の場合もあります。

*nIDBitmapResource*<br/>
ビットマップボタンの normal または "up" 状態のビットマップリソースのリソース ID 番号を指定します。 必須。

*nIDBitmapResourceSel*<br/>
ビットマップボタンの選択または "ダウン" 状態のビットマップリソースのリソース ID 番号を指定します。 0の場合もあります。

*nIDBitmapResourceFocus*<br/>
ビットマップボタンのフォーカス状態に関するビットマップリソースのリソース ID 番号を指定します。 0の場合もあります。

*nIDBitmapResourceDisabled*<br/>
ビットマップボタンの無効状態に関するビットマップリソースのリソース ID 番号を指定します。 0の場合もあります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

## <a name="cbitmapbuttonsizetocontent"></a><a name="sizetocontent"></a> CBitmapButton:: SizeToContent

ビットマップのサイズを変更するには、この関数を呼び出します。

```cpp
void SizeToContent();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>関連項目

[MFC のサンプル CTRLTEST](../../overview/visual-cpp-samples.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
