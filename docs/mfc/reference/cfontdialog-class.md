---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
ms.openlocfilehash: 6a8e24b68f377235c1f1e21fbcd5618aebbe299a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81755019"
---
# <a name="cfontdialog-class"></a>クラス

フォント選択ダイアログ ボックスをアプリケーションに組み込むことができます。

## <a name="syntax"></a>構文

```
class CFontDialog : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ::Cフォントダイアログ](#cfontdialog)|`CFontDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の値を:Dします。](#domodal)|ダイアログを表示し、ユーザーが選択できるようにします。|
|[ダイアログ::取得文字形式](#getcharformat)|選択したフォントの文字書式を取得します。|
|[次の項目を使用します。](#getcolor)|選択したフォントの色を返します。|
|[次のフォントを使用します。](#getcurrentfont)|現在選択されているフォントの特性を構造体に`LOGFONT`割り当てます。|
|[ダイアログ::ゲットフェイスネーム](#getfacename)|選択したフォントのフェイス名を返します。|
|[次の文字列を取得します。](#getsize)|選択したフォントのポイント サイズを返します。|
|[ダイアログボックス::スタイル名を取得します。](#getstylename)|選択したフォントのスタイル名を返します。|
|[Cフォントダイアログ::ゲットウェイト](#getweight)|選択したフォントの太さを返します。|
|[ダイアログ::イズボルト](#isbold)|フォントが太字かどうかを判断します。|
|[ダイアログ::イズイタリック](#isitalic)|フォントが斜体かどうかを判断します。|
|[Cフォントダイアログ::イズストライクアウト](#isstrikeout)|取り消しと共にフォントを表示するかどうかを指定します。|
|[Cフォントダイアログ::イズアンダーライン](#isunderline)|フォントに下線を引くかどうかを判断します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ダイアログ:m_cf](#m_cf)|オブジェクトをカスタマイズするために使用する`CFontDialog`構造体。|

## <a name="remarks"></a>解説

オブジェクト`CFontDialog`は、システムに現在インストールされているフォントのリストを含むダイアログボックスです。 ユーザーは一覧から特定のフォントを選択でき、この選択はアプリケーションに報告されます。

オブジェクトを`CFontDialog`構築するには、指定されたコンストラクターを使用するか、新しいサブクラスを派生させ、独自のカスタム コンストラクターを使用します。

オブジェクトを`CFontDialog`構築したら、この構造体を`m_cf`使用してダイアログ ボックス内のコントロールの値または状態を初期化できます。 [m_cf](#m_cf)構造は、タイプが[CHOOSEFONT です](/windows/win32/api/commdlg/ns-commdlg-choosefontw)。 この構造体の詳細については、Windows SDK を参照してください。

ダイアログ オブジェクトのコントロールを初期化した後、メンバー関数`DoModal`を呼び出してダイアログ ボックスを表示し、ユーザーがフォントを選択できるようにします。 `DoModal`は、ユーザーが OK (IDOK) ボタンまたはキャンセル (IDCANCEL) ボタンを選択したかどうかを返します。

IDOK を返す場合`DoModal`は、メンバー`CFontDialog`関数の 1 つを使用して、ユーザーが入力した情報を取得できます。

Windows [CommDlgExtendedError](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror)関数を使用して、ダイアログ ボックスの初期化中にエラーが発生したかどうかを確認し、エラーの詳細を確認できます。 この関数の詳細については、Windows SDK を参照してください。

`CFontDialog`は、COMMDLG に依存します。Windows バージョン 3.1 以降に付属の DLL ファイル。

ダイアログ ボックスをカスタマイズするには、 から`CFontDialog`クラスを派生させるカスタム ダイアログ テンプレートを提供し、拡張コントロールからの通知メッセージを処理するメッセージ マップを追加します。 未処理のメッセージは、基本クラスに渡す必要があります。

フック機能のカスタマイズは不要です。

の詳細`CFontDialog`については、「 コモン[ダイアログ クラス](../../mfc/common-dialog-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFontDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="cfontdialogcfontdialog"></a><a name="cfontdialog"></a>ダイアログ::Cフォントダイアログ

`CFontDialog` オブジェクトを構築します。

```
CFontDialog(
    LPLOGFONT lplfInitial = NULL,
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,
    DWORD dwFlags = CF_SCREENFONTS,
    CDC* pdcPrinter = NULL,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*初期値を指定します。*<br/>
フォントの特性の一部を設定できる[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)データ構造体へのポインター。

*Charformat*<br/>
リッチ エディット コントロールでフォントの特性の一部を設定できる[CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata)データ構造体へのポインター。

*dwFlags*<br/>
1 つ以上のフォント選択フラグを指定します。 ビットごとの OR 演算子を使用して、1 つ以上の事前設定値を組み合わせることができます。 `m_cf.Flag`s 構造体メンバーを変更する場合は、変更内容でビットごとの OR 演算子を使用して、既定の動作をそのままにします。 これらの各フラグの詳細については、Windows SDK の[CHOOSEFONT](/windows/win32/api/commdlg/ns-commdlg-choosefontw)構造体の説明を参照してください。

*pdc プリンター*<br/>
プリンター デバイス コンテキストへのポインター。 指定すると、このパラメーターはフォントが選択されるプリンターのプリンター デバイス コンテキストを指します。

*pParentWnd*<br/>
フォント ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。

### <a name="remarks"></a>解説

`CHOOSEFONT` 構造体のメンバーはコンストラクターによって自動的に入力されることに注意してください。 既定とは異なるフォント ダイアログが必要な場合にのみ、これらを変更する必要があります。

> [!NOTE]
> この関数の最初のバージョンは、リッチ エディット コントロールのサポートがない場合にのみ存在します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]

## <a name="cfontdialogdomodal"></a><a name="domodal"></a>次の値を:Dします。

この関数を呼び出して、Windows の共通フォント ダイアログ ボックスを表示し、ユーザーがフォントを選択できるようにします。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

IDOK または ID キャンセル。 IDCANCEL が返された場合は、エラーが発生したかどうかを判断するのには関数[を](/windows/win32/api/commdlg/nf-commdlg-commdlgextendederror)呼び出します。

IDOK と IDCANCEL は、ユーザーが [OK] または [キャンセル] ボタンを選択したかどうかを示す定数です。

### <a name="remarks"></a>解説

[m_cf](#m_cf)構造体のメンバを設定してさまざまなフォント ダイアログ コントロールを初期化する場合は、ダイアログ オブジェクトを構築`DoModal`した後で呼び出す前に、この操作を行う必要があります。

IDOK が返された場合`DoModal`は、他のメンバー関数を呼び出して、ユーザーが入力した設定または情報をダイアログ ボックスに取得できます。

### <a name="example"></a>例

  の例を参照してください[: :C フォントダイアログ](#cfontdialog)と[C フォントダイアログ::GetColor](#getcolor).

## <a name="cfontdialoggetcharformat"></a><a name="getcharformat"></a>ダイアログ::取得文字形式

選択したフォントの文字書式を取得します。

```cpp
void GetCharFormat(CHARFORMAT& cf) const;
```

### <a name="parameters"></a>パラメーター

*Cf*<br/>
選択したフォントの文字書式に関する情報を含む[CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata)構造体。

## <a name="cfontdialoggetcolor"></a><a name="getcolor"></a>次の項目を使用します。

選択したフォントの色を取得します。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>戻り値

選択したフォントの色。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]

## <a name="cfontdialoggetcurrentfont"></a><a name="getcurrentfont"></a>次のフォントを使用します。

現在選択されているフォントの特性を[LOGFONT](/windows/win32/api/wingdi/ns-wingdi-logfontw)構造体のメンバーに割り当てます。

```cpp
void GetCurrentFont(LPLOGFONT lplf);
```

### <a name="parameters"></a>パラメーター

*lplf*<br/>
`LOGFONT`構造体へのポインター。

### <a name="remarks"></a>解説

他`CFontDialog`のメンバー関数は、現在のフォントの個々の特性にアクセスするために提供されます。

[DoModal](#domodal)の呼び出し中にこの関数が呼び出されると、その時点での現在の選択項目 (ユーザーがダイアログで表示または変更したもの) が返されます。 この関数が呼び出しの後`DoModal`に呼び`DoModal`出された場合 (IDOK を返す場合のみ)、ユーザーが実際に選択した内容を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]

## <a name="cfontdialoggetfacename"></a><a name="getfacename"></a>ダイアログ::ゲットフェイスネーム

選択したフォントの顔名を取得します。

```
CString GetFaceName() const;
```

### <a name="return-value"></a>戻り値

ダイアログ ボックスで選択したフォントの名前`CFontDialog`。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]

## <a name="cfontdialoggetsize"></a><a name="getsize"></a>次の文字列を取得します。

選択したフォントのサイズを取得します。

```
int GetSize() const;
```

### <a name="return-value"></a>戻り値

フォントのサイズを 10 分の 1 ポイントで指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]

## <a name="cfontdialoggetstylename"></a><a name="getstylename"></a>ダイアログボックス::スタイル名を取得します。

選択したフォントのスタイル名を取得します。

```
CString GetStyleName() const;
```

### <a name="return-value"></a>戻り値

フォントのスタイル名。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]

## <a name="cfontdialoggetweight"></a><a name="getweight"></a>Cフォントダイアログ::ゲットウェイト

選択したフォントの太さを取得します。

```
int GetWeight() const;
```

### <a name="return-value"></a>戻り値

選択したフォントの太さ。

### <a name="remarks"></a>解説

フォントの太さの詳細については、「 [CFont::CreateFont](../../mfc/reference/cfont-class.md#createfont)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]

## <a name="cfontdialogisbold"></a><a name="isbold"></a>ダイアログ::イズボルト

選択したフォントが太字かどうかを調べます。

```
BOOL IsBold() const;
```

### <a name="return-value"></a>戻り値

選択したフォントで太字の特性が有効になっている場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]

## <a name="cfontdialogisitalic"></a><a name="isitalic"></a>ダイアログ::イズイタリック

選択したフォントが斜体かどうかを調べます。

```
BOOL IsItalic() const;
```

### <a name="return-value"></a>戻り値

選択したフォントで斜体特性が有効になっている場合は 0 以外。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]

## <a name="cfontdialogisstrikeout"></a><a name="isstrikeout"></a>Cフォントダイアログ::イズストライクアウト

選択したフォントが取り消しで表示されるかどうかを調べます。

```
BOOL IsStrikeOut() const;
```

### <a name="return-value"></a>戻り値

選択したフォントで取り消しの特性が有効になっている場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]

## <a name="cfontdialogisunderline"></a><a name="isunderline"></a>Cフォントダイアログ::イズアンダーライン

選択したフォントに下線が付いているかどうかを調べます。

```
BOOL IsUnderline() const;
```

### <a name="return-value"></a>戻り値

選択したフォントで下線特性が有効になっている場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]

## <a name="cfontdialogm_cf"></a><a name="m_cf"></a>ダイアログ:m_cf

メンバがダイアログ オブジェクトの特性を格納する構造体。

```
CHOOSEFONT m_cf;
```

### <a name="remarks"></a>解説

オブジェクトを`CFontDialog`作成した後、メンバ関数`m_cf`を呼び出す前にダイアログ ボックスのさまざまな側面`DoModal`を変更できます。 この構造体の詳細については、Windows SDK の[「フォントの選択](/windows/win32/api/commdlg/ns-commdlg-choosefontw)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
