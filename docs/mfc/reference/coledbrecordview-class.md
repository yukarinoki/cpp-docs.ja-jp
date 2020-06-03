---
title: COleDBRecordView クラス
ms.date: 11/04/2016
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
ms.openlocfilehash: de9c602cb747ee3d4449df479530e55ce907cb8a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366104"
---
# <a name="coledbrecordview-class"></a>COleDBRecordView クラス

コントロール内にデータベース レコードを表示するビューです。

## <a name="syntax"></a>構文

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[レコードビューを表示します。](#coledbrecordview)|`COleDBRecordView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を見る](#ongetrowset)|標準の HRESULT 値を返します。|
|[レコードビュー::オンムーブ](#onmove)|データ ソースの現在のレコード (ダーティな場合) を更新し、指定したレコード (次、前、最初、または最後) に移動します。|

## <a name="remarks"></a>解説

ビューは、オブジェクトに直接接続されたフォーム ビュー`CRowset`です。 ビューはダイアログ テンプレート リソースから作成され、ダイアログ テンプレートの`CRowset`コントロールにオブジェクトのフィールドが表示されます。 この`COleDBRecordView`オブジェクトは、ダイアログ データ エクスチェンジ (DDX) と`CRowset`に組み込まれているナビゲーション機能を使用して、フォーム上のコントロールと行セットのフィールド間のデータ移動を自動化します。 `COleDBRecordView`また、最初、次、前、または最後のレコードに移動するための既定の実装と、現在表示されているレコードを更新するためのインターフェイスも提供します。

DDX 関数を使用`COleDbRecordView`すると、データベース レコードセットから直接データを取得し、ダイアログ コントロールに表示できます。 メソッド (`DDX_*`など`DDX_Text`) は、`DDX_Field*`などの 関数`DDX_FieldText`(`COleDbRecordView`など ) を 使用する必要があります。 `DDX_FieldText`型`CRecordset*`(`CRecordView`の場合 ) または`CDaoRecordset*`(`CDaoRecordView`の場合 ) の追加引数を取`COleDbRecordView`るので`DDX_FieldText`、使用できません。

> [!NOTE]
> OLE DB コンシューマー テンプレート クラスではなく、データ アクセス オブジェクト (DAO) クラスを使用している場合は、代わりにクラス[CDaoRecordView を使用します](../../mfc/reference/cdaorecordview-class.md)。 詳細については、「[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

`COleDBRecordView`レコード ビューがユーザー インターフェイスを更新できるように、行セット内のユーザーの位置を追跡します。 ユーザーが行セットの一方の端に移動すると、レコード ビューは、メニュー項目やツール バー ボタンなどのユーザー インターフェイス オブジェクトを無効にして、同じ方向に移動します。

行セット クラスの詳細については[、「OLE DB コンシューマー テンプレートの使用](../../data/oledb/ole-db-consumer-templates-cpp.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxoledb.h

## <a name="coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a>レコードビューを表示します。

`COleDBRecordView` オブジェクトを構築します。

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>パラメーター

*テンプレート名*<br/>
ダイアログ テンプレート リソースの名前である null で終わる文字列を格納します。

*テンプレート*<br/>
ダイアログ テンプレート リソースの ID 番号を格納します。

### <a name="remarks"></a>解説

派生`COleDBRecordView`した型のオブジェクトを作成する場合は、いずれかのコンストラクターを呼び出してビュー オブジェクトを作成し、ビューの基になるダイアログ リソースを識別します。 リソースは、名前 (コンストラクターの引数として文字列を渡す) または ID (引数として符号なし整数を渡す) によって識別できます。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを指定*する必要があります*。 コンストラクターで、`COleDBRecordView::COleDBRecordView`リソース名または ID を引数としてコンストラクター を呼び出します。

## <a name="coledbrecordviewongetrowset"></a><a name="ongetrowset"></a>を見る

レコード ビューに関連付けられた**CRowset<>** オブジェクトのハンドルを返します。

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

行セット オブジェクトを構築または取得し、そのオブジェクトへのハンドルを返す場合は、このメンバー関数をオーバーライドする必要があります。 ClassWizard でレコード ビュー クラスを宣言すると、ウィザードによって既定のオーバーライドが書き込まれます。 ClassWizard の既定の実装では、レコード ビューに格納されている行セット ハンドルが存在する場合は、そのハンドルが返されます。 指定されていない場合は、ClassWizard で指定した型の行セット オブジェクトを構築し、`Open`そのメンバー関数を呼び出してテーブルを開くかクエリを実行してから、オブジェクトへのハンドルを返します。

> [!NOTE]
> MFC 7.0 以前`OnGetRowset`では、 への`CRowset`ポインターが返されます。 を呼び出`OnGetRowset`すコードがある場合は、戻り値の型をテンプレート化クラスの**CRowset<>** に変更する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

詳細と例については、「レコード ビュー [: レコード ビューの使用](../../data/using-a-record-view-mfc-data-access.md)」を参照してください。

## <a name="coledbrecordviewonmove"></a><a name="onmove"></a>レコードビュー::オンムーブ

行セット内の別のレコードに移動し、そのフィールドをレコード ビューのコントロールに表示します。

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>パラメーター

*コマンドを移動します。*<br/>
次の標準コマンド ID 値の 1 つ。

- ID_RECORD_FIRST — レコードセットの最初のレコードに移動します。

- ID_RECORD_LAST — レコードセットの最後のレコードに移動します。

- ID_RECORD_NEXT — レコードセット内の次のレコードに移動します。

- ID_RECORD_PREV — レコードセット内の前のレコードに移動します。

### <a name="return-value"></a>戻り値

移動が成功した場合は 0 以外。それ以外の場合は 0 、移動要求が拒否されました。

### <a name="remarks"></a>解説

既定の実装では、レコード`Move`ビューに関連`CRowset`付けられているオブジェクトの適切なメンバー関数を呼び出します。

既定では、`OnMove`ユーザーがレコード ビューで変更した場合、データ ソースの現在のレコードが更新されます。

アプリケーション ウィザードは、最初のレコード、最終レコード、次のレコード、および前のレコードのメニュー項目を持つメニュー リソースを作成します。 [ドッキング可能なツールバー] オプションを選択すると、アプリケーション ウィザードによって、これらのコマンドに対応するボタンを持つツールバーも作成されます。

レコードセットの最後のレコードを超えて移動すると、レコード ビューには最後のレコードが表示されます。 最初のレコードを後ろに移動すると、レコード ビューには最初のレコードが表示されます。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)
