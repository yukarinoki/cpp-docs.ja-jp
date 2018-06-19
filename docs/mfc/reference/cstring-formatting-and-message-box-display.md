---
title: CString の書式指定とメッセージ ボックスの表示 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.strings
dev_langs:
- C++
helpviewer_keywords:
- CString objects [MFC], formatting and message boxes
ms.assetid: d1068cf4-9cc5-4952-b9e7-d612c53cbc28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8074d84d739b59acfa0c6040bedf76f46b6ea9c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375041"
---
# <a name="cstring-formatting-and-message-box-display"></a>CString の書式指定とメッセージ ボックスの表示
関数の数が書式設定および解析する指定された`CString`オブジェクト。 これらの関数を使用するには、操作する必要があるたびに`CString`オブジェクトではなくはメッセージ ボックスのテキストに表示される文字列を書式設定するために特に有用です。  
  
 この関数のグループには、メッセージ ボックスを表示するためのグローバル関数も含まれています。  
  
### <a name="cstring-functions"></a>CString 関数  
  
|||  
|-|-|  
|[AfxExtractSubString](#afxextractsubstring)|指定された文字列から 1 つの文字で区切られた部分文字列を抽出します。|  
|[AfxFormatString1](#afxformatstring1)|文字列テーブルに置換にはした文字列の書式指定文字"%1"の指定した文字列が含まれています。|  
|[AfxFormatString2](#afxformatstring2)|形式の 2 つの代替文字列は、「1%」と"%2"、文字列内の文字列テーブルに格納されている文字します。|  
|[AfxMessageBox](#afxmessagebox)|メッセージ ボックスを表示します。|  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxextractsubstring"></a>  AfxExtractSubString  
 指定された文字列から部分文字列を抽出するため、このグローバル関数を使用できます。  
  
```   
BOOL AFXAPI AfxExtractSubString (
    CString& rString,  
    LPCTSTR lpszFullString,  
    int iSubString,  
    TCHAR chSep  = '\n'); 
```  
  
### <a name="parameters"></a>パラメーター  
 *rString*  
 -   参照、 [CString](../../atl-mfc-shared/using-cstring.md)個々 の部分文字列を受け取るオブジェクト。  
  
 *lpszFullString*  
 -   文字列から抽出するための完全なテキストを含む文字列です。  
  
 *iSubString*  
 -   抽出する部分文字列の 0 から始まるインデックス*lpszFullString*です。  
  
 *chSep*  
 -   区切り文字が部分文字列を区切るために使用します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**関数は、指定されたインデックスにある部分文字列を正常に展開する場合は、それ以外の場合、 **FALSE**です。  
  
### <a name="remarks"></a>コメント  
 この関数は、既知の単一の文字は、各サブ文字列を区切るときに、ソース文字列から複数の部分文字列を抽出するために役立ちます。 この関数は検索の先頭から、`lpszFullString`パラメーターたびに呼び出されます。  
  
 どちらの場合、この関数は FALSE を返しますが`lpszFullString`に設定されている**NULL**関数の末尾に到達または`lpszFullString`検索せず`iSubString`+1 出現する指定した区切り記号のです。 `rString`場合、パラメーターを元の値から変更されませんが`lpszFullString`に設定された**NULL**、それ以外の`rString`部分文字列を抽出できなかった場合、空の文字列にパラメーターが設定されますを指定インデックス。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#48](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_1.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxformatstring1"></a>  AfxFormatString1  
 指す文字列に置換されます`lpsz1`で識別されるテンプレート文字列リソースで文字"%1"のすべてのインスタンスの`nIDS`します。  
  
```  
void  AfxFormatString1(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1); 
```  
  
### <a name="parameters"></a>パラメーター  
 `rString`  
 参照、`CString`置換が実行された後、結果の文字列を格納するオブジェクト。  
  
 `nIDS`  
 置換を実行する、テンプレート文字列のリソース ID です。  
  
 `lpsz1`  
 「1%」は、テンプレート文字列の文字形式で置換される文字列。  
  
### <a name="remarks"></a>コメント  
 新しく生成された文字列が格納されている`rString`です。 たとえば、文字列テーブル内の文字列が「ファイル %1 は見つかりませんでした」と`lpsz1`と等しい"C:\MYFILE です。TXT"、し`rString`文字列"File C:\MYFILE には。TXT が見つかりません。"です。 この関数は、メッセージ ボックスおよびその他のウィンドウに送信される文字列を書式設定するために役立ちます。  
  
 書式指定文字"%1"は文字列で複数回表示される、複数の置き換えが行われます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#25](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_2.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxformatstring2"></a>  AfxFormatString2  
 指す文字列に置換されます`lpsz1`、文字"%1"、およびが指す文字列のすべてのインスタンスの`lpsz2`で識別されるテンプレート文字列リソースの"%2"の文字のすべてのインスタンスの`nIDS`します。  
  
```   
void AfxFormatString2(
    CString& rString,  
    UINT nIDS,  
    LPCTSTR lpsz1,  
    LPCTSTR lpsz2); 
```  
  
### <a name="parameters"></a>パラメーター  
 `rString`  
 参照、`CString`置換が実行された後、結果の文字列が含まれる。  
  
 `nIDS`  
 置換を実行する、テンプレート文字列の文字列テーブルの ID。  
  
 `lpsz1`  
 「1%」は、テンプレート文字列の文字形式で置換される文字列。  
  
 `lpsz2`  
 "%2"は、テンプレート文字列に文字形式で置換される文字列。  
  
### <a name="remarks"></a>コメント  
 新しく生成された文字列が格納されている`rString`です。 たとえば、文字列テーブル内の文字列が「ファイル %1 がディレクトリ %2 に見つかりません」 `lpsz1` "MYFILE 指します。TXT"、および`lpsz2`"C:\MYDIR"が、指す`rString`文字列"File MYFILE には。TXT C:\MYDIR のディレクトリに見つかりませんでした"  
  
 文字"%1"の形式または"%2"は文字列で複数回表示される、複数の置き換えになります。 数値の順序ではありません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#26](../../mfc/codesnippet/cpp/cstring-formatting-and-message-box-display_3.cpp)]  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxwin.h  
  
##  <a name="afxmessagebox"></a>  AfxMessageBox  
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
 `lpszText`  
 `CString` オブジェクト、またはメッセージ ボックスに表示されるメッセージを含む null で終了する文字列をポイントします。  
  
 `nType`  
 メッセージ ボックスのスタイル。 任意の適用、[メッセージ ボックス スタイル](../../mfc/reference/styles-used-by-mfc.md#message-box-styles)をボックスにします。  
  
 `nIDHelp`  
 メッセージのヘルプ コンテキスト ID。0 は、アプリケーションの既定のヘルプ コンテキストが使用されることを示します。  
  
 `nIDPrompt`  
 文字列テーブル内の文字列の参照に使用される一意の ID。  
  
### <a name="return-value"></a>戻り値  
 メッセージ ボックスを表示する十分なメモリがない場合は 0。それ以外の場合、次のいずれかの値が返されます。  
  
- **IDABORT** [中止] ボタンが選択されています。  
  
- **IDCANCEL** キャンセル ボタンが選択されました。  
  
- **IDIGNORE**を無視するボタンが選択されました。  
  
- **IDNO**されませんボタンが選択されました。  
  
- **IDOK** [ok] ボタンが選択されました。  
  
- **IDRETRY** [再試行] ボタンが選択されています。  
  
- **IDYES** [はい] ボタンが選択されました。  
  
 メッセージ ボックスに、[キャンセル] ボタンがある場合、 **IDCANCEL** ESC キーが押されたか、[キャンセル] ボタンが選択されている場合は、値が返されます。 メッセージ ボックスに [キャンセル] ボタンがない場合、Esc キーを押しても効果はありません。  
  
 関数は、 [AfxFormatString1](#afxformatstring1)と[AfxFormatString2](#afxformatstring2)メッセージ ボックスに表示されるテキストの書式設定に役に立ちます。  
  
### <a name="remarks"></a>コメント  
 このオーバーロード関数の最初の形式には、メッセージ ボックスの `lpszText` がポイントする文字列が表示され、`nIDHelp` を使用してヘルプ コンテキストが記述されます。 ヘルプ コンテキストは、ユーザーがヘルプ キー (通常は F1 キー) を押したときに関連するヘルプ トピックにジャンプするために使用されます。  
  
 関数の 2 番目の形式では、ID `nIDPrompt` を持つ文字列リソースを使用してメッセージ ボックスにメッセージが表示されます。 関連するヘルプ ページは、`nIDHelp` の値を使用して検出されます。 場合の既定値`nIDHelp`使用 (-1)、文字列リソースの ID を`nIDPrompt`、ヘルプ コンテキストを使用します。 ヘルプ コンテキストの定義の詳細については、次を参照してください。[テクニカル ノート 28:](../../mfc/tn028-context-sensitive-help-support.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing#133](../../mfc/reference/codesnippet/cpp/cstring-formatting-and-message-box-display_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CStringT クラス](../../atl-mfc-shared/reference/cstringt-class.md)
