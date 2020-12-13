---
description: '詳細情報: CColorDialog クラス'
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
ms.openlocfilehash: d9af49d4986f0619211ed4fd2dc9174acea27d0c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150138"
---
# <a name="ccolordialog-class"></a>CColorDialog クラス

色の選択ダイアログボックスをアプリケーションに組み込むことができます。

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
|[CColorDialog::D oModal](#domodal)|色のダイアログボックスを表示し、ユーザーが選択できるようにします。|
|[CColorDialog:: GetColor](#getcolor)|`COLORREF`選択された色の値を格納している構造体を返します。|
|[CColorDialog:: GetSavedCustomColors](#getsavedcustomcolors)|ユーザーが作成したカスタム色を取得します。|
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|現在の色の選択を指定した色にします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CColorDialog:: OnColorOK](#oncolorok)|ダイアログボックスに入力された色を検証するには、をオーバーライドします。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CColorDialog:: m_cc](#m_cc)|ダイアログボックスの設定をカスタマイズするために使用される構造体。|

## <a name="remarks"></a>解説

`CColorDialog`オブジェクトは、表示システムに対して定義されている色の一覧を含むダイアログボックスです。 ユーザーは、リストから特定の色を選択または作成できます。これは、ダイアログボックスが終了したときにアプリケーションに戻されます。

オブジェクトを構築するに `CColorDialog` は、指定されたコンストラクターを使用するか、新しいクラスを派生させ、独自のカスタムコンストラクターを使用します。

ダイアログボックスが構築されたら、 [m_cc](#m_cc) 構造体の任意の値を設定または変更して、ダイアログボックスのコントロールの値を初期化できます。 *M_cc* 構造体の型は [CHOOSECOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora-r1)です。

ダイアログボックスのコントロールを初期化した後、 `DoModal` メンバー関数を呼び出してダイアログボックスを表示し、ユーザーが色を選択できるようにします。 `DoModal` ダイアログボックスの [OK] (IDOK) または [キャンセル] (IDCANCEL) ボタンのいずれかをユーザーが選択したものを返します。

が `DoModal` IDOK を返す場合は、のメンバー関数のいずれかを使用し `CColorDialog` て、ユーザーが入力した情報を取得できます。

Windows の [Commdlgextendederror](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 関数を使用すると、ダイアログボックスの初期化中にエラーが発生したかどうかを確認し、エラーの詳細を調べることができます。

`CColorDialog` は、Windows バージョン3.1 以降に付属している COMMDLG.DLL ファイルに依存しています。

ダイアログボックスをカスタマイズするには、からクラスを派生させ、 `CColorDialog` カスタムダイアログテンプレートを指定して、拡張コントロールからの通知メッセージを処理するメッセージマップを追加します。 未処理のメッセージは、基本クラスに渡す必要があります。

フック関数のカスタマイズは必要ありません。

> [!NOTE]
> 一部のインストールでは、 `CColorDialog` フレームワークを使用して他のオブジェクトをグレーで表示した場合、オブジェクトはグレーの背景で表示されません `CDialog` 。

の使用方法の詳細につい `CColorDialog` ては、「[コモンダイアログクラス](../../mfc/common-dialog-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CColorDialog`

## <a name="requirements"></a>要件

**ヘッダー:** afxdlgs

## <a name="ccolordialogccolordialog"></a><a name="ccolordialog"></a> CColorDialog::CColorDialog

`CColorDialog` オブジェクトを構築します。

```
CColorDialog(
    COLORREF clrInit = 0,
    DWORD dwFlags = 0,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*clrInit*<br/>
既定の色の選択。 値が指定されていない場合、既定値は RGB (0, 0, 0) (黒) です。

*dwFlags*<br/>
ダイアログボックスの機能と外観をカスタマイズするフラグのセット。 詳細については、Windows SDK の [CHOOSECOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora-r1) 構造体を参照してください。

*pParentWnd*<br/>
ダイアログボックスの親またはオーナーウィンドウへのポインター。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]

## <a name="ccolordialogdomodal"></a><a name="domodal"></a> CColorDialog::D oModal

Windows の [共通色] ダイアログボックスを表示し、ユーザーが色を選択できるようにするには、この関数を呼び出します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

IDOK または IDCANCEL。 IDCANCEL が返された場合は、Windows の [Commdlgextendederror](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror) 関数を呼び出して、エラーが発生したかどうかを確認します。

IDOK と IDCANCEL は、ユーザーが [OK] または [キャンセル] ボタンを選択したかどうかを示す定数です。

### <a name="remarks"></a>解説

[M_cc](#m_cc)構造体のメンバーを設定して、さまざまな色のダイアログボックスオプションを初期化する場合は、を呼び出す前に、 `DoModal` ダイアログボックスオブジェクトが構築された後にこの操作を行う必要があります。

を呼び出した後 `DoModal` 、他のメンバー関数を呼び出して、ユーザーがダイアログボックスに入力した設定または情報を取得できます。

### <a name="example"></a>例

  [CColorDialog:: CColorDialog](#ccolordialog)の例を参照してください。

## <a name="ccolordialoggetcolor"></a><a name="getcolor"></a> CColorDialog:: GetColor

を呼び出した後 `DoModal` に、ユーザーが選択した色に関する情報を取得するために、この関数を呼び出します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

[色] ダイアログボックスで選択した色の RGB 情報を含む [COLORREF](/windows/win32/gdi/colorref) 値。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]

## <a name="ccolordialoggetsavedcustomcolors"></a><a name="getsavedcustomcolors"></a> CColorDialog:: GetSavedCustomColors

`CColorDialog` オブジェクトを選択すると、ユーザーは色を選択するだけでなく、最大16個のカスタムカラーを定義できます。

```
static COLORREF* PASCAL GetSavedCustomColors();
```

### <a name="return-value"></a>戻り値

ユーザーが作成したカスタム色を格納する16色の RGB カラー値の配列へのポインター。

### <a name="remarks"></a>解説

`GetSavedCustomColors`このメンバー関数は、これらの色へのアクセスを提供します。 これらの色は、 [DoModal](#domodal) から IDOK が返された後に取得できます。

返された配列内の16の RGB 値はそれぞれ、RGB (255255255) (白) に初期化されます。 ユーザーが選択したユーザー設定の色は、アプリケーション内のダイアログボックスの呼び出しの間にのみ保存されます。 アプリケーションの呼び出しの間にこれらの色を保存する場合は、初期化 () など、他の方法で保存する必要があります。INI) ファイル。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]

## <a name="ccolordialogm_cc"></a><a name="m_cc"></a> CColorDialog:: m_cc

ダイアログボックスの特性と値を格納するメンバーを持つ、 [CHOOSECOLOR](/windows/win32/api/commdlg/ns-commdlg-choosecolora-r1)型の構造体。

```
CHOOSECOLOR m_cc;
```

### <a name="remarks"></a>解説

オブジェクトを構築した後 `CColorDialog` 、 *m_cc* を使用して、 [DoModal](#domodal) メンバー関数を呼び出す前にダイアログボックスのさまざまな側面を設定できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]

## <a name="ccolordialogoncolorok"></a><a name="oncolorok"></a> CColorDialog:: OnColorOK

ダイアログボックスに入力された色を検証するには、をオーバーライドします。

```
virtual BOOL OnColorOK();
```

### <a name="return-value"></a>戻り値

ダイアログボックスを閉じない場合は0以外の。それ以外の場合は、0を指定すると、入力された色が受け入れられます。

### <a name="remarks"></a>解説

[色] ダイアログボックスでユーザーが選択した色のカスタム検証を提供する場合にのみ、この関数をオーバーライドします。

ユーザーは、次の2つの方法のいずれかで色を選択できます。

- カラーパレットの色をクリックします。 選択した色の RGB 値が、適切な RGB 編集ボックスに反映されます。

- RGB 編集ボックスに値を入力する

上書き `OnColorOK` を使用すると、アプリケーション固有の理由により、ユーザーが一般的な色のダイアログボックスに入力した色を拒否することができます。

通常、この関数を使用する必要はありません。これは、フレームワークによって色の既定の検証が提供され、無効な色が入力された場合にメッセージボックスが表示されるためです。

内から [SetCurrentColor](#setcurrentcolor) を呼び出して `OnColorOK` 、色の選択を強制することができます。 `OnColorOK`が起動した (つまり、ユーザーが **[OK]** をクリックして色の変更を受け入れる) と、 [getcolor](#getcolor)を呼び出して新しい色の RGB 値を取得できます。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]

## <a name="ccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a> CColorDialog::SetCurrentColor

を呼び出した後 `DoModal` に、この関数を呼び出して、現在の色の選択を *clr* で指定された色の値に強制的に適用します。

```cpp
void SetCurrentColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

<bpt id="p1">*</bpt>clr<ept id="p1">*</ept><br/>
RGB カラー値。

### <a name="remarks"></a>解説

この関数は、メッセージハンドラーまたは内から呼び出され `OnColorOK` ます。 ダイアログボックスによって、 *clr* パラメーターの値に基づいてユーザーの選択が自動的に更新されます。

### <a name="example"></a>例

  [CColorDialog:: OnColorOK](#oncolorok)の例を参照してください。

## <a name="see-also"></a>関連項目

[MFC のサンプル MDI](../../overview/visual-cpp-samples.md)<br/>
[MFC のサンプル DRAWCLI](../../overview/visual-cpp-samples.md)<br/>
[CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
