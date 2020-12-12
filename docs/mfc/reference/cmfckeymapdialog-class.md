---
description: '詳細情報: CMFCKeyMapDialog クラス'
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
ms.openlocfilehash: e339edb54b9c381dd2b27c9ee3ec7566308ae434
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265234"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog クラス

クラスは、 `CMFCKeyMapDialog` コマンドをキーボードのキーにマップするコントロールをサポートします。

## <a name="syntax"></a>構文

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCKeyMapDialog:: CMFCKeyMapDialog](#cmfckeymapdialog)|`CMFCKeyMapDialog` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCKeyMapDialog::D oModal](#domodal)|[キーボードマップ] ダイアログボックスを表示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCKeyMapDialog:: FormatItem](#formatitem)|キーマッピングを記述する文字列を構築するために、フレームワークによって呼び出されます。 既定では、文字列にはコマンド名、使用するショートカットキー、およびショートカットキーの説明が含まれています。|
|[CMFCKeyMapDialog:: GetCommandKeys](#getcommandkeys)|指定したコマンドに関連付けられているショートカットキーのリストを格納している文字列を取得します。|
|[CMFCKeyMapDialog:: OnInsertItem](#oninsertitem)|キーボードマップコントロールをサポートする内部リストコントロールに新しい項目が挿入される前に、フレームワークによって呼び出されます。|
|[CMFCKeyMapDialog:: OnPrintHeader](#onprintheader)|新しいページのキーボードマップのヘッダーを印刷するために、フレームワークによって呼び出されます。|
|[CMFCKeyMapDialog:: OnPrintItem](#onprintitem)|キーボードマップ項目を出力するためにフレームワークによって呼び出されます。|
|[CMFCKeyMapDialog:: OnSetColumns](#onsetcolumns)|キーボードマップコントロールをサポートする内部リストコントロール内の列のキャプションを設定するために、フレームワークによって呼び出されます。|
|[CMFCKeyMapDialog::P rintKeyMap](#printkeymap)|ユーザーが [ **印刷** ] ボタンをクリックしたときにフレームワークによって呼び出されます。|
|[CMFCKeyMapDialog:: Set列幅](#setcolumnswidth)|キーボードマップコントロールをサポートする内部リストコントロール内の列の幅を設定するために、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

クラスを使用して `CMFCKeyMapDialog` 、サイズ変更可能なキーボードマップダイアログボックスを実装します。 ダイアログボックスでは、リストビューコントロールを使用して、キーボードショートカットとそれに関連付けられたコマンドを表示します。

アプリケーションでクラスを使用するには `CMFCKeyMapDialog` 、メインフレームウィンドウへのポインターをコンストラクターのパラメーターとして渡し `CMFCKeyMapDialog` ます。 次に、メソッドを呼び出して `DoModal` モーダルダイアログボックスを開始します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxkeymapdialog

## <a name="cmfckeymapdialogcmfckeymapdialog"></a><a name="cmfckeymapdialog"></a> CMFCKeyMapDialog:: CMFCKeyMapDialog

`CMFCKeyMapDialog` オブジェクトを構築します。

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>パラメーター

*pWndParentFrame*<br/>
からオブジェクトの親ウィンドウへのポインター `CMFCKeyMapDialog` 。

*bEnablePrint*<br/>
からアクセラレータキーの一覧を印刷できる場合は TRUE。それ以外の場合は FALSE。 既定値は FALSE です。

### <a name="remarks"></a>解説

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に示し `CMFCKeyMapDialog` ます。 この例は、 [Visual Studio のデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

## <a name="cmfckeymapdialogdomodal"></a><a name="domodal"></a> CMFCKeyMapDialog::D oModal

[キーボードマップ] ダイアログボックスを表示します。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>戻り値

[CDialog:: EndDialog](../../mfc/reference/cdialog-class.md#enddialog)メソッドに渡される、IDOK や IDCANCEL などの符号付き整数。 その後、メソッドによってダイアログボックスが閉じられます。 詳細については、「 [CDialog::D oModal](../../mfc/reference/cdialog-class.md#domodal)」を参照してください。

### <a name="remarks"></a>解説

[キーボードマップ] ダイアログボックスを使用すると、さまざまなカテゴリのコマンドにアクセラレータキーを選択して割り当てることができます。 また、選択したアクセラレータキーとその説明をクリップボードにコピーできます。

## <a name="cmfckeymapdialogformatitem"></a><a name="formatitem"></a> CMFCKeyMapDialog:: FormatItem

キーマッピングを記述する文字列を構築するために、フレームワークによって呼び出されます。 既定では、文字列にはコマンド名、使用するショートカットキー、およびショートカットキーの説明が含まれています。

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>パラメーター

*nItem*<br/>
からキーマッピングの内部リストに含まれる項目の0から始まるインデックス。

### <a name="return-value"></a>戻り値

`CString`書式設定された項目テキストを格納しているオブジェクト。

### <a name="remarks"></a>解説

## <a name="cmfckeymapdialoggetcommandkeys"></a><a name="getcommandkeys"></a> CMFCKeyMapDialog:: GetCommandKeys

文字列値を取得します。 文字列には、指定したコマンドに関連付けられているショートカットキーの一覧が含まれています。

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>パラメーター

*uiCmdID*<br/>
からコマンド ID。

### <a name="return-value"></a>戻り値

指定したコマンドに関連付けられているショートカットキーの、セミコロンで区切られた ('; ') リスト。

### <a name="remarks"></a>解説

## <a name="cmfckeymapdialogoninsertitem"></a><a name="oninsertitem"></a> CMFCKeyMapDialog:: OnInsertItem

キーボードマップコントロールをサポートする内部リストコントロールに新しい項目が挿入される前に、フレームワークによって呼び出されます。

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>パラメーター

*pButton*<br/>
からキーボードキーの組み合わせをコマンド名と説明にマップするために使用されるツールバーボタンへのポインター。 キーマップ項目は、内部リストコントロールに格納されます。

*nItem*<br/>
から内部リストコントロール内の新しいキーマップ項目の挿入位置を指定する0から始まるインデックス。

### <a name="remarks"></a>解説

## <a name="cmfckeymapdialogonprintheader"></a><a name="onprintheader"></a> CMFCKeyMapDialog:: OnPrintHeader

新しいページのキーボードマップのヘッダーを印刷するために、フレームワークによって呼び出されます。

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
からプリンターのデバイスコンテキスト。

*nPage*<br/>
から印刷するページ番号。

*シリーズ*<br/>
からヘッダーの水平方向のオフセット (ピクセル単位)。

### <a name="return-value"></a>戻り値

成功した場合は、印刷されたテキストの高さ。 詳細については、「 [CDC::D rawText](../../mfc/reference/cdc-class.md#drawtext)」の「戻り値」セクションを参照してください。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを使用してキーボードマップを印刷します。 既定では、このメソッドはページ番号、アプリケーション名、およびダイアログボックスのタイトルを出力します。

## <a name="cmfckeymapdialogonprintitem"></a><a name="onprintitem"></a> CMFCKeyMapDialog:: OnPrintItem

キーボードマップ項目を出力するためにフレームワークによって呼び出されます。

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>パラメーター

*dc*<br/>
からプリンターのデバイスコンテキスト。

*nItem*<br/>
から印刷する項目の0から始まるインデックス。

*y*<br/>
からページの上端と項目の位置との間の垂直方向のオフセット。

*シリーズ*<br/>
からページの左側と項目の位置との間の水平方向のオフセット。

*はい*<br/>
から印刷項目の最適な高さを計算する場合は TRUE。既定のスペースに収まるように印刷項目を切り捨てる場合は FALSE。

### <a name="return-value"></a>戻り値

印刷される項目の高さ。

### <a name="remarks"></a>解説

フレームワークは、このメソッドを呼び出して、キーマップのダイアログボックス項目を印刷します。 既定では、このメソッドは項目のコマンド名、ショートカットキー、およびコマンドの説明を出力します。

## <a name="cmfckeymapdialogonsetcolumns"></a><a name="onsetcolumns"></a> CMFCKeyMapDialog:: OnSetColumns

キーボードマップコントロールをサポートする内部リストコントロール内の列のキャプションを設定するために、フレームワークによって呼び出されます。

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>解説

既定では、このメソッドは3つのリソースの列のキャプションを取得します。 コマンド列のキャプションは IDS_AFXBARRES_COMMAND からのもので、キー列のキャプションは IDS_AFXBARRES_KEYS からのものであり、説明列のキャプションは IDS_AFXBARRES_DESCRIPTION です。

## <a name="cmfckeymapdialogprintkeymap"></a><a name="printkeymap"></a> CMFCKeyMapDialog::P rintKeyMap

ユーザーが [ **印刷** ] ボタンをクリックしたときにフレームワークによって呼び出されます。

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>解説

メソッドは、 `PrintKeyMap` キーマップを出力します。 このメソッドは、新しい印刷ジョブを開始し、すべてのキーマッピングが出力されるまで、 [Cmfckeymapdialog:: OnPrintHeader](#onprintheader) メソッドと [Cmfckeymapdialog:: onprintitem](#onprintitem) メソッドを繰り返し呼び出します。

## <a name="cmfckeymapdialogsetcolumnswidth"></a><a name="setcolumnswidth"></a> CMFCKeyMapDialog:: Set列幅

キーボードマップコントロールをサポートする内部リストコントロール内の列の幅を設定するために、フレームワークによって呼び出されます。

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>解説

このメソッドは、内部リストコントロールの列を既定の幅に設定します。 まず、[ショートカットキー] 列の幅が計算されます。 その後、残りの幅の 1 ~ 3 はコマンド列に割り当てられ、残りの 2 ~ 3 は [説明] 列に割り当てられます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[Cのマネージャークラス](../../mfc/reference/ckeyboardmanager-class.md)
