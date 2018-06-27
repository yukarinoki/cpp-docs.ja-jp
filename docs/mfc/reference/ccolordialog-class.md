---
title: CColorDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CColorDialog
- AFXDLGS/CColorDialog
- AFXDLGS/CColorDialog::CColorDialog
- AFXDLGS/CColorDialog::DoModal
- AFXDLGS/CColorDialog::GetColor
- AFXDLGS/CColorDialog::GetSavedCustomColors
- AFXDLGS/CColorDialog::SetCurrentColor
- AFXDLGS/CColorDialog::OnColorOK
- AFXDLGS/CColorDialog::m_cc
dev_langs:
- C++
helpviewer_keywords:
- CColorDialog [MFC], CColorDialog
- CColorDialog [MFC], DoModal
- CColorDialog [MFC], GetColor
- CColorDialog [MFC], GetSavedCustomColors
- CColorDialog [MFC], SetCurrentColor
- CColorDialog [MFC], OnColorOK
- CColorDialog [MFC], m_cc
ms.assetid: d013dc25-9290-4b5d-a97e-95ad7208e13b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef863a0eb8cec66e7f640a734088a98b1e8d7b83
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952113"
---
# <a name="ccolordialog-class"></a>CColorDialog クラス
色の選択 ダイアログ ボックスをアプリケーションに組み込むことができます。  
  
## <a name="syntax"></a>構文  
  
```  
class CColorDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CColorDialog::CColorDialog](#ccolordialog)|`CColorDialog` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CColorDialog::DoModal](#domodal)|色 ダイアログ ボックスを表示および選択を行うことができます。|  
|[CColorDialog::GetColor](#getcolor)|返します、 **COLORREF**選択した色の値を含む構造体。|  
|[CColorDialog::GetSavedCustomColors](#getsavedcustomcolors)|ユーザーによって作成されたカスタムの色を取得します。|  
|[CColorDialog::SetCurrentColor](#setcurrentcolor)|指定された色を現在の色の選択を強制します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CColorDialog::OnColorOK](#oncolorok)|ダイアログ ボックスに入力された色を検証するためにオーバーライドします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CColorDialog::m_cc](#m_cc)|構造体 ダイアログ ボックスの設定をカスタマイズするために使用します。|  
  
## <a name="remarks"></a>Remarks  
 A`CColorDialog`オブジェクトはダイアログ ボックスに表示システムに対して定義されている色の一覧です。 ユーザーでは、選択したり、リストが報告されますバックアップ アプリケーションに、ダイアログ ボックスの終了時に特定の色を作成することができます。  
  
 構築するために、`CColorDialog`オブジェクト、指定されたコンス トラクターを使用して、新しいクラスを派生や、独自のカスタム コンス トラクターを使用します。  
  
 ダイアログ ボックスを構築すると、設定したり、任意の値を変更、 [m_cc](#m_cc)構造 ダイアログ ボックスのコントロールの値を初期化します。 *M_cc*構造体は型[CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830)です。  
  
 初期化後、ダイアログ ボックスのコントロールを呼び出して、 `DoModal`  ダイアログ ボックスが表示され、色を選択するユーザーを許可するメンバー関数。 `DoModal` いずれかのユーザーの選択 ダイアログ ボックスの ok を返します ( **IDOK**) か、またはキャンセル ( **IDCANCEL**) ボタンをクリックします。  
  
 場合`DoModal`返します**IDOK**のいずれかを使用することができます`CColorDialog`のユーザーが入力情報を取得するメンバー関数。  
  
 Windows を使用する[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)関数およびエラーに関する詳細については、ダイアログ ボックスの初期化中にエラーが発生するかどうかを決定します。  
  
 `CColorDialog` COMMDLG に依存します。Windows 3.1 以降のバージョンに付属している DLL ファイルです。  
  
 ダイアログ ボックスをカスタマイズするからクラスを派生`CColorDialog`拡張コントロールから通知メッセージを処理するメッセージ マップの追加を独自のダイアログ テンプレートを提供します。 基本クラスには、処理されないメッセージを渡す必要があります。  
  
 フック関数をカスタマイズする必要はありません。  
  
> [!NOTE]
>  一部のインストールで、`CColorDialog`させるその他のフレームワークを使用している場合、オブジェクトは背景が灰色表示されません`CDialog`オブジェクト灰色。  
  
 使用する方法についての`CColorDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CColorDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="ccolordialog"></a>  CColorDialog::CColorDialog  
 `CColorDialog` オブジェクトを構築します。  
  
