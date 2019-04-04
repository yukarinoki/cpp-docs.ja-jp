---
title: CRecordView クラス
ms.date: 11/04/2016
f1_keywords:
- CRecordView
- AFXDB/CRecordView
- AFXDB/CRecordView::CRecordView
- AFXDB/CRecordView::IsOnFirstRecord
- AFXDB/CRecordView::IsOnLastRecord
- AFXDB/CRecordView::OnGetRecordset
- AFXDB/CRecordView::OnMove
helpviewer_keywords:
- CRecordView [MFC], CRecordView
- CRecordView [MFC], IsOnFirstRecord
- CRecordView [MFC], IsOnLastRecord
- CRecordView [MFC], OnGetRecordset
- CRecordView [MFC], OnMove
- CRecordView [MFC], OnMove
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
ms.openlocfilehash: a91a9e320b4221b04bbcf996ffa60f1de4b35ec5
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262468"
---
# <a name="crecordview-class"></a>CRecordView クラス

コントロール内にデータベース レコードを表示するビューです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CRecordView : public CFormView
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[よ](#crecordview)|`CRecordView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CRecordView::IsOnFirstRecord](#isonfirstrecord)|現在のレコードが関連付けられているレコード セットの最初のレコードの場合、0 以外の値を返します。|
|[CRecordView::IsOnLastRecord](#isonlastrecord)|現在のレコードが関連付けられているレコード セットの最後のレコードの場合、0 以外の値を返します。|
|[CRecordView::OnGetRecordset](#ongetrecordset)|派生したクラスのオブジェクトへのポインターを返します`CRecordset`します。 ClassWizard では、この関数をオーバーライドし、必要な場合、レコード セットを作成します。|
|[CRecordView::OnMove](#onmove)||

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CRecordView::OnMove](#onmove)|現在のレコードが変更された場合、データ ソースに更新します。 し、指定されたレコードに移動します (次に、前の最初のページまたは最後)。|

## <a name="remarks"></a>Remarks

ビューが、フォーム ビューに直接接続されている、`CRecordset`オブジェクト。 ビューはダイアログ テンプレート リソースから作成されのフィールドが表示されます、`CRecordset`ダイアログ テンプレートのコントロール内のオブジェクト。 `CRecordView`オブジェクト ダイアログ データ エクス (チェンジ DDX) とレコード フィールド エクス (チェンジ RFX) を使用して、フォーム上のコントロールとレコード セットのフィールドの間のデータの移動を自動化します。 `CRecordView` 移動するための既定の実装を提供、最初に [次へ]、前、または最後のレコードとインターフェイス ビューで現在のレコードを更新します。

> [!NOTE]
>  Open Database Connectivity (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスを使用している場合は、クラスを使用して[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)代わりにします。 詳細については、この記事を参照してください。[概要。データベース プログラミング](../../data/data-access-programming-mfc-atl.md)します。

レコード ビューを作成する最も一般的な方法は、アプリケーション ウィザードでです。 アプリケーション ウィザードでは、レコード ビュー クラスとその関連するレコード セット クラスは、初期アプリケーションのスケルトンの一部としての両方を作成します。 アプリケーション ウィザードを使用してレコード ビュー クラスを作成しない場合に、後で ClassWizard で作成できます。 1 つのフォームが単に必要な場合は、アプリケーション ウィザードを使用が簡単です。 ClassWizard では、開発プロセスの後半で、レコード ビューを使用するかを決定できます。 レコード セット クラスの名前付けで詳細に制御が提供されるため、最も柔軟なアプローチは ClassWizard を使用してレコード ビューとレコード セットを個別に作成し、それらを接続するとします。H/。CPP ファイル。 このアプローチでは、同じのレコード セット クラスで複数のレコード ビューがあることもできます。

メニュー (および必要に応じてツールバー) に、レコード ビューのレコード間を移動するエンドユーザーのために、アプリケーション ウィザードで作成リソースを移動するために、最初次、前、または最後のレコード。 ClassWizard でレコード ビュー クラスを作成する場合は、これらのリソースを自分で作成メニューとビットマップ エディター必要があります。

レコード間を移動するための既定の実装については、`IsOnFirstRecord`と`IsOnLastRecord`」および「[レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)を参照してください。

`CRecordView` レコード ビューは、ユーザー インターフェイスを更新できるようにはのレコード セット内のユーザーの位置を追跡します。 ユーザーは、レコード セットのいずれかの端に移動、レコード ビュー、ユーザー インターフェイス オブジェクトを無効にします: メニュー項目またはツール バー ボタンなど — を移動する同じ方向にさらにします。

宣言して、レコード ビューとレコード セット クラスを使用する方法の詳細についてを参照してください「の作成、レコード ビューのデザインと」記事[レコード ビュー](../../data/record-views-mfc-data-access.md)します。 レコード ビューの動作とその使用方法の詳細については、この記事を参照してください。[レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`CRecordView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdb.h

##  <a name="crecordview"></a>  CRecordView::CRecordView

派生した型のオブジェクトを作成するときに`CRecordView`、いずれかの形式のビュー オブジェクトを初期化し、ビューの基になるダイアログ リソースの識別にコンス トラクターを呼び出します。

```
explicit CRecordView(LPCTSTR lpszTemplateName);
explicit CRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>パラメーター

*lpszTemplateName*<br/>
ダイアログ テンプレート リソースの名前を表す null で終わる文字列が含まれています。

*nIDTemplate*<br/>
ダイアログ テンプレート リソースの ID 番号が含まれています。

### <a name="remarks"></a>Remarks

名前 (コンス トラクターに渡す引数として文字列) で、または ID (符号なし整数の引数として渡します) か、リソースを識別できます。 リソースを使用して ID はお勧めします。

> [!NOTE]
>  派生クラスの*する必要があります*独自のコンス トラクターを指定します。 派生クラスのコンス トラクターでコンス トラクターを呼び出す`CRecordView::CRecordView`リソース名または ID を次の例で示すように、引数として使用します。

`CRecordView::OnInitialUpdate` 呼び出し`UpdateData`、呼び出す`DoDataExchange`します。 この最初の呼び出し`DoDataExchange`接続`CRecordView`に (間接的に) 制御`CRecordset`ClassWizard で作成されたデータ メンバーのフィールドします。 これらのデータ メンバーは、基本クラスを呼び出した後まで使用できません`CFormView::OnInitialUpdate`メンバー関数。

> [!NOTE]
>  ClassWizard を使用する場合、ウィザードで定義、**列挙型**値`CRecordView::IDD`クラスの宣言で指定し、コンス トラクターは、のメンバー初期化リストで使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#32](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]

##  <a name="isonfirstrecord"></a>  CRecordView::IsOnFirstRecord

現在のレコードがレコード ビューに関連付けられているレコード セット オブジェクトの最初のレコードであるかどうかを確認するには、このメンバー関数を呼び出します。

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>戻り値

現在のレコードが最初のレコードはレコード セットの場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数は ClassWizard で作成されたコマンド更新ハンドラーの既定の独自の実装を記述するために便利です。

ユーザーは、最初のレコードに移動した場合、フレームワークには、最初または前のレコードに移動のためのユーザー インターフェイス オブジェクトが無効にします。

##  <a name="isonlastrecord"></a>  CRecordView::IsOnLastRecord

現在のレコードがレコード ビューに関連付けられているレコード セット オブジェクトの最後のレコードであるかどうかを確認するには、このメンバー関数を呼び出します。

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>戻り値

現在のレコードが最後のレコードはレコード セットの場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数は、classwizard レコード間を移動するためのユーザー インターフェイスをサポートするためにコマンド更新ハンドラーの既定の独自の実装を記述するために便利です。

> [!CAUTION]
>  ビューは、ユーザーがそれより前に移動するまで、レコード セットの末尾を検出できないことを除いて、この関数の結果は信頼性の高い。 ユーザーは、[次へ] または最後のレコードに移動するためのユーザー インターフェイス オブジェクトを無効にする必要がありますが、レコード ビューを確認する前に、最後のレコードを越えて移動する必要があります。 ユーザーが最後のレコードの後ろに移動され、最後のレコードに向かって戻る場合 (またはその前に)、レコード ビューは、レコード セット内のユーザーの位置を追跡し、ユーザー インターフェイス オブジェクトを正しく無効にできます。 `IsOnLastRecord` 信頼性が低いも実装関数を呼び出した後`OnRecordLast`、ID_RECORD_LAST コマンドを処理または`CRecordset::MoveLast`します。

##  <a name="ongetrecordset"></a>  CRecordView::OnGetRecordset

ポインターを返します、 `CRecordset`-レコード ビューに関連付けられたオブジェクトを派生します。

```
virtual CRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>戻り値

ポインターを`CRecordset`の派生オブジェクトのオブジェクトが正常に作成されたそれ以外の場合は NULL ポインター。

### <a name="remarks"></a>Remarks

構築またはレコード セット オブジェクトを取得してにポインターを返すには、このメンバー関数をオーバーライドする必要があります。 ClassWizard で、レコード ビュー クラスを宣言する場合、ウィザードの既定のオーバーライドを書き込みます。 ClassWizard の既定の実装では、1 つが存在する場合は、レコード ビューに格納されているレコード セットのポインターを返します。 Classwizard で指定した型のレコード セット オブジェクトを作成しますがそうでない場合、`Open`メンバー関数、テーブルを開くか、クエリを実行して、オブジェクトへのポインターを返します。

詳細と例については、この記事を参照してください。[レコード ビュー。レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)します。

##  <a name="onmove"></a>  CRecordView::OnMove

レコード セット内の別のレコードに移動し、レコード ビューのコントロールにそのフィールドを表示するには、このメンバー関数を呼び出します。

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>パラメーター

*nIDMoveCommand*<br/>
標準コマンド ID 値は次のいずれか:

- ID_RECORD_FIRST は、レコード セットの最初のレコードに移動します。

- ID_RECORD_LAST は、レコード セットの最後のレコードに移動します。

- ID_RECORD_NEXT は、レコード セットの次のレコードに移動します。

- ID_RECORD_PREV は、レコード セットの前のレコードに移動します。

### <a name="return-value"></a>戻り値

移動が成功した場合、0 以外の場合移動要求が拒否された場合は 0 それ以外の場合。

### <a name="remarks"></a>Remarks

既定の実装は、適切な呼び出し`Move`のメンバー関数、`CRecordset`レコード ビューに関連付けられているオブジェクト。

既定では、`OnMove`ユーザーを使用すると、レコード ビューに変更された場合は、データ ソースの現在のレコードを更新します。

アプリケーション ウィザードでは、最初のレコード、最後のレコード、次のレコード、および前のレコードのメニュー項目を含むメニュー リソースを作成します。 ツールバーのドッキング可能なオプションを選択すると、これらのコマンドに対応するボタンとツールバーは、アプリケーション ウィザードによっても作成します。

過去のレコード セットの最後のレコードを移動する場合、レコード ビューを最後のレコードの表示が続行されます。 過去の最初のレコード後方移動する場合、最初のレコードを表示するレコードの表示が続行されます。

> [!CAUTION]
>  呼び出す`OnMove`レコード セットにレコードが存在しない場合は、例外をスローします。 適切なユーザー インターフェイス更新ハンドラー関数を呼び出す — `OnUpdateRecordFirst`、 `OnUpdateRecordLast`、 `OnUpdateRecordNext`、または`OnUpdateRecordPrev`—、対応するレコードをレコード セットが存在するかどうかを判断する操作を移動します。

## <a name="see-also"></a>関連項目

[CFormView クラス](../../mfc/reference/cformview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)<br/>
[CFormView クラス](../../mfc/reference/cformview-class.md)
