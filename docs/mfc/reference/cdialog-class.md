---
title: クラス
ms.date: 09/07/2019
f1_keywords:
- CDialog
- AFXWIN/CDialog
- AFXWIN/CDialog::CDialog
- AFXWIN/CDialog::Create
- AFXWIN/CDialog::CreateIndirect
- AFXWIN/CDialog::DoModal
- AFXWIN/CDialog::EndDialog
- AFXWIN/CDialog::GetDefID
- AFXWIN/CDialog::GotoDlgCtrl
- AFXWIN/CDialog::InitModalIndirect
- AFXWIN/CDialog::MapDialogRect
- AFXWIN/CDialog::NextDlgCtrl
- AFXWIN/CDialog::OnInitDialog
- AFXWIN/CDialog::OnSetFont
- AFXWIN/CDialog::PrevDlgCtrl
- AFXWIN/CDialog::SetDefID
- AFXWIN/CDialog::SetHelpID
- AFXWIN/CDialog::OnCancel
- AFXWIN/CDialog::OnOK
helpviewer_keywords:
- CDialog [MFC], CDialog
- CDialog [MFC], Create
- CDialog [MFC], CreateIndirect
- CDialog [MFC], DoModal
- CDialog [MFC], EndDialog
- CDialog [MFC], GetDefID
- CDialog [MFC], GotoDlgCtrl
- CDialog [MFC], InitModalIndirect
- CDialog [MFC], MapDialogRect
- CDialog [MFC], NextDlgCtrl
- CDialog [MFC], OnInitDialog
- CDialog [MFC], OnSetFont
- CDialog [MFC], PrevDlgCtrl
- CDialog [MFC], SetDefID
- CDialog [MFC], SetHelpID
- CDialog [MFC], OnCancel
- CDialog [MFC], OnOK
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
ms.openlocfilehash: 36913cfdd8beda31136176c966890a90077c1b30
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753362"
---
# <a name="cdialog-class"></a>クラス

画面にダイアログ ボックスを表示するために使用される基本クラス。

## <a name="syntax"></a>構文

