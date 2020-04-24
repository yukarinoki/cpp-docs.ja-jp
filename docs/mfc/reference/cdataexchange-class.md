---
title: CDataExchange クラス
ms.date: 11/04/2016
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
ms.openlocfilehash: fd1bce7de7ac323dc3099ab4938306768eb95a35
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754623"
---
# <a name="cdataexchange-class"></a>CDataExchange クラス

MFC で使われているダイアログ データ エクスチェンジ (DDX) およびダイアログ データ検証 (DDV) の両ルーチンをサポートします。

## <a name="syntax"></a>構文

```
class CDataExchange
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次のデータ交換を行います。](#cdataexchange)|`CDataExchange` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の手順を実行します。](#fail)|検証が失敗したときに呼び出されます。 フォーカスを前のコントロールにリセットし、例外をスローします。|
|[:PアレCtrl](#preparectrl)|指定されたコントロールをデータ交換または検証用に準備します。 エディット以外のコントロールに使用します。|
|[:Pアレ編集](#prepareeditctrl)|指定されたエディット コントロールをデータ交換または検証用に準備します。|
|[:Pレパレレレク](#prepareolectrl)|指定された OLE コントロールをデータ交換または検証用に準備します。 エディット以外のコントロールに使用します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[m_bSaveAndValidate](#m_bsaveandvalidate)|DDX および DDV の方向のフラグ。|
|[m_pDlgWnd](#m_pdlgwnd)|データ交換が行われるダイアログ ボックスまたはウィンドウ。|

## <a name="remarks"></a>解説

`CDataExchange`は基本クラスを持っていません。

このクラスは、カスタム データ型またはカスタム コントロールのデータ交換ルーチンを記述する場合、または独自のデータ検証ルーチンを記述する場合に使用します。 独自の DDX ルーチンおよび DDV ルーチンの記述の詳細については、[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)を参照してください。 DDX および DDV の概要については、「[ダイアログ データ エクスチェンジ」および「検証と](../../mfc/dialog-data-exchange-and-validation.md)[ダイアログ ボックス](../../mfc/dialog-boxes.md)」を参照してください。

オブジェクト`CDataExchange`は、DDX および DDV が実行するために必要なコンテキスト情報を提供します。 DDX*を使用*してデータ メンバーのダイアログ コントロールの初期値を入力する場合、フラグ m_bSaveAndValidateは FALSE です。 *DDX*を使用してダイアログ コントロールの現在の値をデータ メンバーに設定する場合、および DDV を使用してデータ値を検証する場合、フラグ m_bSaveAndValidateは TRUE です。 DDV 検証が失敗した場合、DDV プロシージャは入力エラーを説明するメッセージ ボックスを表示します。 DDV プロシージャは、フォーカス`Fail`を問題のあるコントロールにリセットし、検証プロセスを停止する例外をスローするために呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

`CDataExchange`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxwin.h

## <a name="cdataexchangecdataexchange"></a><a name="cdataexchange"></a>次のデータ交換を行います。

オブジェクトを構築するには、このメンバー`CDataExchange`関数を呼び出します。

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>パラメーター

*pDlgWnd*<br/>
コントロールを含む親ウィンドウへのポインター。 通常、これは[CDialog](../../mfc/reference/cdialog-class.md)派生オブジェクトです。

*を保存して検証する*<br/>
TRUE の場合、このオブジェクトはデータを検証し、コントロールからメンバーにデータを書き込みます。 FALSE の場合、このオブジェクトは、データをメンバからコントロールに移動します。

### <a name="remarks"></a>解説

ウィンドウの`CDataExchange` [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数に渡すデータ交換オブジェクトに余分な情報を格納するオブジェクトを自分で構築します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

## <a name="cdataexchangefail"></a><a name="fail"></a>次の手順を実行します。

フレームワークは、ダイアログ データ検証 (DDV) 操作が失敗した場合に、このメンバー関数を呼び出します。

```cpp
void Fail();
```

### <a name="remarks"></a>解説

`Fail`検証に失敗したコントロールにフォーカスと選択を復元します (復元するコントロールがある場合)。 `Fail`その後[、CUserException](../../mfc/reference/cuserexception-class.md)型の例外をスローして、検証プロセスを停止します。 例外は、エラーを説明するメッセージ ボックスが表示されます。 DDV の検証が失敗した後、ユーザーは問題のあるコントロールにデータを再入力できます。

カスタム DDV ルーチンの実装者は、`Fail`検証が失敗したときにルーチンから呼び出すことができます。

独自の DDX ルーチンおよび DDV ルーチンの記述の詳細については、[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)を参照してください。 DDX および DDV の概要については、「[ダイアログ データ エクスチェンジとダイアログ](../../mfc/dialog-data-exchange-and-validation.md)[ボックスのトピック」を参照してください](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangem_bsaveandvalidate"></a><a name="m_bsaveandvalidate"></a>m_bSaveAndValidate

このフラグは、ダイアログ データ エクスチェンジ (DDX) 操作の方向を示します。

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>解説

ユーザーがコントロールを編集した後`CDataExchange`で、ダイアログ コントロールからダイアログ クラスのデータ メンバーにデータを移動するためにオブジェクトを使用する場合、フラグは 0 以外です。 ダイアログ クラスのデータ メンバーからダイアログ コントロールを初期化するためにオブジェクトを使用する場合、フラグは 0 です。

ダイアログ データの検証 (DDV) の間も、フラグは 0 以外です。

独自の DDX ルーチンおよび DDV ルーチンの記述の詳細については、[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)を参照してください。 DDX および DDV の概要については、「[ダイアログ データ エクスチェンジとダイアログ](../../mfc/dialog-data-exchange-and-validation.md)[ボックスのトピック」を参照してください](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangem_pdlgwnd"></a><a name="m_pdlgwnd"></a>m_pDlgWnd

ダイアログ データ エクスチェンジ (DDX) または検証 (DDV) が行われる[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインターを含みます。

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>解説

通常、このオブジェクトは[CDialog](../../mfc/reference/cdialog-class.md)オブジェクトです。 カスタム DDX または DDV ルーチンの実装では、このポインターを使用して、操作しているコントロールを含むダイアログ ウィンドウへのアクセスを取得できます。

独自の DDX ルーチンおよび DDV ルーチンの記述の詳細については、[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)を参照してください。 DDX および DDV の概要については、「[ダイアログ データ エクスチェンジとダイアログ](../../mfc/dialog-data-exchange-and-validation.md)[ボックスのトピック」を参照してください](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangepreparectrl"></a><a name="preparectrl"></a>:PアレCtrl

フレームワークは、ダイアログ データ エクスチェンジ (DDX) と検証 (DDV) の指定されたコントロールを準備するために、このメンバー関数を呼び出します。

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>パラメーター

*nIDC*<br/>
DDX または DDV 用に準備するコントロールの ID。

### <a name="return-value"></a>戻り値

DDX または DDV 用に準備されているコントロールの HWND。

### <a name="remarks"></a>解説

代わりに編集コントロールに[対して PrepareEditCtrl](#prepareeditctrl)を使用します。このメンバー関数は、他のすべてのコントロールに使用します。

準備は、クラスにコントロールの HWND を`CDataExchange`格納することで構成されます。 フレームワークは、このハンドルを使用して、DDX または DDV の障害が発生した場合に、フォーカスを以前フォーカスされたコントロールに復元します。

カスタム DDX ルーチンまたは DDV ルーチンの実装`PrepareCtrl`者は、DDX を介してデータを交換したり、DDV を介してデータを検証したりする非編集コントロールをすべて呼び出す必要があります。

独自の DDX ルーチンおよび DDV ルーチンの記述の詳細については、[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)を参照してください。 DDX および DDV の概要については、「[ダイアログ データ エクスチェンジとダイアログ](../../mfc/dialog-data-exchange-and-validation.md)[ボックスのトピック」を参照してください](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangeprepareeditctrl"></a><a name="prepareeditctrl"></a>:Pアレ編集

フレームワークは、ダイアログ データ エクスチェンジ (DDX) と検証 (DDV) の指定されたエディット コントロールを準備するために、このメンバー関数を呼び出します。

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>パラメーター

*nIDC*<br/>
DDX または DDV 用に準備するエディット コントロールの ID。

### <a name="return-value"></a>戻り値

DDX または DDV 用に準備されているエディット コントロールの HWND。

### <a name="remarks"></a>解説

すべての非編集コントロールに対して[PrepareCtrl を](#preparectrl)使用します。

準備は2つのことから成り立っている。 まず、`PrepareEditCtrl`コントロールの HWND をクラスに`CDataExchange`格納します。 フレームワークは、このハンドルを使用して、DDX または DDV の障害が発生した場合に、フォーカスを以前フォーカスされたコントロールに復元します。 次に`PrepareEditCtrl`、データの`CDataExchange`交換または検証が行われるコントロールがエディット コントロールであることを示すフラグをクラスに設定します。

カスタム DDX ルーチンまたは DDV ルーチンの実装`PrepareEditCtrl`者は、DDX を介してデータを交換したり、DDV を介してデータを検証したりするすべてのエディット コントロールを呼び出す必要があります。

独自の DDX ルーチンおよび DDV ルーチンの記述の詳細については、[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)を参照してください。 DDX および DDV の概要については、「[ダイアログ データ エクスチェンジとダイアログ](../../mfc/dialog-data-exchange-and-validation.md)[ボックスのトピック」を参照してください](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangeprepareolectrl"></a><a name="prepareolectrl"></a>:Pレパレレレク

フレームワークは、ダイアログ データ エクスチェンジ (DDX) と検証 (DDV) の指定された OLE コントロールを準備するために、このメンバー関数を呼び出します。

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>パラメーター

*nIDC*<br/>
DDX または DDV 用に準備する OLE コントロールの ID。

### <a name="return-value"></a>戻り値

OLE コントロール サイトへのポインター。

### <a name="remarks"></a>解説

代わりに編集コントロールに対[して PrepareEditCtrl](#prepareeditctrl)を使用するか、他のすべての OLE コントロール以外のコントロールに対して[PrepareCtrl](#preparectrl)を使用します。

カスタム DDX ルーチンまたは DDV ルーチンの実装`PrepareOleCtrl`者は、DDX を介してデータを交換したり、DDV を介してデータを検証したりするすべての OLE コントロールを呼び出す必要があります。

独自の DDX ルーチンおよび DDV ルーチンの記述の詳細については、[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)を参照してください。 DDX および DDV の概要については、「[ダイアログ データ エクスチェンジとダイアログ](../../mfc/dialog-data-exchange-and-validation.md)[ボックスのトピック」を参照してください](../../mfc/dialog-boxes.md)。

## <a name="see-also"></a>関連項目

[MFC サンプル ビューレックス](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
