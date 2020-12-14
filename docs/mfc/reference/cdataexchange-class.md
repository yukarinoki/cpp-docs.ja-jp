---
description: '詳細情報: CDataExchange クラス'
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
ms.openlocfilehash: 36d11dc2b74142bd869b0e7b459d8bdb888b2cef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222178"
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
|[CDataExchange:: CDataExchange](#cdataexchange)|`CDataExchange` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDataExchange:: Fail](#fail)|検証が失敗したときに呼び出されます。 フォーカスを前のコントロールにリセットし、例外をスローします。|
|[CDataExchange::P repareCtrl](#preparectrl)|データ交換または検証のために、指定されたコントロールを準備します。 非編集コントロールに使用します。|
|[CDataExchange::P repareEditCtrl](#prepareeditctrl)|データ交換または検証のために、指定されたエディットコントロールを準備します。|
|[CDataExchange::P repareOleCtrl](#prepareolectrl)|データ交換または検証のために、指定された OLE コントロールを準備します。 非編集コントロールに使用します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CDataExchange:: m_bSaveAndValidate](#m_bsaveandvalidate)|DDX および DDV の方向を示すフラグ。|
|[CDataExchange:: m_pDlgWnd](#m_pdlgwnd)|データ交換が行われるダイアログボックスまたはウィンドウ。|

## <a name="remarks"></a>解説

`CDataExchange` に基底クラスがありません。

カスタムデータ型またはコントロールのデータ交換ルーチンを作成する場合、または独自のデータ検証ルーチンを作成する場合は、このクラスを使用します。 独自の DDX ルーチンおよび DDV ルーチンを記述する方法の詳細については、「 [テクニカルノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)」を参照してください。 DDX と DDV の概要については、「ダイアログボックスの [データエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md) 」および「 [ダイアログボックス](../../mfc/dialog-boxes.md)」を参照してください。

オブジェクトは、 `CDataExchange` DDX および DDV を実行するために必要なコンテキスト情報を提供します。 DDX を使用してデータメンバーからダイアログコントロールの初期値を埋める場合、フラグ *m_bSaveAndValidate* は FALSE です。 フラグ *m_bSaveAndValidate* は、ダイアログコントロールの現在の値をデータメンバーに設定するために DDX が使用されている場合、およびデータ値の検証に DDV が使用される場合に TRUE になります。 DDV 検証が失敗した場合、DDV プロシージャによって、入力エラーを説明するメッセージボックスが表示されます。 次に、を呼び出して、 `Fail` 問題のあるコントロールにフォーカスをリセットし、例外をスローして検証プロセスを停止します。

## <a name="inheritance-hierarchy"></a>継承階層

`CDataExchange`

## <a name="requirements"></a>要件

**ヘッダー:** afxwin.h

## <a name="cdataexchangecdataexchange"></a><a name="cdataexchange"></a> CDataExchange:: CDataExchange

オブジェクトを構築するには、このメンバー関数を呼び出し `CDataExchange` ます。

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>パラメーター

*pDlgWnd*<br/>
コントロールを格納している親ウィンドウへのポインター。 通常、これは、 [CDialog](../../mfc/reference/cdialog-class.md)によって派生したオブジェクトです。

*bSaveAndValidate*<br/>
TRUE の場合、このオブジェクトはデータを検証してから、コントロールからのデータをメンバーに書き込みます。 FALSE の場合、このオブジェクトはデータをメンバーからコントロールに移動します。

### <a name="remarks"></a>解説

`CDataExchange`ウィンドウの[CWnd::D odataexchange](../../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数に渡す追加情報をデータ交換オブジェクトに格納するために、自身でオブジェクトを構築します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

## <a name="cdataexchangefail"></a><a name="fail"></a> CDataExchange:: Fail

フレームワークは、ダイアログデータ検証 (DDV) 操作が失敗したときにこのメンバー関数を呼び出します。

```cpp
void Fail();
```

### <a name="remarks"></a>解説

`Fail` 検証に失敗したコントロール (復元するコントロールがある場合) にフォーカスと選択を復元します。 `Fail` は、検証プロセスを停止するために、 [Cuserexception](../../mfc/reference/cuserexception-class.md) 型の例外をスローします。 例外により、表示されるエラーを説明するメッセージボックスが表示されます。 DDV 検証が失敗した後、ユーザーは問題のあるコントロールにデータを再入力できます。

カスタム DDV ルーチンを実装する `Fail` と、検証が失敗したときにルーチンからを呼び出すことができます。

独自の DDX ルーチンおよび DDV ルーチンを記述する方法の詳細については、「 [テクニカルノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)」を参照してください。 DDX と DDV の概要については、「 [ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md) および [ダイアログボックスのトピック](../../mfc/dialog-boxes.md)」を参照してください。

## <a name="cdataexchangem_bsaveandvalidate"></a><a name="m_bsaveandvalidate"></a> CDataExchange:: m_bSaveAndValidate

このフラグは、ダイアログデータエクスチェンジ (DDX) 操作の方向を示します。

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>解説

ユーザーがコントロールを編集し `CDataExchange` た後に、オブジェクトがダイアログコントロールからダイアログクラスのデータメンバーにデータを移動するために使用されている場合、フラグは0以外になります。 ダイアログクラスのデータメンバーからダイアログコントロールを初期化するためにオブジェクトが使用されている場合、フラグは0になります。

ダイアログデータ検証 (DDV) では、フラグも0以外になります。

独自の DDX ルーチンおよび DDV ルーチンを記述する方法の詳細については、「 [テクニカルノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)」を参照してください。 DDX と DDV の概要については、「 [ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md) および [ダイアログボックスのトピック](../../mfc/dialog-boxes.md)」を参照してください。

## <a name="cdataexchangem_pdlgwnd"></a><a name="m_pdlgwnd"></a> CDataExchange:: m_pDlgWnd

ダイアログデータエクスチェンジ (DDX) または検証 (DDV) が行われている [CWnd](../../mfc/reference/cwnd-class.md) オブジェクトへのポインターを格納します。

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>解説

通常、このオブジェクトは、 [CDialog](../../mfc/reference/cdialog-class.md) オブジェクトです。 カスタム DDX または DDV ルーチンを実装すると、このポインターを使用して、動作しているコントロールを含むダイアログウィンドウへのアクセスを取得できます。

独自の DDX ルーチンおよび DDV ルーチンを記述する方法の詳細については、「 [テクニカルノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)」を参照してください。 DDX と DDV の概要については、「 [ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md) および [ダイアログボックスのトピック](../../mfc/dialog-boxes.md)」を参照してください。

## <a name="cdataexchangepreparectrl"></a><a name="preparectrl"></a> CDataExchange::P repareCtrl

フレームワークは、このメンバー関数を呼び出して、ダイアログデータエクスチェンジ (DDX) および検証 (DDV) 用に指定されたコントロールを準備します。

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>パラメーター

*nIDC*<br/>
DDX または DDV 用に準備するコントロールの ID。

### <a name="return-value"></a>戻り値

DDX または DDV 用に準備されているコントロールの HWND。

### <a name="remarks"></a>解説

エディットコントロールではなく [PrepareEditCtrl](#prepareeditctrl) を使用します。このメンバー関数は、他のすべてのコントロールに使用します。

準備は、コントロールの HWND をクラスに格納することで構成され `CDataExchange` ます。 このハンドルは、DDX または DDV エラーが発生した場合に、前にフォーカスしたコントロールにフォーカスを戻すために、このハンドルを使用します。

カスタム DDX または DDV ルーチンを実装する場合は `PrepareCtrl` 、ddx を介してデータを交換したり、ddv を使用してデータを検証したりするすべての非編集コントロールに対してを呼び出す必要があります。

独自の DDX ルーチンおよび DDV ルーチンを記述する方法の詳細については、「 [テクニカルノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)」を参照してください。 DDX と DDV の概要については、「 [ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md) および [ダイアログボックスのトピック](../../mfc/dialog-boxes.md)」を参照してください。

## <a name="cdataexchangeprepareeditctrl"></a><a name="prepareeditctrl"></a> CDataExchange::P repareEditCtrl

フレームワークは、このメンバー関数を呼び出して、ダイアログデータエクスチェンジ (DDX) および検証 (DDV) 用に指定されたエディットコントロールを準備します。

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>パラメーター

*nIDC*<br/>
DDX または DDV 用に準備する編集コントロールの ID。

### <a name="return-value"></a>戻り値

DDX または DDV 用に準備されている編集コントロールの HWND。

### <a name="remarks"></a>解説

すべての非編集コントロールには、代わりに [PrepareCtrl](#preparectrl) を使用してください。

準備は、次の2つの要素で構成されます。 最初に、は `PrepareEditCtrl` コントロールの HWND をクラスに格納し `CDataExchange` ます。 このハンドルは、DDX または DDV エラーが発生した場合に、前にフォーカスしたコントロールにフォーカスを戻すために、このハンドルを使用します。 次に、 `PrepareEditCtrl` `CDataExchange` データが交換または検証されるコントロールが編集コントロールであることを示すフラグをクラスに設定します。

カスタム DDX または DDV ルーチンの実装では `PrepareEditCtrl` 、ddx 経由でデータを交換したり、ddv を使用してデータを検証したりするすべての編集コントロールに対してを呼び出す必要があります。

独自の DDX ルーチンおよび DDV ルーチンを記述する方法の詳細については、「 [テクニカルノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)」を参照してください。 DDX と DDV の概要については、「 [ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md) および [ダイアログボックスのトピック](../../mfc/dialog-boxes.md)」を参照してください。

## <a name="cdataexchangeprepareolectrl"></a><a name="prepareolectrl"></a> CDataExchange::P repareOleCtrl

フレームワークは、このメンバー関数を呼び出して、ダイアログデータエクスチェンジ (DDX) および検証 (DDV) 用に指定された OLE コントロールを準備します。

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>パラメーター

*nIDC*<br/>
DDX または DDV 用に準備する OLE コントロールの ID。

### <a name="return-value"></a>戻り値

OLE コントロールサイトへのポインター。

### <a name="remarks"></a>解説

他のすべての非 OLE コントロールに対しては、エディットコントロールまたは[PrepareCtrl](#preparectrl)の代わりに[PrepareEditCtrl](#prepareeditctrl)を使用します。

カスタム DDX または DDV ルーチンの実装では `PrepareOleCtrl` 、ddx を介してデータを交換するすべての OLE コントロール、または ddv を使用したデータの検証を行う必要があります。

独自の DDX ルーチンおよび DDV ルーチンを記述する方法の詳細については、「 [テクニカルノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)」を参照してください。 DDX と DDV の概要については、「 [ダイアログデータエクスチェンジと検証](../../mfc/dialog-data-exchange-and-validation.md) および [ダイアログボックスのトピック](../../mfc/dialog-boxes.md)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC のサンプル VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)
