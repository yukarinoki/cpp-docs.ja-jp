---
title: クラスを検索します。
ms.date: 11/04/2016
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
ms.openlocfilehash: 7a12d0520d070d74afd9fa91e828970d14c82700
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373855"
---
# <a name="cfindreplacedialog-class"></a>クラスを検索します。

アプリケーションに標準の文字列の検索/置換ダイアログ ボックスを実装できます。

## <a name="syntax"></a>構文

```
class CFindReplaceDialog : public CCommonDialog
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[置換ダイアログを検索します。](#cfindreplacedialog)|`CFindReplaceDialog`オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[置換ダイアログ::作成](#create)|ダイアログ ボックスを`CFindReplaceDialog`作成して表示します。|
|[次を検索ダイアログ::次を検索します。](#findnext)|ユーザーが次に検索する検索文字列を検索するかどうかを調べます。|
|[置換ダイアログ::文字列を検索します。](#getfindstring)|現在の検索文字列を取得します。|
|[置換ダイアログを検索します。](#getnotifier)|登録されたメッセージ ハンドラーの`FINDREPLACE`構造体を取得します。|
|[置換ダイアログ::文字列を置換します。](#getreplacestring)|現在の置換文字列を取得します。|
|[置換ダイアログを検索::終了](#isterminating)|ダイアログ ボックスが終了しているかどうかを調べます。|
|[置換ダイアログを検索::マッチケース](#matchcase)|ユーザーが検索文字列の大文字と小文字を正確に一致させるかどうかを調べます。|
|[置換ダイアログ::マッチホールワード](#matchwholeword)|ユーザーが単語全体を一致させるかどうかを調べます。|
|[置換ダイアログ::すべて置換](#replaceall)|ユーザーが文字列のすべての出現を置換するかどうかを調べます。|
|[置換ダイアログ::現在の置換](#replacecurrent)|現在の単語を置換するかどうかを確認します。|
|[検索置換ダイアログ::検索ダウン](#searchdown)|ユーザーが検索を下方向に進めるかどうかを判断します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[置換ダイアログ::m_fr](#m_fr)|オブジェクトをカスタマイズするために使用する`CFindReplaceDialog`構造体。|

## <a name="remarks"></a>解説

他の Windows コモン ダイアログ`CFindReplaceDialog`ボックスとは異なり、オブジェクトはモードレスで、ユーザーは画面上で他のウィンドウと対話できます。 オブジェクトには、[検索]`CFindReplaceDialog`ダイアログ ボックスと [検索/置換] ダイアログ ボックスの 2 種類があります。 ダイアログ ボックスでは、検索文字列の入力と検索/置換を行うことができますが、検索や置換のいずれの機能も実行しません。 これらをアプリケーションに追加する必要があります。

オブジェクトを`CFindReplaceDialog`構築するには、指定されたコンストラクタ (引数を持たない) を使用します。 これはモードレス ダイアログ ボックスなので、スタックではなく**new**演算子を使用して、ヒープ上にオブジェクトを割り当てます。

オブジェクトが`CFindReplaceDialog`作成されたら[、Create](#create)メンバー関数を呼び出してダイアログ ボックスを作成および表示する必要があります。

[m_fr構造体](#m_fr)を使用して、 を呼び出`Create`す前にダイアログ ボックスを初期化します。 構造体`m_fr`の型は[FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew)です。 この構造体の詳細については、Windows SDK を参照してください。

親ウィンドウに検索/置換要求の通知を受け取るには、Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew)関数を使用し、この登録されたメッセージを処理するフレーム ウィンドウで[ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message)メッセージ マップ マクロを使用する必要があります。

ユーザーがメンバ関数を使用してダイアログ ボックスを終了するかどうか決定`IsTerminating`できます。

`CFindReplaceDialog`は、COMMDLG に依存します。Windows バージョン 3.1 以降に付属の DLL ファイル。

ダイアログ ボックスをカスタマイズするには、 から`CFindReplaceDialog`クラスを派生し、カスタム ダイアログ テンプレートを提供し、拡張コントロールからの通知メッセージを処理するメッセージ マップを追加します。 未処理のメッセージは、基本クラスに渡す必要があります。

フック機能のカスタマイズは不要です。

の詳細`CFindReplaceDialog`については、「 コモン[ダイアログ クラス](../../mfc/common-dialog-classes.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CFindReplaceDialog`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdlgs.h

## <a name="cfindreplacedialogcfindreplacedialog"></a><a name="cfindreplacedialog"></a>置換ダイアログを検索します。

