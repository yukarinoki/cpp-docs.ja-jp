---
title: クラスを表示します。
ms.date: 11/04/2016
f1_keywords:
- CRichEditView
- AFXRICH/CRichEditView
- AFXRICH/CRichEditView::CRichEditView
- AFXRICH/CRichEditView::AdjustDialogPosition
- AFXRICH/CRichEditView::CanPaste
- AFXRICH/CRichEditView::DoPaste
- AFXRICH/CRichEditView::FindText
- AFXRICH/CRichEditView::FindTextSimple
- AFXRICH/CRichEditView::GetCharFormatSelection
- AFXRICH/CRichEditView::GetDocument
- AFXRICH/CRichEditView::GetInPlaceActiveItem
- AFXRICH/CRichEditView::GetMargins
- AFXRICH/CRichEditView::GetPageRect
- AFXRICH/CRichEditView::GetPaperSize
- AFXRICH/CRichEditView::GetParaFormatSelection
- AFXRICH/CRichEditView::GetPrintRect
- AFXRICH/CRichEditView::GetPrintWidth
- AFXRICH/CRichEditView::GetRichEditCtrl
- AFXRICH/CRichEditView::GetSelectedItem
- AFXRICH/CRichEditView::GetTextLength
- AFXRICH/CRichEditView::GetTextLengthEx
- AFXRICH/CRichEditView::InsertFileAsObject
- AFXRICH/CRichEditView::InsertItem
- AFXRICH/CRichEditView::IsRichEditFormat
- AFXRICH/CRichEditView::OnCharEffect
- AFXRICH/CRichEditView::OnParaAlign
- AFXRICH/CRichEditView::OnUpdateCharEffect
- AFXRICH/CRichEditView::OnUpdateParaAlign
- AFXRICH/CRichEditView::PrintInsideRect
- AFXRICH/CRichEditView::PrintPage
- AFXRICH/CRichEditView::SetCharFormat
- AFXRICH/CRichEditView::SetMargins
- AFXRICH/CRichEditView::SetPaperSize
- AFXRICH/CRichEditView::SetParaFormat
- AFXRICH/CRichEditView::TextNotFound
- AFXRICH/CRichEditView::GetClipboardData
- AFXRICH/CRichEditView::GetContextMenu
- AFXRICH/CRichEditView::IsSelected
- AFXRICH/CRichEditView::OnFindNext
- AFXRICH/CRichEditView::OnInitialUpdate
- AFXRICH/CRichEditView::OnPasteNativeObject
- AFXRICH/CRichEditView::OnPrinterChanged
- AFXRICH/CRichEditView::OnReplaceAll
- AFXRICH/CRichEditView::OnReplaceSel
- AFXRICH/CRichEditView::OnTextNotFound
- AFXRICH/CRichEditView::QueryAcceptData
- AFXRICH/CRichEditView::WrapChanged
- AFXRICH/CRichEditView::m_nBulletIndent
- AFXRICH/CRichEditView::m_nWordWrap
helpviewer_keywords:
- CRichEditView [MFC], CRichEditView
- CRichEditView [MFC], AdjustDialogPosition
- CRichEditView [MFC], CanPaste
- CRichEditView [MFC], DoPaste
- CRichEditView [MFC], FindText
- CRichEditView [MFC], FindTextSimple
- CRichEditView [MFC], GetCharFormatSelection
- CRichEditView [MFC], GetDocument
- CRichEditView [MFC], GetInPlaceActiveItem
- CRichEditView [MFC], GetMargins
- CRichEditView [MFC], GetPageRect
- CRichEditView [MFC], GetPaperSize
- CRichEditView [MFC], GetParaFormatSelection
- CRichEditView [MFC], GetPrintRect
- CRichEditView [MFC], GetPrintWidth
- CRichEditView [MFC], GetRichEditCtrl
- CRichEditView [MFC], GetSelectedItem
- CRichEditView [MFC], GetTextLength
- CRichEditView [MFC], GetTextLengthEx
- CRichEditView [MFC], InsertFileAsObject
- CRichEditView [MFC], InsertItem
- CRichEditView [MFC], IsRichEditFormat
- CRichEditView [MFC], OnCharEffect
- CRichEditView [MFC], OnParaAlign
- CRichEditView [MFC], OnUpdateCharEffect
- CRichEditView [MFC], OnUpdateParaAlign
- CRichEditView [MFC], PrintInsideRect
- CRichEditView [MFC], PrintPage
- CRichEditView [MFC], SetCharFormat
- CRichEditView [MFC], SetMargins
- CRichEditView [MFC], SetPaperSize
- CRichEditView [MFC], SetParaFormat
- CRichEditView [MFC], TextNotFound
- CRichEditView [MFC], GetClipboardData
- CRichEditView [MFC], GetContextMenu
- CRichEditView [MFC], IsSelected
- CRichEditView [MFC], OnFindNext
- CRichEditView [MFC], OnInitialUpdate
- CRichEditView [MFC], OnPasteNativeObject
- CRichEditView [MFC], OnPrinterChanged
- CRichEditView [MFC], OnReplaceAll
- CRichEditView [MFC], OnReplaceSel
- CRichEditView [MFC], OnTextNotFound
- CRichEditView [MFC], QueryAcceptData
- CRichEditView [MFC], WrapChanged
- CRichEditView [MFC], m_nBulletIndent
- CRichEditView [MFC], m_nWordWrap
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
ms.openlocfilehash: 2d832f3cc07d39ace9e679901c5344a376cea03c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318637"
---
# <a name="cricheditview-class"></a>クラスを表示します。

[では](../../mfc/reference/cricheditdoc-class.md)、MFC のドキュメント[CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)ビュー アーキテクチャのコンテキスト内でリッチ エディット コントロールの機能を提供します。

## <a name="syntax"></a>構文

