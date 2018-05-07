---
title: CFindReplaceDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::CFindReplaceDialog
- AFXDLGS/CFindReplaceDialog::Create
- AFXDLGS/CFindReplaceDialog::FindNext
- AFXDLGS/CFindReplaceDialog::GetFindString
- AFXDLGS/CFindReplaceDialog::GetNotifier
- AFXDLGS/CFindReplaceDialog::GetReplaceString
- AFXDLGS/CFindReplaceDialog::IsTerminating
- AFXDLGS/CFindReplaceDialog::MatchCase
- AFXDLGS/CFindReplaceDialog::MatchWholeWord
- AFXDLGS/CFindReplaceDialog::ReplaceAll
- AFXDLGS/CFindReplaceDialog::ReplaceCurrent
- AFXDLGS/CFindReplaceDialog::SearchDown
- AFXDLGS/CFindReplaceDialog::m_fr
dev_langs:
- C++
helpviewer_keywords:
- CFindReplaceDialog [MFC], CFindReplaceDialog
- CFindReplaceDialog [MFC], Create
- CFindReplaceDialog [MFC], FindNext
- CFindReplaceDialog [MFC], GetFindString
- CFindReplaceDialog [MFC], GetNotifier
- CFindReplaceDialog [MFC], GetReplaceString
- CFindReplaceDialog [MFC], IsTerminating
- CFindReplaceDialog [MFC], MatchCase
- CFindReplaceDialog [MFC], MatchWholeWord
- CFindReplaceDialog [MFC], ReplaceAll
- CFindReplaceDialog [MFC], ReplaceCurrent
- CFindReplaceDialog [MFC], SearchDown
- CFindReplaceDialog [MFC], m_fr
ms.assetid: 610f0b5d-b398-4ef6-8c05-e9d6641e50a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21499f65ac762dfd08d90decad41eedf3dfc5cdf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cfindreplacedialog-class"></a>CFindReplaceDialog クラス
アプリケーションで標準文字列検索と置換 ダイアログ ボックスを実装できます。  
  
## <a name="syntax"></a>構文  
  