`CFindReplaceDialog` オブジェクトを構築します。

```
CFindReplaceDialog();
```

### <a name="remarks"></a>解説

`CFindReplaceDialog`オブジェクトはモードレス ダイアログ ボックスであるため **、new**演算子を使用してヒープ上に構築する必要があります。

破棄中、フレームワークはダイアログ ボックスへのポインター上**で削除を**実行しようとします。 スタック上にダイアログ ボックスを作成した場合 **、this**ポインターは存在せず、未定義の動作が発生する可能性があります。

オブジェクトの`CFindReplaceDialog`構築の詳細については[、「CFindReplaceDialog」の概要を参照](../../mfc/reference/cfindreplacedialog-class.md)してください。 ダイアログ ボックスを表示するには[、CFindReplaceDialog::Create](#create)メンバー関数を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]

## <a name="cfindreplacedialogcreate"></a><a name="create"></a>置換ダイアログ::作成

の値に応じて、[検索] または [検索/置換] ダイアログ`bFindDialogOnly`ボックス オブジェクトを作成して表示します。

```
virtual BOOL Create(
    BOOL bFindDialogOnly,
    LPCTSTR lpszFindWhat,
    LPCTSTR lpszReplaceWith = NULL,
    DWORD dwFlags = FR_DOWN,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>パラメーター

*唯一の情報*<br/>
[**検索**] ダイアログ ボックスを表示するには、このパラメーターを TRUE に設定します。 **[検索/置換**] ダイアログ ボックスを表示するには、FALSE に設定します。

*lpszFind何*<br/>
ダイアログ ボックスが表示されたときの既定の検索文字列へのポインター。 NULL の場合、ダイアログ ボックスには既定の検索文字列は含まれません。

*一緒に置き換える*<br/>
ダイアログ ボックスが表示されたときの既定の置換文字列へのポインター。 NULL の場合、ダイアログ ボックスには既定の置換文字列は含まれません。

*dwFlags*<br/>
ダイアログ ボックスの設定をカスタマイズするために使用できる 1 つ以上のフラグを、ビットごとの OR 演算子を使用して組み合わせます。 デフォルト値はFR_DOWNで、検索を下方向に進めます。 これらのフラグの詳細については、Windows SDK の[FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew)構造体を参照してください。

*pParentWnd*<br/>
ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。 これは、検索/置換アクションが要求されたことを示す特別なメッセージを受け取るウィンドウです。 NULL の場合、アプリケーションのメイン ウィンドウが使用されます。

### <a name="return-value"></a>戻り値

ダイアログ ボックス オブジェクトが正常に作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

親ウィンドウに検索/置換要求が通知されるようにするには、戻り値がアプリケーションのインスタンスに固有のメッセージ番号である Windows [RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew)関数を使用する必要があります。 フレーム ウィンドウには、この登録済みメッセージを処理するコールバック関数 (`OnFindReplace`次の例では) を宣言するメッセージ マップ エントリが必要です。 次のコード例は、という名前のフレーム ウィンドウ クラスに対してこれを`CMyRichEditView`行う方法の例です。

[!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]

[!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]

[!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]

`OnFindReplace`関数内で、ユーザーの意図を解釈するには[、CFindReplaceDialog:::FindNext](#findnext)と[CFindReplaceDialog::IsTerminating](#isterminating)メソッドを使用して、検索/置換操作のコードを作成します。

### <a name="example"></a>例

  次の例[を](#cfindreplacedialog)参照してください。

## <a name="cfindreplacedialogfindnext"></a><a name="findnext"></a>次を検索ダイアログ::次を検索します。

コールバック関数からこの関数を呼び出して、ユーザーが検索文字列の次の出現箇所を検索するかどうかを判断します。

```
BOOL FindNext() const;
```

### <a name="return-value"></a>戻り値

ユーザーが検索文字列の次の出現箇所を検索する場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cfindreplacedialoggetfindstring"></a><a name="getfindstring"></a>置換ダイアログ::文字列を検索します。

コールバック関数からこの関数を呼び出して、検索する既定の文字列を取得します。

```
CString GetFindString() const;
```

### <a name="return-value"></a>戻り値

検索する既定の文字列。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetnotifier"></a><a name="getnotifier"></a>置換ダイアログを検索します。

現在の [置換の検索] ダイアログ ボックスへのポインターを取得します。

```
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

*lParam*<br/>
フレーム ウィンドウの`OnFindReplace`メンバー関数に渡される*lparam*値。

### <a name="return-value"></a>戻り値

現在のダイアログ ボックスへのポインター。

### <a name="remarks"></a>解説

コールバック関数内で使用して、現在のダイアログ ボックスにアクセスし、そのメンバー関数を呼び出`m_fr`し、構造体にアクセスする必要があります。

### <a name="example"></a>例

[置換の検索] ダイアログ ボックスから通知を受け取るために OnFindReplace ハンドラーを登録する方法の例については[、「CFindReplaceDialog::Create」](#create)を参照してください。

[!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]

## <a name="cfindreplacedialoggetreplacestring"></a><a name="getreplacestring"></a>置換ダイアログ::文字列を置換します。

現在の置換文字列を取得します。

```
CString GetReplaceString() const;
```

### <a name="return-value"></a>戻り値

見つかった文字列を置き換える既定の文字列。

### <a name="example"></a>例

  次の例[を](#getfindstring)参照してください。

## <a name="cfindreplacedialogisterminating"></a><a name="isterminating"></a>置換ダイアログを検索::終了

コールバック関数内でこの関数を呼び出して、ユーザーがダイアログ ボックスを終了することを決定したかどうかを確認します。

```
BOOL IsTerminating() const;
```

### <a name="return-value"></a>戻り値

ユーザーがダイアログ ボックスを終了する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数が 0 以外の値を返`DestroyWindow`す場合は、現在のダイアログ ボックスのメンバー関数を呼び出し、ダイアログ ボックスのポインタ変数を NULL に設定する必要があります。 必要に応じて、最後に入力した検索/置換テキストを保存し、それを使用して次の検索/置換ダイアログボックスを初期化することもできます。

### <a name="example"></a>例

  次の例[を](#getfindstring)参照してください。

## <a name="cfindreplacedialogm_fr"></a><a name="m_fr"></a>置換ダイアログ::m_fr

オブジェクトをカスタマイズするために`CFindReplaceDialog`使用します。

```
FINDREPLACE m_fr;
```

### <a name="remarks"></a>解説

`m_fr`は、[型 FINDREPLACE](/windows/win32/api/commdlg/ns-commdlg-findreplacew)の構造体です。 そのメンバーは、ダイアログ ボックス オブジェクトの特性を格納します。 オブジェクトを`CFindReplaceDialog`作成した後で、ダイアログ`m_fr`ボックスのさまざまな値を変更できます。

この構造体の詳細については、Windows SDK`FINDREPLACE`の構造を参照してください。

### <a name="example"></a>例

  次の例[を](#cfindreplacedialog)参照してください。

## <a name="cfindreplacedialogmatchcase"></a><a name="matchcase"></a>置換ダイアログを検索::マッチケース

ユーザーが検索文字列の大文字と小文字を正確に一致させるかどうかを調べます。

```
BOOL MatchCase() const;
```

### <a name="return-value"></a>戻り値

検索文字列の大文字と小文字が正確に一致する検索文字列の出現箇所を検索する場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cfindreplacedialogmatchwholeword"></a><a name="matchwholeword"></a>置換ダイアログ::マッチホールワード

ユーザーが単語全体を一致させるかどうかを調べます。

```
BOOL MatchWholeWord() const;
```

### <a name="return-value"></a>戻り値

検索文字列の単語全体のみを一致させる場合は 0 以外の値を指定します。それ以外の場合は 0。

## <a name="cfindreplacedialogreplaceall"></a><a name="replaceall"></a>置換ダイアログ::すべて置換

ユーザーが文字列のすべての出現を置換するかどうかを調べます。

```
BOOL ReplaceAll() const;
```

### <a name="return-value"></a>戻り値

置換文字列に一致するすべての文字列を置換することをユーザーが要求した場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cfindreplacedialogreplacecurrent"></a><a name="replacecurrent"></a>置換ダイアログ::現在の置換

現在の単語を置換するかどうかを確認します。

```
BOOL ReplaceCurrent() const;
```

### <a name="return-value"></a>戻り値

現在選択されている文字列を置換文字列に置き換える必要がある場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cfindreplacedialogsearchdown"></a><a name="searchdown"></a>検索置換ダイアログ::検索ダウン

ユーザーが検索を下方向に進めるかどうかを判断します。

```
BOOL SearchDown() const;
```

### <a name="return-value"></a>戻り値

ユーザーが下方向に検索を続行する場合は 0 以外の値を指定します。ユーザーが検索を上方向に進める場合は 0。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/ccommondialog-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
