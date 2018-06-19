---
title: COleBusyDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleBusyDialog
- AFXODLGS/COleBusyDialog
- AFXODLGS/COleBusyDialog::COleBusyDialog
- AFXODLGS/COleBusyDialog::DoModal
- AFXODLGS/COleBusyDialog::GetSelectionType
- AFXODLGS/COleBusyDialog::m_bz
dev_langs:
- C++
helpviewer_keywords:
- COleBusyDialog [MFC], COleBusyDialog
- COleBusyDialog [MFC], DoModal
- COleBusyDialog [MFC], GetSelectionType
- COleBusyDialog [MFC], m_bz
ms.assetid: c881a532-9672-4c41-b51b-5ce4a7246a6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b061d2cc31a67c2e6059abeaadb6062b77cacb88
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374371"
---
# <a name="colebusydialog-class"></a>COleBusyDialog クラス
OLE の [サーバーが応答しません] ダイアログ ボックスまたは [サーバーを使用できません] ダイアログ ボックスに使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class COleBusyDialog : public COleDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleBusyDialog::COleBusyDialog](#colebusydialog)|`COleBusyDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleBusyDialog::DoModal](#domodal)|OLE サーバーがビジー状態のダイアログ ボックスが表示されます。|  
|[COleBusyDialog::GetSelectionType](#getselectiontype)|ダイアログ ボックスで行った選択を決定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleBusyDialog::m_bz](#m_bz)|型の構造体**OLEUIBUSY**  ダイアログ ボックスの動作を制御します。|  
  
## <a name="remarks"></a>コメント  
 クラスのオブジェクトを作成`COleBusyDialog`をこれらのダイアログ ボックスを呼び出したいとします。 後に、`COleBusyDialog`オブジェクトが構築された、使用することができます、[各](#m_bz)値やダイアログ ボックスのコントロールの状態を初期化するためにします。 `m_bz`構造体は型**OLEUIBUSY**です。 このダイアログ ボックスの使い方の詳細については、次を参照してください。、 [DoModal](#domodal)メンバー関数。  
  
> [!NOTE]
>  アプリケーション コンテナーのウィザードで生成されたコードでは、このクラスを使用します。  
  
 詳細については、次を参照してください。、 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK 内の構造。  
  
 OLE に固有のダイアログ ボックスの詳細については、記事を参照してください。 [OLE のダイアログ ボックス](../../mfc/dialog-boxes-in-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleBusyDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxodlgs.h  
  
##  <a name="colebusydialog"></a>  COleBusyDialog::COleBusyDialog  
 この関数は、`COleBusyDialog`オブジェクト。  
  
```  
explicit COleBusyDialog(
    HTASK htaskBusy,  
    BOOL bNotResponding = FALSE,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *htaskBusy*  
 ビジー状態であるサーバーのタスクへのハンドルします。  
  
 *bNotResponding*  
 場合**TRUE**サーバーがビジー状態のダイアログ ボックスの代わりに応答していません ダイアログ ボックスを呼び出します。 応答していません ダイアログ ボックスの内容は、サーバーがビジー状態 ダイアログ ボックスの内容と若干異なると、キャンセル ボタンが無効にします。  
  
 `dwFlags`  
 作成フラグ。 0 個以上のビットごとの OR 演算子と組み合わせて、次の値を含めることができます。  
  
- **BZ_DISABLECANCELBUTTON**  ダイアログ ボックスを呼び出すときに、キャンセル ボタンを無効にします。  
  
- **BZ_DISABLESWITCHTOBUTTON**  ダイアログ ボックスを呼び出すときに、切り替えボタンを無効にします。  
  
- **BZ_DISABLERETRYBUTTON**  ダイアログ ボックスを呼び出すときに、再試行 を無効にします。  
  
 `pParentWnd`  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の`CWnd`) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>コメント  
 ダイアログ ボックスを表示するには、呼び出す[DoModal](#domodal)です。  
  
 詳細については、次を参照してください。、 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK 内の構造。  
  
##  <a name="domodal"></a>  COleBusyDialog::DoModal  
 OLE サーバーがビジー状態かサーバーが応答していません ダイアログ ボックスを表示するには、この関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスの終了ステータスです。 次のいずれかの値です。  
  
- **IDOK**  ダイアログ ボックスが正常に表示された場合。  
  
- **IDCANCEL**場合は、ユーザーがダイアログ ボックスをキャンセルします。  
  
- **IDABORT**場合はエラーが発生しました。 場合**IDABORT**は呼び出し、返される、`COleDialog::GetLastError`の詳細については、発生したエラーの種類を取得します。 考えられるエラーの一覧については、次を参照してください。、 [OleUIBusy](http://msdn.microsoft.com/library/windows/desktop/ms680125) Windows SDK 内の関数。  
  
### <a name="remarks"></a>コメント  
 メンバーを設定してさまざまなダイアログ ボックスのコントロールを初期化する場合、[各](#m_bz)構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ オブジェクトを構築します。  
  
 場合`DoModal`返します**IDOK**設定や、ダイアログ ボックスに、ユーザーが入力した情報を取得する関数の他のメンバーを呼び出すことができます。  
  
##  <a name="getselectiontype"></a>  COleBusyDialog::GetSelectionType  
 サーバーがビジー状態のダイアログ ボックスでユーザーが選択した型を取得するには、この関数を呼び出します。  
  
```  
UINT GetSelectionType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 選択内容の種類です。  
  
### <a name="remarks"></a>コメント  
 戻り値の型の値がで指定された、**選択**で宣言された列挙型、`COleBusyDialog`クラスです。  
  
```  
enum Selection {
    switchTo,
    retry,
    callUnblocked
    };
```  
  
 これらの値の簡単な説明に従ってください。  
  
- **COleBusyDialog::switchTo**切り替えボタンが押されました。  
  
- **COleBusyDialog::retry**再試行ボタンが押されました。  
  
- **COleBusyDialog::callUnblocked**サーバーをアクティブ化の呼び出しが、ブロック解除します。  
  
##  <a name="m_bz"></a>  COleBusyDialog::m_bz  
 型の構造体**OLEUIBUSY**サーバーがビジー状態 ダイアログ ボックスの動作を制御するために使用します。  
  
```  
OLEUIBUSY m_bz;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体のメンバーは、直接またはメンバー関数を使って変更できます。  
  
 詳細については、次を参照してください。、 [OLEUIBUSY](http://msdn.microsoft.com/library/windows/desktop/ms682493) Windows SDK 内の構造。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/coledialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)