```  
class CFindReplaceDialog : public CCommonDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)|構築するには、この関数を呼び出して、`CFindReplaceDialog`オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFindReplaceDialog::Create](#create)|作成し、表示、 `CFindReplaceDialog`  ダイアログ ボックス。|  
|[CFindReplaceDialog::FindNext](#findnext)|ユーザーが検索文字列の次の出現箇所を検索するかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::GetFindString](#getfindstring)|現在の検索文字列を取得するには、この関数を呼び出します。|  
|[CFindReplaceDialog::GetNotifier](#getnotifier)|取得するには、この関数を呼び出して、 **FINDREPLACE**登録済みのメッセージ ハンドラーで構造体。|  
|[CFindReplaceDialog::GetReplaceString](#getreplacestring)|この関数では、現在の置換文字列を取得します。|  
|[CFindReplaceDialog::IsTerminating](#isterminating)|ダイアログ ボックスが終了したかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::MatchCase](#matchcase)|ユーザーが検索文字列の大文字と小文字を正確に一致するかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::MatchWholeWord](#matchwholeword)|ユーザーが全体の単語のみが一致するかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::ReplaceAll](#replaceall)|この関数をユーザーが置換される文字列のすべての項目であるかどうかを判断します。|  
|[CFindReplaceDialog::ReplaceCurrent](#replacecurrent)|ユーザーに現在の単語を置換するかどうかを判断するには、この関数を呼び出します。|  
|[CFindReplaceDialog::SearchDown](#searchdown)|ユーザーが下方向へ検索であるかどうかを判断するには、この関数を呼び出します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFindReplaceDialog::m_fr](#m_fr)|カスタマイズに使用される構造体、`CFindReplaceDialog`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 その他の Windows コモン ダイアログ ボックスとは異なり`CFindReplaceDialog`オブジェクトは、モードレス、ユーザーが画面上にある他のウィンドウと対話できるようにします。 2 種類がありますの`CFindReplaceDialog`オブジェクト: ダイアログ ボックスおよび検索と置換 ダイアログ ボックスを検索します。 ダイアログ ボックスには、ユーザーが入力した検索し、検索と置換文字列ができるように、それらは行いません検索または置換関数のいずれか。 アプリケーションに追加する必要があります。  
  
 構築するために、`CFindReplaceDialog`オブジェクト、指定されたコンス トラクター (引数を持たない) を使用します。 これは、モードレス ダイアログ ボックスであるため、ヒープを使用して、オブジェクトの割り当て、**新しい**演算子、スタックではなく、します。  
  
 1 回、`CFindReplaceDialog`オブジェクトが構築された、呼び出す必要があります、[作成](#create)メンバー関数を作成し、ダイアログ ボックスを表示します。  
  
 使用して、 [m_fr](#m_fr)呼び出す前に ダイアログ ボックスを初期化するために**作成**です。 `m_fr`構造体は型[FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835)です。 この構造体の詳細については、Windows SDK を参照してください。  
  
 親ウィンドウ検索/置換要求の通知を受信するためには、Windows を使用する必要があります[を通じて](http://msdn.microsoft.com/library/windows/desktop/ms644947)関数を使用して、 [ON_REGISTERED_MESSAGE](message-map-macros-mfc.md#on_registered_message)フレーム内のメッセージ マップ マクロこの登録されたメッセージを処理するウィンドウです。  
  
 ダイアログ ボックスを終了したかどうかを決定できます、`IsTerminating`メンバー関数。  
  
 `CFindReplaceDialog` COMMDLG に依存します。Windows 3.1 以降のバージョンに付属している DLL ファイルです。  
  
 ダイアログ ボックスをカスタマイズするからクラスを派生`CFindReplaceDialog`拡張コントロールから通知メッセージを処理するメッセージ マップの追加を独自のダイアログ テンプレートを提供します。 基本クラスには、処理されないメッセージを渡す必要があります。  
  
 フック関数をカスタマイズする必要はありません。  
  
 使用する方法についての`CFindReplaceDialog`を参照してください[コモン ダイアログ クラス](../../mfc/common-dialog-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFindReplaceDialog`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="cfindreplacedialog"></a>  CFindReplaceDialog::CFindReplaceDialog  
 `CFindReplaceDialog` オブジェクトを構築します。  
  
```  
CFindReplaceDialog();
```  
  
