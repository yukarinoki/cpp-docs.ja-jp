---
title: CDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialog
- AFXWIN/CDialog
- AFXWIN/CDialog::CDialog
- AFXWIN/CDialog::Create
- AFXWIN/CDialog::CreateIndirect
- AFXWIN/CDialog::DoModal
- AFXWIN/CDialog::EndDialog
- AFXWIN/CDialog::GetDefID
- AFXWIN/CDialog::GotoDlgCtrl
- AFXWIN/CDialog::InitModalIndirect
- AFXWIN/CDialog::MapDialogRect
- AFXWIN/CDialog::NextDlgCtrl
- AFXWIN/CDialog::OnInitDialog
- AFXWIN/CDialog::OnSetFont
- AFXWIN/CDialog::PrevDlgCtrl
- AFXWIN/CDialog::SetDefID
- AFXWIN/CDialog::SetHelpID
- AFXWIN/CDialog::OnCancel
- AFXWIN/CDialog::OnOK
dev_langs:
- C++
helpviewer_keywords:
- CDialog [MFC], CDialog
- CDialog [MFC], Create
- CDialog [MFC], CreateIndirect
- CDialog [MFC], DoModal
- CDialog [MFC], EndDialog
- CDialog [MFC], GetDefID
- CDialog [MFC], GotoDlgCtrl
- CDialog [MFC], InitModalIndirect
- CDialog [MFC], MapDialogRect
- CDialog [MFC], NextDlgCtrl
- CDialog [MFC], OnInitDialog
- CDialog [MFC], OnSetFont
- CDialog [MFC], PrevDlgCtrl
- CDialog [MFC], SetDefID
- CDialog [MFC], SetHelpID
- CDialog [MFC], OnCancel
- CDialog [MFC], OnOK
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ae7748c249cb9c7752b55d07bf10278c9c7f4ce
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955015"
---
# <a name="cdialog-class"></a>CDialog クラス
[画面] ダイアログ ボックスを表示するための基本クラス。  
  
## <a name="syntax"></a>構文  
  
