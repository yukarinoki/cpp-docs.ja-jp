---
title: CDialog クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03cc6ab0708914f9283ac713e2a63dba02711db9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068347"
---
# <a name="cdialog-class"></a>CDialog クラス

画面のダイアログ ボックスを表示するための基本クラス。

## <a name="syntax"></a>構文

```
class CDialog : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[詳細](#cdialog)|`CDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDialog::Create](#create)|`CDialog` オブジェクトを初期化します。 モードレス ダイアログ ボックスを作成しにアタッチします、`CDialog`オブジェクト。|
|[CDialog::CreateIndirect](#createindirect)|(リソースに基づかない) メモリ内のダイアログ ボックス テンプレートからモードレス ダイアログ ボックスを作成します。|
|[CDialog::DoModal](#domodal)|モーダル ダイアログ ボックスの呼び出しを行う場合を返します。|
|[CDialog::EndDialog](#enddialog)|モーダル ダイアログ ボックスを閉じます。|
|[CDialog::GetDefID](#getdefid)|ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得します。|
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|ダイアログ ボックスで指定したダイアログ ボックス コントロールにフォーカスを移動します。|
|[CDialog::InitModalIndirect](#initmodalindirect)|(リソースに基づかない) メモリ内のダイアログ ボックス テンプレートからモーダル ダイアログ ボックスを作成します。 パラメーターを保存する関数まで`DoModal`が呼び出されます。|
|[CDialog::MapDialogRect](#mapdialogrect)|四角形の単位 ダイアログ ボックスを画面の単位に変換します。|
|[CDialog::NextDlgCtrl](#nextdlgctrl)|ダイアログ ボックスで次のダイアログ ボックス コントロールにフォーカスを移動します。|
|[CDialog::OnInitDialog](#oninitdialog)|ダイアログ ボックスの初期化を補強をオーバーライドします。|
|[CDialog::OnSetFont](#onsetfont)|オーバーライドすると、ダイアログ ボックス コントロールでテキストを描画するときを使用するフォントを指定します。|
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|ダイアログ ボックスで、前のダイアログ ボックス コントロールにフォーカスを移動します。|
|[CDialog::SetDefID](#setdefid)|指定したプッシュのダイアログ ボックスの既定のプッシュ ボタン コントロールを変更します。|
|[CDialog::SetHelpID](#sethelpid)|ダイアログ ボックスの状況依存のヘルプ ID を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CDialog::OnCancel](#oncancel)|オーバーライドすると、[キャンセル] ボタンまたは ESC キーの操作を実行します。 既定値は、ダイアログ ボックスを閉じ、 `DoModal` IDCANCEL を返します。|
|[CDialog::OnOK](#onok)|オーバーライドすると、モーダル ダイアログ ボックスで [ok] ボタンのアクションを実行します。 既定値は、ダイアログ ボックスを閉じ、 `DoModal` IDOK を返します。|

## <a name="remarks"></a>Remarks

ダイアログ ボックスが 2 つの型: モーダルとモードレスです。 アプリケーションを続行する前に、ユーザーがモーダル ダイアログ ボックスを閉じる必要があります。 モードレス ダイアログ ボックスは、ダイアログ ボックスが表示され、キャンセルまたはダイアログ ボックスを削除せずに別のタスクに戻るにできます。

A`CDialog`オブジェクトは、ダイアログ テンプレートの組み合わせと`CDialog`-クラスを派生します。 ダイアログ テンプレートを作成し、リソースに格納する、ダイアログ エディターを使用してから派生したクラスを作成するクラスの追加ウィザードを使用して`CDialog`します。

その他のウィンドウのように、ダイアログ ボックスでは、Windows からメッセージを受信します。 ダイアログ ボックスで、ユーザーがダイアログ ボックスと対話する方法では、ダイアログ ボックスのコントロールからの通知メッセージの処理、特に興味のあります。 [プロパティ] ウィンドウを使用すると、処理するメッセージは、適切なメッセージ マップ エントリとメッセージ ハンドラー メンバー関数クラスに追加するのかを選択できます。 のみでハンドラー メンバー関数は、アプリケーション固有のコードを記述する必要があります。

場合は、常に記述できますとメンバー関数のメッセージ マップ エントリを手動で。

最も単純なダイアログ ボックスがすべてで、ユーザーがダイアログ ボックスのコントロールで入力したデータを格納する、またはユーザーのデータを表示するダイアログの派生クラスにメンバー変数を追加します。 変数の追加ウィザードを使用して、メンバー変数を作成し、コントロールに関連付けることができます。 同時に、変数の型と各変数の値の許容範囲を選択します。 コード ウィザードでは、ダイアログの派生クラスにメンバー変数を追加します。

データ マップが自動的にメンバー変数と、ダイアログ ボックスのコントロール間でデータの交換を処理するために生成されます。 データ マップ ダイアログ ボックスで適切な値を持つコントロールを初期化し、データを取得し、データの検証関数を提供します。

モーダル ダイアログ ボックスを作成するには、派生ダイアログ クラスのコンス トラクターを使用して、スタック上のオブジェクトの構築を呼び出して`DoModal`ダイアログ ウィンドウとそのコントロールを作成します。 モードレス ダイアログを作成する場合は、呼び出す`Create`ダイアログ クラスのコンス トラクター。

使用して、メモリ内テンプレートを作成することも、 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Windows SDK」の説明に従って、データが構造体します。 構築した後、`CDialog`オブジェクト、呼び出す[CreateIndirect](#createindirect) 、モードレスを作成するダイアログ ボックスで、または呼び出し[持たない](#initmodalindirect)と[DoModal](#domodal)モーダルを作成するにはダイアログ ボックス。

オーバーライドで、exchange と検証のデータ マップが書き込まれる`CWnd::DoDataExchange`新しいダイアログ クラスに追加されています。 参照してください、 [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数で`CWnd`の詳細については、exchange と検証機能。

プログラマとフレームワークの呼び出しの両方`DoDataExchange`への呼び出しを通じて間接的に[:updatedata](../../mfc/reference/cwnd-class.md#updatedata)します。

Framework 呼び出し`UpdateData`ユーザーがモーダル ダイアログ ボックスを閉じる [ok] ボタンをクリックするとします。 (データは取得されません、[キャンセル] ボタンがクリックされた場合。)既定の実装[OnInitDialog](#oninitdialog)も呼び出して`UpdateData`コントロールの初期値を設定します。 通常、オーバーライドする`OnInitDialog`をさらにコントロールを初期化します。 `OnInitDialog` すべてのダイアログ コントロールを作成し、直前に、ダイアログ ボックスが表示されますが呼び出されます。

呼び出すことができます`CWnd::UpdateData`モーダルまたはモードレス ダイアログ ボックスの実行中にいつでもできます。

ダイアログ ボックスを手動で開発する場合、自分でダイアログ ボックスの派生クラスに必要なメンバー変数を追加して、これらの値を取得または設定するメンバー関数を追加します。

ユーザーが [ok] または [キャンセル] ボタンを押したとき、または、コードを呼び出すと、モーダル ダイアログ ボックスが自動的に閉じます、`EndDialog`メンバー関数。

モードレス ダイアログ ボックスを実装するときに常にオーバーライド、`OnCancel`メンバー関数と呼び出し`DestroyWindow`から内部にします。 基本クラスを呼び出さないでください`CDialog::OnCancel`を呼び出すため、 `EndDialog`、ダイアログ ボックスを非表示にするが破棄されます。 オーバーライドする必要がありますも`PostNcDestroy`を削除するには、モードレス ダイアログ ボックスの**この**モードレス ダイアログ ボックスに通常割り当てられるため、**新しい**。 モーダル ダイアログ ボックスは、通常、フレームで構築され、必要はありません`PostNcDestroy`クリーンアップします。

詳細については`CDialog`を参照してください[ ダイアログ ボックス](../../mfc/dialog-boxes.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

##  <a name="cdialog"></a>  詳細

リソース ベースのモーダル ダイアログ ボックスを作成するには、コンス トラクターのいずれかのパブリックの形式を呼び出します。

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

*lpszTemplateName*<br/>
ダイアログ ボックスのテンプレート リソースの名前を表す null で終わる文字列が含まれています。

*nIDTemplate*<br/>
ダイアログ ボックスのテンプレート リソースの ID 番号が含まれています。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ オブジェクトの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

### <a name="remarks"></a>Remarks

コンス トラクターの 1 つのフォームは、テンプレート名でダイアログ リソースへのアクセスを提供します。 その他のコンス トラクターでアクセスを提供テンプレートの ID 番号では、通常、 **idd _** プレフィックス (IDD_DIALOG1 など)。

メモリ内テンプレートからモーダル ダイアログ ボックスを作成するには、最初に、パラメーターなし、protected のコンス トラクターを呼び出すを呼び出して`InitModalIndirect`します。

上記のメソッドのいずれかで、モーダル ダイアログ ボックスを構築した後で呼び出す`DoModal`します。

モードレス ダイアログ ボックスを作成するには、保護されているフォームを使用して、`CDialog`コンス トラクター。 モードレス ダイアログ ボックスを実装するために、独自のダイアログ ボックス クラスを派生する必要がありますので、コンス トラクターは保護されます。 モードレス ダイアログ ボックスの構築は、2 段階のプロセスです。 コンス トラクターの最初の呼び出し呼び出して、`Create`リソース ベースのダイアログ ボックスを作成するメンバー関数呼び出しまたは`CreateIndirect` ダイアログ ボックスをメモリ内のテンプレートから作成します。

##  <a name="create"></a>  CDialog::Create

呼び出す`Create`リソースからダイアログ ボックスのテンプレートを使用してモードレス ダイアログ ボックスを作成します。

```
virtual BOOL Create(
    LPCTSTR lpszTemplateName,
    CWnd* pParentWnd = NULL);

virtual BOOL Create(
    UINT nIDTemplate,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszTemplateName*<br/>
ダイアログ ボックスのテンプレート リソースの名前を表す null で終わる文字列が含まれています。

*pParentWnd*<br/>
親ウィンドウ オブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ オブジェクトの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

*nIDTemplate*<br/>
ダイアログ ボックスのテンプレート リソースの ID 番号が含まれています。

### <a name="return-value"></a>戻り値

どちらの形式 ダイアログ ボックスの作成と初期化が成功した場合は 0 以外を返すそれ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

呼び出しを配置する`Create`コンス トラクターまたは呼び出しの内部コンス トラクターの後に呼び出されます。

2 つの形式、`Create`メンバー関数は、ダイアログ ボックスのテンプレート リソースにアクセスするためテンプレート名またはテンプレートの ID 番号 (IDD_DIALOG1 など) のいずれかによって提供されます。

いずれかの形式の親ウィンドウ オブジェクトへのポインターを渡します。 場合*pParentWnd*が null の場合、メイン アプリケーション ウィンドウに、親または所有者のウィンドウで、ダイアログ ボックスが作成されます。

`Create`  ダイアログ ボックスが作成された後すぐに、メンバー関数が返されます。

親ウィンドウが作成されると、ダイアログ ボックスを表示する必要がある場合は、ダイアログ ボックスのテンプレートで WS_VISIBLE スタイルを使用します。 それ以外の場合、呼び出す必要がある`ShowWindow`します。 さらにダイアログ ボックスのスタイルと、アプリケーションは、次を参照してください。、 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Windows SDK の構造と[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)で、 *MFC リファレンス*します。

使用して、`CWnd::DestroyWindow`関数によって作成されたダイアログ ボックスを破棄する、`Create`関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]

##  <a name="createindirect"></a>  CDialog::CreateIndirect

メモリ内のダイアログ ボックス テンプレートからモードレス ダイアログ ボックスを作成するには、このメンバー関数を呼び出します。

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

*lpDialogTemplate*<br/>
ダイアログ ボックスを作成するために使用 ダイアログ ボックスのテンプレートが含まれるメモリへのポインター。 このテンプレートは、の形式で、 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate)構造とコントロールは、Windows SDK で説明されているとします。

*pParentWnd*<br/>
ダイアログ オブジェクトの親ウィンドウのオブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md))。 NULL の場合、ダイアログ オブジェクトの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

*lpDialogInit*<br/>
DLGINIT リソースへのポインター。

*hDialogTemplate*<br/>
ダイアログ ボックスのテンプレートを含むグローバル メモリを識別するハンドルが含まれています。 このテンプレートは、の形式で、`DLGTEMPLATE`構造と、ダイアログ ボックス内の各コントロールのデータ。

### <a name="return-value"></a>戻り値

ダイアログ ボックスが作成され、正常に初期化された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

`CreateIndirect`  ダイアログ ボックスが作成された後すぐに、メンバー関数が返されます。

親ウィンドウが作成されると、ダイアログ ボックスを表示する必要がある場合は、ダイアログ ボックスのテンプレートで WS_VISIBLE スタイルを使用します。 それ以外の場合、呼び出す必要がある`ShowWindow`表示することです。 テンプレートの他のダイアログ ボックスのスタイルを指定する方法の詳細については、次を参照してください。、 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Windows SDK の構造体。

使用して、`CWnd::DestroyWindow`関数によって作成されたダイアログ ボックスを破棄する、`CreateIndirect`関数。

ActiveX コントロールを含むダイアログ ボックスでは、DLGINIT リソースで提供される追加情報が必要です。

##  <a name="domodal"></a>  CDialog::DoModal

モーダル ダイアログ ボックスの呼び出しを完了ダイアログ ボックスの結果を返すには、このメンバー関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

**Int**の値を指定する値、*れた*パラメーターに渡された、 [CDialog::EndDialog](#enddialog)メンバー関数は、ダイアログ ボックスを閉じるために使用します。 関数を作成できませんでした ダイアログ ボックスで、または IDABORT 出力ウィンドウがからエラー情報がどのように格納する場合、その他のエラーが発生した場合の場合、戻り値は-1 [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360)します。

### <a name="remarks"></a>Remarks

このメンバー関数は、ダイアログ ボックスがアクティブな間、ユーザーとすべての対話を処理します。 これにより、ダイアログ ボックスがモーダル; は、します。ユーザーは、ダイアログ ボックスが閉じられるまで、他のウィンドウを操作できません。

ユーザーがクリックした場合のダイアログ ボックスで、[ok] または [キャンセル] メッセージ ハンドラー メンバー関数などのプッシュ ボタンなど[OnOK](#onok)または[OnCancel](#oncancel)、しようとするダイアログ ボックスを閉じると呼びます。 既定の`OnOK`メンバー関数は検証しダイアログ ボックスのデータを更新および idok、ダイアログ ボックスを閉じて、既定`OnCancel`メンバー関数は、検証または更新することがなく結果 IDCANCEL をダイアログ ボックスを閉じますが、ダイアログ ボックスのデータ。 その動作を変更するこれらのメッセージ ハンドラー関数をオーバーライドできます。

> [!NOTE]
> `PreTranslateMessage` モーダル ダイアログ ボックスのメッセージの処理と呼ばれます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]

##  <a name="enddialog"></a>  CDialog::EndDialog

モーダル ダイアログ ボックスを終了するには、このメンバー関数を呼び出します。

```
void EndDialog(int nResult);
```

### <a name="parameters"></a>パラメーター

*%n 結果*<br/>
ダイアログ ボックスからの呼び出し元に返される値が含まれる`DoModal`します。

### <a name="remarks"></a>Remarks

このメンバー関数を返します*れた*の戻り値として`DoModal`します。 使用する必要があります、`EndDialog`モーダル ダイアログ ボックスが作成されるたびに処理を完了する関数。

呼び出すことができます`EndDialog`であっても、いつでも[OnInitDialog](#oninitdialog)前に ダイアログ ボックスが表示される閉じる必要がある場合にや、入力フォーカスが設定される前にします。

`EndDialog` ダイアログ ボックスをすぐに閉じません。 代わりに、ダイアログ ボックスの現在のメッセージ ハンドラーによって返された直後に指示するフラグを設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]

[!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]

##  <a name="getdefid"></a>  CDialog::GetDefID

呼び出す、 `GetDefID`  ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得するメンバー関数。

```
DWORD GetDefID() const;
```

### <a name="return-value"></a>戻り値

32 ビット値 ( `DWORD`)。 既定のプッシュ ボタンに ID 値がある場合は、上位ワードには DC_HASDEFID が含まれています、下位ワードに ID 値が含まれています。 既定のプッシュ ボタンが、ID 値を持たない場合、戻り値は 0 です。

### <a name="remarks"></a>Remarks

これは、通常は、[ok] ボタンです。

##  <a name="gotodlgctrl"></a>  CDialog::GotoDlgCtrl

ダイアログ ボックスで指定したコントロールにフォーカスを移動します。

```
void GotoDlgCtrl(CWnd* pWndCtrl);
```

### <a name="parameters"></a>パラメーター

*pWndCtrl*<br/>
フォーカスを受け取るウィンドウ (コントロール) を識別します。

### <a name="remarks"></a>Remarks

コントロールとして渡す (子ウィンドウ) へのポインターを取得する*pWndCtrl*を呼び出し、`CWnd::GetDlgItem`へのポインターを返すメンバー関数、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクト。

### <a name="example"></a>例

  例をご覧ください[:getdlgitem](../../mfc/reference/cwnd-class.md#getdlgitem)します。

##  <a name="initmodalindirect"></a>  CDialog::InitModalIndirect

メモリ内で構築する ダイアログ ボックスのテンプレートを使用してモーダル ダイアログ ボックスのオブジェクトを初期化するためにこのメンバー関数を呼び出します。

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

*lpDialogTemplate*<br/>
ダイアログ ボックスを作成するために使用 ダイアログ ボックスのテンプレートが含まれるメモリへのポインター。 このテンプレートは、の形式で、 [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate)構造とコントロールは、Windows SDK で説明されているとします。

*hDialogTemplate*<br/>
ダイアログ ボックスのテンプレートを含むグローバル メモリを識別するハンドルが含まれています。 このテンプレートは、の形式で、`DLGTEMPLATE`構造と、ダイアログ ボックス内の各コントロールのデータ。

*pParentWnd*<br/>
親またはオーナー ウィンドウのオブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ オブジェクトの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。

*lpDialogInit*<br/>
DLGINIT リソースへのポインター。

### <a name="return-value"></a>戻り値

ダイアログ オブジェクトが作成され、正常に初期化された場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

まず、モーダル ダイアログ ボックスを直接作成するには、グローバル メモリ ブロックを割り当て、 ダイアログ ボックスのテンプレートを格納します。 空を呼び出して`CDialog` ダイアログ ボックスのオブジェクトを構築するコンス トラクター。 次に、呼び出す`InitModalIndirect`をメモリ内のダイアログ ボックスのテンプレートに、ハンドルを格納します。 Windows のダイアログ ボックスが作成され、表示されるときに、後で、 [DoModal](#domodal)メンバー関数が呼び出されます。

ActiveX コントロールを含むダイアログ ボックスでは、DLGINIT リソースで提供される追加情報が必要です。

##  <a name="mapdialogrect"></a>  CDialog::MapDialogRect

四角形の単位 ダイアログ ボックスを画面の単位に変換する場合に呼び出します。

```
void MapDialogRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*lpRect*<br/>
指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)  ダイアログ ボックスを含むオブジェクトを変換する座標します。

### <a name="remarks"></a>Remarks

ダイアログ ボックスのテキストに使用されるフォントの文字の高さと幅の平均から派生した現在のダイアログ ボックス ベース ユニットの観点からは、ダイアログ ボックスのユニットが記載されています。 水平方向の 1 つの単位がベースの幅の単位をダイアログ ボックスの 4 分の 1 と垂直方向の 1 つの単位が 8 分の 1 ダイアログ ボックスの高さの基本単位です。

`GetDialogBaseUnits` Windows 関数が、システム フォントのサイズ情報を返しますが、リソース定義ファイルで DS_SETFONT スタイルを使用する場合は、各ダイアログ ボックスの別のフォントを指定できます。 `MapDialogRect` Windows 関数はこのダイアログ ボックスの適切なフォントを使用します。

`MapDialogRect`メンバー関数は、ダイアログ ボックスの単位*lpRect*で画面の単位 (ピクセル単位) ダイアログ ボックスを作成したり、ボックス内のコントロールの位置四角形を使用できるようにします。

##  <a name="nextdlgctrl"></a>  CDialog::NextDlgCtrl

ダイアログ ボックスで次のコントロールにフォーカスを移動します。

```
void NextDlgCtrl() const;
```

### <a name="remarks"></a>Remarks

ダイアログ ボックスの最後のコントロールにフォーカスがある場合は、最初のコントロールに移動します。

##  <a name="oncancel"></a>  CDialog::OnCancel

フレームワークが、ユーザーがクリックしたときに、このメソッドを呼び出して**キャンセル**モーダルまたはモードレス ダイアログ ボックスで、ESC キーを押すか。

```
virtual void OnCancel();
```

### <a name="remarks"></a>Remarks

(古いデータの復元) などのアクションを実行するには、このメソッドをオーバーライドして、ユーザーがクリックしてダイアログ ボックスを閉じると**キャンセル**または ESC キーを押します。 既定値は、呼び出すことによって、モーダル ダイアログ ボックスを閉じます[EndDialog](#enddialog)の原因と[DoModal](#domodal) IDCANCEL に戻ります。

実装する場合、**キャンセル**ボタン モードレス ダイアログ ボックスでは、オーバーライドする必要があります、`OnCancel`メソッドと呼び出し[DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)内。 呼び出すために、基底クラスのメソッドを呼び出さないでください`EndDialog`、ダイアログ ボックスを非表示にを破棄することができます。

> [!NOTE]
>  使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows XP でコンパイルされたプログラム内のオブジェクト。 詳細については`CFileDialog`を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]

##  <a name="oninitdialog"></a>  CDialog::OnInitDialog

応答でこのメソッドは、`WM_INITDIALOG`メッセージ。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>戻り値

アプリケーションがダイアログ ボックスで、コントロールのいずれかに入力フォーカスを設定したかどうかを指定します。 場合`OnInitDialog`戻り値は 0 以外の場合、Windows で、既定の場所 ダイアログ ボックスの最初のコントロールに入力フォーカスが設定します。 アプリケーションは、ダイアログ ボックスで、コントロールのいずれかに入力フォーカスを設定が明示的に場合にのみ、0 を返します。

### <a name="remarks"></a>Remarks

Windows の送信、`WM_INITDIALOG`メッセージ中に、ダイアログ ボックスに、[作成](#create)、 [CreateIndirect](#createindirect)、または[DoModal](#domodal)呼び出しで、ダイアログ ボックスの直前に発生します。表示されます。

ダイアログ ボックスの初期化時に、特別な処理を実行する場合は、このメソッドをオーバーライドします。 オーバーライドされたバージョンでは、基本クラスを呼び出す最初`OnInitDialog`が、その戻り値を無視します。 通常戻ります`TRUE`からメソッドをオーバーライドします。

Windows の呼び出し、 `OnInitDialog` Microsoft Foundation Class ライブラリのすべてのダイアログ ボックスを共通の標準的なグローバルのダイアログ ボックス プロシージャを使用して関数。 メッセージ マップを使用して関数を 、したがって必要はありませんメッセージ マップのエントリをこのメソッドの。

> [!NOTE]
> 使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows Vista またはそれ以降のオペレーティング システムでコンパイルされたプログラム内のオブジェクト。 変更の詳細については`CFileDialog`Windows vista 以降を参照してください。 [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]

##  <a name="onok"></a>  CDialog::OnOK

ユーザーがクリックしたときに呼び出されます、 **OK**ボタン (idok ID のボタン)。

```
virtual void OnOK();
```

### <a name="remarks"></a>Remarks

アクションを実行するには、このメソッドをオーバーライドするときに、 **[ok]** ボタンがアクティブになります。 ダイアログ ボックスには、データの自動検証と exchange が含まれている場合、このメソッドの既定の実装は ダイアログ ボックスのデータを検証し、アプリケーションの適切な変数を更新します。

実装する場合、 **OK**ボタン モードレス ダイアログ ボックスでは、オーバーライドする必要があります、`OnOK`メソッドを呼び出します[DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)内。 呼び出すために、基底クラスのメソッドを呼び出さないでください[EndDialog](#enddialog)ダイアログ ボックスを非表示が破棄しません。

> [!NOTE]
>  使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows XP でコンパイルされたプログラム内のオブジェクト。 詳細については`CFileDialog`を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]

##  <a name="onsetfont"></a>  CDialog::OnSetFont

テキストを描画するときに、ダイアログ ボックス コントロールが使用するフォントを指定します。

```
Virtual void OnSetFont(CFont* pFont);
```

### <a name="parameters"></a>パラメーター

*pFont*<br/>
[in]このダイアログ ボックスのすべてのコントロールの既定のフォントとして使用されるフォントへのポインターを指定します。

### <a name="remarks"></a>Remarks

ダイアログ ボックスに、そのすべてのコントロールの既定値として指定したフォントを使用します。

ダイアログ エディターは通常、ダイアログ ボックスのテンプレート リソースの一部としてダイアログ ボックスのフォントを設定します。

> [!NOTE]
> 使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows Vista またはそれ以降のオペレーティング システムでコンパイルされたプログラム内のオブジェクト。 変更の詳細については`CFileDialog`Windows vista 以降を参照してください。 [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)します。

##  <a name="prevdlgctrl"></a>  CDialog::PrevDlgCtrl

ダイアログ ボックスで、前のコントロールにフォーカスを設定します。

```
void PrevDlgCtrl() const;
```

### <a name="remarks"></a>Remarks

ダイアログ ボックスの最初のコントロールにフォーカスがある場合、最後にコントロールに移動します。

##  <a name="setdefid"></a>  CDialog::SetDefID

ダイアログ ボックスの既定のプッシュ ボタン コントロールを変更します。

```
void SetDefID(UINT nID);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
既定値になるプッシュ ボタン コントロールの ID を指定します。

##  <a name="sethelpid"></a>  CDialog::SetHelpID

ダイアログ ボックスの状況依存のヘルプ ID を設定します。

```
void SetHelpID(UINT nIDR);
```

### <a name="parameters"></a>パラメーター

*nIDR*<br/>
状況依存のヘルプ ID を指定します

## <a name="see-also"></a>関連項目

[MFC サンプル DLGCBR32](../../visual-cpp-samples.md)<br/>
[MFC サンプル DLGTEMPL](../../visual-cpp-samples.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)

