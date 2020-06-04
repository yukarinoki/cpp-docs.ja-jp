---
title: CString の書式指定とメッセージ ボックスの表示
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
ms.openlocfilehash: fa1fe8826543834872de5257a0f5d56b2ad9fc1c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752674"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString の書式指定とメッセージ ボックスの表示

オブジェクトのフォーマットと解析`CString`には、いくつかの関数が用意されています。 これらの関数は、オブジェクトを操作`CString`する必要がある場合はいつでも使用できますが、メッセージ ボックス テキストに表示される文字列の書式設定に特に役立ちます。

この関数のグループには、メッセージ ボックスを表示するためのグローバル ルーチンも含まれています。

### <a name="cstring-functions"></a>C文字列関数

|||
|-|-|
|[AfxExtractSubString](#afxextractsubstring)|指定されたソース文字列から 1 文字で区切られた部分文字列を抽出します。|
|[AfxFormatString1](#afxformatstring1)|文字列テーブルに含まれる文字列の書式指定文字列 "%1" を指定します。|
|[AfxFormatString2](#afxformatstring2)|文字列テーブルに含まれる文字列の書式指定文字 "%1" と "%2" の 2 つの文字列を置換します。|
|[AfxMessageBox](#afxmessagebox)|メッセージ ボックスを表示します。|

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxextractsubstring"></a><a name="afxextractsubstring"></a>サブストリング

このグローバル関数を使用して、指定されたソース文字列から部分文字列を抽出できます。

```
BOOL AFXAPI AfxExtractSubString (
    CString& rString,
    LPCTSTR lpszFullString,
    int iSubString,
    TCHAR chSep  = '\n');
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
個々の部分文字列を受け取る[CString](../../atl-mfc-shared/using-cstring.md)オブジェクトへの参照。

*文字列を指定します。*<br/>
抽出元の文字列の全文を含む文字列。

*をクリックします。*<br/>
*lpszFullString*から抽出する部分文字列の 0 から始まるインデックス。

*chSep*<br/>
部分文字列を区切るために使用する区切り文字。

### <a name="return-value"></a>戻り値

関数が指定されたインデックスの部分文字列を正常に抽出した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

この関数は、既知の 1 文字が各部分文字列を区切るときに、ソース文字列から複数の部分文字列を抽出する場合に便利です。 この関数は、呼び出されるたびに*lpszFullString*パラメーターの先頭から検索します。

この関数は、指定された区切り文字の*iSubString*+1 オカレンスを見つけずに *、lpszFullString*が NULL に設定されているか、関数が*lpszFullString*の末尾に達した場合に、FALSE を返します。 *lpszFullString*が NULL に設定されている場合 *、rString*パラメーターは元の値から変更されません。それ以外の場合、指定されたインデックスの部分文字列を抽出できなかった場合は *、rString*パラメーターが空の文字列に設定されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxformatstring1"></a><a name="afxformatstring1"></a>1 の文字列

*nIDS*で識別されるテンプレート文字列リソース内の文字 "%1" のインスタンスに対して *、lpsz1*が指す文字列を置き換えます。

```cpp
void  AfxFormatString1(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
置換の実行後`CString`に、結果の文字列を格納するオブジェクトへの参照。

*国際*<br/>
置換を実行するテンプレート文字列のリソース ID。

*lpsz1*<br/>
テンプレート文字列の書式指定文字 "%1" を置き換える文字列。

### <a name="remarks"></a>解説

新しく作成された文字列は*rString*に格納されます。 たとえば、文字列テーブルの文字列が "ファイル %1 が見つかりません" で *、lpsz1*が "C:\MYFILE" と等しい場合です。TXT」、次に *、rString*は文字列 "ファイル C:\MYFILE を含みます。TXT が見つかりません。 この関数は、メッセージ ボックスや他のウィンドウに送信される文字列を書式設定する場合に便利です。

文字列内に書式指定文字 "%1" が複数回出現すると、複数の置換が行われます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxformatstring2"></a><a name="afxformatstring2"></a>2018年12月11日

文字 "%1" のインスタンスに対して*lpsz1*によって指す文字列 *、nIDS*で識別されるテンプレート文字列リソース内の文字 "%2" のインスタンスに対して*lpsz2*が指す文字列を置き換えます。

```cpp
void AfxFormatString2(
    CString& rString,
    UINT nIDS,
    LPCTSTR lpsz1,
    LPCTSTR lpsz2);
```

### <a name="parameters"></a>パラメーター

*文字列*<br/>
置換`CString`の実行後に、結果の文字列を含む を参照します。

*国際*<br/>
置換を実行するテンプレート文字列の文字列テーブル ID。

*lpsz1*<br/>
テンプレート文字列の書式指定文字 "%1" を置き換える文字列。

*lpsz2*<br/>
テンプレート文字列の書式指定文字 "%2" を置き換える文字列。

### <a name="remarks"></a>解説

新しく作成された文字列は*rString*に格納されます。 たとえば、文字列テーブルの文字列が "ファイル %1 がディレクトリ %2 に見つかりません" の場合 *、lpsz1*は "MYFILE.TXT」と *、lpsz2*が"C:\MYDIR"を指し示すと *、rString*には文字列"ファイルMYFILE"が含まれます。ディレクトリ C:\MYDIR に TXT が見つかりません"

文字列内に "%1" または "%2" という書式が複数回出現すると、複数の置換が行われます。 数値の順序である必要はありません。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]

### <a name="requirements"></a>必要条件

  **ヘッダー** afxwin.h

## <a name="afxmessagebox"></a><a name="afxmessagebox"></a>Afx メッセージ ボックス

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
メッセージ ボックスのスタイル。 メッセージ ボックスの[スタイル](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)をボックスに適用します。

*ヘルプ*<br/>
メッセージのヘルプ コンテキスト ID。0 は、アプリケーションの既定のヘルプ コンテキストが使用されることを示します。

*プロンプトを表示します。*<br/>
文字列テーブル内の文字列の参照に使用される一意の ID。

### <a name="return-value"></a>戻り値

メッセージ ボックスを表示する十分なメモリがない場合は 0。それ以外の場合、次のいずれかの値が返されます。

- [中止] ボタンが選択されました。

- IDCANCEL キャンセルボタンが選択されました。

- IDIGNORE 無視ボタンが選択されました。

- IDNO [いいえ] ボタンが選択されました。

- IDOK [OK] ボタンが選択されました。

- IDRETRY 再試行ボタンが選択されました。

- IDYES [はい] ボタンが選択されました。

メッセージ ボックスに [キャンセル] ボタンがある場合、Esc キーが押されるか、または [キャンセル] ボタンが選択されると、IDCANCEL 値が返されます。 メッセージ ボックスに [キャンセル] ボタンがない場合、Esc キーを押しても効果はありません。

関数[AfxFormatString1](#afxformatstring1)と[AfxFormatString2](#afxformatstring2)は、メッセージ ボックスに表示されるテキストの書式設定に役立ちます。

### <a name="remarks"></a>解説

このオーバーロード関数の最初の形式では、メッセージ ボックスに*lpszText*が指すテキスト文字列が表示され *、nIDHelp*を使用してヘルプ コンテキストを記述します。 ヘルプ コンテキストは、ユーザーがヘルプ キー (通常は F1 キー) を押したときに関連するヘルプ トピックにジャンプするために使用されます。

2 番目の形式の関数では、id *nIDPrompt*を持つ文字列リソースを使用してメッセージ ボックスにメッセージを表示します。 関連付けられたヘルプ ページは *、 nIDHelp*の値を通して見つかります。 *nIDHelp*の既定値が使用されている場合 (-1)、文字列リソース ID *nIDPrompt*がヘルプ コンテキストに使用されます。 ヘルプ コンテキストの定義の詳細については、テクニカル[ノート 28](../../mfc/tn028-context-sensitive-help-support.md)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]

## <a name="see-also"></a>関連項目

[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)<br/>
[CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)