```  
CColorDialog(
    COLORREF clrInit = 0,  
    DWORD dwFlags = 0,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *clrInit*  
 既定の色の選択 値が指定されていない場合は、既定では RGB(0,0,0) (黒です)。  
  
 *dwFlags*  
 関数と、ダイアログ ボックスの外観をカスタマイズするフラグのセット。 詳細については、次を参照してください。、 [CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830) Windows SDK 内の構造。  
  
 *pParentWnd*  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#49](../../mfc/codesnippet/cpp/ccolordialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CColorDialog::DoModal  
 この関数では、Windows に共通の [色] ダイアログ ボックスを表示し、ユーザーの色を選択できるようにします。  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>戻り値  
 **IDOK**または**IDCANCEL**です。 場合**IDCANCEL**は、Windows を呼び出し、返される[情報を得る](http://msdn.microsoft.com/library/windows/desktop/ms646916)エラーが発生したかどうかを判断する関数。  
  
 **IDOK**と**IDCANCEL**ユーザーが、[ok] または [キャンセル] ボタンを選択するかどうかを示す定数です。  
  
### <a name="remarks"></a>Remarks  
 メンバーを設定して、さまざまな色 ダイアログ ボックスのオプションを初期化する場合、 [m_cc](#m_cc)構造体、呼び出す前にこれを行う必要があります`DoModal`はダイアログ ボックスのオブジェクトを構築します。  
  
 呼び出した後`DoModal`、他のメンバーは、ダイアログ ボックスに、設定や、ユーザーが入力した情報を取得する関数で呼び出すことができます。  
  
### <a name="example"></a>例  
  例を参照して[CColorDialog::CColorDialog](#ccolordialog)です。  
  
##  <a name="getcolor"></a>  CColorDialog::GetColor  
 この関数を呼び出した後`DoModal`色の選択したユーザーに関する情報を取得します。  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)色のダイアログ ボックスで選択した色の RGB 情報を含む値です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#50](../../mfc/codesnippet/cpp/ccolordialog-class_2.cpp)]  
  
##  <a name="getsavedcustomcolors"></a>  CColorDialog::GetSavedCustomColors  
 `CColorDialog` オブジェクトは、最大 16 個のカスタム カラーを定義するユーザー、色を選択するだけでなくを許可します。  
  
```  
static COLORREF* PASCAL GetSavedCustomColors();
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが作成したカスタム カラーを格納する 16 の RGB 色の値の配列を指すポインターです。  
  
### <a name="remarks"></a>Remarks  
 `GetSavedCustomColors`メンバー関数は、これらの色へのアクセスを提供します。 後にこれらの色を取得できる[DoModal](#domodal)返します**IDOK**です。  
  
 返される配列には、16 の RGB 値のそれぞれは、RGB(255,255,255) (白) に初期化されます。 ユーザーが選択したカスタムの色は、アプリケーション内でのダイアログ ボックスの呼び出しの間でのみ保存されます。 アプリケーションの呼び出しの間でこれらの色を保存する場合は、保存があります、他の方法でように初期化 (です。INI) ファイルです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#51](../../mfc/codesnippet/cpp/ccolordialog-class_3.cpp)]  
  
##  <a name="m_cc"></a>  CColorDialog::m_cc  
 型の構造体[CHOOSECOLOR](http://msdn.microsoft.com/library/windows/desktop/ms646830)メンバーの特性と、ダイアログ ボックスの値を格納します。  
  
```  
CHOOSECOLOR m_cc;  
```  
  
### <a name="remarks"></a>Remarks  
 構築した後、`CColorDialog`オブジェクトを使用する*m_cc*を呼び出す前に ダイアログ ボックスのさまざまな側面を設定する、 [DoModal](#domodal)メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#53](../../mfc/codesnippet/cpp/ccolordialog-class_4.cpp)]  
  
##  <a name="oncolorok"></a>  CColorDialog::OnColorOK  
 ダイアログ ボックスに入力された色を検証するためにオーバーライドします。  
  
```  
virtual BOOL OnColorOK();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ダイアログ ボックスを消去しない必要があります。入力された色を受け入れるようにそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 色のダイアログ ボックスで、ユーザーが選択した色のカスタム検証を提供する場合にのみ、この関数をオーバーライドします。  
  
 ユーザーは、次の 2 つのメソッドのいずれかで色を選択できます。  
  
-   カラー パレットで色をクリックします。 選択した色の RGB 値は、適切な RGB 編集ボックスに反映されます。  
  
-   エディット ボックスに、RGB 値を入力します。  
  
 オーバーライドする`OnColorOK`ユーザーがアプリケーションに固有の何らかの理由が一般的な色のダイアログ ボックスに入力色を拒否することができます。  
  
 通常、フレームワークは色の既定の検証を提供し、無効な色が入力された場合は、メッセージ ボックスを表示するために、この関数を使用する必要はありません。  
  
 呼び出すことができます[SetCurrentColor](#setcurrentcolor)内から`OnColorOK`色の選択を強制します。 1 回`OnColorOK`が発生したこと (つまり、ユーザーがクリックした**OK**色の変更を受け入れるように)、呼び出すことができます[GetColor](#getcolor)新しい色の RGB 値を取得します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#52](../../mfc/codesnippet/cpp/ccolordialog-class_5.cpp)]  
  
##  <a name="setcurrentcolor"></a>  CColorDialog::SetCurrentColor  
 この関数を呼び出した後`DoModal`で指定された色の値に現在の色の選択を強制する*clr*です。  
  
```  
void SetCurrentColor(COLORREF clr);
```  
  
### <a name="parameters"></a>パラメーター  
 *clr*  
 色の RGB 値。  
  
### <a name="remarks"></a>Remarks  
 メッセージ ハンドラーから呼び出されたこの関数または`OnColorOK`です。 ダイアログ ボックスは、ユーザーの選択の値に基づいて自動的に更新、 *clr*パラメーター。  
  
### <a name="example"></a>例  
  例を参照して[CColorDialog::OnColorOK](#oncolorok)です。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [MFC サンプル DRAWCLI](../../visual-cpp-samples.md)   
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)

