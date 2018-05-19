---
title: CPropertyPage クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPropertyPage
- AFXDLGS/CPropertyPage
- AFXDLGS/CPropertyPage::CPropertyPage
- AFXDLGS/CPropertyPage::CancelToClose
- AFXDLGS/CPropertyPage::Construct
- AFXDLGS/CPropertyPage::GetPSP
- AFXDLGS/CPropertyPage::OnApply
- AFXDLGS/CPropertyPage::OnCancel
- AFXDLGS/CPropertyPage::OnKillActive
- AFXDLGS/CPropertyPage::OnOK
- AFXDLGS/CPropertyPage::OnQueryCancel
- AFXDLGS/CPropertyPage::OnReset
- AFXDLGS/CPropertyPage::OnSetActive
- AFXDLGS/CPropertyPage::OnWizardBack
- AFXDLGS/CPropertyPage::OnWizardFinish
- AFXDLGS/CPropertyPage::OnWizardNext
- AFXDLGS/CPropertyPage::QuerySiblings
- AFXDLGS/CPropertyPage::SetModified
- AFXDLGS/CPropertyPage::m_psp
dev_langs:
- C++
helpviewer_keywords:
- CPropertyPage [MFC], CPropertyPage
- CPropertyPage [MFC], CancelToClose
- CPropertyPage [MFC], Construct
- CPropertyPage [MFC], GetPSP
- CPropertyPage [MFC], OnApply
- CPropertyPage [MFC], OnCancel
- CPropertyPage [MFC], OnKillActive
- CPropertyPage [MFC], OnOK
- CPropertyPage [MFC], OnQueryCancel
- CPropertyPage [MFC], OnReset
- CPropertyPage [MFC], OnSetActive
- CPropertyPage [MFC], OnWizardBack
- CPropertyPage [MFC], OnWizardFinish
- CPropertyPage [MFC], OnWizardNext
- CPropertyPage [MFC], QuerySiblings
- CPropertyPage [MFC], SetModified
- CPropertyPage [MFC], m_psp
ms.assetid: d9000a21-aa81-4530-85d9-f43432afb4dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 434a0b428199b7c2298815523517097aeee2ab47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cpropertypage-class"></a>CPropertyPage クラス
タブ ダイアログ ボックスとして知られているプロパティ シートの各ページを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CPropertyPage : public CDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertyPage::CPropertyPage](#cpropertypage)|`CPropertyPage` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertyPage::CancelToClose](#canceltoclose)|[閉じる] ボタンに変更し、モーダル プロパティ シートのページで回復不可能な、変更した後に [キャンセル] ボタンを無効にします。|  
|[CPropertyPage::Construct](#construct)|`CPropertyPage` オブジェクトを構築します。 使用して`Construct`、実行時に、パラメーターを指定する場合、または配列を使用している場合。|  
|[CPropertyPage::GetPSP](#getpsp)|Windows の取得[PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)構造に関連付けられている、`CPropertyPage`オブジェクト。|  
|[CPropertyPage::OnApply](#onapply)|今すぐ適用 ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnCancel](#oncancel)|[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnKillActive](#onkillactive)|現在のページがアクティブでは不要になったときに、フレームワークによって呼び出されます。 ここでデータの検証を実行します。|  
|[送るに](#onok)|Ok、今すぐ適用、または 閉じる ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnQueryCancel](#onquerycancel)|[キャンセル] ボタンがクリックされたときに、キャンセルが行われる前に、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnReset](#onreset)|[キャンセル] ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnSetActive](#onsetactive)|ページには、アクティブなページが行われたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardBack](#onwizardback)|ウィザード形式のプロパティ シートを使用しているときに、[戻る] ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardFinish](#onwizardfinish)|ウィザード形式のプロパティ シートを使用しているときに、[完了] ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::OnWizardNext](#onwizardnext)|ウィザード形式のプロパティ シートを使用しているときに、[次へ] ボタンがクリックされたときに、フレームワークによって呼び出されます。|  
|[CPropertyPage::QuerySiblings](#querysiblings)|プロパティ シートの各ページにメッセージを転送します。|  
|[CPropertyPage::SetModified](#setmodified)|今すぐ適用 ボタンをアクティブまたは非アクティブの呼び出しです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CPropertyPage::m_psp](#m_psp)|Windows [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)構造体。 基本的なプロパティ ページのパラメーターへのアクセスを提供します。|  
  
## <a name="remarks"></a>コメント  
 クラスを派生する標準的なダイアログ ボックスで、`CPropertyPage`プロパティ シートの各ページに対してです。 使用する`CPropertyPage`-派生オブジェクトは、まずを作成、 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)オブジェクト、およびプロパティ シートでページごとにオブジェクトを作成します。 呼び出す[が](../../mfc/reference/cpropertysheet-class.md#addpage)各シートで、ページし、呼び出すことによって、プロパティ シートを表示[する](../../mfc/reference/cpropertysheet-class.md#domodal)、モーダル プロパティ シートまたは[CPropertySheet:。作成](../../mfc/reference/cpropertysheet-class.md#create)モードレス プロパティ シートのです。  
  
 デバイスのセットアップやニュースレターを作成するなど、操作の手順を追ってプロパティ ページのシーケンスを持つプロパティ シートで構成される、ウィザードと呼ばれるタブ ダイアログ ボックスの種類を作成できます。 ウィザードの種類 タブのダイアログ ボックスでは、プロパティ ページには、タブはありません。 と、一度に 1 つのプロパティ ページが表示されます。 また、ボタンが ok と 今すぐ適用するのではなくウィザード型タブ ダイアログ ボックスが、戻る ボタン、次へ または 完了 ボタン、および キャンセル ボタン。  
  
 ウィザードとしてプロパティ シートを確立する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)です。 使用する方法についての`CPropertyPage`、オブジェクトが、記事を参照して[プロパティ シートとプロパティ ページ](../../mfc/property-sheets-and-property-pages-in-mfc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CPropertyPage`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="canceltoclose"></a>  CPropertyPage::CancelToClose  
 モーダル プロパティ シートのページ内のデータを回復できない変更が行われた後は、この関数を呼び出します。  
  
```  
void CancelToClose();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、[ok] ボタンを閉じるに変更し、[キャンセル] ボタンを無効にします。 これは、アラートの変更が確定され、変更があるユーザーはキャンセルできませんを変更します。  
  
 `CancelToClose`モードレス プロパティ シートでは、既定では、[キャンセル] ボタンはありませんのでメンバー関数は、モードレス プロパティ シートではありません。  
  
### <a name="example"></a>例  
  例を参照して[CPropertyPage::QuerySiblings](#querysiblings)です。  
  
##  <a name="construct"></a>  CPropertyPage::Construct  
 構築するには、このメンバー関数を呼び出す、`CPropertyPage`オブジェクト。  
  
```  
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0);

 
void Construct(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);

 
void Construct(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDTemplate`  
 このページで使用するテンプレートの ID です。  
  
 `nIDCaption`  
 このページのタブに配置する名前の ID です。 0 の場合、名前がこのページのダイアログ テンプレートから取得されます。  
  
 `lpszTemplateName`  
 テンプレート リソースの名前を表す null で終わる文字列が含まれています。  
  
 `nIDHeaderTitle`  
 プロパティ ページのヘッダーのタイトルの位置に配置する名前の ID です。 既定では、0 です。  
  
 `nIDHeaderSubTitle`  
 プロパティ ページのヘッダーの字幕の場所に配置する名前の ID です。 既定では、0 です。  
  
### <a name="remarks"></a>コメント  
 すべての次の条件が満たされた後、オブジェクトが表示されます。  
  
-   ページを使用してプロパティ シートに追加された[が](../../mfc/reference/cpropertysheet-class.md#addpage)です。  
  
-   プロパティ シートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)または[作成](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。  
  
-   ユーザーが選択されています (タブ) このページ。  
  
 呼び出す**構築**他のクラス コンス トラクターのいずれかが呼び出されていない場合。 `Construct`パラメーター ステートメントを空白のままにして、コードで複数のパラメーターと任意の時点の構築を指定するので、メンバー関数は柔軟です。  
  
 使用する必要があります`Construct`ときに、配列を使用して、呼び出す必要があります**構築**配列の各メンバーのデータ メンバーには、適切な値が割り当てられるようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#112](../../mfc/codesnippet/cpp/cpropertypage-class_1.cpp)]  
  
##  <a name="cpropertypage"></a>  CPropertyPage::CPropertyPage  
 `CPropertyPage` オブジェクトを構築します。  
  
```  
CPropertyPage();

 
explicit CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
explicit CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    UINT nIDTemplate,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));

 
CPropertyPage(
    LPCTSTR lpszTemplateName,  
    UINT nIDCaption,  
    UINT nIDHeaderTitle,  
    UINT nIDHeaderSubTitle = 0,  
    DWORD dwSize = sizeof(PROPSHEETPAGE));
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDTemplate`  
 このページで使用するテンプレートの ID です。  
  
 `nIDCaption`  
 このページのタブに配置する名前の ID です。 0 の場合、名前がこのページのダイアログ テンプレートから取得されます。  
  
 `dwSize`  
 `lpszTemplateName`  
 このページのテンプレートの名前を含む文字列へのポインター。 ことはできません**NULL**です。  
  
 `nIDHeaderTitle`  
 プロパティ ページのヘッダーのタイトルの位置に配置する名前の ID です。  
  
 `nIDHeaderSubTitle`  
 プロパティ ページのヘッダーの字幕の場所に配置する名前の ID です。  
  
### <a name="remarks"></a>コメント  
 すべての次の条件が満たされた後、オブジェクトが表示されます。  
  
-   ページを使用してプロパティ シートに追加された[が](../../mfc/reference/cpropertysheet-class.md#addpage)です。  
  
-   プロパティ シートの[DoModal](../../mfc/reference/cpropertysheet-class.md#domodal)または[作成](../../mfc/reference/cpropertysheet-class.md#create)関数が呼び出されました。  
  
-   ユーザーが選択されています (タブ) このページ。  
  
 複数のパラメーター (たとえば、配列を使用している場合) があればを使用して[まず、](../../mfc/reference/cpropertysheet-class.md#construct)の代わりに`CPropertyPage`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#113](../../mfc/codesnippet/cpp/cpropertypage-class_2.cpp)]  
  
##  <a name="getpsp"></a>  CPropertyPage::GetPSP  
 Windows の取得[PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)構造に関連付けられている、`CPropertyPage`オブジェクト。  
  
```  
const PROPSHEETPAGE& GetPSP() const;  
  
PROPSHEETPAGE& GetPSP();
```  
  
### <a name="return-value"></a>戻り値  
 参照、 **PROPSHEETPAGE**構造体。  
  
##  <a name="m_psp"></a>  CPropertyPage::m_psp  
 `m_psp` 構造体メンバーの格納の特性は、 [PROPSHEETPAGE](http://msdn.microsoft.com/library/windows/desktop/bb774548)です。  
  
```  
PROPSHEETPAGE m_psp;  
```  
  
### <a name="remarks"></a>コメント  
 この構造体を使用して、構築した後、プロパティ ページの外観を初期化します。  
  
 そのメンバーの一覧を含めて、この構造の詳細についてを参照してください。 **PROPSHEETPAGE** Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#128](../../mfc/codesnippet/cpp/cpropertypage-class_3.cpp)]  
  
##  <a name="onapply"></a>  CPropertyPage::OnApply  
 このメンバー関数は、[ok] または [適用] を選択すると、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnApply();
```  
  
### <a name="return-value"></a>戻り値  
 変更が受け付けられた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークがこの関数を呼び出すと、プロパティ シート内のすべてのプロパティ ページに加えられた変更が受け入れられます、プロパティ シートが、フォーカスを保持および`OnApply`返します**TRUE** (値 1)。 前に`OnApply`呼び出すことができます、フレームワークによってする必要がありますが呼び出さ[SetModified](#setmodified)そのパラメーターを設定および**TRUE**です。 今すぐ適用] ボタン、ユーザーは、[プロパティ ページで変更を行うとすぐにアクティブになります。  
  
 ユーザーは、[今すぐ適用] ボタンをクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライドします。 をオーバーライドする関数で返す必要があります**TRUE**の変更を確定と**FALSE**変更反映されないようにします。  
  
 既定の実装`OnApply`呼び出し`OnOK`です。  
  
 ユーザー プロパティ シートで、今すぐ適用または [ok] ボタンを押したときに送信された通知メッセージの詳細については、次を参照してください。 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
  例を参照して[送るに](#onok)です。  
  
##  <a name="oncancel"></a>  CPropertyPage::OnCancel  
 [キャンセル] ボタンを選択すると、このメンバー関数は、フレームワークによって呼び出されます。  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>コメント  
 [キャンセル] ボタンの操作を実行するには、このメンバー関数をオーバーライドします。 既定値は、加えられた変更を否定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#114](../../mfc/codesnippet/cpp/cpropertypage-class_4.cpp)]  
  
##  <a name="onkillactive"></a>  CPropertyPage::OnKillActive  
 このメンバー関数は、ページがアクティブではなくなるときにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnKillActive();
```  
  
### <a name="return-value"></a>戻り値  
 データが正常に更新された場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 特別なデータの検証タスクを実行するには、このメンバー関数をオーバーライドします。  
  
 このメンバー関数の既定の実装では、プロパティ ページのメンバー変数に、コントロールのプロパティ ページから設定をコピーします。 ダイアログ データ バリデーション (DDV) エラーのため、データが正常に更新されない場合は、ページがフォーカスを保持します。  
  
 このメンバー関数が正常に返されると、呼び出しますページの[OnOK](#onok)関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#115](../../mfc/codesnippet/cpp/cpropertypage-class_5.cpp)]  
  
##  <a name="onok"></a>  送るに  
 このメンバー関数は、フレームワークによって、ユーザー、フレームワークによって後すぐに、[ok] または [今すぐ適用] ボタンのいずれかを選択したときに[OnKillActive](#onkillactive)です。  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークが受信 OK または [適用] ボタンを選択すると、 [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552)プロパティ ページからの通知です。 呼び出し`OnOK`を呼び出す場合に行われるされません[CPropertySheet::PressButton](../../mfc/reference/cpropertysheet-class.md#pressbutton)のため、プロパティ ページが、通知をその場合は送信されません。  
  
 ユーザーがプロパティ シート全体を閉じるときに、現在アクティブなページに固有の他の動作を実装するには、このメンバー関数をオーバーライドします。  
  
 このメンバー関数の既定の実装で、データが更新されたことを反映するには、「クリーンアップ」としてそのページをマークする、`OnKillActive`関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#116](../../mfc/codesnippet/cpp/cpropertypage-class_6.cpp)]  
  
##  <a name="onquerycancel"></a>  CPropertyPage::OnQueryCancel  
 このメンバー関数は、[キャンセル] ボタンをクリックし、キャンセルする前に動作が発生したときにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnQueryCancel();
```  
  
### <a name="return-value"></a>戻り値  
 返します**FALSE**キャンセル操作または許可する場合は TRUE を防ぐためです。  
  
### <a name="remarks"></a>コメント  
 ユーザーは [キャンセル] ボタンをクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライドします。  
  
 既定の実装`OnQueryCancel`返します**TRUE**です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#117](../../mfc/codesnippet/cpp/cpropertypage-class_7.cpp)]  
  
##  <a name="onreset"></a>  CPropertyPage::OnReset  
 このメンバー関数は、[キャンセル] ボタンを選択すると、フレームワークによって呼び出されます。  
  
```  
virtual void OnReset();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、この関数を呼び出す、以前 [適用] ボタンを選択するユーザーによって加えられたすべてのプロパティ ページへの変更は破棄され、プロパティ シートにフォーカスが保持されます。  
  
 ユーザーは [キャンセル] ボタンをクリックしたときのプログラムの動作を指定するには、このメンバー関数をオーバーライドします。  
  
 既定の実装`OnReset`何も行われません。  
  
### <a name="example"></a>例  
  例を参照して[CPropertyPage::OnCancel](#oncancel)です。  
  
##  <a name="onsetactive"></a>  CPropertyPage::OnSetActive  
 このメンバー関数はページがユーザーによって選択され、アクティブになったときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnSetActive();
```  
  
### <a name="return-value"></a>戻り値  
 ページを正常にアクティブに設定されている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ページがアクティブになったときにタスクを実行するには、このメンバー関数をオーバーライドします。 このメンバー関数のオーバーライドは、ページ コントロールを新しいデータで更新することを許可する、データ メンバーを更新した後に通常既定のバージョンを呼び出します。  
  
 既定の実装は、ページ、ウィンドウを作成しない場合、以前に作成し、作業中のページになります。  
  
### <a name="example"></a>例  
  例を参照して[CPropertySheet::SetFinishText](../../mfc/reference/cpropertysheet-class.md#setfinishtext)です。  
  
##  <a name="onwizardback"></a>  CPropertyPage::OnWizardBack  
 このメンバー関数は、ユーザーがウィザードの [戻る] ボタンをクリックすると、フレームワークによって呼び出されます。  
  
```  
virtual LRESULT OnWizardBack();
```  
  
### <a name="return-value"></a>戻り値  
 次のページに自動的に進める 0ページを変更できないようにする-1 です。 次の 1 つ以外のページにジャンプするには、表示されるダイアログ ボックスの識別子を返します。  
  
### <a name="remarks"></a>コメント  
 [戻る] ボタンがクリックされたときに、ユーザーが操作を指定するには、このメンバー関数をオーバーライドします。  
  
 ウィザード形式のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#118](../../mfc/codesnippet/cpp/cpropertypage-class_8.cpp)]  
  
##  <a name="onwizardfinish"></a>  CPropertyPage::OnWizardFinish  
 このメンバー関数は、ユーザーが、ウィザードで、[完了] をクリックすると、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnWizardFinish();
```  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートが、ウィザードが終了したときに破棄される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーがクリックしたとき、**完了**ウィザード、フレームワークのボタンは、この関数を呼び出します以外の場合`OnWizardFinish`を返します**TRUE** (0 以外の値)、プロパティ シートは破棄されることはできません (が、実際には破棄されます)。 呼び出す`DestroyWindow`プロパティ シートを破棄します。 呼び出す必要はありません`DestroyWindow`から`OnWizardFinish`; そう原因なりますヒープの破損またはその他のエラーです。  
  
 [完了] ボタンがクリックされたときに、ユーザーが操作を指定するには、このメンバー関数をオーバーライドすることができます。 この関数をオーバーライドする場合は、返す**FALSE**をプロパティ シートが破棄されていることを防ぐためにします。  
  
 ウィザードのプロパティ シートでユーザーが [完了] ボタンを押したときに送信される通知メッセージの詳細については、次を参照してください。 [PSN_WIZFINISH](http://msdn.microsoft.com/library/windows/desktop/bb774571) Windows SDK に含まれています。  
  
 ウィザード形式のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#119](../../mfc/codesnippet/cpp/cpropertypage-class_9.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#120](../../mfc/codesnippet/cpp/cpropertypage-class_10.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#121](../../mfc/codesnippet/cpp/cpropertypage-class_11.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#122](../../mfc/codesnippet/cpp/cpropertypage-class_12.cpp)]  
  
##  <a name="onwizardnext"></a>  CPropertyPage::OnWizardNext  
 このメンバー関数は、ユーザーが、ウィザードの [次へ] ボタンをクリックしたときにフレームワークによって呼び出されます。  
  
```  
virtual LRESULT OnWizardNext();
```  
  
### <a name="return-value"></a>戻り値  
 次のページに自動的に進める 0ページを変更できないようにする-1 です。 次の 1 つ以外のページにジャンプするには、表示されるダイアログ ボックスの識別子を返します。  
  
### <a name="remarks"></a>コメント  
 [次へ] ボタンが押されたときに、ユーザーが操作を指定するには、このメンバー関数をオーバーライドします。  
  
 ウィザード形式のプロパティ シートを作成する方法の詳細については、次を参照してください。 [CPropertySheet::SetWizardMode](../../mfc/reference/cpropertysheet-class.md#setwizardmode)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#123](../../mfc/codesnippet/cpp/cpropertypage-class_13.cpp)]  
  
##  <a name="querysiblings"></a>  CPropertyPage::QuerySiblings  
 プロパティ シートの各ページにメッセージを転送するには、このメンバー関数を呼び出します。  
  
```  
LRESULT QuerySiblings(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `wParam`  
 追加のメッセージに依存する情報を指定します。  
  
 `lParam`  
 その他のメッセージに依存する情報を指定します  
  
### <a name="return-value"></a>戻り値  
 プロパティ シートで、または 0 の場合のページから 0 以外の値のすべてのページは、値 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ページが 0 以外の値を返す場合、プロパティ シートは後続のページにメッセージを送信しません。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#124](../../mfc/codesnippet/cpp/cpropertypage-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#125](../../mfc/codesnippet/cpp/cpropertypage-class_15.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#126](../../mfc/codesnippet/cpp/cpropertypage-class_16.cpp)]  
  
##  <a name="setmodified"></a>  CPropertyPage::SetModified  
 有効にするにまたは、今すぐ適用 ボタン、適切な外部のオブジェクトにプロパティ ページの設定を適用する必要があるかどうかに基づいてを無効にするには、このメンバー関数を呼び出します。  
  
```  
void SetModified(BOOL bChanged = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bChanged`  
 **TRUE**プロパティ ページの設定が適用されたか、前回以降変更されていることを示すために**FALSE**プロパティ ページの設定が適用されているか、無視するかを示します。  
  
### <a name="remarks"></a>コメント  
 そのうちページは「ダーティ」、つまり追跡、プロパティ ページが呼び出しのフレームワークが保持**SetModified (TRUE)** です。 今すぐ適用 ボタンは常に有効にするを呼び出す場合**SetModified (TRUE)** ページのいずれか。 呼び出すときに、今すぐ適用 ボタンは無効になります**SetModified (FALSE)** のみ場合、その他のページの なし は「ダーティ」ですが、ページの 1 つの  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#127](../../mfc/codesnippet/cpp/cpropertypage-class_17.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [MFC サンプル PROPDLG](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPropertySheet クラス](../../mfc/reference/cpropertysheet-class.md)   
 [CDialog クラス](../../mfc/reference/cdialog-class.md)
