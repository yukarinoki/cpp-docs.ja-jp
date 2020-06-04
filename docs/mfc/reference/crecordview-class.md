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
ms.openlocfilehash: b706a80f91a3c952d80da13f453a807c775b9405
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368354"
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
|[レコードビュー::Cレコードビュー](#crecordview)|`CRecordView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[レコードビュー::イソンファーストレコード](#isonfirstrecord)|現在のレコードが関連付けられたレコードセットの最初のレコードである場合は、0 以外を返します。|
|[レコードビュー::イソンラストレコード](#isonlastrecord)|現在のレコードが関連付けられたレコードセットの最後のレコードである場合は、0 以外を返します。|
|[レコードビュー::オンゲットレコードセット](#ongetrecordset)|から`CRecordset`派生したクラスのオブジェクトへのポインターを返します。 ClassWizard は、この関数をオーバーライドし、必要に応じてレコードセットを作成します。|
|[レコードビュー::オンムーブ](#onmove)||

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[レコードビュー::オンムーブ](#onmove)|現在のレコードが変更されている場合は、データ ソースで更新し、指定したレコード (次、前、先頭、または最後) に移動します。|

## <a name="remarks"></a>解説

ビューは、オブジェクトに直接接続されたフォーム ビュー`CRecordset`です。 ビューはダイアログ テンプレート リソースから作成され、ダイアログ テンプレートの`CRecordset`コントロールにオブジェクトのフィールドが表示されます。 この`CRecordView`オブジェクトは、ダイアログ データ エクスチェンジ (DDX) とレコード フィールド エクスチェンジ (RFX) を使用して、フォーム上のコントロールとレコードセットのフィールド間のデータ移動を自動化します。 `CRecordView`また、最初、次、前、または最後のレコードに移動するための既定の実装と、現在表示されているレコードを更新するためのインターフェイスも提供します。

> [!NOTE]
> オープン データベース接続 (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスを使用している場合は、代わりにクラス[CDaoRecordView を使用します](../../mfc/reference/cdaorecordview-class.md)。 詳細については、「[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

レコード ビューを作成する最も一般的な方法は、アプリケーション ウィザードを使用することです。 アプリケーション ウィザードは、スケルトン スターター アプリケーションの一部として、レコード ビュー クラスと関連レコードセット クラスの両方を作成します。 アプリケーション ウィザードでレコード ビュー クラスを作成しない場合は、後で ClassWizard を使用して作成できます。 単一のフォームが必要な場合は、アプリケーション ウィザードの方法が簡単です。 ClassWizard を使用すると、後で開発プロセスでレコード ビューを使用できます。 ClassWizard を使用してレコード ビューとレコードセットを個別に作成し、それらを接続する方法は、レコードセット クラスとその名前付けをより詳細に制御できるため、最も柔軟性の高いアプローチです。H/.CPP ファイル。 この方法では、同じレコードセット クラスに複数のレコード ビューを作成することもできます。

エンド ユーザーがレコード ビュー内のレコード間を簡単に移動できるように、アプリケーション ウィザードは、最初、次、前、または最後のレコードに移動するためのメニュー (およびオプションのツール バー) リソースを作成します。 ClassWizard を使用してレコード ビュー クラスを作成する場合は、メニューエディタとビットマップエディタを使用して、これらのリソースを自分で作成する必要があります。

レコード間の移動に関する既定の実装については、「 および`IsOnFirstRecord``IsOnLastRecord`レコード ビューを使用する 」および「[レコード ビューの使用](../../data/using-a-record-view-mfc-data-access.md)」を参照してください。

`CRecordView`レコード ビューがユーザー インターフェイスを更新できるように、レコードセット内でのユーザーの位置を追跡します。 ユーザーがレコードセットの一方の端に移動すると、レコード ビューは、メニュー項目やツール バー ボタンなどのユーザー インターフェイス オブジェクトを無効にして、同じ方向に移動します。

レコード ビューとレコードセット クラスの宣言と使用の詳細については、「レコード ビュー」の「レコード ビューのデザインと作成」を参照[してください](../../data/record-views-mfc-data-access.md)。 レコード ビューの動作と使用方法の詳細については、「レコード ビューの[使用](../../data/using-a-record-view-mfc-data-access.md)」を参照してください。

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

## <a name="crecordviewcrecordview"></a><a name="crecordview"></a>レコードビュー::Cレコードビュー

派生`CRecordView`した型のオブジェクトを作成する場合は、いずれかの形式のコンストラクターを呼び出してビュー オブジェクトを初期化し、ビューの基になるダイアログ リソースを識別します。

```
explicit CRecordView(LPCTSTR lpszTemplateName);
explicit CRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>パラメーター

*テンプレート名*<br/>
ダイアログ テンプレート リソースの名前である null で終わる文字列を格納します。

*テンプレート*<br/>
ダイアログ テンプレート リソースの ID 番号を格納します。

### <a name="remarks"></a>解説

リソースを名前で識別するか (コンストラクタの引数として文字列を渡す)、または ID (引数として符号なし整数を渡す) を使用できます。 リソース ID の使用をお勧めします。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを指定*する必要があります*。 派生クラスのコンストラクターで、次の例に示`CRecordView::CRecordView`すように、リソース名または ID を引数としてコンストラクターを呼び出します。

`CRecordView::OnInitialUpdate`を`UpdateData`呼び出`DoDataExchange`します。 ClassWizard によって`DoDataExchange`作成`CRecordView`されたフィールド データ メンバー`CRecordset`にコントロールを間接的に接続する最初の呼び出しです。 これらのデータ メンバーは、基本クラス`CFormView::OnInitialUpdate`のメンバー関数を呼び出すまで使用できません。

> [!NOTE]
> ClassWizard を使用する場合、ウィザードは**列挙**値`CRecordView::IDD`を定義し、クラス宣言で指定し、コンストラクターのメンバー初期化リストで使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#32](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]

## <a name="crecordviewisonfirstrecord"></a><a name="isonfirstrecord"></a>レコードビュー::イソンファーストレコード

現在のレコードが、このレコード ビューに関連付けられたレコードセット オブジェクトの最初のレコードかどうかを調べます。

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>戻り値

カレント レコードがレコードセットの最初のレコードの場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

ClassWizard によって記述された既定のコマンド更新ハンドラーの独自の実装を記述する場合に便利です。

ユーザーが最初のレコードに移動すると、フレームワークは、最初または前のレコードに移動するために持っているユーザー インターフェイス オブジェクトを無効にします。

## <a name="crecordviewisonlastrecord"></a><a name="isonlastrecord"></a>レコードビュー::イソンラストレコード

現在のレコードが、このレコード ビューに関連付けられているレコードセット オブジェクトの最後のレコードかどうかを調べます。

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>戻り値

現在のレコードがレコードセットの最後のレコードの場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、ClassWizard がレコード間を移動するためのユーザー インターフェイスをサポートするために書き込む既定のコマンド更新ハンドラーの独自の実装を記述する場合に便利です。

> [!CAUTION]
> この関数の結果は、ユーザーがレコードセットを越えて移動するまでビューがレコードセットの終了を検出できない点を除いて、信頼性が高くなります。 ユーザーは、レコード ビューが、次または最後のレコードに移動するためにユーザー インターフェイス オブジェクトを無効にする必要があることを示す前に、最後のレコードを超えて移動する必要があります。 ユーザーが最後のレコードを超えて移動し、最後のレコード (またはその前) に戻った場合、レコード ビューはレコードセット内でのユーザーの位置を追跡し、ユーザー インターフェイス オブジェクトを正しく無効にできます。 `IsOnLastRecord`ID_RECORD_LASTコマンドを処理する実装関数`OnRecordLast`、または`CRecordset::MoveLast`を呼び出した後も、信頼性が低くなります。

## <a name="crecordviewongetrecordset"></a><a name="ongetrecordset"></a>レコードビュー::オンゲットレコードセット

レコード ビューに関連`CRecordset`付けられた派生オブジェクトへのポインターを返します。

```
virtual CRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>戻り値

オブジェクトが`CRecordset`正常に作成された場合は派生オブジェクトへのポインター。それ以外の場合は NULL ポインター。

### <a name="remarks"></a>解説

レコードセット オブジェクトを構築または取得し、そのオブジェクトへのポインターを返す場合は、このメンバー関数をオーバーライドする必要があります。 ClassWizard でレコード ビュー クラスを宣言すると、ウィザードによって既定のオーバーライドが書き込まれます。 ClassWizard の既定の実装は、レコード ビューに格納されているレコード セット のポインターが存在する場合は、そのポインターを返します。 指定されていない場合は、ClassWizard で指定した型のレコードセット オブジェクトを構築し`Open`、そのメンバー関数を呼び出してテーブルを開くかクエリを実行してから、オブジェクトへのポインターを返します。

詳細と例については、「レコード ビュー [: レコード ビューの使用](../../data/using-a-record-view-mfc-data-access.md)」を参照してください。

## <a name="crecordviewonmove"></a><a name="onmove"></a>レコードビュー::オンムーブ

レコードセット内の別のレコードに移動し、そのフィールドをレコード ビューのコントロールに表示します。

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>パラメーター

*コマンドを移動します。*<br/>
次の標準コマンド ID 値の 1 つ。

- ID_RECORD_FIRST レコードセットの最初のレコードに移動します。

- ID_RECORD_LAST レコードセットの最後のレコードに移動します。

- ID_RECORD_NEXT レコードセット内の次のレコードに移動します。

- ID_RECORD_PREV レコードセット内の前のレコードに移動します。

### <a name="return-value"></a>戻り値

移動が成功した場合は 0 以外。それ以外の場合は 0 、移動要求が拒否されました。

### <a name="remarks"></a>解説

既定の実装では、レコード`Move`ビューに関連`CRecordset`付けられているオブジェクトの適切なメンバー関数を呼び出します。

既定では、`OnMove`ユーザーがレコード ビューで変更した場合、データ ソースの現在のレコードが更新されます。

アプリケーション ウィザードは、最初のレコード、最終レコード、次のレコード、および前のレコードのメニュー項目を持つメニュー リソースを作成します。 [ドッキング可能なツールバー] オプションを選択すると、アプリケーション ウィザードによって、これらのコマンドに対応するボタンを含むツール バーも作成されます。

レコードセットの最後のレコードを超えて移動すると、レコード ビューには最後のレコードが表示されます。 最初のレコードを後ろに移動すると、レコード ビューには最初のレコードが表示されます。

> [!CAUTION]
> レコード`OnMove`セットにレコードがない場合、呼び出しは例外をスローします。 対応する移動操作の前に、適切`OnUpdateRecordFirst`な`OnUpdateRecordLast`ユーザー`OnUpdateRecordNext`インターフェイス`OnUpdateRecordPrev`更新ハンドラー関数 、、、、または 、 を呼び出して、レコードセットにレコードがあるかどうかを確認します。

## <a name="see-also"></a>関連項目

[クラスを表示します。](../../mfc/reference/cformview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/crecordset-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cformview-class.md)
