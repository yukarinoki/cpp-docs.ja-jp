---
title: クラスを表示します。
ms.date: 11/04/2016
f1_keywords:
- CDaoRecordView
- AFXDAO/CDaoRecordView
- AFXDAO/CDaoRecordView::CDaoRecordView
- AFXDAO/CDaoRecordView::IsOnFirstRecord
- AFXDAO/CDaoRecordView::IsOnLastRecord
- AFXDAO/CDaoRecordView::OnGetRecordset
- AFXDAO/CDaoRecordView::OnMove
helpviewer_keywords:
- CDaoRecordView [MFC], CDaoRecordView
- CDaoRecordView [MFC], IsOnFirstRecord
- CDaoRecordView [MFC], IsOnLastRecord
- CDaoRecordView [MFC], OnGetRecordset
- CDaoRecordView [MFC], OnMove
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
ms.openlocfilehash: b8c411dbd29316219759351f1f1633b6e57b92e8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377137"
---
# <a name="cdaorecordview-class"></a>クラスを表示します。

コントロール内にデータベース レコードを表示するビューです。

## <a name="syntax"></a>構文

```
class AFX_NOVTABLE CDaoRecordView : public CFormView
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[レコードビュー::CDaoレコードビュー](#cdaorecordview)|`CDaoRecordView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コダオレコードビュー::イソンファーストレコード](#isonfirstrecord)|現在のレコードが関連付けられたレコードセットの最初のレコードである場合は、0 以外を返します。|
|[レコードビュー::イソンラストレコード](#isonlastrecord)|現在のレコードが関連付けられたレコードセットの最後のレコードである場合は、0 以外を返します。|
|[レコードビュー::オンゲットレコードセット](#ongetrecordset)|から`CDaoRecordset`派生したクラスのオブジェクトへのポインターを返します。 ClassWizard は、この関数をオーバーライドし、必要に応じてレコードセットを作成します。|
|[レコードビュー::オンムーブ](#onmove)|現在のレコードが変更されている場合は、データ ソースで更新し、指定したレコード (次、前、先頭、または最後) に移動します。|

## <a name="remarks"></a>解説

ビューは、オブジェクトに直接接続されたフォーム ビュー`CDaoRecordset`です。 ビューはダイアログ テンプレート リソースから作成され、ダイアログ テンプレートの`CDaoRecordset`コントロールにオブジェクトのフィールドが表示されます。 この`CDaoRecordView`オブジェクトは、ダイアログ データ エクスチェンジ (DDX) と DAO レコード フィールド エクスチェンジ (DFX) を使用して、フォーム上のコントロールとレコードセットのフィールド間のデータ移動を自動化します。 `CDaoRecordView`また、最初、次、前、または最後のレコードに移動するための既定の実装と、現在表示されているレコードを更新するためのインターフェイスも提供します。

> [!NOTE]
> DAO データベース クラスは、オープン データベース接続 (ODBC) に基づく MFC データベース クラスとは異なります。 DAO データベースクラス名には、すべて "CDao" というプレフィックスが付いています。 DAO クラスを使用して ODBC データ ソースにアクセスすることはできます。DAO クラスは、一般に、Jet データベース エンジンを使用するため、優れた機能を提供します。

レコード ビューを作成する最も一般的な方法は、アプリケーション ウィザードを使用することです。 アプリケーション ウィザードは、スケルトン スターター アプリケーションの一部として、レコード ビュー クラスと関連レコードセット クラスの両方を作成します。

単一のフォームが必要な場合は、アプリケーション ウィザードの方法が簡単です。 ClassWizard を使用すると、後で開発プロセスでレコード ビューを使用できます。 アプリケーション ウィザードでレコード ビュー クラスを作成しない場合は、後で ClassWizard を使用して作成できます。 ClassWizard を使用してレコード ビューとレコードセットを個別に作成し、それらを接続する方法は、レコードセット クラスとその名前付けをより詳細に制御できるため、最も柔軟性の高いアプローチです。H/.CPP ファイル。 この方法では、同じレコードセット クラスに複数のレコード ビューを作成することもできます。

エンド ユーザーがレコード ビュー内のレコード間を簡単に移動できるように、アプリケーション ウィザードは、最初、次、前、または最後のレコードに移動するためのメニュー (およびオプションのツール バー) リソースを作成します。 ClassWizard を使用してレコード ビュー クラスを作成する場合は、メニューエディタとビットマップエディタを使用して、これらのリソースを自分で作成する必要があります。

レコード間の移動に関する既定の実装については、「 および`IsOnFirstRecord``IsOnLastRecord`と レコード[ビューの使用](../../data/using-a-record-view-mfc-data-access.md)」 を参照`CRecordView`してください`CDaoRecordView`。

`CDaoRecordView`レコード ビューがユーザー インターフェイスを更新できるように、レコードセット内でのユーザーの位置を追跡します。 ユーザーがレコードセットの一方の端に移動すると、レコード ビューは、メニュー項目やツール バー ボタンなどのユーザー インターフェイス オブジェクトを無効にして、同じ方向に移動します。

レコード ビューとレコードセット クラスの宣言と使用の詳細については、「レコード ビュー」の「レコード ビューのデザインと作成」を参照[してください](../../data/record-views-mfc-data-access.md)。 レコード ビューの動作と使用方法の詳細については、「レコード ビューの[使用](../../data/using-a-record-view-mfc-data-access.md)」を参照してください。 上記の記事はすべて、 と`CRecordView`の`CDaoRecordView`両方に適用されます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`CDaoRecordView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao.h

## <a name="cdaorecordviewcdaorecordview"></a><a name="cdaorecordview"></a>レコードビュー::CDaoレコードビュー

派生`CDaoRecordView`した型のオブジェクトを作成する場合は、いずれかの形式のコンストラクターを呼び出してビュー オブジェクトを初期化し、ビューの基になるダイアログ リソースを識別します。

```
explicit CDaoRecordView(LPCTSTR lpszTemplateName);
explicit CDaoRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>パラメーター

*テンプレート名*<br/>
ダイアログ テンプレート リソースの名前である null で終わる文字列を格納します。

*テンプレート*<br/>
ダイアログ テンプレート リソースの ID 番号を格納します。

### <a name="remarks"></a>解説

リソースを名前で識別するか (コンストラクタの引数として文字列を渡す)、または ID (引数として符号なし整数を渡す) を使用できます。 リソース ID の使用をお勧めします。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを指定する必要があります。 派生クラスのコンストラクターで、リソース名または ID`CDaoRecordView::CDaoRecordView`を引数としてコンストラクターを呼び出します。

`CDaoRecordView::OnInitialUpdate`を`CWnd::UpdateData`呼び出`CWnd::DoDataExchange`します。 ClassWizard によって`DoDataExchange`作成`CDaoRecordView`されたフィールド データ メンバー`CDaoRecordset`にコントロールを間接的に接続する最初の呼び出しです。 これらのデータ メンバーは、基本クラス`CFormView::OnInitialUpdate`のメンバー関数を呼び出すまで使用できません。

> [!NOTE]
> ClassWizard を使用する場合、ウィザードは**enum**クラス宣言`CDaoRecordView::IDD`で列挙値を定義し、コンストラクターのメンバー初期化リストで使用します。

[!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]

## <a name="cdaorecordviewisonfirstrecord"></a><a name="isonfirstrecord"></a>コダオレコードビュー::イソンファーストレコード

現在のレコードが、このレコード ビューに関連付けられたレコードセット オブジェクトの最初のレコードかどうかを調べます。

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>戻り値

カレント レコードがレコードセットの最初のレコードの場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、ClassWizard によって記述された既定のコマンド更新ハンドラーの独自の実装を記述する場合に便利です。

ユーザーが最初のレコードに移動すると、最初のレコードまたは前のレコードに移動するために必要なユーザー インターフェイス オブジェクト (メニュー項目やツール バー ボタンなど) が無効になります。

## <a name="cdaorecordviewisonlastrecord"></a><a name="isonlastrecord"></a>レコードビュー::イソンラストレコード

現在のレコードが、このレコード ビューに関連付けられているレコードセット オブジェクトの最後のレコードかどうかを調べます。

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>戻り値

現在のレコードがレコードセットの最後のレコードの場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数は、ClassWizard がレコード間を移動するためのユーザー インターフェイスをサポートするために書き込む既定のコマンド更新ハンドラーの独自の実装を記述する場合に便利です。

> [!CAUTION]
> この関数の結果は、ユーザーがレコードセットを越えて移動するまで、ビューがレコードセットの終了を検出できない場合を除いて、信頼性が高くなります。 レコード ビューが、次または最後のレコードに移動するためにユーザー インターフェイス オブジェクトを無効にする必要があることを示す前に、ユーザーが最後のレコードを超えて移動する必要があります。 ユーザーが最後のレコードを超えて移動し、最後のレコード (またはその前) に戻った場合、レコード ビューはレコードセット内でのユーザーの位置を追跡し、ユーザー インターフェイス オブジェクトを正しく無効にできます。

## <a name="cdaorecordviewongetrecordset"></a><a name="ongetrecordset"></a>レコードビュー::オンゲットレコードセット

レコード ビューに関連`CDaoRecordset`付けられた派生オブジェクトへのポインターを返します。

```
virtual CDaoRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>戻り値

オブジェクトが`CDaoRecordset`正常に作成された場合は派生オブジェクトへのポインター。それ以外の場合は NULL ポインター。

### <a name="remarks"></a>解説

レコードセット オブジェクトを構築または取得し、そのオブジェクトへのポインターを返す場合は、このメンバー関数をオーバーライドする必要があります。 ClassWizard でレコード ビュー クラスを宣言すると、ウィザードによって既定のオーバーライドが書き込まれます。 ClassWizard の既定の実装は、レコード ビューに格納されているレコード セット のポインターが存在する場合は、そのポインターを返します。 指定されていない場合は、ClassWizard で指定した型のレコードセット オブジェクトを構築し`Open`、そのメンバー関数を呼び出してテーブルを開くかクエリを実行してから、オブジェクトへのポインターを返します。

詳細と例については、「レコード ビュー [: レコード ビューの使用](../../data/using-a-record-view-mfc-data-access.md)」を参照してください。

## <a name="cdaorecordviewonmove"></a><a name="onmove"></a>レコードビュー::オンムーブ

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

既定の実装では、レコード ビューに関連付`CDaoRecordset`けられているオブジェクトの適切な Move メンバー関数を呼び出します。

既定では、`OnMove`ユーザーがレコード ビューで変更した場合、データ ソースの現在のレコードが更新されます。

アプリケーション ウィザードは、最初のレコード、最終レコード、次のレコード、および前のレコードのメニュー項目を持つメニュー リソースを作成します。 [ツールバー] オプションを選択すると、アプリケーション ウィザードによって、これらのコマンドに対応するボタンを含むツールバーも作成されます。

レコードセットの最後のレコードを超えて移動すると、レコード ビューには最後のレコードが表示されます。 最初のレコードを後ろに移動すると、レコード ビューには最初のレコードが表示されます。

> [!CAUTION]
> レコード`OnMove`セットにレコードがない場合、呼び出しは例外をスローします。 対応する移動操作の前に、適切`OnUpdateRecordFirst`な`OnUpdateRecordLast`ユーザー`OnUpdateRecordNext`インターフェイス`OnUpdateRecordPrev`更新ハンドラー関数 、、、、または 、 を呼び出して、レコードセットにレコードがあるかどうかを確認します。

## <a name="see-also"></a>関連項目

[クラスを表示します。](../../mfc/reference/cformview-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/cdaorecordset-class.md)<br/>
[クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[クラス](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDAOワークスペースクラス](../../mfc/reference/cdaoworkspace-class.md)<br/>
[クラスを表示します。](../../mfc/reference/cformview-class.md)