### <a name="remarks"></a>コメント  
 `CFindReplaceDialog`オブジェクトは、モードレス ダイアログ ボックスを使用して、ヒープを作成する必要があります、`new`演算子。  
  
 破棄、中に、フレームワークが実行しよう、 `delete this`  ダイアログ ボックスへのポインターにします。 スタックで、ダイアログ ボックスを作成した場合、`this`ポインターが存在しないと、未定義の動作が発生する可能性があります。  
  
 構築の詳細については`CFindReplaceDialog`、オブジェクトを参照してください、 [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)の概要です。 使用して、 [CFindReplaceDialog::Create](#create)  ダイアログ ボックスを表示するメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#170](../../mfc/codesnippet/cpp/cfindreplacedialog-class_1.cpp)]  
  
##  <a name="create"></a>  CFindReplaceDialog::Create  
 作成し、[検索] または [検索と置換] ダイアログ ボックスによってオブジェクトの値を表示`bFindDialogOnly`です。  
  
```  
virtual BOOL Create(
    BOOL bFindDialogOnly,  
    LPCTSTR lpszFindWhat,  
    LPCTSTR lpszReplaceWith = NULL,  
    DWORD dwFlags = FR_DOWN,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bFindDialogOnly`  
 このパラメーターに設定`TRUE`を表示する、**検索** ダイアログ ボックス。 設定`FALSE`を表示する、**検索/置換** ダイアログ ボックス。  
  
 `lpszFindWhat`  
 ダイアログ ボックスが表示されたら、既定の検索文字列へのポインター。 場合`NULL`、ダイアログ ボックスに既定の検索文字列が含まれていません。  
  
 `lpszReplaceWith`  
 ダイアログ ボックスが表示されたら、既定の置換文字列へのポインター。 場合`NULL`、ダイアログ ボックスに、既定値の置換文字列が含まれていません。  
  
 `dwFlags`  
 1 つまたは複数のフラグはビットごとの OR 演算子を使用して結合します ダイアログ ボックスの設定のカスタマイズに使用することができます。 既定値は`FR_DOWN`検索では、下方向に続行することを指定します。 参照してください、 [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835)これらのフラグの詳細について、Windows SDK 内の構造。  
  
 `pParentWnd`  
 ダイアログ ボックスの親ウィンドウまたはオーナー ウィンドウへのポインター。 これは、検索と置換操作が必要であることを示す特殊なメッセージを受信するウィンドウです。 場合`NULL`アプリケーションのメイン ウィンドウを使用します。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスのオブジェクトが作成された場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 親ウィンドウ検索/置換要求の通知を受信するためには、Windows を使用する必要があります[を通じて](http://msdn.microsoft.com/library/windows/desktop/ms644947)関数の戻り値を返すは、アプリケーションのインスタンスに固有のメッセージ番号。 フレーム ウィンドウは、コールバック関数を宣言するメッセージ マップ エントリを持つ必要があります (`OnFindReplace`次の例で) この登録されたメッセージを処理します。 次のコード フラグメントは、これを行うという名前のフレーム ウィンドウ クラスの方法の例`CMyRichEditView`:  
  
 [!code-cpp[NVC_MFCDocView#171](../../mfc/codesnippet/cpp/cfindreplacedialog-class_2.h)]  
  
 [!code-cpp[NVC_MFCDocView#172](../../mfc/codesnippet/cpp/cfindreplacedialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#173](../../mfc/codesnippet/cpp/cfindreplacedialog-class_4.cpp)]  
  
 内で、`OnFindReplace`関数を使用して、ユーザーの意図を解釈する、 [CFindReplaceDialog::FindNext](#findnext)と[CFindReplaceDialog::IsTerminating](#isterminating)メソッドを作成するコード検索/置換操作します。  
  
### <a name="example"></a>例  
  例を参照して[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)です。  
  
##  <a name="findnext"></a>  CFindReplaceDialog::FindNext  
 この関数、ユーザーが検索文字列の次の出現箇所を検索するかどうかを決定するコールバック関数を呼び出します。  
  
```  
BOOL FindNext() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが検索文字列の次の出現箇所を検索する場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="getfindstring"></a>  CFindReplaceDialog::GetFindString  
 この関数を検索する既定の文字列を取得するコールバック関数を呼び出します。  
  
```  
CString GetFindString() const;  
```  
  
### <a name="return-value"></a>戻り値  
 検索する既定の文字列。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getnotifier"></a>  CFindReplaceDialog::GetNotifier  
 現在の検索置換 ダイアログ ボックスへのポインターを取得するには、この関数を呼び出します。  
  
```  
static CFindReplaceDialog* PASCAL GetNotifier(LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `lParam`  
 **Lparam**フレーム ウィンドウの値が渡される**次 OnFindReplace**メンバー関数。  
  
### <a name="return-value"></a>戻り値  
 現在のダイアログ ボックスへのポインター。  
  
### <a name="remarks"></a>コメント  
 現在のダイアログ ボックスを表示、関数、およびアクセスは、そのメンバーを呼び出し、コールバック関数内で使用する必要があります、`m_fr`構造体。  
  
### <a name="example"></a>例  
 参照してください[CFindReplaceDialog::Create](#create)置換を検索 ダイアログ ボックスから通知を受け取る次 OnFindReplace ハンドラーを登録する方法の例についてはします。  
  
 [!code-cpp[NVC_MFCDocView#69](../../mfc/codesnippet/cpp/cfindreplacedialog-class_5.cpp)]  
  
##  <a name="getreplacestring"></a>  CFindReplaceDialog::GetReplaceString  
 この関数では、現在の置換文字列を取得します。  
  
```  
CString GetReplaceString() const;  
```  
  
### <a name="return-value"></a>戻り値  
 検索した文字列の置換に使用する既定の文字列。  
  
### <a name="example"></a>例  
  例を参照して[CFindReplaceDialog::GetFindString](#getfindstring)です。  
  
##  <a name="isterminating"></a>  CFindReplaceDialog::IsTerminating  
 ユーザーをダイアログ ボックスを終了することにしたかどうかを決定するコールバック関数の中からこの関数を呼び出します。  
  
```  
BOOL IsTerminating() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、ユーザーは、ダイアログ ボックスを終了することにしましたそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は 0 以外の値を返す必要がありますを呼び出した場合、`DestroyWindow`メンバー関数は、現在のダイアログ ボックスと任意のダイアログ ボックスへのポインター変数設定の**NULL**です。 必要に応じても入力した最後の検索と置換テキストを保存して、次へ の検索と置換 ダイアログ ボックスを初期化するために使用します。  
  
### <a name="example"></a>例  
  例を参照して[CFindReplaceDialog::GetFindString](#getfindstring)です。  
  
##  <a name="m_fr"></a>  CFindReplaceDialog::m_fr  
 カスタマイズに使用される、`CFindReplaceDialog`オブジェクト。  
  
```  
FINDREPLACE m_fr;  
```  
  
### <a name="remarks"></a>コメント  
 `m_fr` 型の構造体は、 [FINDREPLACE](http://msdn.microsoft.com/library/windows/desktop/ms646835)です。 そのメンバーは、ダイアログ ボックスのオブジェクトの特性を格納します。 構築した後、`CFindReplaceDialog`オブジェクトを使用する`m_fr` ダイアログ ボックスのさまざまな値を変更します。  
  
 この構造体の詳細については、次を参照してください。、 **FINDREPLACE** Windows SDK 内の構造。  
  
### <a name="example"></a>例  
  例を参照して[CFindReplaceDialog::CFindReplaceDialog](#cfindreplacedialog)です。  
  
##  <a name="matchcase"></a>  CFindReplaceDialog::MatchCase  
 ユーザーが検索文字列の大文字と小文字を正確に一致するかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL MatchCase() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが検索文字列の大文字と小文字を正確に一致する検索文字列の出現を検索する場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="matchwholeword"></a>  CFindReplaceDialog::MatchWholeWord  
 ユーザーが全体の単語のみが一致するかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL MatchWholeWord() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが検索文字列の全体の単語のみが一致する場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="replaceall"></a>  CFindReplaceDialog::ReplaceAll  
 この関数をユーザーが置換される文字列のすべての項目であるかどうかを判断します。  
  
```  
BOOL ReplaceAll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが置換文字列に一致するすべての文字列が置き換えられることです。 要求している場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="replacecurrent"></a>  CFindReplaceDialog::ReplaceCurrent  
 ユーザーに現在の単語を置換するかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL ReplaceCurrent() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーが、現在選択されている文字列を置換文字列に置き換えることを要求した場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="searchdown"></a>  CFindReplaceDialog::SearchDown  
 ユーザーが下方向へ検索であるかどうかを判断するには、この関数を呼び出します。  
  
```  
BOOL SearchDown() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーは、下方向の方向に続行する検索を望んでいる場合は 0 以外。上方向へ検索する場合は 0 を返します。  
  
## <a name="see-also"></a>関連項目  
 [CCommonDialog クラス](../../mfc/reference/ccommondialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)  
