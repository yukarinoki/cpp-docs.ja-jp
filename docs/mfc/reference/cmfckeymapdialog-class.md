---
title: CMFCKeyMapDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
dev_langs:
- C++
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25d86a4797479fe3ee95dde162e22cde63aaa71e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog クラス
`CMFCKeyMapDialog`クラスは、コマンドをキーボードのキーにマップされるコントロールをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCKeyMapDialog : public CDialogEx  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|`CMFCKeyMapDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCKeyMapDialog::DoModal](#domodal)|キーボード マップ ダイアログ ボックスが表示されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCKeyMapDialog::FormatItem](#formatitem)|キーのマッピングを説明する文字列を構築するためにフレームワークによって呼び出されます。 既定では、文字列には、コマンド名、ショートカット キー、およびショートカット キーの説明が含まれています。|  
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|指定されたコマンドに関連付けられているショートカット キーの一覧を含む文字列を取得します。|  
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|キーボード マップ コントロールをサポートする内部リスト コントロールに新しい項目を挿入する前に、フレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|新しいページに、キーボード マップのヘッダーを印刷するためにフレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|キーボード マップ項目を印刷するためにフレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|キーボード マップ コントロールをサポートする内部リスト コントロール内の列のキャプションを設定するためにフレームワークによって呼び出されます。|  
|[CMFCKeyMapDialog::PrintKeyMap](#printkeymap)|ユーザーがクリックしたときに、フレームワークによって呼び出されます、**印刷**ボタンをクリックします。|  
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|キーボード マップ コントロールをサポートする内部リスト コントロール内の列の幅を設定するためにフレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 使用して、`CMFCKeyMapDialog`サイズ変更可能なキーボード マッピング ダイアログ ボックスを実装するクラス。 ダイアログ ボックスでは、リスト ビュー コントロールを使用して、キーボード ショートカットとそれに関連付けられているコマンドを表示します。  
  
 使用する、`CMFCKeyMapDialog`クラスをアプリケーション内にパラメーターとしてメイン フレーム ウィンドウへのポインターに渡さ、`CMFCKeyMapDialog`コンス トラクターです。 まず、`DoModal`モーダル ダイアログ ボックスを起動する方法です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxkeymapdialog.h  
  
##  <a name="cmfckeymapdialog"></a>  CMFCKeyMapDialog::CMFCKeyMapDialog  
 `CMFCKeyMapDialog` オブジェクトを構築します。  
  
```  
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,  
    BOOL bEnablePrint=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pWndParentFrame`  
 親ウィンドウへのポインター、`CMFCKeyMapDialog`オブジェクト。  
  
 [入力] `bEnablePrint`  
 `TRUE` アクセラレータ キーの一覧を印刷する場合それ以外の場合、`FALSE`です。 既定値は、`FALSE` です。  
  
### <a name="remarks"></a>コメント  
  
### <a name="example"></a>例  
 次の例でのオブジェクトを作成する方法、`CMFCKeyMapDialog`クラスです。 この例の一部である、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CMFCKeyMapDialog::DoModal  
 キーボード マップ ダイアログ ボックスが表示されます。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 符号付き整数など`IDOK`または`IDCANCEL`、つまりに渡される、 [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog)メソッドです。 メソッドは、さらに、ダイアログ ボックスを閉じます。 詳細については、次を参照してください。 [CDialog::DoModal](../../mfc/reference/cdialog-class.md#domodal)です。  
  
### <a name="remarks"></a>コメント  
 キーボード マップ ダイアログ ボックスを使用すると、選択し、コマンドのさまざまなカテゴリにアクセラレータ キーを割り当てることができます。 さらに、選択されたアクセラレータ キーとその説明をクリップボードにコピーすることができます。  
  
##  <a name="formatitem"></a>  CMFCKeyMapDialog::FormatItem  
 キーのマッピングを説明する文字列を構築するためにフレームワークによって呼び出されます。 既定では、文字列には、コマンド名、ショートカット キー、およびショートカット キーの説明が含まれています。  
  
```  
virtual CString FormatItem(int nItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nItem`  
 キー マッピングの内部リスト内の項目の 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 A`CString`書式設定された項目のテキストを含むオブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcommandkeys"></a>  CMFCKeyMapDialog::GetCommandKeys  
 文字列値を取得します。 文字列には、指定されたコマンドに関連付けられているショートカット キーの一覧が含まれています。  
  
```  
virtual CString GetCommandKeys(UINT uiCmdID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmdID`  
 コマンド id。  
  
### <a name="return-value"></a>戻り値  
 セミコロンで区切られた、指定されたコマンドに関連付けられているショートカット キーの (';') の一覧です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oninsertitem"></a>  CMFCKeyMapDialog::OnInsertItem  
 キーボード マップ コントロールをサポートする内部リスト コントロールに新しい項目を挿入する前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,  
    int nItem);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pButton`  
 コマンドの名前と説明をキーボードのキーの組み合わせをマップに使用されるツール バー ボタンへのポインター。 キー マップ項目は、内部リスト コントロールに格納されます。  
  
 [入力] `nItem`  
 内部リスト コントロールに新しいキー マップ項目を挿入する場所を指定する 0 から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onprintheader"></a>  CMFCKeyMapDialog::OnPrintHeader  
 新しいページに、キーボード マップのヘッダーを印刷するためにフレームワークによって呼び出されます。  
  
```  
virtual int OnPrintHeader(
    CDC& dc,  
    int nPage,  
    int cx) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dc`  
 プリンター デバイス コンテキスト。  
  
 [入力] `nPage`  
 印刷するページ番号です。  
  
 [入力] `cx`  
 ピクセル単位でヘッダーの横方向のオフセット。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、印刷したテキストの高さ。 詳細についてを参照してください、戻り値の[CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)です。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、このメソッドを使用して、キーボード マップを印刷します。 既定では、このメソッドは、ページ番号、アプリケーション名、およびダイアログ ボックスのタイトルを出力します。  
  
##  <a name="onprintitem"></a>  CMFCKeyMapDialog::OnPrintItem  
 キーボード マップ項目を印刷するためにフレームワークによって呼び出されます。  
  
```  
virtual int OnPrintItem(
    CDC& dc,  
    int nItem,  
    int y,  
    int cx,  
    BOOL bCalcHeight) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `dc`  
 プリンター デバイス コンテキスト。  
  
 [入力] `nItem`  
 印刷する項目の 0 から始まるインデックス。  
  
 [入力] `y`  
 ページの上部とアイテムの位置の垂直方向のオフセット。  
  
 [入力] `cx`  
 ページの左側と項目の位置の水平方向のオフセット。  
  
 [入力] `bCalcHeight`  
 `TRUE` 最適な印刷項目の高さを計算するには`FALSE`を切り捨てます印刷既定の領域に収まるようにします。  
  
### <a name="return-value"></a>戻り値  
 印刷対象の項目の高さ。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、キー マップ ダイアログ ボックスの項目を印刷するには、このメソッドを呼び出します。 既定では、このメソッドは、項目のコマンド名、ショートカット キー、およびコマンドの説明を出力します。  
  
##  <a name="onsetcolumns"></a>  CMFCKeyMapDialog::OnSetColumns  
 キーボード マップ コントロールをサポートする内部リスト コントロール内の列のキャプションを設定するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドは、3 つのリソースから列のキャプションを取得します。 コマンドの列のキャプション IDS_AFXBARRES_COMMAND、IDS_AFXBARRES_KEYS からは、キー列のキャプション、説明の列のキャプションは IDS_AFXBARRES_DESCRIPTION から。  
  
##  <a name="printkeymap"></a>  CMFCKeyMapDialog::PrintKeyMap  
 ユーザーがクリックしたときに、フレームワークによって呼び出されます、**印刷**ボタンをクリックします。  
  
```  
virtual void PrintKeyMap();
```  
  
### <a name="remarks"></a>コメント  
 `PrintKeyMap`メソッドは、キー マップを出力します。 新しい印刷ジョブを開始し、繰り返し呼び出し、 [CMFCKeyMapDialog::OnPrintHeader](#onprintheader)と[CMFCKeyMapDialog::OnPrintItem](#onprintitem)メソッド キーのすべてのマッピングが印刷されるまでです。  
  
##  <a name="setcolumnswidth"></a>  CMFCKeyMapDialog::SetColumnsWidth  
 キーボード マップ コントロールをサポートする内部リスト コントロール内の列の幅を設定するためにフレームワークによって呼び出されます。  
  
```  
virtual void SetColumnsWidth();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、既定の幅のコントロールの列を内部リストに設定します。 最初に、ショートカット キー列の幅が計算されます。 残りの幅の 3 分の 1 つが、[コマンド] 列に割り当てられているし、[説明] 列に、残りの 3 分の 2 が割り当てられています。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)