```  
class CDialog : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[詳細](#cdialog)|`CDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDialog::Create](#create)|初期化、`CDialog`オブジェクト。 モードレス ダイアログ ボックスを作成しにアタッチ、`CDialog`オブジェクト。|  
|[CDialog::CreateIndirect](#createindirect)|(ないリソースに基づく) のメモリ内のダイアログ ボックス テンプレートからモードレス ダイアログ ボックスを作成します。|  
|[CDialog::DoModal](#domodal)|モーダル ダイアログ ボックスの呼び出しを行う場合を返します。|  
|[CDialog::EndDialog](#enddialog)|モーダル ダイアログ ボックスを閉じます。|  
|[CDialog::GetDefID](#getdefid)|ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得します。|  
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|ダイアログ ボックス内の指定 ダイアログ ボックス コントロールにフォーカスを移動します。|  
|[CDialog::InitModalIndirect](#initmodalindirect)|(ないリソースに基づく) のメモリ内のダイアログ ボックス テンプレートからモーダル ダイアログ ボックスを作成します。 パラメーターが関数まで格納されている`DoModal`と呼びます。|  
|[CDialog::MapDialogRect](#mapdialogrect)|四角形のダイアログ ボックスの単位を画面の単位に変換します。|  
|[CDialog::NextDlgCtrl](#nextdlgctrl)|ダイアログ ボックスで次のダイアログ ボックス コントロールにフォーカスを移動します。|  
|[CDialog::OnInitDialog](#oninitdialog)|ダイアログ ボックスの初期化を拡張するためにオーバーライドします。|  
|[CDialog::OnSetFont](#onsetfont)|ダイアログ ボックス コントロールがテキストを描画するときを使用するフォントを指定するためにオーバーライドします。|  
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|ダイアログ ボックスで、前のダイアログ ボックス コントロールにフォーカスを移動します。|  
|[CDialog::SetDefID](#setdefid)|指定されたプッシュ ボタンをダイアログ ボックスの既定のプッシュ ボタン コントロールを変更します。|  
|[CDialog::SetHelpID](#sethelpid)|ダイアログ ボックスの状況依存のヘルプ ID を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDialog::OnCancel](#oncancel)|オーバーライドして、[キャンセル] ボタンまたは ESC キーの操作を実行します。 既定値は、ダイアログ ボックスを閉じ、`DoModal`返します**IDCANCEL**です。|  
|[CDialog::OnOK](#onok)|モーダル ダイアログ ボックスで [ok] ボタンの操作を実行するためにオーバーライドします。 既定値は、ダイアログ ボックスを閉じ、`DoModal`返します**IDOK**です。|  
  
## <a name="remarks"></a>Remarks  
 ダイアログ ボックスの 2 つの型である: モーダルとモードレスです。 アプリケーションを続行する前に、ユーザーが、モーダル ダイアログ ボックスを閉じる必要があります。 モードレス ダイアログ ボックスは、ダイアログ ボックスを表示し、キャンセルまたはダイアログ ボックスを削除せずに別のタスクに戻ることができます。  
  
 A`CDialog`オブジェクトするダイアログ テンプレートの組み合わせは、および`CDialog`-クラスを派生します。 ダイアログ テンプレートを作成し、リソースに格納する、ダイアログ エディターを使用してから派生したクラスを作成するクラスの追加ウィザードを使用して`CDialog`です。  
  
 その他のウィンドウと同様に、ダイアログ ボックスでは、Windows からメッセージを受信します。 ダイアログ ボックスで、ユーザーが、ダイアログ ボックスと対話する方法であるため、ダイアログ ボックスのコントロールからの通知メッセージを処理、特に興味のあります。 [プロパティ] ウィンドウを使用すると、どの対象のメッセージ処理は、適切なメッセージ マップ エントリとメッセージ ハンドラー メンバー関数をクラスに追加するを選択できます。 のみでハンドラー メンバー関数は、アプリケーション固有のコードを記述する必要があります。  
  
 場合は、することが常にメッセージ マップ エントリとメンバー関数を手動で作成します。  
  
 すべてのページで、最も単純なダイアログ ボックスが、ダイアログの派生クラスをユーザーがダイアログ ボックスのコントロールに入力されたデータを格納するか、ユーザーのデータを表示するにメンバー変数を追加します。 変数の追加ウィザードを使用して、メンバー変数を作成し、コントロールに関連付けることができます。 同時に、変数の型と各変数の値の許容範囲を選択します。 コード ウィザードでは、派生ダイアログ クラスにメンバー変数を追加します。  
  
 データ マップを生成して、メンバー変数と、ダイアログ ボックスのコントロール間のデータ交換を自動的に処理されます。 データ マップは、適切な値を使用して、ダイアログ ボックスでコントロールを初期化し、データを取得、データの検証機能を提供します。  
  
 モーダル ダイアログ ボックスを作成するには、派生ダイアログ クラスのコンス トラクターを使用して、スタック上のオブジェクトを構築およびを呼び出す`DoModal`ダイアログ ウィンドウとそのコントロールを作成します。 モードレス ダイアログを作成する場合は、呼び出す`Create`ダイアログ クラスのコンス トラクターです。  
  
 使用して、メモリ内テンプレートを作成することも、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Windows SDK」の説明に従って、データが構造体します。 構築した後、`CDialog`オブジェクトを呼び出す[CreateIndirect](#createindirect) 、モードレスを作成するダイアログ ボックスで、または呼び出し[持たない](#initmodalindirect)と[DoModal](#domodal)モーダルを作成するにはダイアログ ボックス。  
  
 データ マップの交換と検証のオーバーライドで書き込まれます`CWnd::DoDataExchange`ですが、新しいダイアログ クラスに追加します。 参照してください、 [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)メンバー関数内`CWnd`の詳細については、exchange と検証の機能です。  
  
 プログラマとフレームワークの呼び出しの両方`DoDataExchange`への呼び出しを通じて間接的に[:updatedata](../../mfc/reference/cwnd-class.md#updatedata)です。  
  
 フレームワークによって`UpdateData`ユーザーがモーダル ダイアログ ボックスを閉じる [ok] ボタンをクリックしたとき。 (データは取得されません、[キャンセル] ボタンがクリックされた場合。)既定の実装[OnInitDialog](#oninitdialog)も呼び出します`UpdateData`コントロールの初期値を設定します。 通常、オーバーライドする`OnInitDialog`をさらにコントロールを初期化します。 `OnInitDialog` すべてのダイアログ コントロールを作成し、ボックスが表示されるダイアログ ボックスの直前に呼び出されます。  
  
 呼び出すことができます`CWnd::UpdateData`モーダルまたはモードレス ダイアログ ボックスの実行中にいつでもできます。  
  
 ダイアログ ボックスを手動で開発する場合は、自分自身、ダイアログ ボックスの派生クラスに必要なメンバー変数を追加して、設定またはこれらの値を取得するメンバー関数を追加します。  
  
 ユーザーが、[ok] または [キャンセル] ボタンを押したときや、コードを呼び出すと、モーダル ダイアログ ボックスが自動的に終了、`EndDialog`メンバー関数。  
  
 モードレス ダイアログ ボックスを実装するときに常にオーバーライド、`OnCancel`メンバー関数と呼び出し`DestroyWindow`から内部にします。 基本クラスを呼び出しません`CDialog::OnCancel`を呼び出すので、 `EndDialog`、 ダイアログ ボックスを非表示になりますは破棄されません。 オーバーライドする必要がありますも`PostNcDestroy`を削除するために、モードレス ダイアログ ボックスの**この**モードレス ダイアログ ボックスは通常に割り当てられているため、**新しい**です。 モーダル ダイアログ ボックスは、通常、フレームに構築され、必要はありません`PostNcDestroy`クリーンアップします。  
  
 `CDialog` の詳細については、次を参照してください。  
  
- [ダイアログ ボックス](../../mfc/dialog-boxes.md)  
  
-   サポート技術情報の記事 Q262954: HOWTO: スクロール バーのあるサイズ ダイアログ ボックスを作成します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cdialog"></a>  詳細  
 リソース ベースのモーダル ダイアログ ボックスを作成するには、どちらのパブリック コンス トラクターは、の形式を呼び出します。  
  
```  
explicit CDialog(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
explicit CDialog(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);  
  
CDialog();
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszTemplateName*  
 ダイアログ テンプレート リソースの名前を表す null で終わる文字列が含まれています。  
  
 *nIDTemplate*  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
 *pParentWnd*  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
### <a name="remarks"></a>Remarks  
 コンス トラクターの 1 つのフォームは、テンプレート名でダイアログ リソースへのアクセスを提供します。 その他のコンス トラクターへのアクセス提供テンプレート ID 番号では、通常、**文字列の先頭**プレフィックス (IDD_DIALOG1 など)。  
  
 メモリ内のテンプレートからモーダル ダイアログ ボックスを構築するために、まずパラメーターなし、保護されているコンス トラクターを呼び出すし、呼び出す`InitModalIndirect`です。  
  
 上記のメソッドのいずれかでモーダル ダイアログ ボックスを構築した後で呼び出す`DoModal`です。  
  
 モードレス ダイアログ ボックスを作成するには、保護されたフォームを使用して、`CDialog`コンス トラクターです。 モードレス ダイアログ ボックスを実装する独自のダイアログ ボックス クラスを派生させる必要があるために、コンス トラクターは保護されています。 モードレス ダイアログ ボックスの構築は、2 段階に分かれたプロセスです。 コンス トラクターの最初の呼び出し呼び出す、`Create`リソース ベースのダイアログ ボックスを作成するメンバー関数を呼び出したり`CreateIndirect`メモリ内のテンプレートからダイアログ ボックスを作成します。  
  
##  <a name="create"></a>  CDialog::Create  
 呼び出す`Create`リソースからダイアログ ボックスのテンプレートを使用してモードレス ダイアログ ボックスを作成します。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
virtual BOOL Create(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszTemplateName*  
 ダイアログ テンプレート リソースの名前を表す null で終わる文字列が含まれています。  
  
 *pParentWnd*  
 親ウィンドウ オブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 *nIDTemplate*  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
### <a name="return-value"></a>戻り値  
 両方の形式 ダイアログ ボックスの作成と初期化が成功した場合は 0 以外を返しますそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出しを配置する`Create`コンス トラクターまたは呼び出しの内部、コンス トラクターの後に呼び出されます。  
  
 2 つの形式、`Create`テンプレート名またはテンプレートの ID 番号 (IDD_DIALOG1 など) のいずれかによってダイアログ テンプレート リソースにアクセスするためのメンバー関数が提供されます。  
  
 いずれかの形式では、親ウィンドウ オブジェクトへのポインターを渡します。 場合*pParentWnd*は**NULL**、その親ウィンドウまたはオーナー ウィンドウにアプリケーションのメイン ウィンドウ設定のダイアログ ボックスが作成されます。  
  
 `Create`  ダイアログ ボックスを作成したらすぐに、メンバー関数が返されます。  
  
 使用して、 **WS_VISIBLE**  ダイアログ ボックス テンプレートのスタイルを設定 ダイアログ ボックスが表示されない場合は親ウィンドウが作成されます。 それ以外の場合、呼び出す必要があります`ShowWindow`です。 さらにダイアログ ボックスのスタイルとそのアプリケーションは、次を参照してください。、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Windows SDK 内の構造と[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)で、 *『 MFC リファレンス*です。  
  
 使用して、`CWnd::DestroyWindow`によって作成されたダイアログ ボックスを破棄する関数、`Create`関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]  
  
##  <a name="createindirect"></a>  CDialog::CreateIndirect  
 メモリ内のダイアログ ボックス テンプレートからモードレス ダイアログ ボックスを作成するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL CreateIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
virtual BOOL CreateIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDialogTemplate*  
 ダイアログ ボックスを作成するために使用 ダイアログ ボックス テンプレートが含まれるメモリへのポインター。 このテンプレートは、の形式では、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394)構造とコントロールについては、Windows SDK」の説明に従ってします。  
  
 *pParentWnd*  
 ダイアログ オブジェクトの親ウィンドウ オブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md))。 場合は**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 *lpDialogInit*  
 指す、 **DLGINIT**リソース。  
  
 *hDialogTemplate*  
 ダイアログ ボックスのテンプレートを含むグローバル メモリへのハンドルが含まれています。 このテンプレートは、の形式では、 **DLGTEMPLATE**構造と、ダイアログ ボックス内の各コントロールのデータ。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスが作成され、正常に初期化される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 `CreateIndirect`  ダイアログ ボックスを作成したらすぐに、メンバー関数が返されます。  
  
 使用して、 **WS_VISIBLE**  ダイアログ ボックス テンプレートのスタイルを設定 ダイアログ ボックスが表示されない場合は親ウィンドウが作成されます。 それ以外の場合、呼び出す必要があります`ShowWindow`に表示されるようにします。 テンプレートの他のダイアログ ボックスのスタイルを指定する方法の詳細については、次を参照してください。、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Windows SDK 内の構造。  
  
 使用して、`CWnd::DestroyWindow`によって作成されたダイアログ ボックスを破棄する関数、`CreateIndirect`関数。  
  
 ActiveX コントロールを含むダイアログ ボックスで提供される追加情報を必要とする**DLGINIT**リソース。 詳細については、サポート技術情報の記事 Q231591 を参照してください"HOWTO: ダイアログ テンプレートを使用して ActiveX コントロールを MFC ダイアログ ボックスを作成します。"。 サポート技術情報については、「 [ http://support.microsoft.com](http://support.microsoft.com/)です。  
  
##  <a name="domodal"></a>  CDialog::DoModal  
 モーダル ダイアログ ボックスを起動して完了ダイアログ ボックスの結果を返すには、このメンバー関数を呼び出します。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **Int**の値を指定する値、 *%n*パラメーターに渡された、 [CDialog::EndDialog](#enddialog)メンバー関数は、ダイアログ ボックスを閉じるために使用します。 関数は、ダイアログ ボックスを作成できませんでしたの場合、戻り値は-1 または**IDABORT**その他のエラーが発生した場合いる場合は、出力ウィンドウがエラー情報を含むから[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数は、ダイアログ ボックスがアクティブな間にユーザーとすべての対話を処理します。 モーダル ダイアログ ボックスは、します。ユーザーは、ダイアログ ボックスが閉じられるまで、他のウィンドウを操作できません。  
  
 ユーザーがクリックするとダイアログ ボックスで、[ok] または [キャンセル] メッセージ ハンドラー メンバー関数などのプッシュ ボタンのいずれかのように[OnOK](#onok)または[OnCancel](#oncancel)、しようとするダイアログ ボックスを閉じると呼びます。 既定値`OnOK`メンバー関数は、検証およびダイアログ ボックスのデータを更新し、結果を含むダイアログ ボックスを閉じます**IDOK**と既定`OnCancel`メンバー関数は、ダイアログ ボックスを閉じます結果と共に**IDCANCEL**なしの検証またはダイアログ ボックスのデータを更新します。 これらのメッセージ ハンドラー関数の動作を変更するのにはオーバーライドできます。  
  
> [!NOTE]
> `PreTranslateMessage` モーダル ダイアログ ボックスのメッセージの処理に対しては呼び出さようになりました。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]  
  
##  <a name="enddialog"></a>  CDialog::EndDialog  
 モーダル ダイアログ ボックスを終了するには、このメンバー関数を呼び出します。  
  
```  
void EndDialog(int nResult);
```  
  
### <a name="parameters"></a>パラメーター  
 *%n*  
 ダイアログ ボックスからの呼び出し元に返される値が含まれる`DoModal`です。  
  
### <a name="remarks"></a>Remarks  
 このメンバー関数を返します *%n*の戻り値として`DoModal`です。 使用する必要があります、`EndDialog`関数がモーダル ダイアログ ボックスが作成されるたびに処理を完了します。  
  
 呼び出すことができます`EndDialog`であっても、いつでも[OnInitDialog](#oninitdialog)case を閉じる必要がある前にダイアログ ボックスを表示または入力フォーカスを設定する前にします。  
  
 `EndDialog` ダイアログ ボックスをすぐに閉じません。 代わりに、現在のメッセージ ハンドラーを返すとすぐに閉じるダイアログ ボックスに指示するフラグを設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]  
  
##  <a name="getdefid"></a>  CDialog::GetDefID  
 呼び出す、 `GetDefID`  ダイアログ ボックスの既定のプッシュ ボタン コントロールの ID を取得します。  
  
```  
DWORD GetDefID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 32 ビットの値 ( `DWORD`)。 高位の単語に含まれる既定のプッシュ ボタンに ID 値がある場合は、 **DC_HASDEFID**下位ワードに ID 値が含まれています。 既定のプッシュ ボタンが ID 値を持たない場合、戻り値は 0 です。  
  
### <a name="remarks"></a>Remarks  
 これは、通常、[ok] ボタンです。  
  
##  <a name="gotodlgctrl"></a>  CDialog::GotoDlgCtrl  
 ダイアログ ボックスで指定されたコントロールにフォーカスを移動します。  
  
```  
void GotoDlgCtrl(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndCtrl*  
 フォーカスを受け取るには、ウィンドウ (コントロール) を識別します。  
  
### <a name="remarks"></a>Remarks  
 コントロールとして渡す (子ウィンドウ) へのポインターを取得する*pWndCtrl*を呼び出し、`CWnd::GetDlgItem`へのポインターを返すメンバー関数、 [CWnd](../../mfc/reference/cwnd-class.md)オブジェクト。  
  
### <a name="example"></a>例  
  例を参照して[:getdlgitem](../../mfc/reference/cwnd-class.md#getdlgitem)です。  
  
##  <a name="initmodalindirect"></a>  CDialog::InitModalIndirect  
 メモリ内で構築する ダイアログ ボックス テンプレートを使用してモーダル ダイアログ ボックスのオブジェクトを初期化するためにこのメンバー関数を呼び出します。  
  
```  
BOOL InitModalIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
    BOOL InitModalIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpDialogTemplate*  
 ダイアログ ボックスを作成するために使用 ダイアログ ボックス テンプレートが含まれるメモリへのポインター。 このテンプレートは、の形式では、 [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394)構造とコントロールについては、Windows SDK」の説明に従ってします。  
  
 *hDialogTemplate*  
 ダイアログ ボックスのテンプレートを含むグローバル メモリへのハンドルが含まれています。 このテンプレートは、の形式では、 **DLGTEMPLATE**構造と、ダイアログ ボックス内の各コントロールのデータ。  
  
 *pParentWnd*  
 親またはオーナー ウィンドウ オブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 場合は**NULL**、ダイアログ オブジェクトの親ウィンドウがアプリケーションのメイン ウィンドウに設定します。  
  
 *lpDialogInit*  
 指す、 **DLGINIT**リソース。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ オブジェクトが作成され、正常に初期化される場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 まず、モーダル ダイアログ ボックスを直接作成するには、グローバル メモリ ブロックを割り当て、 ダイアログ ボックスのテンプレートを使用して入力します。 空を呼び出す`CDialog` ダイアログ ボックスのオブジェクトを構築するコンス トラクターです。 次に、呼び出す`InitModalIndirect`をメモリ内のダイアログ ボックスのテンプレートに、ハンドルを格納します。 Windows のダイアログ ボックスが作成され、表示されるときに、後で、 [DoModal](#domodal)メンバー関数が呼び出されます。  
  
 ActiveX コントロールを含むダイアログ ボックスで提供される追加情報を必要とする**DLGINIT**リソース。 詳細については、サポート技術情報の記事 Q231591 を参照してください"HOWTO: ダイアログ テンプレートを使用して ActiveX コントロールを MFC ダイアログ ボックスを作成します。"。 サポート技術情報については、「 [ http://support.microsoft.com](http://support.microsoft.com/)です。  
  
##  <a name="mapdialogrect"></a>  CDialog::MapDialogRect  
 四角形のダイアログ ボックスの単位を画面の単位に変換する呼び出しです。  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lpRect*  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)  ダイアログ ボックスを含むオブジェクトを変換する座標します。  
  
### <a name="remarks"></a>Remarks  
 ダイアログ単位は、に関して、平均の幅と高さの使用 ダイアログ ボックスのテキストのフォントの文字から派生した現在のダイアログ ボックス基本単位です。 水平方向に 1 つのユニットのダイアログ ボックスのベースの幅単位の 4 分の 1、垂直方向の 1 つの単位 ダイアログ ボックスの高さの基本単位の 8 分の 1。  
  
 **GetDialogBaseUnits** Windows 関数はシステム フォントのサイズ情報を返しますが、使用する場合は、ダイアログ ボックスごとに別のフォントを指定できます、 **DS_SETFONT**のスタイルを設定しますリソース定義ファイルです。 `MapDialogRect` Windows の機能は、このダイアログ ボックスの適切なフォントを使用します。  
  
 `MapDialogRect`メンバー関数は、ダイアログ ボックスの単位を置き換えます*lpRect*で画面の作成 ダイアログ ボックスをボックス内のコントロールの位置四角形を使用できるようにする単位 (ピクセル単位)。  
  
##  <a name="nextdlgctrl"></a>  CDialog::NextDlgCtrl  
 ダイアログ ボックスで、次のコントロールにフォーカスを移動します。  
  
```  
void NextDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Remarks  
 ダイアログ ボックスで、最後のコントロールにフォーカスがある場合は、最初のコントロールに移動します。  
  
##  <a name="oncancel"></a>  CDialog::OnCancel  
 フレームワークは、ユーザーがクリックしたときにこのメソッドを呼び出します**キャンセル**かモーダルまたはモードレス ダイアログ ボックスで、ESC キーを押します。  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Remarks  
 (古いデータを復元する) などのアクションを実行するには、このメソッドをオーバーライドして、ユーザーが をクリックしてダイアログ ボックスを閉じたときに**キャンセル**ESC キーを押すか。 既定値は、呼び出すことによって、モーダル ダイアログ ボックスを閉じます[EndDialog](#enddialog)およびによって[DoModal](#domodal) IDCANCEL に戻ります。  
  
 実装する場合、**キャンセル**ボタン モードレス ダイアログ ボックスでは、オーバーライドする必要があります、`OnCancel`メソッドと呼び出し[DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)内です。 呼び出すので、基本クラスのメソッドを呼び出さないでください`EndDialog`は、ダイアログ ボックスを非表示にを破棄することができます。  
  
> [!NOTE]
>  使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows XP でコンパイルされたプログラム内のオブジェクト。 詳細については`CFileDialog`を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]  
  
##  <a name="oninitdialog"></a>  CDialog::OnInitDialog  
 応答でこのメソッドは、`WM_INITDIALOG`メッセージ。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションがダイアログ ボックスで、コントロールのいずれかに入力フォーカスを設定したかどうかを指定します。 場合`OnInitDialog`0 以外を返します、Windows、入力フォーカスを設定 ダイアログ ボックスの最初のコントロール、既定の場所。 アプリケーションは、明示的にフォーカスを設定した、入力コントロールのいずれかに ダイアログ ボックスで場合にのみ、0 を返すことができます。  
  
### <a name="remarks"></a>Remarks  
 Windows の送信、`WM_INITDIALOG`中に、ダイアログ ボックスにメッセージ、[作成](#create)、 [CreateIndirect](#createindirect)、または[DoModal](#domodal)呼び出しで、ダイアログ ボックスの直前に発生します。表示されます。  
  
 ダイアログ ボックスが初期化されたときに、特別な処理を実行する場合は、このメソッドをオーバーライドします。 オーバーライドされたバージョンでは、基底クラスを呼び出して最初`OnInitDialog`が、その戻り値は無視されます。 通常戻ります`TRUE`オーバーライドされたメソッドからです。  
  
 Windows の呼び出し、 `OnInitDialog` Microsoft Foundation Class ライブラリのすべてのダイアログ ボックスに共通の標準のグローバル ダイアログ ボックス プロシージャを使用することによって機能します。 メッセージ マップを使用して関数を呼び出しません、したがってする必要はありませんメッセージ マップ エントリこのメソッドの。  
  
> [!NOTE]
> 使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows Vista またはそれ以降のオペレーティング システムでコンパイルされたプログラム内のオブジェクト。 変更の詳細については`CFileDialog`下にある Windows Vista 以降を参照してください。 [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]  
  
##  <a name="onok"></a>  CDialog::OnOK  
 ユーザーがクリックしたときに呼び出されます、 **OK**ボタン (idok ID のボタン)。  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Remarks  
 アクションを実行するには、このメソッドをオーバーライドときに、 **OK**  ボタンがアクティブにします。 ダイアログ ボックスには、データの自動検証し、exchange が含まれている場合、このメソッドの既定の実装はダイアログ ボックスのデータを検証し、アプリケーションの適切な変数を更新します。  
  
 実装する場合、 **OK**ボタン モードレス ダイアログ ボックスでは、オーバーライドする必要があります、`OnOK`メソッドを呼び出します[DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow)内です。 呼び出すので、基本クラスのメソッドを呼び出さないでください[EndDialog](#enddialog)  ダイアログ ボックスを非表示にするは、破棄することができます。  
  
> [!NOTE]
>  使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows XP でコンパイルされたプログラム内のオブジェクト。 詳細については`CFileDialog`を参照してください[CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]  
  
##  <a name="onsetfont"></a>  CDialog::OnSetFont  
 テキストを描画するときに、ダイアログ ボックス コントロールを使用するフォントを指定します。  
  
```  
Virtual void OnSetFont(CFont* pFont);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pFont*  
 このダイアログ ボックスのすべてのコントロールの既定のフォントとして使用されるフォントへのポインターを指定します。  
  
### <a name="remarks"></a>Remarks  
 ダイアログ ボックスは、そのすべてのコントロールを指定したフォントを既定値として使用されます。  
  
 ダイアログ エディターは通常、ダイアログ ボックスのテンプレート リソースの一部として、ダイアログ ボックスのフォントを設定します。  
  
> [!NOTE]
> 使用する場合は、このメソッドをオーバーライドすることはできません、 `CFileDialog` Windows Vista またはそれ以降のオペレーティング システムでコンパイルされたプログラム内のオブジェクト。 変更の詳細については`CFileDialog`下にある Windows Vista 以降を参照してください。 [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)です。  
  
##  <a name="prevdlgctrl"></a>  CDialog::PrevDlgCtrl  
 ダイアログ ボックスで、前のコントロールにフォーカスを設定します。  
  
```  
void PrevDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Remarks  
 ダイアログ ボックスの最初のコントロールにフォーカスがある場合、最後に移動コントロール ボックス。  
  
##  <a name="setdefid"></a>  CDialog::SetDefID  
 ダイアログ ボックスの既定のプッシュ ボタン コントロールを変更します。  
  
```  
void SetDefID(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 *nID*  
 既定値になるプッシュ ボタン コントロールの ID を指定します。  
  
##  <a name="sethelpid"></a>  CDialog::SetHelpID  
 ダイアログ ボックスの状況依存のヘルプ ID を設定します。  
  
```  
void SetHelpID(UINT nIDR);
```  
  
### <a name="parameters"></a>パラメーター  
 *nIDR*  
 状況依存のヘルプ ID を指定します  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル DLGCBR32](../../visual-cpp-samples.md)   
 [MFC サンプル DLGTEMPL](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)

