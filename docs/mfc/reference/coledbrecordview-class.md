---
title: COleDBRecordView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- COleDBRecordView [MFC], COleDBRecordView
- COleDBRecordView [MFC], OnGetRowset
- COleDBRecordView [MFC], OnMove
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b69aafa7f8b07d96d754d080e7fb5abd170e167
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|`COleDBRecordView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|返します、標準的な`HRESULT`値。|  
|[COleDBRecordView::OnMove](#onmove)|データ ソースで (ダーティの場合)、現在のレコードを更新し、指定されたレコードに移動します (次に、前の最初のページまたは最後)。|  
  
## <a name="remarks"></a>コメント  
 ビューに直接接続されているフォーム ビュー、`CRowset`オブジェクト。 ビューはダイアログ テンプレート リソースから作成およびのフィールドを表示、`CRowset`ダイアログ テンプレートのコントロール内のオブジェクト。 `COleDBRecordView`ダイアログ データ エクス チェンジ (DDX) を使用するオブジェクトとナビゲーション機能に組み込まれて`CRowset`フォーム上のコントロールと行セットのフィールド間のデータ移動を自動化します。 `COleDBRecordView` 移動するための既定の実装を提供、最初に [次へ]、前、または最後のレコードと、ビューの現在のレコードを更新するためのインターフェイスです。  
  
 DDX 関数を使用することができます**COleDbRecordView**データベース レコード セットから直接データを取得し、ダイアログ コントロールで表示します。 使用する必要があります、 **ddx _\*** メソッド (など`DDX_Text`) ではなく、 **DDX_Field\*** 関数 (など`DDX_FieldText`) と**COleDbRecordView**. `DDX_FieldText` は動作しません**COleDbRecordView**ため`DDX_FieldText`型の追加の引数を受け取る**CRecordset\***  (の`CRecordView`) または**CDaoRecordset\*** (の`CDaoRecordView`)。  
  
> [!NOTE]
>  OLE DB コンシューマー テンプレート クラスではなく、データ アクセス オブジェクト (DAO) クラスで作業している場合は、クラスを使用して[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)代わりにします。 詳細については、記事を参照してください。[概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)です。  
  
 `COleDBRecordView` 追跡、行セット内のユーザーの位置、レコード ビューは、ユーザー インターフェイスを更新できるようにします。 ユーザーは、行セットの先頭または末尾に移動、レコード ビュー、ユーザー インターフェイス オブジェクトを無効になります: メニュー項目またはツール バー ボタンなど — を移動する同じ方向にさらにします。  
  
 行セット クラスの詳細については、次を参照してください。、[を使用して OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)資料です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxoledb.h  
  
##  <a name="coledbrecordview"></a>  COleDBRecordView::COleDBRecordView  
 `COleDBRecordView` オブジェクトを構築します。  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を指定する null で終わる文字列が含まれています。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
### <a name="remarks"></a>コメント  
 派生した型のオブジェクトを作成するときに`COleDBRecordView`、ビュー オブジェクトを作成し、ビューの基になるダイアログ リソースを識別するコンス トラクターの 1 つを呼び出します。 名前 (コンス トラクターの引数として文字列を渡す) で、または ID (パスを符号なし整数の引数として) では、リソースを識別できます。  
  
> [!NOTE]
>  派生クラス*必要があります*独自のコンス トラクターを指定します。 コンス トラクターを呼び出す、コンス トラクターで`COleDBRecordView::COleDBRecordView`リソース名または ID を引数として使用します。  
  
##  <a name="ongetrowset"></a>  COleDBRecordView::OnGetRowset  
 ハンドルを返します、 **CRowset <>** レコード ビューに関連付けられているオブジェクト。  
  
```  
virtual CRowset<>* OnGetRowset() = 0;  
 
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 作成または行セット オブジェクトを取得してハンドルを返すには、このメンバー関数をオーバーライドする必要があります。 ClassWizard で、レコード ビュー クラスを宣言する場合の既定のオーバーライドが書き込まれます。 ClassWizard の既定の実装では、1 つが存在する場合は、レコード ビューに格納されている行セット ハンドルを返します。 ClassWizard でユーザーが指定した型の行セット オブジェクトを構築されていない場合、**開く**メンバー関数のテーブルを開くか、クエリを実行して、オブジェクトへのハンドルを返します。  
  
> [!NOTE]
>  MFC 7.0 より前`OnGetRowset`へのポインターが返されます`CRowset`です。 呼び出すコードを使用していれば`OnGetRowset`、テンプレート化されたクラスを戻り値の型を変更する必要があります**CRowset <>** です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase#38](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 詳細と例については、記事を参照してください。[レコード ビュー: レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)です。  
  
##  <a name="onmove"></a>  COleDBRecordView::OnMove  
 行セットと表示内のレコードに移動、レコードのコントロールは、そのフィールドを表示します。  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDMoveCommand`  
 標準コマンド ID 値は次のいずれかです。  
  
- `ID_RECORD_FIRST` レコード セットの最初のレコードに移動します。  
  
- `ID_RECORD_LAST` — レコードに移動最後のレコード セットにします。  
  
- `ID_RECORD_NEXT` レコード セットの次のレコードに移動します。  
  
- `ID_RECORD_PREV` レコード セットの前のレコードに移動します。  
  
### <a name="return-value"></a>戻り値  
 移動が成功した場合は 0 以外。移動要求が拒否された場合は、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装を呼び出す、適切な**移動**のメンバー関数、`CRowset`レコード ビューに関連付けられているオブジェクト。  
  
 既定では、`OnMove`ユーザーを使用すると、レコード ビューに変更された場合に、データ ソースの現在のレコードを更新します。  
  
 アプリケーションのウィザードでは、最初のレコード、最後のレコード、次のレコードと前のレコードのメニュー項目をメニュー リソースを作成します。 ドッキング可能ツールバー オプションを選択すると、これらのコマンドに対応するボタンとツールバーは、アプリケーション ウィザードで、によってもを作成します。  
  
 過去のレコード セットの最後のレコードを移動する場合、レコード ビューを最後のレコードが表示されます。 を越えて移動した最初のレコード場合、レコード ビューは最初のレコードが表示されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)



