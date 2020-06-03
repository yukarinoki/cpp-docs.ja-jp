---
title: クラス
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
ms.openlocfilehash: df21591dec1da5861125d7e9480fb9345aaad061
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752952"
---
# <a name="cbitmapbutton-class"></a>クラス

ラベルがテキストではなくビットマップ イメージのプッシュ ボタン コントロールを作成します。

## <a name="syntax"></a>構文

```
class CBitmapButton : public CButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[をクリックします。](#cbitmapbutton)|`CBitmapButton` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#autoload)|ダイアログ ボックスのボタンを`CBitmapButton`クラスのオブジェクトに関連付け、名前でビットマップを読み込み、ビットマップに合わせてボタンのサイズを変更します。|
|[ビットマップボタン::ビットマップを読み込む](#loadbitmaps)|アプリケーションのリソース ファイルから 1 つ以上の名前付きビットマップ リソースを読み込み、そのビットマップをオブジェクトにアタッチして、オブジェクトを初期化します。|
|[コンテンツのサイズ](#sizetocontent)|ビットマップに合わせてボタンのサイズを変更します。|

## <a name="remarks"></a>解説

`CBitmapButton`オブジェクトには最大 4 つのビットマップが含まれ、ボタンが想定できるさまざまな状態のイメージ(アップ(または通常)、下(または選択)、フォーカス、無効のイメージが含まれます。 最初のビットマップのみが必要です。その他はオプションです。

ビットマップ ボタン イメージには、イメージの周囲の境界線と、イメージ自体が含まれます。 通常、境界線はボタンの状態を示す部分を果たします。 たとえば、フォーカス状態のビットマップは、通常、上の状態のビットマップと似ていますが、境界線から差し込んだ破線の四角形、または境界線に太い実線が付いています。 無効状態のビットマップは、通常、アップ状態のビットマップに似ていますが、コントラストが低くなります (淡色表示または淡色表示のメニュー選択など)。

これらのビットマップは任意のサイズにできますが、すべてのビットマップはアップ状態のビットマップと同じサイズであるかのように扱われます。

さまざまなアプリケーションで、ビットマップイメージの異なる組み合わせが必要です。

|上へ|[下へ]|フォーカスされている|無効|Application|
|--------|----------|-------------|--------------|-----------------|
|×||||Bitmap|
|×|×|||WS_TABSTOPスタイルのないボタン|
|×|×|×|×|すべての状態を含むダイアログ ボタン|
|×|×|×||WS_TABSTOPスタイルのダイアログ ボタン|

ビットマップ ボタン コントロールを作成する場合は、BS_OWNERDRAWスタイルを設定して、ボタンがオーナー描画であることを指定します。 これにより、Windows はボタンのWM_MEASUREITEMとWM_DRAWITEMメッセージを送信します。フレームワークは、これらのメッセージを処理し、ボタンの外観を管理します。

### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>ウィンドウのクライアント領域にビットマップ ボタン コントロールを作成するには

1. ボタンに対して 1 ~ 4 個のビットマップ イメージを作成します。

1. [オブジェクトを](#cbitmapbutton)構築します。

1. [Create](../../mfc/reference/cbutton-class.md#create)関数を呼び出して Windows ボタン コントロールを`CBitmapButton`作成し、オブジェクトにアタッチします。

1. [LoadBitmaps](#loadbitmaps)メンバー関数を呼び出して、ビットマップ ボタンが構築された後にビットマップ リソースを読み込みます。

### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>ダイアログ ボックスにビットマップ ボタン コントロールを含めるには

1. ボタンに対して 1 ~ 4 個のビットマップ イメージを作成します。

1. ビットマップ ボタンを配置するオーナー描画ボタンを使用して、ダイアログ テンプレートを作成します。 テンプレートのボタンのサイズは重要ではありません。

1. ボタンのキャプションを "MYIMAGE" などの値に設定し、IDC_MYIMAGEなどのボタンのシンボルを定義します。

1. アプリケーションのリソース スクリプトで、ボタン用に作成された各イメージに、ステップ 3 のボタン キャプションに使用される文字列に"U"、"D"、"F"、または "X" (上下、フォーカス、および無効) の文字を追加して作成された ID を指定します。 たとえば、ボタンのキャプション"MYIMAGE"の場合、IDは"MYIMAGEU"、"MYIMAGED"、"MYIMAGEF"、および "MYIMAGEX"になります。 ビットマップの ID は二重引用符で囲んで指定**する必要があります**。 それ以外の場合、リソース エディターは、リソースに整数を割り当てると、MFC はイメージを読み込むときに失敗します。

1. アプリケーションのダイアログ クラス ( から`CDialog`派生 )`CBitmapButton`で、メンバー オブジェクトを追加します。

1. オブジェクトの`CDialog` [OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)ルーチンで、ボタンの`CBitmapButton`コントロール ID とオブジェクトの**this**ポインターをパラメーターとして使用して、オブジェクト`CDialog`の[AutoLoad](#autoload)関数を呼び出します。

ビットマップ ボタン コントロールから親に送信されるBN_CLICKEDなどの Windows 通知メッセージ (通常は派生`CDialog`クラス) を処理する場合は、各メッセージ`CDialog`のメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を派生オブジェクトに追加します。 オブジェクトによって送信される`CBitmapButton`通知は[、CButton](../../mfc/reference/cbutton-class.md)オブジェクトによって送信されるものと同じです。

[CToolBar](../../mfc/reference/ctoolbar-class.md)クラスは、ビットマップボタンに対して異なるアプローチをとっています。

`CBitmapButton`の詳細については、「[コントロール](../../mfc/controls-mfc.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CBitmapButton`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="cbitmapbuttonautoload"></a><a name="autoload"></a>をクリックします。

