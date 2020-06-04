---
title: CColorDialog クラス
ms.date: 11/04/2016
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
ms.openlocfilehash: 99b4ff27a7686972bcbc85478998b52ed713ab5b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754264"
---
# <a name="ccolordialog-class"></a>CColorDialog クラス

色選択ダイアログ ボックスをアプリケーションに組み込むことができます。

## <a name="syntax"></a>構文

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ::Cカラーダイアログ](#ccolordialog)|`CColorDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ:Doモーダル](#domodal)|色のダイアログ ボックスを表示し、ユーザーが選択できるようにします。|
|[ダイアログ::取得カラー](#getcolor)|選択した`COLORREF`色の値を含む構造体を返します。|
|[ダイアログ::保存されたカスタムカラーを取得します。](#getsavedcustomcolors)|ユーザーが作成したカスタムカラーを取得します。|
|[ダイアログ::現在の色を設定します。](#setcurrentcolor)|現在の色選択を指定した色に強制的に適用します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[カラーダイアログ::オンコロック](#oncolorok)|ダイアログ ボックスに入力した色を検証するには、オーバーライドします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ::m_cc](#m_cc)|ダイアログ ボックスの設定をカスタマイズするために使用する構造体。|

## <a name="remarks"></a>解説

オブジェクト`CColorDialog`は、表示システムに定義された色のリストを持つダイアログボックスです。 ユーザーは、一覧から特定の色を選択または作成できます。

オブジェクトを`CColorDialog`構築するには、指定されたコンストラクターを使用するか、新しいクラスを派生させ、独自のカスタム コンストラクターを使用します。

ダイアログ ボックスを作成したら[、m_cc](#m_cc)構造体の値を設定または変更して、ダイアログ ボックスのコントロールの値を初期化できます。 *m_cc*構造体の型は[、CHOOSECOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)です。

ダイアログ ボックスのコントロールを初期化した後、メンバー関数`DoModal`を呼び出してダイアログ ボックスを表示し、ユーザーが色を選択できるようにします。 `DoModal`は、ダイアログ ボックスの [OK] ボタンまたは [キャンセル] (IDCANCEL) ボタンのいずれかをユーザーが選択した状態で返します。

IDOK を返す場合`DoModal`は、メンバー`CColorDialog`関数の 1 つを使用して、ユーザーが入力した情報を取得できます。

Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror)関数を使用して、ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、エラーの詳細を確認できます。

`CColorDialog`は、COMMDLG に依存します。Windows バージョン 3.1 以降に付属の DLL ファイル。

ダイアログ ボックスをカスタマイズするには、 から`CColorDialog`クラスを派生し、カスタム ダイアログ テンプレートを提供し、拡張コントロールからの通知メッセージを処理するメッセージ マップを追加します。 未処理のメッセージは、基本クラスに渡す必要があります。

フック機能のカスタマイズは不要です。

> [!NOTE]
> 一部のインストールでは`CColorDialog`、フレームワークを使用して他`CDialog`のオブジェクトをグレーにした場合、オブジェクトは灰色の背景で表示されません。

の使用`CColorDialog`の詳細については、「[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="ccolordialogccolordialog"></a><a name="ccolordialog"></a>ダイアログ::Cカラーダイアログ

`CColorDialog` オブジェクトを構築します。

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*clrInit*<br/>
既定の色の選択。 値を指定しない場合、デフォルトは RGB(0,0,0) (黒) になります。

*dwFlags*<br/>
ダイアログ ボックスの機能と外観をカスタマイズするフラグのセット。 詳細については、Windows SDK の[「CHOOSECOLOR」](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)構造を参照してください。

*pParentWnd*<br/>
ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

## <a name="ccolordialogdomodal"></a><a name="domodal"></a>ダイアログ:Doモーダル

Windows の共通の色のダイアログ ボックスを表示し、ユーザーが色を選択できるようにします。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

IDOK または ID キャンセル。 IDCANCEL が返された場合は、エラーが発生したかどうかを判断するのには関数[を](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror)呼び出します。

IDOK と IDCANCEL は、ユーザーが [OK] または [キャンセル] ボタンを選択したかどうかを示す定数です。

### <a name="remarks"></a>解説

[m_cc](#m_cc)構造体のメンバーを設定してさまざまな色のダイアログ ボックス オプションを初期化する場合は、ダイアログ ボックス オブジェクト`DoModal`が構築された後に呼び出す前に、この操作を行う必要があります。

を呼`DoModal`び出した後、他のメンバー関数を呼び出して、ユーザーが入力した設定または情報をダイアログ ボックスに取得できます。

### <a name="example"></a>例

  [の](#ccolordialog)例を参照してください。

## <a name="ccolordialoggetcolor"></a><a name="getcolor"></a>ダイアログ::取得カラー

ユーザーが選択した色`DoModal`に関する情報を取得するために呼び出した後、この関数を呼び出します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

カラー ダイアログ ボックスで選択した色の RGB 情報を含む[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

## <a name="ccolordialoggetsavedcustomcolors"></a><a name="getsavedcustomcolors"></a>ダイアログ::保存されたカスタムカラーを取得します。

`CColorDialog`オブジェクトは、ユーザーが色を選択するだけでなく、最大 16 個のカスタム カラーを定義することを許可します。

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>戻り値

ユーザーが作成したカスタム カラーを格納する 16 個の RGB カラー値の配列へのポインター。

### <a name="remarks"></a>解説

メンバー`GetSavedCustomColors`関数は、これらの色へのアクセスを提供します。 これらの色は[、DoModal](#domodal)が IDOK を返した後に取得できます。

返される配列の 16 個の RGB 値は、それぞれ RGB(255,255,255) (白) に初期化されます。 ユーザーが選択したカスタムカラーは、アプリケーション内のダイアログボックス呼び出しの間にのみ保存されます。 アプリケーションの呼び出しの間にこれらの色を保存する場合は、初期化 (.INI) ファイル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

## <a name="ccolordialogm_cc"></a><a name="m_cc"></a>ダイアログ::m_cc

ダイアログ ボックスの特性と値をメンバに格納する[CHOOSECOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora~r1)型の構造体。

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>解説

オブジェクトを`CColorDialog`作成した後[、DoModal](#domodal)メンバー関数を呼び出す前に *、m_cc*を使用してダイアログ ボックスのさまざまな側面を設定できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

## <a name="ccolordialogoncolorok"></a><a name="oncolorok"></a>カラーダイアログ::オンコロック

ダイアログ ボックスに入力した色を検証するには、オーバーライドします。

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスを閉じないようにする場合は 0 以外の値を指定します。それ以外の場合は 0 を指定すると、入力された色を受け入れます。

### <a name="remarks"></a>解説

ユーザーが色ダイアログ ボックスで選択した色のカスタム検証を行う場合にのみ、この関数をオーバーライドします。

ユーザーは、次の 2 つの方法のいずれかで色を選択できます。

- カラー パレットの色をクリックします。 選択したカラーの RGB 値が、適切な RGB 編集ボックスに反映されます。

- RGB 編集ボックスに値を入力する

オーバーライド`OnColorOK`を使用すると、アプリケーション固有の理由でユーザーが共通の色ダイアログ ボックスに入力した色を拒否できます。

通常、フレームワークは既定の色の検証を提供し、無効な色が入力された場合にメッセージ ボックスを表示するため、この関数を使用する必要はありません。

色選択を強制するために、内部`OnColorOK`から[SetCurrentColor](#setcurrentcolor)を呼び出すことができます。 いったん`OnColorOK`起動された (つまり、ユーザーが**OK**をクリックして色の変更を受け入れる) 場合は[、GetColor](#getcolor)を呼び出して新しい色の RGB 値を取得できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

## <a name="ccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>ダイアログ::現在の色を設定します。

clr*で指定*された`DoModal`色の値に現在の色の選択を強制するために呼び出した後、この関数を呼び出します。

```cpp
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

*Clr*<br/>
RGB カラー値。

### <a name="remarks"></a>解説

この関数は、メッセージ ハンドラまたは の`OnColorOK`内部から呼び出されます。 ダイアログ ボックスは *、clr*パラメーターの値に基づいてユーザーの選択を自動的に更新します。

### <a name="example"></a>例

  [「CColorDialog::OnColorOK」](#oncolorok)の例を参照してください。

## <a name="see-also"></a>関連項目

[MDI のサンプル](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル ドローCLI](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