```
class CRichEditView : public CCtrlView
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[コントロール ビュー::リッチエディットビュー](#cricheditview)|`CRichEditView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コントロール ビュー::アジャスタダイアログポジション](#adjustdialogposition)|現在の選択内容が隠されないようにダイアログ ボックスを移動します。|
|[表示::缶ペースト](#canpaste)|クリップボードにリッチ エディット ビューに貼り付けることができるデータが含まれているかどうかを示します。|
|[クリッチエディットビュー::Doペースト](#dopaste)|OLE アイテムをこのリッチ エディット ビューに貼り付けます。|
|[コントロール ビュー::テキストを検索します。](#findtext)|待機カーソルを呼び出して、指定されたテキストを検索します。|
|[コントロール ビュー::テキストを検索シンプル](#findtextsimple)|指定したテキストを検索します。|
|[コントロールの選択](#getcharformatselection)|現在の選択範囲の文字書式属性を取得します。|
|[表示::取得ドキュメント](#getdocument)|関連する[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)へのポインターを取得します。|
|[コントロール ビュー::インプレイスアクティブアイテム](#getinplaceactiveitem)|リッチ エディット ビューで現在作業中の OLE アイテムを取得します。|
|[コントロール ビュー::ゲットマージン](#getmargins)|このリッチ エディット ビューの余白を取得します。|
|[コントロール ビュー::ページレッt](#getpagerect)|このリッチ エディット ビューのページ四角形を取得します。|
|[コントロール ビュー::取得用紙サイズ](#getpapersize)|リッチ エディット ビューの用紙サイズを取得します。|
|[コントロールの選択](#getparaformatselection)|現在の選択範囲の段落書式属性を取得します。|
|[コントロール ビュー::取得プリントレック](#getprintrect)|このリッチ エディット ビューの印刷用四角形を取得します。|
|[コントロール ビュー::プリント幅を取得します。](#getprintwidth)|このリッチ エディット ビューの印刷幅を取得します。|
|[コントロール ビュー::取得リッチエディットCtrl](#getricheditctrl)|リッチ エディット コントロールを取得します。|
|[ビュー::選択されたアイテムを取得します。](#getselecteditem)|リッチ エディット ビューから選択したアイテムを取得します。|
|[ビュー::テキストの長さを取得します。](#gettextlength)|リッチ エディット ビューのテキストの長さを取得します。|
|[コントロール ビュー::テキスト長さ](#gettextlengthex)|リッチ エディット ビューの文字数またはバイト数を取得します。 長さを決定する方法の展開フラグリスト。|
|[表示::ファイルのオブジェクトを挿入します。](#insertfileasobject)|OLE アイテムとしてファイルを挿入します。|
|[ビュー::アイテムを挿入します。](#insertitem)|新しいアイテムを OLE アイテムとして挿入します。|
|[コントロール ビュー::イズリッチエディットフォーマット](#isricheditformat)|クリップボードにリッチ エディット形式またはテキスト形式のデータが含まれているかどうかを示します。|
|[コントロールビュー::オンチャーエフェクト](#onchareffect)|現在の選択範囲の文字書式を切り替えます。|
|[クリッチエディットビュー::オンパラ整列](#onparaalign)|段落の配置を変更します。|
|[コントロールビュー::オンアップデートシャーエフェクト](#onupdatechareffect)|文字パブリック メンバー関数のコマンド UI を更新します。|
|[クリッチエディットビュー::オンアップデートパラアライメント](#onupdateparaalign)|段落パブリック メンバー関数のコマンド UI を更新します。|
|[クリッチエディットビュー::Pリントインサイドレック](#printinsiderect)|指定された四角形内の指定したテキストを書式設定します。|
|[コントロール ビュー::Pリントページ](#printpage)|指定したページ内の指定したテキストを書式設定します。|
|[コントロールビュー::セットキャラフォーマット](#setcharformat)|現在の選択範囲の文字書式属性を設定します。|
|[ビュー::セットマージン](#setmargins)|このリッチ エディット ビューの余白を設定します。|
|[表示::セットペーパーサイズ](#setpapersize)|リッチ エディット ビューの用紙サイズを設定します。|
|[コントロールビュー::セットパラフォーマット](#setparaformat)|現在の選択範囲の段落書式属性を設定します。|
|[表示::テキストは見つかりませんでした](#textnotfound)|コントロールの内部検索状態をリセットします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[コントロール ビュー::クリップボードデータを取得します。](#getclipboarddata)|このリッチ エディット ビューの範囲のクリップボード オブジェクトを取得します。|
|[コントロール ビュー::メニューを取得します。](#getcontextmenu)|マウスの右ボタンで使用するコンテキスト メニューを取得します。|
|[表示::選択されました](#isselected)|指定した OLE アイテムが選択されているかどうかを示します。|
|[次の画面を見る](#onfindnext)|次に出現する部分文字列を検索します。|
|[プログラムビュー::オンイニシャルアップデート](#oninitialupdate)|ドキュメントに最初にアタッチされたときにビューを更新します。|
|[ビュー::オンペーストネイティブオブジェクト](#onpastenativeobject)|OLE アイテムからネイティブ データを取得します。|
|[クリッチエディットビュー::オンプリンタ変更](#onprinterchanged)|指定されたデバイスに印刷特性を設定します。|
|[クリッチエディットビュー::オンスReplaceAll](#onreplaceall)|指定した文字列のすべての出現箇所を新しい文字列で置き換えます。|
|[クリッチエディットビュー::オンコセプセル](#onreplacesel)|現在の選択範囲を置き換えます。|
|[クリッチエディットビュー::オンテキストNotFound](#ontextnotfound)|要求されたテキストが見つからなかったというユーザー通知を処理します。|
|[ビュー::クエリアクセプデータ](#queryacceptdata)|のデータを確認するクエリ。 `IDataObject`|
|[コントロール ビュー::ラップ変更](#wrapchanged)|の値に基づいて、このリッチ エディット ビューのターゲット出力デバイス`m_nWordWrap`を調整します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[クリッチエディットビュー::m_nBulletIndent](#m_nbulletindent)|箇条書きのインデントの量を示します。|
|[クリッチエディットビュー::m_nWordWrap](#m_nwordwrap)|ワード ラップ制約を示します。|

## <a name="remarks"></a>解説

"リッチ エディット コントロール" とは、ユーザーがテキストを入力および編集できるウィンドウです。 テキストには、文字および段落の書式を割り当てることができ、埋め込み OLE オブジェクトを含めることができます。 リッチ エディット コントロールは、テキストを書式設定するためのプログラミング インターフェイスを提供します。 ただし、アプリケーションは、ユーザーが書式設定操作を使用できるようにするために必要なユーザー インターフェイス コンポーネントを実装する必要があります。

`CRichEditView`は、テキストのテキストと書式設定の特性を維持します。 `CRichEditDoc`は、ビュー内にある OLE クライアントアイテムのリストを保持します。 `CRichEditCntrItem`は、OLE クライアントアイテムへのコンテナ側アクセスを提供します。

この Windows コモン コントロール (および[CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)と関連クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

MFC アプリケーションでリッチ エディット ビューを使用する例については[、WORDPAD](../../overview/visual-cpp-samples.md)サンプル アプリケーションを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CCtrlView](../../mfc/reference/cctrlview-class.md)

`CRichEditView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxrich.h

## <a name="cricheditviewadjustdialogposition"></a><a name="adjustdialogposition"></a>コントロール ビュー::アジャスタダイアログポジション

現在の選択内容が隠されないように、指定されたダイアログ ボックスを移動します。

```
void AdjustDialogPosition(CDialog* pDlg);
```

### <a name="parameters"></a>パラメーター

*pDlg*<br/>
`CDialog`オブジェクトへのポインター。

## <a name="cricheditviewcanpaste"></a><a name="canpaste"></a>表示::缶ペースト

クリップボードに、このリッチ エディット ビューに貼り付けることができる情報が含まれているかどうかを調べます。

```
BOOL CanPaste() const;
```

### <a name="return-value"></a>戻り値

クリップボードに、このリッチ エディット ビューで使用できる形式のデータが含まれている場合は 0 以外の値を返します。それ以外の場合は 0。

## <a name="cricheditviewcricheditview"></a><a name="cricheditview"></a>コントロール ビュー::リッチエディットビュー

`CRichEditView`オブジェクトを作成します。

```
CRichEditView();
```

## <a name="cricheditviewdopaste"></a><a name="dopaste"></a>クリッチエディットビュー::Doペースト

このリッチ エディット ドキュメント/ビューに*dataobj*の OLE アイテムを貼り付けます。

```
void DoPaste(
    COleDataObject& dataobj,
    CLIPFORMAT cf,
    HMETAFILEPICT hMetaPict);
```

### <a name="parameters"></a>パラメーター

*データobj*<br/>
貼り付けるデータを含む[COleData オブジェクト](../../mfc/reference/coledataobject-class.md)。

*Cf*<br/>
目的のクリップボード形式。

*メタピクト*<br/>
貼り付ける項目を表すメタファイル。

### <a name="remarks"></a>解説

フレームワークは[、QueryAcceptData](#queryacceptdata)の既定の実装の一部としてこの関数を呼び出します。

この関数は、形式を選択して貼り付けのハンドラーの結果に基づいて、貼り付けの種類を決定します。 *cf が*0 の場合、新しい項目は現在のアイコニック表現を使用します。 *cf が*ゼロ以外で *、hMetaPict*が NULL でない場合、新しい項目は*hMetaPict*を使用してその表現を行います。

## <a name="cricheditviewfindtext"></a><a name="findtext"></a>コントロール ビュー::テキストを検索します。

指定したテキストを検索し、現在の選択テキストに設定します。

```
BOOL FindText(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
検索する文字列を含みます。

*bCase*<br/>
検索で大文字と小文字が区別されるかどうかを示します。

*bワード*<br/>
検索で単語の一部ではなく、単語全体のみを一致させるかどうかを示します。

*Bnext*<br/>
検索の方向を示します。 TRUE の場合、検索方向はバッファーの末尾に向かっています。 FALSE の場合、検索方向はバッファーの先頭に向かっています。

### <a name="return-value"></a>戻り値

*lpszFind*テキストが見つかった場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、検索操作中に待機カーソルを表示します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#151](../../mfc/codesnippet/cpp/cricheditview-class_1.cpp)]

## <a name="cricheditviewfindtextsimple"></a><a name="findtextsimple"></a>コントロール ビュー::テキストを検索シンプル

指定したテキストを検索し、現在の選択テキストに設定します。

```
BOOL FindTextSimple(
    LPCTSTR lpszFind,
    BOOL bCase = TRUE,
    BOOL bWord = TRUE,
    BOOL bNext = TRUE);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
検索する文字列を含みます。

*bCase*<br/>
検索で大文字と小文字が区別されるかどうかを示します。

*bワード*<br/>
検索で単語の一部ではなく、単語全体のみを一致させるかどうかを示します。

*Bnext*<br/>
検索の方向を示します。 TRUE の場合、検索方向はバッファーの末尾に向かっています。 FALSE の場合、検索方向はバッファーの先頭に向かっています。

### <a name="return-value"></a>戻り値

*lpszFind*テキストが見つかった場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="example"></a>例

  [「CRichEditView::テキストを検索](#findtext)する」の例を参照してください。

## <a name="cricheditviewgetcharformatselection"></a><a name="getcharformatselection"></a>コントロールの選択

現在の選択範囲の文字書式属性を取得します。

```
CHARFORMAT2& GetCharFormatSelection();
```

### <a name="return-value"></a>戻り値

現在の選択範囲の文字書式属性を含む[CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w)構造体。

### <a name="remarks"></a>解説

詳細については、Windows SDK の[EM_GETCHARFORMAT](/windows/win32/Controls/em-getcharformat)メッセージと[CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w)構造体を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

## <a name="cricheditviewgetclipboarddata"></a><a name="getclipboarddata"></a>コントロール ビュー::クリップボードデータを取得します。

フレームワークは、この関数を処理の一環として呼び出[します](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)。

```
virtual HRESULT GetClipboardData(
    CHARRANGE* lpchrg,
    DWORD dwReco,
    LPDATAOBJECT lpRichDataObj,
    LPDATAOBJECT* lplpdataobj);
```

### <a name="parameters"></a>パラメーター

*lpchrg*<br/>
*lplpdataobj*で指定されたデータ オブジェクトにコピーする文字 (および OLE アイテム) の範囲を指定する[CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange)構造体へのポインター。

*ドレコ*<br/>
クリップボード操作フラグ。 これらの値のいずれかです。

- RECO_COPY クリップボードにコピーします。

- RECO_CUT クリップボードに切り取ります。

- RECO_DRAGドラッグ操作(ドラッグアンドドロップ)を実行します。

- RECO_DROP ドロップ操作 (ドラッグ アンド ドロップ)

- RECO_PASTE クリップボードから貼り付けします。

*を使用します。*<br/>
リッチ エディット コントロールからのクリップボード データを含む[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)オブジェクトへのポインター ( [IRichEditOle::GetClipboardData](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata))。

*を指定します。*<br/>
*lpchrg*パラメーターで指定された範囲を表す`IDataObject`オブジェクトのアドレスを受け取るポインター変数へのポインター。 エラーが戻された場合 *、lplpdataobj*の値は無視されます。

### <a name="return-value"></a>戻り値

操作の成功を報告する HRESULT 値。 HRESULT の詳細については、Windows SDK[の COM エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)を参照してください。

### <a name="remarks"></a>解説

戻り値が成功を示`IRichEditOleCallback::GetClipboardData`す場合`IDataObject`は *、lplpdataobj*によってアクセスされた値を返します。それ以外の場合は *、lpRichDataObj*によってアクセスされる値を返します。 独自のクリップボード データを指定するには、この関数をオーバーライドします。 この関数の既定の実装は、E_NOTIMPLを返します。

これは、高度なオーバーライド可能です。

詳細については、Windows SDK の[「IRichEditOle::クリップボードデータ](/windows/win32/api/richole/nf-richole-iricheditole-getclipboarddata)[、IRichEditOleコールバック::クリップボードデータの取得](/windows/win32/api/richole/nf-richole-iricheditolecallback-getclipboarddata)」、[および「Windows](/windows/win32/api/richedit/ns-richedit-charrange) SDK の[IDataObject」](/windows/win32/api/objidl/nn-objidl-idataobject)を参照してください。

## <a name="cricheditviewgetcontextmenu"></a><a name="getcontextmenu"></a>コントロール ビュー::メニューを取得します。

フレームワークは、この関数を処理の一部として呼び出[します](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu)。

```
virtual HMENU GetContextMenu(
    WORD seltyp,
    LPOLEOBJECT lpoleobj,
    CHARRANGE* lpchrg);
```

### <a name="parameters"></a>パラメーター

*セルティップ*<br/>
選択の種類。 選択タイプの値については、「解説」セクションで説明します。

*ルポレブ*<br/>
選択項目に`OLEOBJECT`OLE アイテムが 1 つ以上含まれている場合に、最初に選択した OLE オブジェクトを指定する構造体へのポインター。 選択項目に項目が含まれる場合 *、lpoleobj*は NULL です。 この`OLEOBJECT`構造体は、OLE オブジェクトの v テーブルへのポインターを保持します。

*lpchrg*<br/>
現在の選択範囲を含む[CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange)構造体へのポインター。

### <a name="return-value"></a>戻り値

コンテキスト メニューへのハンドル。

### <a name="remarks"></a>解説

この関数は、マウスの右ボタンダウン処理の典型的な部分です。

選択タイプは、次のフラグの任意の組み合わせにすることができます。

- SEL_EMPTY 現在の選択がないことを示します。

- SEL_TEXT現在の選択範囲にテキストが含まれていることを示します。

- SEL_OBJECT現在の選択項目に少なくとも 1 つの OLE アイテムが含まれていることを示します。

- SEL_MULTICHAR現在の選択範囲に複数の文字のテキストが含まれていることを示します。

- SEL_MULTIOBJECT現在の選択内容に複数の OLE オブジェクトが含まれていることを示します。

既定の実装では NULL が返されます。 これは、高度なオーバーライド可能です。

詳細[については、](/windows/win32/api/richole/nf-richole-iricheditolecallback-getcontextmenu)次を参照してください。 [CHARRANGE](/windows/win32/api/richedit/ns-richedit-charrange)

## <a name="cricheditviewgetdocument"></a><a name="getdocument"></a>表示::取得ドキュメント

このビューに`CRichEditDoc`関連付けられているポインターを取得します。

```
CRichEditDoc* GetDocument() const;
```

### <a name="return-value"></a>戻り値

`CRichEditView`オブジェクトに関連付けられた[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)オブジェクトへのポインター。

## <a name="cricheditviewgetinplaceactiveitem"></a><a name="getinplaceactiveitem"></a>コントロール ビュー::インプレイスアクティブアイテム

この`CRichEditView`オブジェクト内で現在アクティブになっている OLE アイテムを取得します。

```
CRichEditCntrItem* GetInPlaceActiveItem() const;
```

### <a name="return-value"></a>戻り値

このリッチ エディット ビュー内の 1 つの埋め込み先アクティブ[な CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)オブジェクトへのポインター。現在、インプレース アクティブ状態の OLE アイテムがない場合は NULL。

## <a name="cricheditviewgetmargins"></a><a name="getmargins"></a>コントロール ビュー::ゲットマージン

印刷に使用される現在の余白を取得します。

```
CRect GetMargins() const;
```

### <a name="return-value"></a>戻り値

印刷に使用される余白 (MM_TWIPS単位)。

## <a name="cricheditviewgetpagerect"></a><a name="getpagerect"></a>コントロール ビュー::ページレッt

印刷に使用するページのサイズを取得します。

```
CRect GetPageRect() const;
```

### <a name="return-value"></a>戻り値

印刷に使用されるページの境界をMM_TWIPS単位で指定します。

### <a name="remarks"></a>解説

この値は、用紙サイズに基づいています。

## <a name="cricheditviewgetpapersize"></a><a name="getpapersize"></a>コントロール ビュー::取得用紙サイズ

現在の用紙サイズを取得します。

```
CSize GetPaperSize() const;
```

### <a name="return-value"></a>戻り値

印刷に使用する用紙のサイズをMM_TWIPS単位で指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#153](../../mfc/codesnippet/cpp/cricheditview-class_3.cpp)]

## <a name="cricheditviewgetparaformatselection"></a><a name="getparaformatselection"></a>コントロールの選択

現在の選択範囲の段落書式属性を取得します。

```
PARAFORMAT2& GetParaFormatSelection();
```

### <a name="return-value"></a>戻り値

現在の選択範囲の段落書式属性を含む[PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2)構造体。

### <a name="remarks"></a>解説

詳細については、Windows SDK[の EM_GETPARAFORMAT](/windows/win32/Controls/em-getparaformat)メッセージと[PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2)構造体を参照してください。

## <a name="cricheditviewgetprintrect"></a><a name="getprintrect"></a>コントロール ビュー::取得プリントレック

ページ四角形内の印刷領域の境界を取得します。

```
CRect GetPrintRect() const;
```

### <a name="return-value"></a>戻り値

印刷に使用されるイメージ領域の境界をMM_TWIPS単位で指定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#154](../../mfc/codesnippet/cpp/cricheditview-class_4.cpp)]

## <a name="cricheditviewgetprintwidth"></a><a name="getprintwidth"></a>コントロール ビュー::プリント幅を取得します。

印刷領域の幅を調べます。

```
int GetPrintWidth() const;
```

### <a name="return-value"></a>戻り値

印刷領域の幅をMM_TWIPS単位で指定します。

## <a name="cricheditviewgetricheditctrl"></a><a name="getricheditctrl"></a>コントロール ビュー::取得リッチエディットCtrl

オブジェクトに関連付けられている`CRichEditView` [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md)オブジェクトを取得します。

```
CRichEditCtrl& GetRichEditCtrl() const;
```

### <a name="return-value"></a>戻り値

この`CRichEditCtrl`ビューのオブジェクト。

### <a name="example"></a>例

  [「CRichEditView::テキストを検索](#findtext)する」の例を参照してください。

## <a name="cricheditviewgetselecteditem"></a><a name="getselecteditem"></a>ビュー::選択されたアイテムを取得します。

この`CRichEditView`オブジェクトで現在選択されている OLE アイテム`CRichEditCntrItem`(オブジェクト) を取得します。

```
CRichEditCntrItem* GetSelectedItem() const;
```

### <a name="return-value"></a>戻り値

オブジェクト内で選択されたオブジェクトへのポインター。 [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) `CRichEditView`このビューで項目が選択されていない場合は NULL です。

## <a name="cricheditviewgettextlength"></a><a name="gettextlength"></a>ビュー::テキストの長さを取得します。

この`CRichEditView`オブジェクトのテキストの長さを取得します。

```
long GetTextLength() const;
```

### <a name="return-value"></a>戻り値

この`CRichEditView`オブジェクト内のテキストの長さ。

## <a name="cricheditviewgettextlengthex"></a><a name="gettextlengthex"></a>コントロール ビュー::テキスト長さ

この`CRichEditView`オブジェクトのテキストの長さを計算します。

```
long GetTextLengthEx(
    DWORD dwFlags,
    UINT uCodePage = -1) const;
```

### <a name="parameters"></a>パラメーター

*dwFlags*<br/>
テキストの長さを決定する際に使用する方法を指定する値。 このメンバーは、Windows SDK で説明されている[GETTEXTLENGTHEX](/windows/win32/api/richedit/ns-richedit-gettextlengthex)のフラグ メンバーにリストされている値の 1 つ以上を指定できます。

*コードページ*<br/>
翻訳用のコード ページ (ANSI コード ページの場合はCP_ACP、Unicode の場合は 1200)。

### <a name="return-value"></a>戻り値

エディット コントロール内の文字数またはバイト数。 *dwFlags*に互換性のないフラグが設定されている場合、このメンバー関数はE_INVALIDARG返します。

### <a name="remarks"></a>解説

`GetTextLengthEx`では、テキストの長さを決定する追加の方法が提供されます。 リッチ エディット 2.0 の機能をサポートしています。 詳細については、「Windows SDK[のリッチ エディット コントロールについて](/windows/win32/Controls/about-rich-edit-controls)」を参照してください。

## <a name="cricheditviewinsertfileasobject"></a><a name="insertfileasobject"></a>表示::ファイルのオブジェクトを挿入します。

リッチ エディット ビューに指定したファイル[(CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)オブジェクトとして) を挿入します。

```
void InsertFileAsObject(LPCTSTR lpszFileName);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
挿入するファイルの名前を含む文字列。

## <a name="cricheditviewinsertitem"></a><a name="insertitem"></a>ビュー::アイテムを挿入します。

リッチ エディット ビューに[CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)オブジェクトを挿入します。

```
HRESULT InsertItem(CRichEditCntrItem* pItem);
```

### <a name="parameters"></a>パラメーター

*Pitem*<br/>
挿入する項目へのポインター。

### <a name="return-value"></a>戻り値

挿入が成功したことを示す HRESULT 値。

### <a name="remarks"></a>解説

HRESULT の詳細については、Windows SDK[の COM エラー コードの構造](/windows/win32/com/structure-of-com-error-codes)を参照してください。

## <a name="cricheditviewisricheditformat"></a><a name="isricheditformat"></a>コントロール ビュー::イズリッチエディットフォーマット

*cf*が、テキスト、リッチ テキスト、または OLE アイテムを含むリッチ テキストのどちらであるか、クリップボード形式かどうかを調べます。

```
static BOOL AFX_CDECL IsRichEditFormat(CLIPFORMAT cf);
```

### <a name="parameters"></a>パラメーター

*Cf*<br/>
対象のクリップボード形式。

### <a name="return-value"></a>戻り値

*cf*がリッチ エディット形式またはテキスト クリップボード形式の場合は 0 以外の値を指定します。

## <a name="cricheditviewisselected"></a><a name="isselected"></a>表示::選択されました

指定した OLE アイテムがこのビューで現在選択されているかどうかを調べます。

```
virtual BOOL IsSelected(const CObject* pDocItem) const;
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
ビュー内のオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

オブジェクトが選択されている場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

派生ビュー クラスに OLE アイテムの選択を処理するための別のメソッドがある場合は、この関数をオーバーライドします。

## <a name="cricheditviewm_nbulletindent"></a><a name="m_nbulletindent"></a>クリッチエディットビュー::m_nBulletIndent

箇条書きの項目のインデント。デフォルトでは、720 単位で 1/2 インチです。

```
int m_nBulletIndent;
```

## <a name="cricheditviewm_nwordwrap"></a><a name="m_nwordwrap"></a>クリッチエディットビュー::m_nWordWrap

このリッチ エディット ビューの折り返しの種類を示します。

```
int m_nWordWrap;
```

### <a name="remarks"></a>解説

次のいずれかの値:

- `WrapNone`自動的に折り返さないを示します。

- `WrapToWindow`ウィンドウの幅に基づいてワード ラップを示します。

- `WrapToTargetDevice`ターゲットデバイスの特性に基づいてワードラップを示します。

### <a name="example"></a>例

  [「CRichEditView::ラップ変更](#wrapchanged)」の例を参照してください。

## <a name="cricheditviewonchareffect"></a><a name="onchareffect"></a>コントロールビュー::オンチャーエフェクト

現在の選択範囲の文字書式効果を切り替えます。

```
void OnCharEffect(
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>パラメーター

*Dwmask*<br/>
現在の選択範囲で変更する文字書式効果。

*エフェクト*<br/>
切り替える文字書式効果のリスト。

### <a name="remarks"></a>解説

この関数を呼び出すたびに、現在の選択範囲に対して指定された書式効果が切り替わります。

*dwMask*と*dwEffect*パラメーターとその可能性のある値の詳細については、Windows SDK の[CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata)の対応するデータ メンバーを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#155](../../mfc/codesnippet/cpp/cricheditview-class_5.cpp)]

## <a name="cricheditviewonfindnext"></a><a name="onfindnext"></a>次の画面を見る

[検索/置換] ダイアログ ボックスからコマンドを処理するときに、フレームワークによって呼び出されます。

```
virtual void OnFindNext(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
検索する文字列です。

*Bnext*<br/>
検索する方向: TRUE は下を示します。FALSE、アップ。

*bCase*<br/>
検索で大文字と小文字を区別するかどうかを示します。

*bワード*<br/>
検索が単語全体に一致するかどうかを示します。

### <a name="remarks"></a>解説

内のテキストを検索します`CRichEditView`。 派生ビュー クラスの検索特性を変更するには、この関数をオーバーライドします。

## <a name="cricheditviewoninitialupdate"></a><a name="oninitialupdate"></a>プログラムビュー::オンイニシャルアップデート

ビューが最初にドキュメントにアタッチされた後、ビューが最初に表示される前に、フレームワークによって呼び出されます。

```
virtual void OnInitialUpdate();
```

### <a name="remarks"></a>解説

この関数の既定の実装では、ヒント情報を含まず[CView::OnUpdate](../../mfc/reference/cview-class.md#onupdate)メンバー関数を呼び出します (つまり *、lHint*パラメーターに*0、pHint*パラメーターに NULL という既定値を使用します)。 ドキュメントに関する情報を必要とする 1 回限りの初期化を実行するには、この関数をオーバーライドします。 たとえば、アプリケーションに固定サイズのドキュメントがある場合、この関数を使用して、ドキュメントサイズに基づいてビューのスクロール制限を初期化できます。 アプリケーションが可変サイズのドキュメントをサポートしている場合`OnUpdate`は、ドキュメントが変更されるたびにスクロール制限を更新するために使用します。

### <a name="example"></a>例

  [「CRichEditView::m_nWordWrap](#m_nwordwrap)の例」を参照してください。

## <a name="cricheditviewonpastenativeobject"></a><a name="onpastenativeobject"></a>ビュー::オンペーストネイティブオブジェクト

埋め込みアイテムからネイティブ データを読み込むには、この関数を使用します。

```
virtual BOOL OnPasteNativeObject(LPSTORAGE lpStg);
```

### <a name="parameters"></a>パラメーター

*lpStg*<br/>
[オブジェクト](/windows/win32/api/objidl/nn-objidl-istorage)へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

通常は、 を囲む[COleStreamFile](../../mfc/reference/colestreamfile-class.md)を作成`IStorage`してこれを行います。 アーカイブ`COleStreamFile`にアタッチでき[、CObject::Serialize を](../../mfc/reference/cobject-class.md#serialize)呼び出してデータを読み込むことができます。

これは、高度なオーバーライド可能です。

詳細については、Windows SDK[の IStorage](/windows/win32/api/objidl/nn-objidl-istorage)を参照してください。

## <a name="cricheditviewonparaalign"></a><a name="onparaalign"></a>クリッチエディットビュー::オンパラ整列

選択した段落の段落の配置を変更します。

```
void OnParaAlign(WORD wAlign);
```

### <a name="parameters"></a>パラメーター

*wAlign*<br/>
必要な段落の配置。 次のいずれかの値:

- PFA_LEFT 段落を左余白に合わせます。

- PFA_RIGHT 段落を右余白に合わせます。

- PFA_CENTER余白の間に段落を中央揃えします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#156](../../mfc/codesnippet/cpp/cricheditview-class_6.cpp)]

## <a name="cricheditviewonprinterchanged"></a><a name="onprinterchanged"></a>クリッチエディットビュー::オンプリンタ変更

プリンターが変更されたときに、このリッチ エディット ビューの特性を変更するには、この関数をオーバーライドします。

```
virtual void OnPrinterChanged(const CDC& dcPrinter);
```

### <a name="parameters"></a>パラメーター

*dcプリンター*<br/>
新しいプリンタの[CDC](../../mfc/reference/cdc-class.md)オブジェクト。

### <a name="remarks"></a>解説

既定の実装では、出力デバイス (プリンター) の物理的な高さと幅に用紙サイズを設定します。 *dcPrinter*に関連付けられたデバイス コンテキストがない場合、既定の実装では、用紙サイズが 8.5 × 11 インチに設定されます。

## <a name="cricheditviewonreplaceall"></a><a name="onreplaceall"></a>クリッチエディットビュー::オンスReplaceAll

[置換] ダイアログ ボックスから [すべて置換] コマンドを処理するときに、フレームワークによって呼び出されます。

```
virtual void OnReplaceAll(
    LPCTSTR lpszFind,
    LPCTSTR lpszReplace,
    BOOL bCase,
    BOOL bWord);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
置換するテキスト。

*置き換え*<br/>
置換後のテキスト。

*bCase*<br/>
検索で大文字と小文字が区別されるかどうかを示します。

*bワード*<br/>
検索で単語全体を選択する必要があるかどうかを示します。

### <a name="remarks"></a>解説

指定されたテキストの出現箇所をすべて別の文字列に置き換えます。 このビューの検索特性を変更するには、この関数をオーバーライドします。

### <a name="example"></a>例

  [「CRichEditView::テキストを検索](#findtext)する」の例を参照してください。

## <a name="cricheditviewonreplacesel"></a><a name="onreplacesel"></a>クリッチエディットビュー::オンコセプセル

[置換] ダイアログ ボックスから置換コマンドを処理するときに、フレームワークによって呼び出されます。

```
virtual void OnReplaceSel(
    LPCTSTR lpszFind,
    BOOL bNext,
    BOOL bCase,
    BOOL bWord,
    LPCTSTR lpszReplace);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
置換するテキスト。

*Bnext*<br/>
検索の方向を示します。FALSE、アップ。

*bCase*<br/>
検索で大文字と小文字が区別されるかどうかを示します。

*bワード*<br/>
検索で単語全体を選択する必要があるかどうかを示します。

*置き換え*<br/>
置換後のテキスト。

### <a name="remarks"></a>解説

指定したテキストの 1 つの出現箇所を別の文字列に置き換えます。 このビューの検索特性を変更するには、この関数をオーバーライドします。

## <a name="cricheditviewontextnotfound"></a><a name="ontextnotfound"></a>クリッチエディットビュー::オンテキストNotFound

検索が失敗するたびに、フレームワークによって呼び出されます。

```
virtual void OnTextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
見つからなかったテキスト。

### <a name="remarks"></a>解説

[MessageBeep](/windows/win32/api/winuser/nf-winuser-messagebeep)から出力通知を変更するには、この関数をオーバーライドします。

詳細については、Windows SDK[のメッセージビープ](/windows/win32/api/winuser/nf-winuser-messagebeep)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#157](../../mfc/codesnippet/cpp/cricheditview-class_7.cpp)]

## <a name="cricheditviewonupdatechareffect"></a><a name="onupdatechareffect"></a>コントロールビュー::オンアップデートシャーエフェクト

フレームワークは、文字効果コマンドのコマンド UI を更新するには、この関数を呼び出します。

```
void OnUpdateCharEffect(
    CCmdUI* pCmdUI,
    DWORD dwMask,
    DWORD dwEffect);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
[オブジェクト](../../mfc/reference/ccmdui-class.md)へのポインター。

*Dwmask*<br/>
文字書式マスクを示します。

*エフェクト*<br/>
文字書式の効果を示します。

### <a name="remarks"></a>解説

マスク*dwMask*は、チェックする文字書式属性を指定します。 フラグ*dwEffect*は、設定/クリアする文字書式属性をリストします。

*dwMask*と*dwEffect*パラメーターとその可能性のある値の詳細については、Windows SDK の[CHARFORMAT](/windows/win32/api/richedit/ns-richedit-charformata)の対応するデータ メンバーを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#158](../../mfc/codesnippet/cpp/cricheditview-class_8.cpp)]

## <a name="cricheditviewonupdateparaalign"></a><a name="onupdateparaalign"></a>クリッチエディットビュー::オンアップデートパラアライメント

フレームワークは、この関数を呼び出して、段落効果コマンドのコマンド UI を更新します。

```
void OnUpdateParaAlign(
    CCmdUI* pCmdUI,
    WORD wAlign);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
[オブジェクト](../../mfc/reference/ccmdui-class.md)へのポインター。

*wAlign*<br/>
チェックする段落の配置。 次のいずれかの値:

- PFA_LEFT 段落を左余白に合わせます。

- PFA_RIGHT 段落を右余白に合わせます。

- PFA_CENTER余白の間に段落を中央揃えします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#159](../../mfc/codesnippet/cpp/cricheditview-class_9.cpp)]

## <a name="cricheditviewprintinsiderect"></a><a name="printinsiderect"></a>クリッチエディットビュー::Pリントインサイドレック

リッチ エディット コントロール内のテキストの範囲を *、pDC*で指定されたデバイスの*rectLayout*に収まるように書式設定します。

```
long PrintInsideRect(
    CDC* pDC,
    RECT& rectLayout,
    long nIndexStart,
    long nIndexStop,
    BOOL bOutput);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
出力領域のデバイス コンテキストへのポインター。

*レクトレイアウト*<br/>
出力域を定義する[RECT](/windows/win32/api/windef/ns-windef-rect)または[CRect。](../../atl-mfc-shared/reference/crect-class.md)

*インデックススタート*<br/>
書式設定される最初の文字の 0 から始まるインデックス。

*インデックスストップ*<br/>
書式設定される最後の文字の 0 から始まるインデックス。

*出力*<br/>
テキストをレンダリングする必要があるかどうかを示します。 FALSE の場合、テキストは単に測定されます。

### <a name="return-value"></a>戻り値

出力域に収まる最後の文字のインデックスに 1 を足した値。

### <a name="remarks"></a>解説

通常、この呼び出しの後に、出力を生成する[CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband)への呼び出しが続きます。

### <a name="example"></a>例

  [次](#getpapersize)の例を参照してください。

## <a name="cricheditviewprintpage"></a><a name="printpage"></a>コントロール ビュー::Pリントページ

*pDC*で指定された出力デバイスのリッチ エディット コントロール内のテキスト範囲をフォーマットします。

```
long PrintPage(
    CDC* pDC,
    long nIndexStart,
    long nIndexStop);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
ページ出力のデバイス コンテキストへのポインター。

*インデックススタート*<br/>
書式設定される最初の文字の 0 から始まるインデックス。

*インデックスストップ*<br/>
書式設定される最後の文字の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

ページに収まる最後の文字のインデックスに 1 を加えた値。

### <a name="remarks"></a>解説

各ページのレイアウトは[、GetPageRect](#getpagerect)と[GetPrintRect](#getprintrect)によって制御されます。 通常、この呼び出しの後に、出力を生成する[CRichEditCtrl::DisplayBand](../../mfc/reference/cricheditctrl-class.md#displayband)への呼び出しが続きます。

余白は、論理ページではなく、物理ページを基準にしています。 したがって、多くのプリンタはページ上に印刷できない領域を持つため、余白がゼロの場合、テキストがクリップされることがよくあります。 テキストのクリッピングを避けるには、印刷する前に[SetMargins](#setmargins)を呼び出して適切な余白を設定する必要があります。

## <a name="cricheditviewqueryacceptdata"></a><a name="queryacceptdata"></a>ビュー::クエリアクセプデータ

リッチ エディットにオブジェクトを貼り付けるために、フレームワークによって呼び出されます。

```
virtual HRESULT QueryAcceptData(
    LPDATAOBJECT lpdataobj,
    CLIPFORMAT* lpcfFormat,
    DWORD dwReco,
    BOOL bReally,
    HGLOBAL hMetaFile);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
クエリを実行[する IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)へのポインター。

*フォーマットを指定します。*<br/>
許容可能なデータ形式へのポインター。

*ドレコ*<br/>
使用されていません。

*本当に*<br/>
貼り付け操作を続行する必要があるかどうかを示します。

*ファイル*<br/>
項目のアイコンの描画に使用するメタファイルへのハンドル。

### <a name="return-value"></a>戻り値

操作の成功を報告する HRESULT 値。

### <a name="remarks"></a>解説

派生ドキュメント クラス内の COM 項目の編成を変更するには、この関数をオーバーライドします。 これは、高度なオーバーライド可能です。

HRESULT と`IDataObject`の詳細については、Windows SDK の[COM エラー コード](/windows/win32/com/structure-of-com-error-codes)と[IDataObject](/windows/win32/api/objidl/nn-objidl-idataobject)の構造をそれぞれ参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#160](../../mfc/codesnippet/cpp/cricheditview-class_10.cpp)]

## <a name="cricheditviewsetcharformat"></a><a name="setcharformat"></a>コントロールビュー::セットキャラフォーマット

この`CRichEditView`オブジェクトの新しいテキストの文字書式属性を設定します。

```
void SetCharFormat(CHARFORMAT2 cf);
```

### <a name="parameters"></a>パラメーター

*Cf*<br/>
新しいデフォルト文字フォーマット属性を含む[CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w)構造体。

### <a name="remarks"></a>解説

cf の`dwMask`メンバーによって指定された属性*のみがこの関数*によって変更されます。

詳細については、Windows SDK の「メッセージと[CHARFORMAT2](/windows/win32/api/richedit/ns-richedit-charformat2w)構造体[のEM_SETCHARFORMAT」](/windows/win32/Controls/em-setcharformat)を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#152](../../mfc/codesnippet/cpp/cricheditview-class_2.cpp)]

## <a name="cricheditviewsetmargins"></a><a name="setmargins"></a>ビュー::セットマージン

このリッチ エディット ビューの印刷余白を設定します。

```
void SetMargins(const CRect& rectMargin);
```

### <a name="parameters"></a>パラメーター

*レクトマージン*<br/>
印刷用の新しい余白の値 (MM_TWIPS単位)。

### <a name="remarks"></a>解説

[m_nWordWrap](#m_nwordwrap)場合は`WrapToTargetDevice`、この関数を使用して印刷特性を調整した後に[WrapChanged](#wrapchanged)を呼び出す必要があります。

[PrintPage](#printpage)で使用される余白は、論理ページではなく、物理ページに対する相対パスであることに注意してください。 したがって、多くのプリンタはページ上に印刷できない領域を持つため、余白がゼロの場合、テキストがクリップされることがよくあります。 テキストのクリッピングを避けるには、印刷前`SetMargins`に適切なプリンタの余白を設定するために use を呼び出す必要があります。

### <a name="example"></a>例

  [次](#getpapersize)の例を参照してください。

## <a name="cricheditviewsetpapersize"></a><a name="setpapersize"></a>表示::セットペーパーサイズ

このリッチ エディット ビューを印刷するための用紙サイズを設定します。

```
void SetPaperSize(CSize sizePaper);
```

### <a name="parameters"></a>パラメーター

*サイズ用紙*<br/>
印刷用の新しい用紙サイズの値 (MM_TWIPS単位)。

### <a name="remarks"></a>解説

[m_nWordWrap](#m_nwordwrap)場合は`WrapToTargetDevice`、この関数を使用して印刷特性を調整した後に[WrapChanged](#wrapchanged)を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#161](../../mfc/codesnippet/cpp/cricheditview-class_11.cpp)]

## <a name="cricheditviewsetparaformat"></a><a name="setparaformat"></a>コントロールビュー::セットパラフォーマット

この`CRichEditView`オブジェクトの現在の選択範囲の段落書式属性を設定します。

```
BOOL SetParaFormat(PARAFORMAT2& pf);
```

### <a name="parameters"></a>パラメーター

*Pf*<br/>
新しいデフォルトの段落書式属性を含む[PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2)構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数によって変更されるのは`dwMask`*、pf*のメンバーによって指定された属性だけです。

詳細については、Windows SDK[の「EM_SETPARAFORMAT](/windows/win32/Controls/em-setparaformat)メッセージと[PARAFORMAT2](/windows/win32/api/richedit/ns-richedit-paraformat2)構造体」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#162](../../mfc/codesnippet/cpp/cricheditview-class_12.cpp)]

## <a name="cricheditviewtextnotfound"></a><a name="textnotfound"></a>表示::テキストは見つかりませんでした

この関数を呼び出して[、FindText](#findtext)の呼び出しが失敗した後に[、CRichEditView](../../mfc/reference/cricheditview-class.md)コントロールの内部検索状態をリセットします。

```
void TextNotFound(LPCTSTR lpszFind);
```

### <a name="parameters"></a>パラメーター

*lpsz検索*<br/>
見つからなかったテキスト文字列が含まれています。

### <a name="remarks"></a>解説

コントロールの内部検索状態が正しくリセットされるように[、FindText](#findtext)の呼び出しが失敗した直後にこのメソッドを呼び出すことをお勧めします。

*lpszFind*パラメーターには[、FindText](#findtext)に指定された文字列と同じ内容を含める必要があります。 内部検索状態をリセットした後、このメソッドは指定された検索文字列を使用して[OnTextNotFound](#ontextnotfound)メソッドを呼び出します。

### <a name="example"></a>例

  [「CRichEditView::テキストを検索](#findtext)する」の例を参照してください。

## <a name="cricheditviewwrapchanged"></a><a name="wrapchanged"></a>コントロール ビュー::ラップ変更

印刷特性が変更された場合にこの関数を呼び出します ( [SetMargins](#setmargins)または[SetPaperSize](#setpapersize))。

```
virtual void WrapChanged();
```

### <a name="remarks"></a>解説

リッチ エディット ビューが[m_nWordWrap](#m_nwordwrap)または印刷特性 ( [OnPrinterChanged](#onprinterchanged)) の変更に応答する方法を変更するには、この関数をオーバーライドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#163](../../mfc/codesnippet/cpp/cricheditview-class_13.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル ワードパッド](../../overview/visual-cpp-samples.md)<br/>
[クラスを表示します。](../../mfc/reference/cctrlview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)<br/>
[CRichEditCntrItem クラス](../../mfc/reference/cricheditcntritem-class.md)
