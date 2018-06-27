---
title: CDaoRecordView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRecordView
- AFXDAO/CDaoRecordView
- AFXDAO/CDaoRecordView::CDaoRecordView
- AFXDAO/CDaoRecordView::IsOnFirstRecord
- AFXDAO/CDaoRecordView::IsOnLastRecord
- AFXDAO/CDaoRecordView::OnGetRecordset
- AFXDAO/CDaoRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CDaoRecordView [MFC], CDaoRecordView
- CDaoRecordView [MFC], IsOnFirstRecord
- CDaoRecordView [MFC], IsOnLastRecord
- CDaoRecordView [MFC], OnGetRecordset
- CDaoRecordView [MFC], OnMove
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a228a545061c4807688014b62907c4c41a82151e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952304"
---
# <a name="cdaorecordview-class"></a>CDaoRecordView クラス
コントロール内にデータベース レコードを表示するビューです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[指定して](#cdaorecordview)|`CDaoRecordView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|現在のレコードが関連付けられているレコード セットの最初のレコードの場合は 0 以外を返します。|  
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|現在のレコードが関連付けられているレコード セットの最後のレコードの場合は 0 以外を返します。|  
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|派生したクラスのオブジェクトへのポインターを返します`CDaoRecordset`です。 ClassWizard では、この関数を上書きし、必要な場合、レコード セットを作成します。|  
|[CDaoRecordView::OnMove](#onmove)|現在のレコードを変更した場合、データ ソースを更新し、指定されたレコードに移動 (次に、前の最初のページまたは最後)。|  
  
## <a name="remarks"></a>Remarks  
 ビューに直接接続されているフォーム ビュー、`CDaoRecordset`オブジェクト。 ビューはダイアログ テンプレート リソースから作成およびのフィールドを表示、`CDaoRecordset`ダイアログ テンプレートのコントロール内のオブジェクト。 `CDaoRecordView`オブジェクト ダイアログ データ エクス (チェンジ DDX) および DAO レコード フィールド エクス (チェンジ DFX) を使用して、フォーム上のコントロールとレコード セットのフィールドの間でデータの移動を自動化します。 `CDaoRecordView` 移動するための既定の実装を提供、最初に [次へ]、前、または最後のレコードと、ビューで現在のレコードを更新するためのインターフェイスです。  
  
> [!NOTE]
>  DAO データベース クラスは、MFC データベース クラス ODBC Open Database Connectivity () をベースとは異なります。 DAO データベース クラスの名前では、"CDao"プレフィックスがあります。 DAO クラス; で ODBC データ ソースのアクセスをできます。Microsoft Jet データベース エンジンを使用するため、DAO クラスは通常、優れた機能を提供します。  
  
 レコード ビューを作成する最も一般的な方法は、アプリケーション ウィザードでです。 アプリケーションのウィザードでは、レコード ビュー クラスとその関連するレコード セット クラスは、初期アプリケーションのスケルトンの一部としての両方を作成します。  
  
 単に 1 つのフォームが必要がある場合、アプリケーション ウィザードを使用は簡単です。 ClassWizard では、開発プロセスの後半で、レコード ビューを使用することにすることができます。 アプリケーション ウィザードを使用してレコード ビュー クラスを作成しない場合に、後で ClassWizard で作成できます。 レコード セット クラスの名前付けで詳細に制御を確保できるため、最も柔軟なアプローチは、ClassWizard を使用して、レコード ビューとレコード セットを個別に作成し、それらを接続して、そのします。H/です。CPP ファイル。 この方法では、同じのレコード セット クラスの複数のレコード ビューを持つこともできます。  
  
 メニュー (および必要に応じてツールバー) 簡単、エンドユーザーが、レコード ビューのレコード間を移動するためにアプリケーション ウィザードで作成リソースを移動するため、最初次、前、または最後のレコードです。 ClassWizard とレコード ビュー クラスを作成する場合は、エディターを作成するこれらのリソース自分でメニューとビットマップを使用する必要があります。  
  
 レコード間を移動するための既定の実装については、次を参照してください。`IsOnFirstRecord`と`IsOnLastRecord`」および「[レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)、両方に適用されます`CRecordView`と`CDaoRecordView`です。  
  
 `CDaoRecordView` 追跡レコード セット内のユーザーの位置、レコード ビューは、ユーザー インターフェイスを更新できるようにします。 ユーザーは、レコード セットの先頭または末尾に移動、レコード ビュー、ユーザー インターフェイス オブジェクトを無効になります: メニュー項目またはツール バー ボタンなど — を移動するため、同じ方向にさらに。  
  
 詳細については、宣言して、レコード ビューとレコード セット クラスを使用して、参照してください「の作成、レコード ビューのデザインと」アーティクル[レコード ビュー](../../data/record-views-mfc-data-access.md)です。 レコード ビューの動作とその使用方法の詳細については、記事を参照してください。[レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)です。 上記のすべてのアーティクルが両方に適用`CRecordView`と`CDaoRecordView`です。  
  
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
  
##  <a name="cdaorecordview"></a>  指定して  
 派生した型のオブジェクトを作成するときに`CDaoRecordView`、ビュー オブジェクトを初期化し、ビューの基になるダイアログ リソースを識別するコンス トラクターのいずれかの形式を呼び出します。  
  
```  
explicit CDaoRecordView(LPCTSTR lpszTemplateName);  
explicit CDaoRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszTemplateName*  
 ダイアログ テンプレート リソースの名前を指定する null で終わる文字列が含まれています。  
  
 *nIDTemplate*  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
### <a name="remarks"></a>Remarks  
 名前 (コンス トラクターの引数として文字列を渡す) によって、または ID (パスを符号なし整数の引数として) か、リソースを識別できます。 リソースを使用して ID をお勧めします。  
  
> [!NOTE]
>  派生クラスでは、独自のコンス トラクターを指定する必要があります。 派生クラスのコンス トラクターで、コンス トラクターを呼び出します`CDaoRecordView::CDaoRecordView`リソース名または ID を引数として使用します。  
  
 `CDaoRecordView::OnInitialUpdate` 呼び出し`CWnd::UpdateData`、どの呼び出し`CWnd::DoDataExchange`です。 この最初の呼び出し`DoDataExchange`接続`CDaoRecordView`(間接的に) に制御`CDaoRecordset`ClassWizard で作成したデータ メンバーのフィールドです。 これらのデータ メンバーは、基本クラスを呼び出した後まで使用できません`CFormView::OnInitialUpdate`メンバー関数。  
  
> [!NOTE]
>  ClassWizard を使用する場合、ウィザードで定義、 **enum**値`CDaoRecordView::IDD`コンス トラクターの一覧でメンバーの初期化を使用してクラスの宣言にします。  
  
 [!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>  CDaoRecordView::IsOnFirstRecord  
 現在のレコードがレコード ビューに関連付けられているレコード セット オブジェクトの最初のレコードであるかどうかを判別するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>戻り値  
 現在のレコードがレコード セットの最初のレコードの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は ClassWizard で作成されたコマンド更新ハンドラーの既定の実装を記述するために役立ちます。  
  
 ユーザーは、最初のレコードに移動、すべてのユーザー インターフェイス オブジェクト (メニュー項目やツール バー ボタンなど) フレームワークを無効になりますがある場合、最初のページと前のレコードに移動するためです。  
  
##  <a name="isonlastrecord"></a>  CDaoRecordView::IsOnLastRecord  
 現在のレコードがレコード ビューに関連付けられているレコード セット オブジェクトの最後のレコードであるかどうかを判別するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>戻り値  
 現在のレコードがレコード セットの最後のレコードの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数は、classwizard レコード間を移動するためのユーザー インターフェイスをサポートするためにコマンド更新ハンドラーの既定の実装を記述するために役立ちます。  
  
> [!CAUTION]
>  ビューは、それ以降、ユーザーに移動されるまで、レコード セットの末尾が検出できない場合がある点を除いて、この関数の結果は信頼できます。 ユーザーは、[次へ] または最後のレコードに移動するためのユーザー インターフェイス オブジェクトを無効にする必要があります、レコード ビューが通知前に、最後のレコードを超える移動する必要があります。 最後のレコードの後ろに移動し、移動最後のレコード (またはその前に)、レコード ビュー、レコード セット内のユーザーの位置を追跡できユーザー インターフェイス オブジェクトを正しく無効にできます。  
  
##  <a name="ongetrecordset"></a>  CDaoRecordView::OnGetRecordset  
 ポインターを返します、 `CDaoRecordset`-レコード ビューに関連付けられているオブジェクトを派生します。  
  
```  
virtual CDaoRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `CDaoRecordset`-派生オブジェクトのオブジェクトが正常に作成されたそれ以外の場合、 **NULL**ポインター。  
  
### <a name="remarks"></a>Remarks  
 作成またはレコード セット オブジェクトを取得してにポインターを返すには、このメンバー関数をオーバーライドする必要があります。 ClassWizard で、レコード ビュー クラスを宣言する場合の既定のオーバーライドが書き込まれます。 ClassWizard の既定の実装では、いずれかが存在する場合は、レコード ビューに格納されているレコード セットのポインターを返します。 ClassWizard でユーザーが指定した型のレコード セット オブジェクトを構築されていない場合、`Open`メンバー関数のテーブルを開くか、クエリを実行して、オブジェクトへのポインターを返します。  
  
 詳細と例については、記事を参照してください。[レコード ビュー: レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)です。  
  
##  <a name="onmove"></a>  CDaoRecordView::OnMove  
 レコード セット内の別のレコードに移動し、レコード ビューのコントロールにそのフィールドを表示するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDMoveCommand*  
 標準コマンド ID 値は次のいずれかです。  
  
- `ID_RECORD_FIRST` レコード セットの最初のレコードに移動します。  
  
- `ID_RECORD_LAST` レコード セットの最後のレコードに移動します。  
  
- `ID_RECORD_NEXT` レコード セットの次のレコードに移動します。  
  
- `ID_RECORD_PREV` レコード セットの前のレコードに移動します。  
  
### <a name="return-value"></a>戻り値  
 移動が成功した場合は 0 以外。移動要求が拒否された場合は、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 既定の実装が、適切な移動のメンバー関数を呼び出す、`CDaoRecordset`レコード ビューに関連付けられているオブジェクト。  
  
 既定では、`OnMove`ユーザーを使用すると、レコード ビューに変更された場合に、データ ソースの現在のレコードを更新します。  
  
 アプリケーションのウィザードでは、最初のレコード、最後のレコード、次のレコードと前のレコードのメニュー項目をメニュー リソースを作成します。 [ツールバー] オプションを選択した場合、アプリケーションのウィザードもこれらのコマンドに対応するボタンをツールバーを作成します。  
  
 過去のレコード セットの最後のレコードを移動する場合、レコード ビューを最後のレコードが表示されます。 を越えて移動した最初のレコード場合、レコード ビューは最初のレコードが表示されます。  
  
> [!CAUTION]
>  呼び出す`OnMove`レコード セットにレコードが存在しない場合、例外をスローします。 適切なユーザー インターフェイス更新ハンドラー関数を呼び出す — `OnUpdateRecordFirst`、 `OnUpdateRecordLast`、 `OnUpdateRecordNext`、または`OnUpdateRecordPrev`: 対応する前に、レコード セットがすべてのレコードを持つかどうかを決定する操作を移動します。  
  
## <a name="see-also"></a>関連項目  
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)
