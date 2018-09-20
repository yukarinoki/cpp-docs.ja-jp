---
title: CColorDialog クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63b909c80ab8f2f8f5bd1c5ad002f2c5f6523081
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441045"
---
# <a name="ccolordialog-class"></a>CColorDialog クラス

色の選択 ダイアログ ボックスをアプリケーションに組み込むことができます。

## <a name="syntax"></a>構文

```
class CColorDialog : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CColorDialog::CColorDialog](#ccolordialog)|`CColorDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CColorDialog::DoModal](#domodal)|色のダイアログ ボックスが表示されますおよびを選択できます。|
|[CColorDialog::GetColor](#getcolor)|返します、`COLORREF`選択された色の値を含む構造体。|
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|ユーザーによって作成されたカスタムの色を取得します。|
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|指定した色に現在の色の選択を強制します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CColorDialog::OnColorOK](#oncolorok)|ダイアログ ボックスに入力された色の検証をオーバーライドします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CColorDialog::m_cc](#m_cc)|ダイアログ ボックスの設定をカスタマイズするために使用する構造体。|

## <a name="remarks"></a>Remarks

A`CColorDialog`オブジェクトはダイアログ ボックスに表示システムに対して定義されている色の一覧。 ユーザーでは、選択したり、しに報告アプリケーションにダイアログ ボックスの終了時に、一覧から特定の色を作成することができます。

構築する、`CColorDialog`オブジェクトで指定されたコンス トラクターを使用して、または新しいクラスを派生し、独自のカスタム コンス トラクターを使用します。

ダイアログ ボックスが構築されると、設定または任意の値を変更、 [m_cc](#m_cc)構造 ダイアログ ボックスのコントロールの値を初期化します。 *M_cc*型の構造は、 [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora)します。

ダイアログ ボックスのコントロールを初期化した後、 `DoModal`  ダイアログ ボックスが表示され、ユーザーが色を選択できるようにするメンバー関数。 `DoModal` いずれか、ダイアログ ボックスの ok (IDOK) またはキャンセル (IDCANCEL) ボタンのユーザーの選択範囲を返します。

場合`DoModal`IDOK を返しますのいずれかを使用することができます`CColorDialog`のユーザーによって入力された情報を取得するメンバー関数。

Windows を使用する[情報を得る](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror) ダイアログ ボックスの初期化中にエラーが発生したかどうかを判断して、エラーに関する詳細については、関数。

`CColorDialog` COMMDLG に依存します。Windows 3.1 以降のバージョンに付属する DLL ファイルです。

ダイアログ ボックスをカスタマイズするには、派生クラスを`CColorDialog`独自のダイアログ テンプレートを提供し、拡張コントロールからの通知メッセージを処理するメッセージ マップを追加します。 基本クラスには、処理されないメッセージを渡す必要があります。

フック関数をカスタマイズする必要はありません。

> [!NOTE]
>  一部のインストールで、`CColorDialog`オブジェクトでは、させるその他のフレームワークを使用している場合、背景が灰色表示は`CDialog`灰色のオブジェクト。

使用しての詳細については`CColorDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxdlgs.h

##  <a name="ccolordialog"></a>  CColorDialog::CColorDialog

`CColorDialog` オブジェクトを構築します。

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*clrInit*<br/>
既定色を選択します。 値が指定されていない場合は、既定では RGB(0,0,0) (黒です)。

*dwFlags*<br/>
関数と、ダイアログ ボックスの外観をカスタマイズするフラグのセット。 詳細については、次を参照してください。、 [CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora) Windows SDK の構造体。

*pParentWnd*<br/>
ウィンドウ、ダイアログ ボックスの親またはオーナー ウィンドウへのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

##  <a name="domodal"></a>  CColorDialog::DoModal

Windows の一般的な色 ダイアログ ボックスを表示し、ユーザーが色を選択できるようにするには、この関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

IDOK や IDCANCEL。 IDCANCEL が返された場合は、Windows を呼び出す[情報を得る](/windows/desktop/api/commdlg/nf-commdlg-commdlgextendederror)エラーが発生したかどうかを判断する関数。

IDOK や IDCANCEL は、ユーザーが [ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。

### <a name="remarks"></a>Remarks

メンバーを設定して、さまざまな色 ダイアログ ボックスのオプションを初期化する場合、 [m_cc](#m_cc)構造体を呼び出す前に、これを行う必要があります`DoModal`はダイアログ ボックスのオブジェクトを構築します。

呼び出した後`DoModal`、他のメンバー、ダイアログ ボックスに、設定やユーザーによって入力された情報を取得する関数を呼び出すことができます。

### <a name="example"></a>例

  例をご覧ください[CColorDialog::CColorDialog](#ccolordialog)します。

##  <a name="getcolor"></a>  CColorDialog::GetColor

この関数を呼び出した後`DoModal`色の選択したユーザーに関する情報を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

A [COLORREF](/windows/desktop/gdi/colorref)色 ダイアログ ボックスで選択した色の RGB の情報を含む値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

##  <a name="getsavedcustomcolors"></a>  CColorDialog::GetSavedCustomColors

`CColorDialog` オブジェクトは、色を選択するだけでなく最大 16 個のカスタム色を定義するユーザーを許可します。

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>戻り値

ユーザーによって作成されたカスタム カラーを格納する 16 の RGB カラー値の配列へのポインター。

### <a name="remarks"></a>Remarks

`GetSavedCustomColors`メンバー関数は、これらの色へのアクセスを提供します。 後に、これらの色を取得できる[DoModal](#domodal) IDOK を返します。

返される配列には、16 の RGB 値のそれぞれは、RGB(255,255,255) (白) に初期化されます。 ユーザーが選択したカスタムの色は、アプリケーション内でのダイアログ ボックスの呼び出しの間でのみ保存されます。 アプリケーションの呼び出しの間でこれらの色を保存する場合は、する必要があります、その他の方法でなどに保存、初期化 (します。INI) ファイルです。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

##  <a name="m_cc"></a>  CColorDialog::m_cc

型の構造体[CHOOSECOLOR](/windows/desktop/api/commdlg/ns-commdlg-tagchoosecolora)メンバーの特性と、ダイアログ ボックスの値を格納します。

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>Remarks

構築した後、`CColorDialog`オブジェクトを使用することができます*m_cc*を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

##  <a name="oncolorok"></a>  CColorDialog::OnColorOK

ダイアログ ボックスに入力された色の検証をオーバーライドします。

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>戻り値

以外の場合は、ダイアログ ボックスを消去しない必要があります。入力された色をそのまま使用する場合は 0 を返します。

### <a name="remarks"></a>Remarks

色のダイアログ ボックスで、ユーザーが選択した色のカスタム検証を提供したい場合にのみ、この関数をオーバーライドします。

ユーザーは、次の 2 つのメソッドのいずれかで色を選択できます。

- カラー パレットの色をクリックします。 選択した色の RGB 値は、適切な RGB 編集ボックスに反映されます。

- エディット ボックスに、RGB 値を入力します。

オーバーライドする`OnColorOK`の色をユーザーがアプリケーションに固有の何らかの理由が一般的な色 ダイアログ ボックスに入力を拒否することができます。

通常、フレームワークの色の既定の検証を提供し、無効な色が入力した場合は、メッセージ ボックスを表示するために、この関数を使用する必要はありません。

呼び出すことができます[SetCurrentColor](#setcurrentcolor)内から`OnColorOK`色の選択を強制します。 1 回`OnColorOK`が発生したこと (つまり、ユーザーがクリックした **[ok]** 色の変更を受け入れるように)、呼び出すことができます[GetColor](#getcolor)新しい色の RGB 値を取得します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

##  <a name="setcurrentcolor"></a>  CColorDialog::SetCurrentColor

この関数を呼び出した後`DoModal`で指定された色の値に現在の色の選択を強制する*clr*します。

```
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

*clr*<br/>
RGB 色の値。

### <a name="remarks"></a>Remarks

この関数は、メッセージ ハンドラー内から呼び出されるまたは`OnColorOK`します。 ダイアログ ボックスが自動的の値に基づいて、ユーザーの選択を更新、 *clr*パラメーター。

### <a name="example"></a>例

  例をご覧ください[CColorDialog::OnColorOK](#oncolorok)します。

## <a name="see-also"></a>関連項目

[MFC サンプル MDI](../../visual-cpp-samples.md)<br/>
[MFC サンプル DRAWCLI](../../visual-cpp-samples.md)<br/>
[CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)