```
class CDialog : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ::Cダイアログ](#cdialog)|`CDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ::作成](#create)|`CDialog` オブジェクトを初期化します。 モードレス ダイアログ ボックスを作成し、オブジェクトに`CDialog`アタッチします。|
|[Cダイアログ::インダイレクトを作成](#createindirect)|メモリ内のダイアログ ボックス テンプレート (リソース ベースではない) からモードレス ダイアログ ボックスを作成します。|
|[ダイアログ::Doモーダル](#domodal)|モーダル ダイアログ ボックスを呼び出し、完了したら返します。|
|[ダイアログ::エンドダイアログ](#enddialog)|モーダル ダイアログ ボックスを閉じます。|
|[次のダイアログ::ゲットデフID](#getdefid)|ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得します。|
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|ダイアログ ボックス内の指定されたダイアログ ボックス コントロールにフォーカスを移動します。|
|[ダイアログ::イニトモーダルインダイレクト](#initmodalindirect)|メモリ内のダイアログ ボックス テンプレート (リソース ベースではない) からモーダル ダイアログ ボックスを作成します。 パラメーターは、関数`DoModal`が呼び出されるまで格納されます。|
|[CDialog::MapDialogRect](#mapdialogrect)|四角形のダイアログ ボックスの単位を画面単位に変換します。|
|[ダイアログ::次のDlgCtrl](#nextdlgctrl)|ダイアログ ボックス内の次のダイアログ ボックス コントロールにフォーカスを移動します。|
|[CDialog::OnInitDialog](#oninitdialog)|ダイアログ ボックスの初期化を拡張する場合にオーバーライドします。|
|[ダイアログ::オンセットフォント](#onsetfont)|ダイアログ ボックス コントロールがテキストを描画するときに使用するフォントを指定する場合は、オーバーライドします。|
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|ダイアログ ボックスの前のダイアログ ボックス コントロールにフォーカスを移動します。|
|[を設定します。](#setdefid)|ダイアログボックスのデフォルト押ボタンコントロールを指定した押ボタンに変更します。|
|[ダイアログ::セットヘルプID](#sethelpid)|ダイアログ ボックスの状況依存のヘルプ ID を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ::キャンセル](#oncancel)|[キャンセル] ボタンまたは Esc キーの操作を実行する場合は、オーバーライドします。 既定では、ダイアログ ボックスが閉`DoModal`じ、IDCANCEL が返されます。|
|[CDialog::OnOK](#onok)|モーダル ダイアログ ボックスで [OK] ボタンアクションを実行する場合は、オーバーライドします。 既定では、ダイアログ ボックスが閉`DoModal`じ、IDOK が返されます。|

## <a name="remarks"></a>解説

ダイアログ ボックスには、モーダルとモードレスの 2 種類があります。 モーダル ダイアログ ボックスは、アプリケーションを続行する前にユーザーが閉じる必要があります。 モードレス ダイアログ ボックスを使用すると、ダイアログ ボックスをキャンセルしたり削除したりすることなく、ダイアログ ボックスを表示して別のタスクに戻ることができます。

オブジェクト`CDialog`は、ダイアログ テンプレートと派生クラスの`CDialog`組み合わせです。 ダイアログ エディターを使用してダイアログ テンプレートを作成し、リソースに格納してから、 [クラスの追加] ウィザードを使用`CDialog`して から派生したクラスを作成します。

ダイアログ ボックスは、他のウィンドウと同様に、Windows からメッセージを受信します。 ダイアログ ボックスでは、ユーザーがダイアログ ボックスを操作する方法であるため、ダイアログ ボックスのコントロールからの通知メッセージの処理に特に関心があります。 クラス[ウィザード](mfc-class-wizard.md)を使用して、処理するメッセージを選択し、適切なメッセージ マップ エントリとメッセージ ハンドラー メンバー関数をクラスに追加します。 アプリケーション固有のコードをハンドラー メンバー関数に記述するだけで済みます。

必要に応じて、メッセージ マップ エントリとメンバー関数を手動でいつでも記述できます。

最も単純なダイアログ ボックス以外のすべてに、派生ダイアログ クラスにメンバー変数を追加して、ユーザーがダイアログ ボックスのコントロールに入力したデータを格納したり、ユーザーのデータを表示したりします。 変数の追加ウィザードを使用して、メンバー変数を作成し、それらをコントロールに関連付けることができます。 同時に、変数の型と各変数の許容範囲を選択します。 コード ウィザードは、派生ダイアログ クラスにメンバー変数を追加します。

メンバ変数とダイアログ ボックスのコントロール間のデータ交換を自動的に処理するデータ マップが生成されます。 データ マップには、ダイアログ ボックス内のコントロールを適切な値で初期化し、データを取得し、データを検証する関数が用意されています。

モーダル ダイアログ ボックスを作成するには、派生ダイアログ クラスのコンストラクターを使用してスタックにオブジェクトを構築`DoModal`し、ダイアログ ウィンドウとそのコントロールを呼び出します。 モードレスダイアログを作成する場合は、ダイアログクラス`Create`のコンストラクタで呼び出します。

Windows SDK で説明されているように[、DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate)データ構造体を使用して、メモリ内にテンプレートを作成することもできます。 オブジェクト`CDialog`を作成したら[、CreateIndirect](#createindirect)を呼び出してモードレス ダイアログ ボックスを作成するか[、InitModalIndirect](#initmodalindirect)と[DoModal](#domodal)を呼び出してモーダル ダイアログ ボックスを作成します。

交換データ マップと検証データ マップは、新`CWnd::DoDataExchange`しいダイアログ クラスに追加された上書きで書き込まれます。 交換および検証機能の詳細については[、DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数`CWnd`のを参照してください。

プログラマとフレームワークの両方が`DoDataExchange`[、CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)への呼び出しを通じて間接的に呼び出します。

ユーザーが`UpdateData`[OK] ボタンをクリックしてモーダル ダイアログ ボックスを閉じると、フレームワークが呼び出されます。 ([キャンセル] ボタンをクリックしても、データは取得されません)。[OnInitDialog](#oninitdialog)の既定の実装では`UpdateData`、コントロールの初期値を設定する呼び出しも行われます。 通常は、`OnInitDialog`コントロールをさらに初期化するためにオーバーライドします。 `OnInitDialog`は、すべてのダイアログ コントロールが作成された後、ダイアログ ボックスが表示される直前に呼び出されます。

モーダル`CWnd::UpdateData`またはモードレス ダイアログ ボックスの実行中はいつでも呼び出すことができます。

手動でダイアログ ボックスを作成する場合は、必要なメンバ変数を派生ダイアログ ボックス クラスに追加し、これらの値を設定または取得するメンバー関数を追加します。

モーダル ダイアログ ボックスは、ユーザーが [OK] または [キャンセル] ボタンを`EndDialog`押したとき、またはコードがメンバー関数を呼び出したときに自動的に閉じます。

モードレス ダイアログ ボックスを実装する場合は、`OnCancel`常にメンバー関数`DestroyWindow`をオーバーライドし、その中から呼び出します。 基本クラス`CDialog::OnCancel`を呼び出さないでください`EndDialog`。 モードレス ダイアログ`PostNcDestroy`ボックスは通常**は新しい**を使用して割り当てられるため、**この**ダイアログ ボックスを削除するためにはモードレス ダイアログ ボックスの場合もオーバーライドする必要があります。 モーダル ダイアログ ボックスは、通常、フレーム上に`PostNcDestroy`構築され、クリーンアップする必要はありません。

詳細については、「 ダイアログ[ボックス](../../mfc/dialog-boxes.md)」を参照してください。 `CDialog`

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cdialogcdialog"></a><a name="cdialog"></a>ダイアログ::Cダイアログ

リソース ベースのモーダル ダイアログ ボックスを構築するには、いずれかのパブリック形式のコンストラクターを呼び出します。

```
explicit CDialog(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd = NULL);

explicit CDialog(
    UINT nIDTemplate,
    CWnd* pParentWnd = NULL);

CDialog();
```

### <a name="parameters"></a>パラメーター

*テンプレート名*<br/>
ダイアログ ボックス テンプレート リソースの名前である null で終わる文字列を格納します。

*テンプレート*<br/>
ダイアログ ボックス テンプレート リソースの ID 番号を格納します。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクト ( [CWnd](../../mfc/reference/cwnd-class.md)型 ) へのポインター。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

### <a name="remarks"></a>解説

コンストラクターの 1 つの形式では、テンプレート名によってダイアログ リソースにアクセスできます。 もう一方のコンストラクターは、IDD_DIALOG1 **IDD_** テンプレート ID 番号によるアクセスを提供します。

メモリ内のテンプレートからモーダル ダイアログ ボックスを構築するには、まずパラメーターなしのプロテクト コンストラクタ`InitModalIndirect`を呼び出してから、 を呼び出します。

上記のいずれかのメソッドを使用してモーダル ダイアログ ボックスを作成したら`DoModal`、 を呼び出します。

モードレス ダイアログ ボックスを構築するには、プロテクト形式の`CDialog`コンストラクターを使用します。 モードレス ダイアログ ボックスを実装するには独自のダイアログ ボックス クラスを派生させる必要があるため、コンストラクターは保護されています。 モードレス ダイアログ ボックスの構築は、2 段階の手順で行います。 最初にコンストラクタを呼び出します。次に、`Create`メンバー関数を呼び出してリソース ベースのダイアログ`CreateIndirect`ボックスを作成するか、メモリ内のテンプレートからダイアログ ボックスを作成します。

## <a name="cdialogcreate"></a><a name="create"></a>ダイアログ::作成

リソース`Create`のダイアログ ボックス テンプレートを使用して、モードレス ダイアログ ボックスを作成する呼び出し。

```
virtual BOOL Create(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd = NULL);

virtual BOOL Create(
    UINT nIDTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*テンプレート名*<br/>
ダイアログ ボックス テンプレート リソースの名前である null で終わる文字列を格納します。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する親ウィンドウ オブジェクト[(CWnd](../../mfc/reference/cwnd-class.md)型) へのポインター。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

*テンプレート*<br/>
ダイアログ ボックス テンプレート リソースの ID 番号を格納します。

### <a name="return-value"></a>戻り値

ダイアログ ボックスの作成と初期化が成功した場合、両方の形式は 0 以外を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

コンストラクター内に呼`Create`び出しを入れるか、コンストラクターが呼び出された後で呼び出すことができます。

`Create`ダイアログ ボックス テンプレート リソースにアクセスするための 2 つの形式のメンバー関数が、テンプレート名またはテンプレート ID 番号 (IDD_DIALOG1 など) によって提供されます。

どちらの形式でも、親ウィンドウ オブジェクトへのポインターを渡します。 *pParentWnd*が NULL の場合、ダイアログ ボックスは、その親ウィンドウまたはオーナー ウィンドウがメイン アプリケーション ウィンドウに設定された設定で作成されます。

メンバ`Create`関数は、ダイアログ ボックスを作成した直後に返されます。

親ウィンドウの作成時にダイアログ ボックスが表示される場合は、ダイアログ ボックス テンプレートのWS_VISIBLE スタイルを使用します。 それ以外の場合は`ShowWindow`、 を呼び出す必要があります。 ダイアログ ボックスのスタイルとそのアプリケーションについては、「MFC リファレンス」の「Windows SDK および[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)」の[DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate)構造体を*参照してください*。

関数を`CWnd::DestroyWindow`使用して、関数によって作成されたダイアログ`Create`ボックスを破棄します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]

## <a name="cdialogcreateindirect"></a><a name="createindirect"></a>Cダイアログ::インダイレクトを作成

メモリ内のダイアログ ボックス テンプレートからモードレス ダイアログ ボックスを作成します。

```
virtual BOOL CreateIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,
    CWnd* pParentWnd = NULL,
    void* lpDialogInit = NULL);

virtual BOOL CreateIndirect(
    HGLOBAL hDialogTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
ダイアログ ボックスの作成に使用するダイアログ ボックス テンプレートを含むメモリへのポイント。 このテンプレートは、Windows SDK で説明されているように[、DLGTEMPLATE 構造体](/windows/win32/api/winuser/ns-winuser-dlgtemplate)と制御情報の形式です。

*pParentWnd*<br/>
ダイアログ オブジェクトの親ウィンドウ オブジェクト[(CWnd](../../mfc/reference/cwnd-class.md)型) へのポイント。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

*をクリックします。*<br/>
DLGINIT リソースへの参照。

*テンプレート*<br/>
ダイアログ ボックス テンプレートを含むグローバル メモリへのハンドルを格納します。 このテンプレートは、ダイアログ ボックスの`DLGTEMPLATE`各コントロールの構造とデータの形式で作成されます。

### <a name="return-value"></a>戻り値

ダイアログ ボックスが正常に作成され、初期化された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

メンバ`CreateIndirect`関数は、ダイアログ ボックスを作成した直後に返されます。

親ウィンドウの作成時にダイアログ ボックスが表示される場合は、ダイアログ ボックス テンプレートのWS_VISIBLE スタイルを使用します。 それ以外の場合は`ShowWindow`、呼び出して表示する必要があります。 テンプレートで他のダイアログ ボックス スタイルを指定する方法の詳細については、Windows SDK の[DLGTEMPLATE](/windows/win32/api/winuser/ns-winuser-dlgtemplate)構造体を参照してください。

関数を`CWnd::DestroyWindow`使用して、関数によって作成されたダイアログ`CreateIndirect`ボックスを破棄します。

ActiveX コントロールを含むダイアログ ボックスには、DLGINIT リソースで提供される追加情報が必要です。

## <a name="cdialogdomodal"></a><a name="domodal"></a>ダイアログ::Doモーダル

モーダル ダイアログ ボックスを呼び出し、完了時にダイアログ ボックスの結果を返します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスを閉じるために使用される[、CDialog::EndDialog](#enddialog)メンバー関数に渡された*nResult*パラメーターの値を指定する**int**値。 関数がダイアログ ボックスを作成できなかった場合は -1、他のエラーが発生した場合は IDABORT を返[します。](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror)

### <a name="remarks"></a>解説

このメンバー関数は、ダイアログ ボックスがアクティブな間、ユーザーとのすべての操作を処理します。 これがダイアログ ボックスをモーダルにするものです。つまり、ダイアログ ボックスが閉じられるまで、他のウィンドウと対話することはできません。

ユーザーがダイアログ ボックスの押ボタン ([OK] または [キャンセル] など) をクリックすると、メッセージ ハンドラのメンバー関数[(OnOK](#onok)や[OnCancel](#oncancel)など) が呼び出され、ダイアログ ボックスが閉じられます。 既定`OnOK`のメンバー関数は、ダイアログ ボックスのデータを検証して更新し、結果 IDOK を持つダイアログ`OnCancel`ボックスを閉じ、既定のメンバー関数はダイアログ ボックスのデータを検証または更新せずに、結果 IDCANCEL を持つダイアログ ボックスを閉じます。 これらのメッセージ ハンドラ関数をオーバーライドして、動作を変更できます。

> [!NOTE]
> `PreTranslateMessage`モーダル ダイアログ ボックス メッセージ処理用に呼び出されました。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]

## <a name="cdialogenddialog"></a><a name="enddialog"></a>ダイアログ::エンドダイアログ

モーダル ダイアログ ボックスを終了するには、このメンバー関数を呼び出します。

```cpp
void EndDialog(int nResult);
```

### <a name="parameters"></a>パラメーター

*n結果*<br/>
ダイアログ ボックスから の呼び出し元に返される`DoModal`値を格納します。

### <a name="remarks"></a>解説

このメンバー関数は *、* の戻り値として`DoModal`nResult を返します。 モーダル ダイアログ`EndDialog`ボックスが作成されるたびに、この関数を使用して処理を完了する必要があります。

`EndDialog` [OnInitDialog](#oninitdialog)でも、いつでも呼び出すことができますが、その場合は、ダイアログ ボックスが表示される前、または入力フォーカスが設定される前に閉じる必要があります。

`EndDialog`ダイアログ ボックスをすぐに閉じません。 代わりに、現在のメッセージ ハンドラーが返されるとすぐにダイアログ ボックスを閉じるように指示するフラグを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]

[!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]

## <a name="cdialoggetdefid"></a><a name="getdefid"></a>次のダイアログ::ゲットデフID

メンバ関数`GetDefID`を呼び出して、ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得します。

```
DWORD GetDefID() const;
```

### <a name="return-value"></a>戻り値

32 ビット値 ( `DWORD`) デフォルトの押ボタンに ID 値がある場合、上位ワードにはDC_HASDEFIDが含まれ、下位ワードには ID 値が入ります。 デフォルトの押ボタンに ID 値がない場合、戻り値は 0 です。

### <a name="remarks"></a>解説

これは通常 OK ボタンです。

## <a name="cdialoggotodlgctrl"></a><a name="gotodlgctrl"></a>ダイアログ::ゴトドルグCtrl

ダイアログ ボックス内の指定したコントロールにフォーカスを移動します。

```cpp
void GotoDlgCtrl(CWnd* pWndCtrl);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
フォーカスを受け取るウィンドウ (コントロール) を識別します。

### <a name="remarks"></a>解説

*pWndCtrl*として渡すコントロール (子ウィンドウ) へのポインターを取得するには`CWnd::GetDlgItem`[、CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインターを返すメンバー関数を呼び出します。

### <a name="example"></a>例

  [次](../../mfc/reference/cwnd-class.md#getdlgitem)の例を参照してください。

## <a name="cdialoginitmodalindirect"></a><a name="initmodalindirect"></a>ダイアログ::イニトモーダルインダイレクト

メモリ内に作成するダイアログ ボックス テンプレートを使用してモーダル ダイアログ オブジェクトを初期化します。

```
BOOL InitModalIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,
    CWnd* pParentWnd = NULL,
    void* lpDialogInit = NULL);

    BOOL InitModalIndirect(
    HGLOBAL hDialogTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*テンプレート*<br/>
ダイアログ ボックスの作成に使用するダイアログ ボックス テンプレートを含むメモリへのポイント。 このテンプレートは、Windows SDK で説明されているように[、DLGTEMPLATE 構造体](/windows/win32/api/winuser/ns-winuser-dlgtemplate)と制御情報の形式です。

*テンプレート*<br/>
ダイアログ ボックス テンプレートを含むグローバル メモリへのハンドルを格納します。 このテンプレートは、ダイアログ ボックスの`DLGTEMPLATE`各コントロールの構造とデータの形式で作成されます。

*pParentWnd*<br/>
ダイアログ オブジェクトが属する親ウィンドウ オブジェクトまたはオーナー ウィンドウ オブジェクト ( [CWnd](../../mfc/reference/cwnd-class.md)型 ) へのポインター。 NULL の場合、ダイアログ オブジェクトの親ウィンドウはメイン アプリケーション ウィンドウに設定されます。

*をクリックします。*<br/>
DLGINIT リソースへの参照。

### <a name="return-value"></a>戻り値

ダイアログ オブジェクトが正常に作成され、初期化された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

モーダル ダイアログ ボックスを間接的に作成するには、まずメモリのグローバル ブロックを割り当て、ダイアログ ボックス テンプレートを使用してそのメモリを設定します。 次に、空`CDialog`のコンストラクターを呼び出して、ダイアログ ボックス オブジェクトを構築します。 次に、`InitModalIndirect`メモリ内のダイアログ ボックス テンプレートへのハンドルを格納する呼び出しします。 ダイアログ ボックスが作成され、[後で表示されます、DoModal](#domodal)メンバー関数が呼び出されたときにします。

ActiveX コントロールを含むダイアログ ボックスには、DLGINIT リソースで提供される追加情報が必要です。

## <a name="cdialogmapdialogrect"></a><a name="mapdialogrect"></a>ダイアログ::マップダイアログレック

四角形のダイアログ ボックスの単位を画面単位に変換する呼び出し。

```cpp
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*Lprect*<br/>
変換するダイアログ ボックス座標を含む[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

ダイアログ ボックスの単位は、ダイアログ ボックス テキストに使用されるフォントの文字の平均幅と高さから派生した、現在のダイアログ ボックスの基本単位を表します。 水平単位はダイアログ ボックスの基本幅単位の 4 分の 1 で、垂直単位はダイアログ ボックスの基本高さの単位の 8 分の 1 です。

Windows`GetDialogBaseUnits`関数はシステム フォントのサイズ情報を返しますが、リソース定義ファイルでDS_SETFONT スタイルを使用する場合は、ダイアログ ボックスごとに異なるフォントを指定できます。 Windows`MapDialogRect`関数は、このダイアログ ボックスに適切なフォントを使用します。

この`MapDialogRect`メンバー関数は、ダイアログ ボックスを作成したり、ボックス内にコントロールを配置したりするために、この四角形を使用して *、lpRect*のダイアログ ボックス単位を画面単位 (ピクセル) に置き換えます。

## <a name="cdialognextdlgctrl"></a><a name="nextdlgctrl"></a>ダイアログ::次のDlgCtrl

ダイアログ ボックスの次のコントロールにフォーカスを移動します。

```cpp
void NextDlgCtrl() const;
```

### <a name="remarks"></a>解説

フォーカスがダイアログ ボックスの最後のコントロールにある場合は、最初のコントロールに移動します。

## <a name="cdialogoncancel"></a><a name="oncancel"></a>ダイアログ::キャンセル

ユーザーが **[キャンセル]** をクリックするか、モーダルまたはモードレス ダイアログ ボックスで Esc キーを押すと、フレームワークはこのメソッドを呼び出します。

```
virtual void OnCancel();
```

### <a name="remarks"></a>解説

ユーザーが **[キャンセル**] をクリックするか Esc キーを押してダイアログ ボックスを閉じたときに、古いデータの復元などの操作を実行するには、このメソッドをオーバーライドします。 既定では[、EndDialog](#enddialog)を呼び出して[、DOModal](#domodal)が IDCANCEL を返すようにしてモーダル ダイアログ ボックスを閉じます。

モードレス ダイアログ ボックスで **[キャンセル]** ボタンを実装する場合`OnCancel`は、メソッドをオーバーライドし、メソッド内で[DestroyWindow を](../../mfc/reference/cwnd-class.md#destroywindow)呼び出す必要があります。 は、ダイアログ ボックスを非表示にしますが、破棄`EndDialog`しないという基本クラスのメソッドを呼び出すため、呼び出しません。

> [!NOTE]
> Windows XP でコンパイルされたプログラムで`CFileDialog`オブジェクトを使用する場合、このメソッドをオーバーライドすることはできません。 の詳細については、「 `CFileDialog` [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]

## <a name="cdialogoninitdialog"></a><a name="oninitdialog"></a>ダイアログ::オンイニトダイアログ

このメソッドは、メッセージに応答して`WM_INITDIALOG`呼び出されます。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

アプリケーションが入力フォーカスをダイアログ ボックスのいずれかのコントロールに設定したかどうかを指定します。 0`OnInitDialog`以外の値を返す場合、Windows は入力フォーカスを既定の場所に設定し、ダイアログ ボックスの最初のコントロールを設定します。 アプリケーションは、入力フォーカスをダイアログ ボックスのコントロールのいずれかに明示的に設定した場合にのみ 0 を返すことができます。

### <a name="remarks"></a>解説

Windows は`WM_INITDIALOG`、ダイアログ ボックスが表示される直前に発生する[、作成](#create)、[作成、](#createindirect)または[DoModal](#domodal)呼び出し中にダイアログ ボックスにメッセージを送信します。

ダイアログ ボックスが初期化されるときに特別な処理を実行する場合は、このメソッドをオーバーライドします。 オーバーライドされたバージョンでは、最初に基本クラス`OnInitDialog`を呼び出しますが、戻り値は無視します。 通常は、オーバーライド`TRUE`されたメソッドから戻ります。

Windows では`OnInitDialog`、すべての Microsoft Foundation クラス ライブラリ ダイアログ ボックスに共通する標準のグローバル ダイアログ ボックス プロシージャを使用して、関数を呼び出します。 メッセージ マップを通じてこの関数を呼び出さないため、このメソッドにメッセージ マップ エントリは必要ありません。

> [!NOTE]
> Windows Vista 以降の`CFileDialog`オペレーティング システムでコンパイルされたプログラムでオブジェクトを使用する場合、このメソッドをオーバーライドすることはできません。 Windows Vista 以降の`CFileDialog`での変更の詳細については[、「CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]

## <a name="cdialogonok"></a><a name="onok"></a>ダイアログ::オノク

ユーザーが **[OK]** ボタン (IDOK の ID を持つボタン) をクリックしたときに呼び出されます。

```
virtual void OnOK();
```

### <a name="remarks"></a>解説

**[OK]** ボタンがアクティブになったときにアクションを実行するには、このメソッドをオーバーライドします。 ダイアログ ボックスに自動データ検証と交換が含まれている場合、このメソッドの既定の実装では、ダイアログ ボックスのデータが検証され、アプリケーション内の適切な変数が更新されます。

モードレス ダイアログ ボックスで **[OK]** ボタンを実装する場合`OnOK`は、メソッドをオーバーライドし、メソッド内で[DestroyWindow を](../../mfc/reference/cwnd-class.md#destroywindow)呼び出す必要があります。 このメソッドは、ダイアログ ボックスを非表示にしますが、破棄しない[EndDialog](#enddialog)を呼び出すため、基本クラスのメソッドを呼び出しません。

> [!NOTE]
> Windows XP でコンパイルされたプログラムで`CFileDialog`オブジェクトを使用する場合、このメソッドをオーバーライドすることはできません。 の詳細については、「 `CFileDialog` [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]

## <a name="cdialogonsetfont"></a><a name="onsetfont"></a>ダイアログ::オンセットフォント

テキストを描画するときにダイアログ ボックス コントロールで使用するフォントを指定します。

```
Virtual void OnSetFont(CFont* pFont);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
[in]このダイアログ ボックスのすべてのコントロールの既定のフォントとして使用されるフォントへのポインターを指定します。

### <a name="remarks"></a>解説

ダイアログ ボックスでは、指定したフォントがすべてのコントロールの既定のフォントとして使用されます。

ダイアログ エディターは、通常、ダイアログ ボックスのフォントをダイアログ ボックス テンプレート リソースの一部として設定します。

> [!NOTE]
> Windows Vista 以降の`CFileDialog`オペレーティング システムでコンパイルされたプログラムでオブジェクトを使用する場合、このメソッドをオーバーライドすることはできません。 Windows Vista 以降の`CFileDialog`での変更の詳細については[、「CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)」を参照してください。

## <a name="cdialogprevdlgctrl"></a><a name="prevdlgctrl"></a>ダイアログ::PドルグCtrl

ダイアログ ボックスの前のコントロールにフォーカスを設定します。

```cpp
void PrevDlgCtrl() const;
```

### <a name="remarks"></a>解説

ダイアログ ボックスの最初のコントロールにフォーカスがある場合は、ボックス内の最後のコントロールに移動します。

## <a name="cdialogsetdefid"></a><a name="setdefid"></a>を設定します。

ダイアログボックスのデフォルトの押ボタンコントロールを変更します。

```cpp
void SetDefID(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
デフォルトになる押ボタンコントロールの ID を指定します。

## <a name="cdialogsethelpid"></a><a name="sethelpid"></a>ダイアログ::セットヘルプID

ダイアログ ボックスの状況依存のヘルプ ID を設定します。

```cpp
void SetHelpID(UINT nIDR);
```

### <a name="parameters"></a>パラメーター

*NIDR*<br/>
状況依存のヘルプ ID を指定します。

## <a name="see-also"></a>関連項目

[サンプル DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[サンプル DLGTEMPL](../../overview/visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