ダイアログ ボックスのボタンを`CBitmapButton`クラスのオブジェクトに関連付け、名前でビットマップを読み込み、ビットマップに合わせてボタンのサイズを変更します。

```
BOOL AutoLoad(
    UINT nID,
    CWnd* pParent);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
ボタンのコントロール ID。

*親*<br/>
ボタンを所有するオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数`AutoLoad`を使用して、ダイアログ ボックスのオーナー描画ボタンをビットマップ ボタンとして初期化します。 この関数を使用する手順は、クラスの解説`CBitmapButton`にあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#75](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]

## <a name="cbitmapbuttoncbitmapbutton"></a><a name="cbitmapbutton"></a>をクリックします。

`CBitmapButton` オブジェクトを作成します。

```
CBitmapButton();
```

### <a name="remarks"></a>解説

C++`CBitmapButton`オブジェクトを作成した後[、CButton::Create](../../mfc/reference/cbutton-class.md#create)を呼び出して Windows ボタン`CBitmapButton`コントロールを作成し、オブジェクトにアタッチします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#57](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]

## <a name="cbitmapbuttonloadbitmaps"></a><a name="loadbitmaps"></a>ビットマップボタン::ビットマップを読み込む

この関数は、リソース名または ID 番号で識別されるビットマップ イメージを読み込む場合、または`AutoLoad`ダイアログ ボックスの一部ではないビットマップ ボタンを作成する場合などに、この関数を使用できない場合に使用します。

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

*リソース*<br/>
ビットマップ ボタンの標準状態または "up" 状態のビットマップの名前を含む null で終わる文字列を指します。 必須。

*を使用します。*<br/>
ビットマップ ボタンの選択状態または "down" 状態のビットマップの名前を含む null で終わる文字列を指します。 NULL の場合もあります。

*リソースを割り当てる*<br/>
ビットマップ ボタンのフォーカス状態のビットマップの名前を含む null で終わる文字列へのポイント。 NULL の場合もあります。

*リソースを割り出しました。*<br/>
ビットマップ ボタンの無効状態のビットマップの名前を含む null で終わる文字列へのポイント。 NULL の場合もあります。

*リソース*<br/>
ビットマップ ボタンの標準状態または "up" 状態のビットマップ リソースのリソース ID 番号を指定します。 必須。

*を使用します。*<br/>
ビットマップ ボタンの選択状態または "down" 状態のビットマップ リソースのリソース ID 番号を指定します。 0 であってもよい。

*リソースを割り当てる*<br/>
ビットマップ ボタンのフォーカス状態のビットマップ リソースのリソース ID 番号を指定します。 0 であってもよい。

*を無効にします。*<br/>
ビットマップ ボタンの無効状態のビットマップ リソースのリソース ID 番号を指定します。 0 であってもよい。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#58](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]

## <a name="cbitmapbuttonsizetocontent"></a><a name="sizetocontent"></a>コンテンツのサイズ

ビットマップ ボタンのサイズをビットマップのサイズに変更します。

```cpp
void SizeToContent();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#59](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CTRL テスト](../../overview/visual-cpp-samples.md)<br/>
[CButton クラス](../../mfc/reference/cbutton-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
