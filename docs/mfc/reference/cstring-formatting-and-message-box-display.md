---
title: CString の書式指定とメッセージ ボックスの表示
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
ms.openlocfilehash: ad880c5302fd2274c5d46719e912461fd7497f10
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79426517"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString の書式指定とメッセージ ボックスの表示

`CString` オブジェクトを書式設定および解析するための多くの関数が用意されています。 これらの関数は、`CString` オブジェクトを操作する必要がある場合は常に使用できますが、メッセージボックスのテキストに表示される文字列を書式設定する場合に特に便利です。

この一連の関数には、メッセージボックスを表示するためのグローバルルーチンも含まれています。

### <a name="cstring-functions"></a>CString 関数

|||
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|指定されたソース文字列の1つの文字で区切られた部分文字列を抽出します。|
|[AfxFormatString1](#afxformatstring1)|文字列テーブルに含まれる文字列内の書式文字 "%1" に対して、指定された文字列を置換します。|
|[AfxFormatString2](#afxformatstring2)|文字列テーブルに格納されている文字列の書式文字 "%1" と "%2" の2つの文字列を置換します。|
|[AfxMessageBox](#afxmessagebox)|メッセージ ボックスを表示します。|

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxextractsubstring"></a>AfxExtractSubString

このグローバル関数は、指定されたソース文字列から部分文字列を抽出するために使用できます。

```
BOOL AFXAPI AfxExtractSubString (
    CString& rString,
    LPCTSTR lpszFullString,
    int iSubString,
    TCHAR chSep  = '\n');
```

### <a name="parameters"></a>パラメーター

*rString*<br/>
個々の部分文字列を受け取る[CString](../../atl-mfc-shared/using-cstring.md)オブジェクトへの参照。

*lpszFullString*<br/>
抽出元の文字列の完全なテキストを含む文字列。

*iSubString*<br/>
*Lpszfullstring*から抽出する部分文字列の0から始まるインデックス。

*chSep*<br/>
部分文字列を区切るために使用する区切り記号。

### <a name="return-value"></a>戻り値

関数が、指定されたインデックス位置にある部分文字列を正常に抽出した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数は、既知の1文字が各部分文字列を区切るときに、ソース文字列から複数の部分文字列を抽出する場合に便利です。 この関数は、呼び出されるたびに、 *Lpszfullstring*パラメーターの先頭から検索します。

この関数は、 *lpszfullstring*が NULL に設定されているか、指定された区切り記号文字の*isubstring*と1回の出現を検出せずに、関数が*lpszfullstring*の末尾に到達した場合に FALSE を返します。 *Lpszfullstring*が NULL に設定されている場合、 *rstring*パラメーターは元の値から変更されません。それ以外の場合、指定されたインデックスの部分文字列を抽出できなかった場合は、 *rstring*パラメーターに空の文字列が設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxformatstring1"></a>AfxFormatString1

*Lpsz1*が指す文字列を、 *nIDS*によって識別されるテンプレート文字列リソース内の文字 "%1" のすべてのインスタンスに置き換えます。

```
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>パラメーター

*rString*<br/>
置換が実行された後に結果の文字列を格納する `CString` オブジェクトへの参照。

*nIDS*<br/>
置換が実行されるテンプレート文字列のリソース ID。

*lpsz1*<br/>
テンプレート文字列の書式文字 "%1" を置換する文字列。

### <a name="remarks"></a>解説

新しく形成された文字列は*rstring*に格納されます。 たとえば、文字列テーブル内の文字列が "ファイル %1 が見つかりません" で、 *lpsz1*が "C:\MYFILE. と等しい場合などです。TXT ",、 *Rstring*に" File C:\MYFILE. "という文字列が含まれています。TXT が見つかりませんでした。 この関数は、メッセージボックスやその他のウィンドウに送信される文字列を書式設定する場合に便利です。

書式文字 "%1" が文字列に複数回出現する場合は、複数の置換が行われます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxformatstring2"></a>AfxFormatString2

*Lpsz1*が指す文字列を、文字 "%1" のすべてのインスタンス、および*lpsz2*が指す文字列を、 *nIDS*で識別されるテンプレート文字列リソースの文字 "%2" のすべてのインスタンスに置き換えます。

```
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>パラメーター

*rString*<br/>
置換が実行された後に結果の文字列を格納する `CString` への参照。

*nIDS*<br/>
置換が実行されるテンプレート文字列の文字列テーブル ID。

*lpsz1*<br/>
テンプレート文字列の書式文字 "%1" を置換する文字列。

*lpsz2*<br/>
テンプレート文字列の書式文字 "%2" を置換する文字列。

### <a name="remarks"></a>解説

新しく形成された文字列は*rstring*に格納されます。 たとえば、文字列テーブルの文字列が "ファイル %1 がディレクトリ %2 に見つかりません" である場合、 *lpsz1*は "MYFILE" を指します。TXT ", and *lpsz2*は" C:\MYDIR "を指し、 *rstring*には" File MYFILE "という文字列が含まれます。TXT がディレクトリ C:\MYDIR に見つかりませんでした。 "

書式文字 "%1" または "%2" が文字列に複数回出現する場合は、複数の置換が行われます。 数字の順序で指定する必要はありません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

##  <a name="afxmessagebox"></a>AfxMessageBox

画面にメッセージ ボックスを表示します。

```
int AfxMessageBox(
    LPCTSTR lpszText,
    UINT nType = MB_OK,
    UINT nIDHelp = 0);

int AFXAPI AfxMessageBox(
    UINT nIDPrompt,
    UINT nType = MB_OK,
    UINT nIDHelp = (UINT) -1);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
`CString` オブジェクト、またはメッセージ ボックスに表示されるメッセージを含む null で終了する文字列をポイントします。

*nType*<br/>
メッセージ ボックスのスタイル。 ボックスに任意の[メッセージボックススタイル](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)を適用します。

*nIDHelp*<br/>
メッセージのヘルプ コンテキスト ID。0 は、アプリケーションの既定のヘルプ コンテキストが使用されることを示します。

*nIDPrompt*<br/>
文字列テーブル内の文字列の参照に使用される一意の ID。

### <a name="return-value"></a>戻り値

メッセージ ボックスを表示する十分なメモリがない場合は 0。それ以外の場合、次のいずれかの値が返されます。

- IDABORT [中止] ボタンが選択されました。

- IDCANCEL [キャンセル] ボタンが選択されました。

- IDIGNORE [無視] ボタンが選択されました。

- IDNO ボタンが選択されました。

- IDOK [OK] ボタンが選択されました。

- IDRETRY [再試行] ボタンが選択されました。

- IDYES [はい] ボタンが選択されました。

メッセージ ボックスに [キャンセル] ボタンがある場合、Esc キーが押されるか、または [キャンセル] ボタンが選択されると、IDCANCEL 値が返されます。 メッセージ ボックスに [キャンセル] ボタンがない場合、Esc キーを押しても効果はありません。

[AfxFormatString1](#afxformatstring1)および[AfxFormatString2](#afxformatstring2)関数は、メッセージボックスに表示されるテキストの書式を設定するときに役立ちます。

### <a name="remarks"></a>解説

このオーバーロードされた関数の最初の形式では、メッセージボックスで*lpszText*が指すテキスト文字列を表示し、 *nIDHelp*を使用してヘルプコンテキストを記述します。 ヘルプ コンテキストは、ユーザーがヘルプ キー (通常は F1 キー) を押したときに関連するヘルプ トピックにジャンプするために使用されます。

関数の2番目の形式では、ID *nIDPrompt*の文字列リソースを使用して、メッセージボックスにメッセージを表示します。 関連付けられているヘルプページは、 *nIDHelp*の値を使用して検出されます。 *NIDHelp*の既定値 (-1) が使用されている場合は、ヘルプコンテキストに対して文字列リソース ID *nIDPrompt*が使用されます。 ヘルプコンテキストの定義の詳細については、「[テクニカルノート 28](../../mfc/tn028-context-sensitive-help-support.md)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>参照

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)
