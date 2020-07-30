---
title: CDaoRecordView クラス
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
ms.openlocfilehash: 95ed9207d0047287e373401da52f05235a817999
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223136"
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
|[CDaoRecordView:: CDaoRecordView](#cdaorecordview)|`CDaoRecordView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CDaoRecordView:: IsOnFirstRecord](#isonfirstrecord)|現在のレコードが、関連付けられたレコードセット内の最初のレコードの場合は、0以外の値を返します。|
|[CDaoRecordView:: IsOnLastRecord](#isonlastrecord)|現在のレコードが、関連付けられたレコードセットの最後のレコードである場合は、0以外の値を返します。|
|[CDaoRecordView:: OnGetRecordset](#ongetrecordset)|から派生したクラスのオブジェクトへのポインターを返し `CDaoRecordset` ます。 ClassWizard はこの関数をオーバーライドし、必要に応じてレコードセットを作成します。|
|[CDaoRecordView:: OnMove](#onmove)|現在のレコードが変更されている場合、はデータソースでそのレコードを更新してから、指定されたレコード (next、previous、first、last) に移動します。|

## <a name="remarks"></a>解説

ビューは、オブジェクトに直接接続されたフォームビューです `CDaoRecordset` 。 ビューはダイアログテンプレートリソースから作成され、 `CDaoRecordset` ダイアログテンプレートのコントロールにオブジェクトのフィールドが表示されます。 オブジェクトは、 `CDaoRecordView` ダイアログデータエクスチェンジ (DDX) と DAO レコードフィールドエクスチェンジ (DFX) を使用して、フォーム上のコントロールとレコードセットのフィールドの間でのデータの移動を自動化します。 `CDaoRecordView`また、は、最初、次、前、または最後のレコードに移動するための既定の実装と、現在ビューにあるレコードを更新するためのインターフェイスを提供します。

> [!NOTE]
> DAO データベースクラスは、Open Database Connectivity (ODBC) に基づく MFC データベースクラスとは異なります。 すべての DAO データベースクラス名には、"CDao" プレフィックスが付いています。 DAO クラスを使用して ODBC データソースにアクセスすることもできます。DAO クラスは、一般に Microsoft Jet データベースエンジンを使用するため、優れた機能を提供します。

レコードビューを作成する最も一般的な方法は、アプリケーションウィザードを使用することです。 アプリケーションウィザードでは、レコードビュークラスとそれに関連付けられているレコードセットクラスの両方がスケルトンスターターアプリケーションの一部として作成されます。

単に1つのフォームが必要な場合は、アプリケーションウィザードのアプローチが簡単です。 ClassWizard では、開発プロセスの後半でレコードビューを使用することを決定できます。 アプリケーションウィザードでレコードビュークラスを作成しない場合は、後で ClassWizard を使用して作成できます。 ClassWizard を使用してレコードビューとレコードセットを個別に作成し、それを接続することは、レコードセットクラスとそのの名前付けをより細かく制御できるため、最も柔軟な方法です。H/。CPP ファイル。 この方法では、同じレコードセットクラスに複数のレコードビューを含めることもできます。

エンドユーザーがレコードビューでレコード間を簡単に移動できるようにするために、アプリケーションウィザードでは、最初、次、前、または最後のレコードに移動するためのメニュー (および必要に応じてツールバー) リソースを作成します。 ClassWizard でレコードビュークラスを作成する場合は、メニューエディターとビットマップエディターを使用してこれらのリソースを自分で作成する必要があります。

レコード間の移動の既定の実装の詳細については、「」および「」と「」を参照してください `IsOnFirstRecord` `IsOnLastRecord` 。[レコードビューは](../../data/using-a-record-view-mfc-data-access.md)、との両方に適用され `CRecordView` `CDaoRecordView` ます。

`CDaoRecordView`レコードビューでユーザーインターフェイスを更新できるように、レコードセット内のユーザーの位置を追跡します。 ユーザーがレコードセットの末尾に移動すると、[レコード] ビューでは、メニュー項目やツールバーボタンなどのユーザーインターフェイスオブジェクトが、同じ方向に移動するために無効になります。

レコードビューおよびレコードセットクラスの宣言と使用の詳細については、 [「レコードビュー](../../data/record-views-mfc-data-access.md)のデザインと作成」の「レコードビューのデザインと作成」を参照してください。 レコードビューの動作と使用方法の詳細については、[レコードビューの使用](../../data/using-a-record-view-mfc-data-access.md)に関する記事を参照してください。 前述のすべての記事は、との両方に適用され `CRecordView` `CDaoRecordView` ます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

`CDaoRecordView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxdao

## <a name="cdaorecordviewcdaorecordview"></a><a name="cdaorecordview"></a>CDaoRecordView:: CDaoRecordView

から派生した型のオブジェクトを作成する場合は `CDaoRecordView` 、コンストラクターのいずれかの形式を呼び出して、ビューオブジェクトを初期化し、ビューの基になるダイアログリソースを識別します。

```
explicit CDaoRecordView(LPCTSTR lpszTemplateName);
explicit CDaoRecordView(UINT nIDTemplate);
```

### <a name="parameters"></a>パラメーター

*lpszTemplateName*<br/>
ダイアログテンプレートリソースの名前である null で終わる文字列を格納します。

*nIDTemplate*<br/>
ダイアログテンプレートリソースの ID 番号を格納します。

### <a name="remarks"></a>解説

リソースを名前で識別する (コンストラクターの引数として文字列を渡す) か、ID (符号なし整数を引数として渡す) のいずれかを指定できます。 リソース ID を使用することをお勧めします。

> [!NOTE]
> 派生クラスは、独自のコンストラクターを提供する必要があります。 派生クラスのコンストラクターで、 `CDaoRecordView::CDaoRecordView` リソース名または ID を引数として使用してコンストラクターを呼び出します。

`CDaoRecordView::OnInitialUpdate`を呼び出す `CWnd::UpdateData` と、が呼び出さ `CWnd::DoDataExchange` れます。 への最初の呼び出しでは、 `DoDataExchange` `CDaoRecordView` `CDaoRecordset` ClassWizard によって作成されたフィールドデータメンバーにコントロール (間接的に) を接続します。 これらのデータメンバーは、基底クラスのメンバー関数を呼び出すまで使用できません `CFormView::OnInitialUpdate` 。

> [!NOTE]
> ClassWizard を使用する場合、ウィザードは **`enum`** `CDaoRecordView::IDD` クラス宣言で値を定義し、コンストラクターのメンバー初期化リストでそれを使用します。

[!code-cpp[NVC_MFCDatabase#35](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]

## <a name="cdaorecordviewisonfirstrecord"></a><a name="isonfirstrecord"></a>CDaoRecordView:: IsOnFirstRecord

このメンバー関数を呼び出して、現在のレコードが、このレコードビューに関連付けられているレコードセットオブジェクトの最初のレコードであるかどうかを確認します。

```
BOOL IsOnFirstRecord();
```

### <a name="return-value"></a>戻り値

現在のレコードがレコードセット内の最初のレコードである場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、ClassWizard によって作成された既定のコマンド更新ハンドラーの独自の実装を記述する場合に便利です。

ユーザーが最初のレコードに移動した場合、フレームワークは、最初または前のレコードに移動するために必要なユーザーインターフェイスオブジェクト (メニュー項目やツールバーボタンなど) を無効にします。

## <a name="cdaorecordviewisonlastrecord"></a><a name="isonlastrecord"></a>CDaoRecordView:: IsOnLastRecord

このメンバー関数を呼び出して、現在のレコードが、このレコードビューに関連付けられているレコードセットオブジェクトの最後のレコードであるかどうかを確認します。

```
BOOL IsOnLastRecord();
```

### <a name="return-value"></a>戻り値

現在のレコードがレコードセット内の最後のレコードである場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数は、ClassWizard によって記述された既定のコマンド更新ハンドラーの実装を作成して、レコードからレコードへ移動するためのユーザーインターフェイスをサポートする場合に役立ちます。

> [!CAUTION]
> この関数の結果は信頼性が高くなります。ただし、ビューでは、ユーザーがレコードセットを移動してから、レコードセットの末尾を検出できない可能性があります。 ユーザーは最後のレコードを超えて移動することが必要になる場合があります。レコードビューでは、次のレコードまたは最後のレコードに移動するためにユーザーインターフェイスオブジェクトを無効にする必要があることがわかります。 ユーザーが最後のレコードを移動してから最後のレコード (またはその前) に戻ると、レコードビューでレコードセット内のユーザーの位置を追跡し、ユーザーインターフェイスオブジェクトを正しく無効にすることができます。

## <a name="cdaorecordviewongetrecordset"></a><a name="ongetrecordset"></a>CDaoRecordView:: OnGetRecordset

`CDaoRecordset`レコードビューに関連付けられているから派生したオブジェクトへのポインターを返します。

```
virtual CDaoRecordset* OnGetRecordset() = 0;
```

### <a name="return-value"></a>戻り値

`CDaoRecordset`オブジェクトが正常に作成された場合は、派生オブジェクトへのポインター。それ以外の場合は NULL ポインター。

### <a name="remarks"></a>解説

このメンバー関数をオーバーライドして、レコードセットオブジェクトを構築または取得し、そのオブジェクトへのポインターを返すようにする必要があります。 ClassWizard でレコードビュークラスを宣言すると、ウィザードによって既定の上書きが書き込まれます。 ClassWizard の既定の実装では、レコードビューに格納されているレコードセットポインターが存在する場合、そのポインターが返されます。 そうでない場合は、ClassWizard で指定した型のレコードセットオブジェクトを構築し、そのメンバー関数を呼び出して `Open` テーブルを開くかクエリを実行し、オブジェクトへのポインターを返します。

詳細と例については、レコード[ビューの使用](../../data/using-a-record-view-mfc-data-access.md)に関する記事を参照してください。

## <a name="cdaorecordviewonmove"></a><a name="onmove"></a>CDaoRecordView:: OnMove

レコードセット内の別のレコードに移動し、そのフィールドを [レコード] ビューのコントロールに表示するには、このメンバー関数を呼び出します。

```
virtual BOOL OnMove(UINT nIDMoveCommand);
```

### <a name="parameters"></a>パラメーター

*nIDMoveCommand*<br/>
次の標準コマンド ID 値のいずれか。

- ID_RECORD_FIRST レコードセット内の最初のレコードに移動します。

- ID_RECORD_LAST レコードセット内の最後のレコードに移動します。

- ID_RECORD_NEXT レコードセット内の次のレコードに移動します。

- ID_RECORD_PREV レコードセット内の前のレコードに移動します。

### <a name="return-value"></a>戻り値

移動が成功した場合は0以外の。それ以外の場合は、移動要求が拒否された場合は0です。

### <a name="remarks"></a>解説

既定の実装は、 `CDaoRecordset` レコードビューに関連付けられているオブジェクトの適切な移動メンバー関数を呼び出します。

既定では、は、 `OnMove` ユーザーがレコードビューで変更した場合、データソースの現在のレコードを更新します。

アプリケーションウィザードでは、最初のレコード、最後のレコード、次のレコード、および前の [レコード] メニュー項目を含むメニューリソースが作成されます。 [最初のツールバー] オプションを選択した場合、アプリケーションウィザードでは、これらのコマンドに対応するボタンを備えたツールバーも作成されます。

レコードセットの最後のレコードを越えて移動すると、レコードビューでは、最後のレコードが引き続き表示されます。 最初のレコードを後方に移動すると、レコードビューでは、最初のレコードが引き続き表示されます。

> [!CAUTION]
> レコード `OnMove` セットにレコードがない場合、を呼び出すと例外がスローされます。 対応する移動操作の前に、適切なユーザーインターフェイス更新ハンドラー関数 (、、、または) を呼び出して、レコード `OnUpdateRecordFirst` `OnUpdateRecordLast` セットに `OnUpdateRecordNext` `OnUpdateRecordPrev` レコードがあるかどうかを確認します。

## <a name="see-also"></a>関連項目

[CFormView クラス](../../mfc/reference/cformview-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CFormView クラス](../../mfc/reference/cformview-class.md)
