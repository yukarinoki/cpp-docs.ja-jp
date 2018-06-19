---
title: CDataExchange クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03d68359d075efd72a1bf1907daa71e74110fa28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368938"
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
|[CDataExchange::CDataExchange](#cdataexchange)|`CDataExchange` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDataExchange::Fail](#fail)|検証が失敗したときに呼び出されます。 前のコントロールにフォーカスをリセットし、例外をスローします。|  
|[CDataExchange::PrepareCtrl](#preparectrl)|データ交換または検証のためには、指定したコントロールを準備します。 エディット コントロールに使用します。|  
|[CDataExchange::PrepareEditCtrl](#prepareeditctrl)|データ交換または検証のためには、指定されたエディット コントロールを準備します。|  
|[CDataExchange::PrepareOleCtrl](#prepareolectrl)|データ交換または検証のためには、指定した OLE コントロールを準備します。 エディット コントロールに使用します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDataExchange::m_bSaveAndValidate](#m_bsaveandvalidate)|DDX ルーチンおよび DDV の方向を示すフラグします。|  
|[CDataExchange::m_pDlgWnd](#m_pdlgwnd)|データ交換がダイアログ ボックスまたはウィンドウが行われます。|  
  
## <a name="remarks"></a>コメント  
 `CDataExchange` 基本クラスはありません。  
  
 コントロールやカスタム データ型のデータ エクス チェンジ ルーチンを記述する場合は、このクラスを使用して、独自のデータ検証ルーチンを記述する場合またはします。 DDX ルーチンおよび DDV ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)です。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ ダイアログ ボックス](../../mfc/dialog-boxes.md)です。  
  
 A`CDataExchange`オブジェクト DDX ルーチンおよび DDV を配置に必要なコンテキスト情報を提供します。 フラグ`m_bSaveAndValidate`は**FALSE**データ メンバーからダイアログ コントロールの初期値を入力する DDX を使用する場合。 フラグ`m_bSaveAndValidate`は**TRUE**データ メンバーおよびデータ値を検証する DDV を使用する場合にダイアログ コントロールの現在の値を設定する DDX を使用する場合。 DDV 検証が失敗した場合、ddv 入力エラーを示すメッセージ ボックスが表示されます。 DDV プロシージャが呼び出され、**失敗**害のあるコントロールにフォーカスをリセットし、検証プロセスを停止する例外をスローします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CDataExchange`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cdataexchange"></a>  CDataExchange::CDataExchange  
 構築するには、このメンバー関数を呼び出す、`CDataExchange`オブジェクト。  
  
```  
CDataExchange(
    CWnd* pDlgWnd,  
    BOOL bSaveAndValidate);
```  
  
### <a name="parameters"></a>パラメーター  
 *pDlgWnd*  
 コントロールを格納する親ウィンドウへのポインター。 これは通常、 [CDialog](../../mfc/reference/cdialog-class.md)-派生オブジェクト。  
  
 `bSaveAndValidate`  
 場合**TRUE**、このオブジェクトは、データを検証し、メンバーへのコントロールからデータを書き込みます。 場合**FALSE**、このオブジェクトは、メンバーからデータをコントロールに移動されます。  
  
### <a name="remarks"></a>コメント  
 構築、`CDataExchange`オブジェクトに渡す、ウィンドウのデータ交換オブジェクトに追加情報を格納する自分で[CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]  
  
##  <a name="fail"></a>  CDataExchange::Fail  
 ダイアログ データ バリデーション (DDV) の操作が失敗したときに、フレームワークはこのメンバー関数を呼び出します。  
  
```  
void Fail();
```  
  
### <a name="remarks"></a>コメント  
 **失敗**が検証には、(を復元するコントロールがある場合) が失敗しました。 コントロールにフォーカスと選択を復元します。 **失敗**型の例外をスロー[チェック](../../mfc/reference/cuserexception-class.md)検証プロセスを停止します。 例外は、メッセージ ボックスが表示されるエラーの説明をによりします。 DDV 検証が失敗した後、ユーザーは、問題のあるコントロール内のデータを再入力できます。  
  
 DDV ルーチンのカスタムの実装を呼び出すことができます**失敗**検証が失敗したときに、そのルーチンからです。  
  
 DDX ルーチンおよび DDV ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)です。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)です。  
  
##  <a name="m_bsaveandvalidate"></a>  CDataExchange::m_bSaveAndValidate  
 このフラグは、ダイアログ データ エクス (チェンジ DDX) 操作の方向を示します。  
  
```  
BOOL m_bSaveAndValidate;  
```  
  
### <a name="remarks"></a>コメント  
 フラグが 0 でない場合、`CDataExchange`オブジェクトは、ユーザーがコントロールを編集した後は、ダイアログ クラスのデータ メンバーにダイアログのコントロールからデータを移動に使用されています。 オブジェクトは、ダイアログ コントロール ダイアログ クラスのデータ メンバーからを初期化するために使用されている場合、このフラグは 0 です。  
  
 ダイアログ データ バリデーション (DDV) の中には、フラグを 0 以外の値もです。  
  
 DDX ルーチンおよび DDV ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)です。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)です。  
  
##  <a name="m_pdlgwnd"></a>  CDataExchange::m_pDlgWnd  
 ポインターが含まれています、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクト ダイアログ データ エクス (チェンジ DDX) または検証 (DDV) が行われています。  
  
```  
CWnd* m_pDlgWnd;  
```  
  
### <a name="remarks"></a>コメント  
 このオブジェクトは、通常、 [CDialog](../../mfc/reference/cdialog-class.md)オブジェクト。 独自の DDX または DDV ルーチンを記述するときは、このポインターを使用して、操作するコントロールを含むダイアログ ウィンドウへのアクセスを取得します。  
  
 DDX ルーチンおよび DDV ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)です。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)です。  
  
##  <a name="preparectrl"></a>  CDataExchange::PrepareCtrl  
 フレームワークは、ダイアログ データ エクス (チェンジ DDX) および検証 (DDV) の指定したコントロールを準備するには、このメンバー関数を呼び出します。  
  
```  
HWND PrepareCtrl(int nIDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDC`  
 DDX または DDV の準備をするコントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 `HWND` DDX DDV 用に準備されているコントロールのです。  
  
### <a name="remarks"></a>コメント  
 使用して[性チェックされる](#prepareeditctrl)代わりにエディット コントロールを他のすべてのコントロールのこのメンバー関数を使用します。  
  
 コントロールを格納するは、準備`HWND`で、`CDataExchange`クラスです。 フレームワークでは、このハンドルを使用して、DDX または DDV に障害が発生した場合、以前フォーカスされたコントロールにフォーカスを復元します。  
  
 独自の DDX または DDV ルーチンを記述するときに呼び出す必要があります`PrepareCtrl`すべての非エディット コントロールを DDX を使用してデータを交換するされたり、DDV を使ってデータを検証します。  
  
 DDX ルーチンおよび DDV ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)です。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)です。  
  
##  <a name="prepareeditctrl"></a>  CDataExchange::PrepareEditCtrl  
 フレームワークは、ダイアログ データ エクス (チェンジ DDX) および検証 (DDV) の指定した編集コントロールを準備するには、このメンバー関数を呼び出します。  
  
```  
HWND PrepareEditCtrl(int nIDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDC`  
 DDX または DDV の準備をするエディット コントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 `HWND` DDX DDV 用に準備されている編集コントロールのです。  
  
### <a name="remarks"></a>コメント  
 使用して[記述](#preparectrl)代わりにすべての非エディット コントロールにします。  
  
 準備は、次の 2 つで構成されます。 最初に、`PrepareEditCtrl`コントロールの格納`HWND`で、`CDataExchange`クラスです。 フレームワークでは、このハンドルを使用して、DDX または DDV に障害が発生した場合、以前フォーカスされたコントロールにフォーカスを復元します。 2 番目、`PrepareEditCtrl`にフラグを設定、`CDataExchange`ことを示すクラスのデータが交換またはエディット コントロールは、検証コントロール。  
  
 独自の DDX または DDV ルーチンを記述するときに呼び出す必要があります`PrepareEditCtrl`のすべての編集コントロールを DDX を使用してデータを交換するされたり、DDV を使ってデータを検証します。  
  
 DDX ルーチンおよび DDV ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)です。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)です。  
  
##  <a name="prepareolectrl"></a>  CDataExchange::PrepareOleCtrl  
 フレームワークは、ダイアログ データ エクス (チェンジ DDX) および検証 (DDV) の指定した OLE コントロールを準備するには、このメンバー関数を呼び出します。  
  
```  
COleControlSite* PrepareOleCtrl(int nIDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDC`  
 DDX または DDV の準備をする OLE コントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 OLE コントロール サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 使用[性チェックされる](#prepareeditctrl)代わりにエディット コントロールのまたは[記述](#preparectrl)他のすべての非 OLE コントロール。  
  
 独自の DDX または DDV ルーチンを記述するときに呼び出す必要があります`PrepareOleCtrl`のすべての OLE コントロールを DDX を使用してデータを交換するされたり、DDV を使ってデータを検証します。  
  
 DDX ルーチンおよび DDV ルーチンの作成方法の詳細については、次を参照してください。[テクニカル ノート 26](../../mfc/tn026-ddx-and-ddv-routines.md)です。 DDX ルーチンおよび DDV の概要については、次を参照してください。[ダイアログ データ エクス チェンジと検証](../../mfc/dialog-data-exchange-and-validation.md)と[ダイアログ ボックスに関するトピック](../../mfc/dialog-boxes.md)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル VIEWEX](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd::DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)   
 [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)

