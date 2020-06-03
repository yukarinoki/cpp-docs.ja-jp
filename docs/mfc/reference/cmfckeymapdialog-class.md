---
title: CMFCKeyMapDialog クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 22aa006ce214ca720192bb761e2ff2b35a64fce3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374416"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog クラス

この`CMFCKeyMapDialog`クラスは、コマンドをキーボードのキーにマップするコントロールをサポートしています。

## <a name="syntax"></a>構文

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::CMFC キーマップ ダイアログ](#cmfckeymapdialog)|`CMFCKeyMapDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログ ボックス::Do モーダル](#domodal)|キーボード マッピング ダイアログ ボックスを表示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ダイアログボックス::フォーマットアイテム](#formatitem)|キー マッピングを記述する文字列を構築するために、フレームワークによって呼び出されます。 既定では、文字列にはコマンド名、使用するショートカット キー、およびショートカット キーの説明が含まれます。|
|[ダイアログボックス::コマンドキー](#getcommandkeys)|指定したコマンドに関連付けられているショートカット キーの一覧を含む文字列を取得します。|
|[ダイアログボックス::挿入アイテム](#oninsertitem)|キーボード マッピング コントロールをサポートする内部リスト コントロールに新しい項目が挿入される前に、フレームワークによって呼び出されます。|
|[ダイアログボックス::オンプリントヘッダー](#onprintheader)|新しいページにキーボード マップのヘッダーを印刷するために、フレームワークによって呼び出されます。|
|[ダイアログボックス::オンプリントアイテム](#onprintitem)|キーボード マッピング項目を印刷するために、フレームワークによって呼び出されます。|
|[ダイアログボックス::オンセットカラム](#onsetcolumns)|キーボード マッピング コントロールをサポートする内部リスト コントロールの列のキャプションを設定するために、フレームワークによって呼び出されます。|
|[ダイアログ ボックス::Pリント キーマップ](#printkeymap)|ユーザーが **[印刷**] ボタンをクリックしたときに、フレームワークによって呼び出されます。|
|[ダイアログボックス::列幅の設定](#setcolumnswidth)|キーボード マッピング コントロールをサポートする内部リスト コントロールの列の幅を設定するために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

このクラス`CMFCKeyMapDialog`を使用して、変更可能なキーボード マッピング ダイアログ ボックスを実装します。 ダイアログ ボックスでは、リスト ビュー コントロールを使用して、キーボード ショートカットと、関連するコマンドを表示します。

アプリケーションで`CMFCKeyMapDialog`クラスを使用するには、`CMFCKeyMapDialog`メイン フレーム ウィンドウへのポインターをコンストラクターへのパラメーターとして渡します。 次に、`DoModal`モーダル ダイアログ ボックスを開始するメソッドを呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxkeymapdialog.h

## <a name="cmfckeymapdialogcmfckeymapdialog"></a><a name="cmfckeymapdialog"></a>ダイアログ ボックス::CMFC キーマップ ダイアログ

`CMFCKeyMapDialog` オブジェクトを構築します。

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>パラメーター

*親フレーム*<br/>
[in]`CMFCKeyMapDialog`オブジェクトの親ウィンドウへのポインター。

*b 印刷を有効にする*<br/>
[in]アクセラレータ キーの一覧を印刷できる場合は TRUE。それ以外の場合は FALSE。 デフォルトは FALSE です。

### <a name="remarks"></a>解説

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に`CMFCKeyMapDialog`示します。 この例は[、Visual Studio のデモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

## <a name="cmfckeymapdialogdomodal"></a><a name="domodal"></a>ダイアログ ボックス::Do モーダル

キーボード マッピング ダイアログ ボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

[メソッド](../../mfc/reference/cdialog-class.md#enddialog)に渡される IDOK または IDCANCEL などの符号付き整数。 このメソッドは、ダイアログ ボックスを閉じます。 詳細については[、「CDialog::DoModal」を参照してください](../../mfc/reference/cdialog-class.md#domodal)。

### <a name="remarks"></a>解説

キーボード マッピング ダイアログ ボックスでは、アクセラレータ キーを選択して、さまざまなカテゴリのコマンドに割り当てることができます。 また、選択したアクセラレータ キーとその説明をクリップボードにコピーすることもできます。

## <a name="cmfckeymapdialogformatitem"></a><a name="formatitem"></a>ダイアログボックス::フォーマットアイテム

キー マッピングを記述する文字列を構築するために、フレームワークによって呼び出されます。 既定では、文字列にはコマンド名、使用するショートカット キー、およびショートカット キーの説明が含まれます。

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>パラメーター

*Nitem*<br/>
[in]キー マッピングの内部リスト内の項目の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

書式設定`CString`されたアイテムのテキストを格納するオブジェクト。

### <a name="remarks"></a>解説

## <a name="cmfckeymapdialoggetcommandkeys"></a><a name="getcommandkeys"></a>ダイアログボックス::コマンドキー

文字列値を取得します。 文字列には、指定したコマンドに関連付けられているショートカット キーの一覧が含まれています。

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>パラメーター

*UICmdID*<br/>
[in]コマンド ID。

### <a name="return-value"></a>戻り値

指定したコマンドに関連付けられているショートカット キーのセミコロン区切り (';') リスト。

### <a name="remarks"></a>解説

## <a name="cmfckeymapdialogoninsertitem"></a><a name="oninsertitem"></a>ダイアログボックス::挿入アイテム

キーボード マッピング コントロールをサポートする内部リスト コントロールに新しい項目が挿入される前に、フレームワークによって呼び出されます。

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>パラメーター

*ボタン*<br/>
[in]キーボード のキーの組み合わせをコマンド名と説明にマップするために使用されるツール バー ボタンへのポインター。 キー マップ項目は、内部リスト コントロールに格納されます。

*Nitem*<br/>
[in]内部リスト コントロール内の新しいキー マップ項目を挿入する位置を指定する 0 から始まるインデックス。

### <a name="remarks"></a>解説

## <a name="cmfckeymapdialogonprintheader"></a><a name="onprintheader"></a>ダイアログボックス::オンプリントヘッダー

新しいページにキーボード マップのヘッダーを印刷するために、フレームワークによって呼び出されます。

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>パラメーター

*Dc*<br/>
[in]プリンターのデバイス コンテキスト。

*nページ*<br/>
[in]印刷するページ番号。

*Cx*<br/>
[in]ヘッダーの水平方向のオフセット (ピクセル単位)。

### <a name="return-value"></a>戻り値

正常に印刷された場合は、印刷されたテキストの高さ。 詳細については[、CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)の戻り値セクションを参照してください。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを使用してキーボード マップを印刷します。 既定では、このメソッドはページ番号、アプリケーション名、およびダイアログ ボックスのタイトルを出力します。

## <a name="cmfckeymapdialogonprintitem"></a><a name="onprintitem"></a>ダイアログボックス::オンプリントアイテム

キーボード マッピング項目を印刷するために、フレームワークによって呼び出されます。

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>パラメーター

*Dc*<br/>
[in]プリンターのデバイス コンテキスト。

*Nitem*<br/>
[in]印刷する項目の 0 から始まるインデックス。

*Y*<br/>
[in]ページの上端と項目の位置との間の垂直オフセット。

*Cx*<br/>
[in]ページの左側と項目の位置との間の水平オフセット。

*をクリックします。*<br/>
[in]印刷項目の最適な高さを計算する場合は TRUE。FALSE を指定すると、印刷項目が既定のスペースに収まるように切り詰められます。

### <a name="return-value"></a>戻り値

印刷される項目の高さ。

### <a name="remarks"></a>解説

フレームワークは、キー マップ ダイアログ ボックス項目を印刷するために、このメソッドを呼び出します。 既定では、このメソッドは、アイテムのコマンド名、ショートカット キー、およびコマンドの説明を出力します。

## <a name="cmfckeymapdialogonsetcolumns"></a><a name="onsetcolumns"></a>ダイアログボックス::オンセットカラム

キーボード マッピング コントロールをサポートする内部リスト コントロールの列のキャプションを設定するために、フレームワークによって呼び出されます。

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>解説

既定では、このメソッドは 3 つのリソースから列のキャプションを取得します。 コマンド列のキャプションはIDS_AFXBARRES_COMMANDから、キー列のキャプションはIDS_AFXBARRES_KEYSから、説明列のキャプションはIDS_AFXBARRES_DESCRIPTION。

## <a name="cmfckeymapdialogprintkeymap"></a><a name="printkeymap"></a>ダイアログ ボックス::Pリント キーマップ

ユーザーが **[印刷**] ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>解説

この`PrintKeyMap`メソッドは、キー マップを出力します。 新しい印刷ジョブを開始し、すべてのキー マッピングが印刷されるまで[、CMFCKeyMapDialog::OnPrintヘッダー](#onprintheader)と[CMFCKeyMapDialog::OnPrintItem](#onprintitem)メソッドを繰り返し呼び出します。

## <a name="cmfckeymapdialogsetcolumnswidth"></a><a name="setcolumnswidth"></a>ダイアログボックス::列幅の設定

キーボード マッピング コントロールをサポートする内部リスト コントロールの列の幅を設定するために、フレームワークによって呼び出されます。

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>解説

このメソッドは、内部リスト コントロールの列を既定の幅に設定します。 まず、ショートカット キー列の幅が計算されます。 その後、残りの幅の 3 分の 1 がコマンド列に割り当てられ、残りの 3 分の 2 が記述列に割り振られます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/ckeyboardmanager-class.md)
