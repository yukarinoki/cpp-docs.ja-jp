---
description: '詳細情報: Co○ Brecordview クラス'
title: Cobf Brecordview クラス
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
ms.openlocfilehash: bce03a482aff558ed6d22c7720ff74f304a9214f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227313"
---
# <a name="coledbrecordview-class"></a>Cobf Brecordview クラス

コントロール内にデータベース レコードを表示するビューです。

## <a name="syntax"></a>構文

```
class COleDBRecordView : public CFormView
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[Cobf Brecordview:: Coの Brecordview](#coledbrecordview)|`COleDBRecordView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CoOnGetRowset Brecordview::](#ongetrowset)|標準の HRESULT 値を返します。|
|[CoOnMove Brecordview::](#onmove)|データソースで現在のレコード (ダーティの場合) を更新し、指定されたレコード (next、previous、first、last) に移動します。|

## <a name="remarks"></a>解説

ビューは、オブジェクトに直接接続されたフォームビューです `CRowset` 。 ビューはダイアログテンプレートリソースから作成され、 `CRowset` ダイアログテンプレートのコントロールにオブジェクトのフィールドが表示されます。 オブジェクトは、 `COleDBRecordView` ダイアログデータエクスチェンジ (DDX) と、に組み込まれているナビゲーション機能を使用して、 `CRowset` フォーム上のコントロールと行セットのフィールドの間でのデータの移動を自動化します。 `COleDBRecordView` また、は、最初、次、前、または最後のレコードに移動するための既定の実装と、現在ビューにあるレコードを更新するためのインターフェイスを提供します。

と共に DDX 関数を使用すると `COleDbRecordView` 、データベースレコードセットから直接データを取得し、ダイアログコントロールに表示できます。 関数 (など) ではなく、メソッド (など) を使用する必要があり `DDX_*` `DDX_Text` `DDX_Field*` `DDX_FieldText` `COleDbRecordView` ます。 `DDX_FieldText` は `COleDbRecordView` 、 `DDX_FieldText` 型 `CRecordset*` (の場合 `CRecordView` ) または `CDaoRecordset*` (の場合) の追加引数を受け取るため、では機能 `CDaoRecordView` しません。

> [!NOTE]
> OLE DB コンシューマーテンプレートクラスではなく、データアクセスオブジェクト (DAO) クラスを使用している場合は、代わりにクラス [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md) を使用してください。 詳細については、記事「 [概要: データベースプログラミング](../../data/data-access-programming-mfc-atl.md)」を参照してください。

`COleDBRecordView` レコードビューでユーザーインターフェイスを更新できるように、行セット内のユーザーの位置を追跡します。 ユーザーが行セットの末尾に移動すると、[レコード] ビューでは、メニュー項目やツールバーボタンなどのユーザーインターフェイスオブジェクトが、同じ方向に移動するために無効になります。

行セットクラスの詳細については、 [OLE DB コンシューマーテンプレートの使用](../../data/oledb/ole-db-consumer-templates-cpp.md) に関する記事を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`COleDBRecordView`

## <a name="requirements"></a>要件

**ヘッダー:** afxoledb

## <a name="coledbrecordviewcoledbrecordview"></a><a name="coledbrecordview"></a> Cobf Brecordview:: Coの Brecordview

`COleDBRecordView` オブジェクトを構築します。

```
COleDBRecordView(LPCTSTR lpszTemplateName);
COleDBRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>パラメーター

*lpszTemplateName*<br/>
ダイアログテンプレートリソースの名前である null で終わる文字列を格納します。

*nIDTemplate*<br/>
ダイアログテンプレートリソースの ID 番号を格納します。

### <a name="remarks"></a>解説

から派生した型のオブジェクトを作成する場合 `COleDBRecordView` は、いずれかのコンストラクターを呼び出してビューオブジェクトを作成し、ビューの基になるダイアログリソースを識別します。 リソースは、名前で識別できます (コンストラクターの引数として文字列を渡すか、または ID で符号なし整数を渡します)。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを提供 *する必要があり* ます。 コンストラクターで、 `COleDBRecordView::COleDBRecordView` リソース名または ID を引数として指定して、コンストラクターを呼び出します。

## <a name="coledbrecordviewongetrowset"></a><a name="ongetrowset"></a> CoOnGetRowset Brecordview::

レコードビューに関連付けられている **CRowset<>** オブジェクトのハンドルを返します。

```
virtual CRowset<>* OnGetRowset() = 0;
```

### <a name="return-value"></a>戻り値

標準の HRESULT 値。

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、行セットオブジェクトを構築または取得し、そのハンドルを返すようにする必要があります。 ClassWizard でレコードビュークラスを宣言すると、ウィザードによって既定の上書きが書き込まれます。 ClassWizard の既定の実装では、レコードビューに格納されている行セットハンドル (存在する場合) が返されます。 そうでない場合は、ClassWizard で指定した型の行セットオブジェクトを構築し、そのメンバー関数を呼び出して `Open` テーブルを開くかクエリを実行した後、オブジェクトへのハンドルを返します。

> [!NOTE]
> MFC 7.0 以前では、から `OnGetRowset` へのポインターが返されました `CRowset` 。 を呼び出すコードがある場合は `OnGetRowset` 、戻り値の型をテンプレート化クラス **CRowset<>** に変更する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]

詳細と例については、レコード [ビューの使用](../../data/using-a-record-view-mfc-data-access.md)に関する記事を参照してください。

## <a name="coledbrecordviewonmove"></a><a name="onmove"></a> CoOnMove Brecordview::

行セット内の別のレコードに移動し、そのフィールドを [レコード] ビューのコントロールに表示します。

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>パラメーター

*nIDMoveCommand*<br/>
次の標準コマンド ID 値のいずれか。

- ID_RECORD_FIRST —レコードセット内の最初のレコードに移動します。

- ID_RECORD_LAST —レコードセット内の最後のレコードに移動します。

- ID_RECORD_NEXT —レコードセット内の次のレコードに移動します。

- ID_RECORD_PREV —レコードセット内の前のレコードに移動します。

### <a name="return-value"></a>戻り値

移動が成功した場合は0以外の。それ以外の場合は、移動要求が拒否された場合は0です。

### <a name="remarks"></a>解説

既定の実装は、 `Move` `CRowset` レコードビューに関連付けられているオブジェクトの適切なメンバー関数を呼び出します。

既定では、は、 `OnMove` ユーザーがレコードビューで変更した場合、データソースの現在のレコードを更新します。

アプリケーションウィザードでは、最初のレコード、最後のレコード、次のレコード、および前の [レコード] メニュー項目を含むメニューリソースが作成されます。 [ドッキング可能なツールバー] オプションを選択した場合は、アプリケーションウィザードによって、これらのコマンドに対応するボタンを備えたツールバーも作成されます。

レコードセットの最後のレコードを越えて移動すると、レコードビューでは、最後のレコードが引き続き表示されます。 最初のレコードを後方に移動すると、レコードビューでは、最初のレコードが引き続き表示されます。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)
