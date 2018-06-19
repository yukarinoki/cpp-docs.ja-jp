---
title: CKeyboardManager クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
dev_langs:
- C++
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9d4aace502310836429ec8f8f9db74d7cf17ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369103"
---
# <a name="ckeyboardmanager-class"></a>CKeyboardManager クラス
メイン フレーム ウィンドウおよび子フレーム ウィンドウのショートカット キーのテーブルを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CKeyboardManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CKeyboardManager::CKeyboardManager](#ckeyboardmanager)|`CKeyboardManager` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CKeyboardManager::CleanUp](#cleanup)|ショートカット キーのテーブルをクリアします。|  
|[CKeyboardManager::FindDefaultAccelerator](#finddefaultaccelerator)|指定したコマンドおよびウィンドウの既定のショートカット キーを取得します。|  
|[CKeyboardManager::IsKeyHandled](#iskeyhandled)|アクセラレータ テーブルで、キーが処理されるかどうかを判断します。|  
|[CKeyboardManager::IsKeyPrintable](#iskeyprintable)|文字が印刷可能かどうかを示します。|  
|[CKeyboardManager::IsShowAllAccelerators](#isshowallaccelerators)|メニューには、コマンドのすべてのショートカット キーまたは既定のショートカット キーのみが表示されるかどうかを示します。|  
|[CKeyboardManager::LoadState](#loadstate)|Windows レジストリからショートカット キーのテーブルを読み込みます。|  
|[CKeyboardManager::ResetAll](#resetall)|アプリケーション リソースからショートカット キーのテーブルを再読み込みします。|  
|[CKeyboardManager::SaveState](#savestate)|ショートカット キーのテーブルを Windows レジストリに保存します。|  
|[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)|フレームワークは、すべてのコマンドのショートカット キーのすべてまたはコマンドごとに 1 つのショートカット キーを表示するかどうかを指定します。 このメソッドは、1 つだけの関連付けられているショートカット キーを持つコマンドには影響しません。|  
|[CKeyboardManager::TranslateCharToUpper](#translatechartoupper)|文字を大文字レジスタに変換します。|  
|[CKeyboardManager::UpdateAccelTable](#updateacceltable)|新しいショートカット キー テーブルのショートカット キーのテーブルを更新します。|  
  
## <a name="remarks"></a>コメント  
 このクラスのメンバーを使用すると、保存、Windows レジストリにショートカット キーのテーブルを読み込むと、テーブルを更新してショートカット キー、テンプレートを使用してあり、フレーム ウィンドウにコマンドの既定のショートカット キーを検索します。 さらに、`CKeyboardManager`オブジェクトでは、ユーザーにショートカット キーを表示する方法を制御することができます。  
  
 作成しないようにする、`CKeyboardManager`手動でのオブジェクトします。 アプリケーションのためにフレームワークによって自動的に作成されます。 ただし、呼び出す必要があります[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)アプリケーションの初期化プロセス中にします。 アプリケーションのキーボード マネージャーへのポインターを取得、呼び出す[CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)です。  
  
## <a name="example"></a>例  
 次の例へのポインターを取得する方法を示します、`CKeyboardManager`オブジェクトから、`CWinAppEx`クラス、およびメニュー コマンドに関連付けられているすべてのショートカット キーを表示する方法です。 このコード スニペットの一部である、[カスタム ページ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxkeyboardmanager.h  
  
##  <a name="ckeyboardmanager"></a>  CKeyboardManager::CKeyboardManager  
 `CKeyboardManager` オブジェクトを構築します。  
  
```  
CKeyboardManager();
```  
  
### <a name="remarks"></a>コメント  
 ほとんどの場合は作成する必要はありません、`CKeyboardManager`直接です。 既定では、フレームワークの機能の 1 つを作成します。 ポインターを取得する、 `CKeyboardManager`、呼び出す[CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)です。 いずれかを手動で作成する場合、は、メソッドを使用して初期化する必要があります[CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)です。  
  
##  <a name="cleanup"></a>  CKeyboardManager::CleanUp  
 解放、`CKeyboardManager`リソースおよびすべてのショートカット キー マッピング クリアします。  
  
```  
static void CleanUp();
```  
  
### <a name="remarks"></a>コメント  
 ショートカット キーの詳細については、次を参照してください。[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)です。  
  
 ため、フレームワークが自動的にアプリケーションを終了中に、アプリケーションの終了時に、この関数を呼び出す必要はありません。  
  
##  <a name="finddefaultaccelerator"></a>  CKeyboardManager::FindDefaultAccelerator  
 指定したコマンドおよびウィンドウの既定のショートカット キーを取得します。  
  
```  
static BOOL FindDefaultAccelerator(
    UINT uiCmd,  
    CString& str,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiCmd`  
 コマンド ID。  
  
 [出力] `str`  
 `CString` オブジェクトへの参照。  
  
 [入力] `pWndFrame`  
 フレーム ウィンドウへのポインター。  
  
 [入力] `bIsDefaultFrame`  
 フレーム ウィンドウが既定のフレーム ウィンドウであるかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 ショートカット キーが見つかった場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは指定されたコマンドを検索`uiCmd`し、既定のショートカット キーを取得します。 メソッドはこのショートカット キーに関連付けられている文字列を受け取りし、値を書き込みます、`str`パラメーター。  
  
##  <a name="iskeyhandled"></a>  CKeyboardManager::IsKeyHandled  
 によって指定されたキーを処理するかどうかを判断、 [CKeyboardManager クラス](../../mfc/reference/ckeyboardmanager-class.md)です。  
  
```  
static BOOL __stdcall IsKeyHandled(
    WORD nKey,  
    BYTE fVirt,  
    CFrameWnd* pWndFrame,  
    BOOL bIsDefaultFrame);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `nKey`|チェックするキー。|  
|[入力] `fVirt`|ショートカット キーの動作を指定します。 使用可能な値の一覧は、次を参照してください。[アクセル構造](http://msdn.microsoft.com/library/windows/desktop/ms646340)です。|  
|[入力] `pWndFrame`|フレーム ウィンドウです。 このメソッドは、このフレームで、ショートカット キーが処理されるかどうかを判断します。|  
|[入力] `bIsDefaultFrame`|示すブール値パラメーターかどうか`pWndFrame`は、既定のフレーム ウィンドウです。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ショートカット キーが処理されます。 `FALSE` キーが処理されない場合、または`pWndFrame`は`NULL`します。  
  
### <a name="remarks"></a>コメント  
 入力パラメーターは、アクセラレータ テーブルで両方のエントリと一致する必要があります`nKey`と`fVirt`でショートカット キーを処理するかどうかを確認する`pWndFrame`です。  
  
##  <a name="iskeyprintable"></a>  CKeyboardManager::IsKeyPrintable  
 文字が印刷可能かどうかを示します。  
  
```  
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[入力] `nChar`|このメソッドをチェックする文字。|  
  
### <a name="return-value"></a>戻り値  
 0 以外の文字が印刷可能な場合は、されていない場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 このメソッドへの呼び出しが失敗した[GetKeyboardState](http://msdn.microsoft.com/library/windows/desktop/ms646299)は失敗します。  
  
##  <a name="isshowallaccelerators"></a>  CKeyboardManager::IsShowAllAccelerators  
 メニューにメニュー コマンドに関連付けられているショートカット キーのすべてまたは既定のショートカット キーのみが表示されるかどうかを示します。  
  
```  
static BOOL IsShowAllAccelerators();
```  
  
### <a name="return-value"></a>戻り値  
 アプリケーションにメニュー コマンドのショートカット キーのすべてが表示されている場合は 0 以外。アプリケーションは、既定のショートカット キーのみを表示する場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションは、メニュー バーでメニュー コマンドのショートカット キーを一覧表示します。 関数を使用して[CKeyboardManager::ShowAllAccelerators](#showallaccelerators)を制御するかどうか、アプリケーションを一覧表示すべてのショートカット キーまたは既定のショートカット キーを持つユーザーだけです。  
  
##  <a name="loadstate"></a>  CKeyboardManager::LoadState  
 Windows レジストリからショートカット キーのテーブルを読み込みます。  
  
```  
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 レジストリ パスを`CKeyboardManager`データを保存します。  
  
 [入力] `pDefaultFrame`  
 既定のウィンドウとして使用するフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、状態が正常に読み込まれたか 0 それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 場合、`lpszProfileName`パラメーターは`NULL`、このメソッドの既定のレジストリの場所をチェックする`CKeyboardManager`データ。 既定のレジストリの場所が指定された、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)です。 データをメソッドを使用して以前書き込む必要がある[CKeyboardManager::SaveState](#savestate)です。  
  
 既定のウィンドウを指定しない場合は、アプリケーションのメイン フレーム ウィンドウが使用されます。  
  
##  <a name="resetall"></a>  CKeyboardManager::ResetAll  
 アプリケーション リソースからショートカット キーのテーブルを再読み込みします。  
  
```  
void ResetAll();
```  
  
### <a name="remarks"></a>コメント  
 この関数に格納されているショートカットをクリア、`CKeyboardManager`インスタンス。 アプリケーション リソースからキーボード マネージャーの状態が、再読み込みします。  
  
##  <a name="savestate"></a>  CKeyboardManager::SaveState  
 ショートカット キーのテーブルを Windows レジストリに保存します。  
  
```  
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszProfileName`  
 保存するためのレジストリ パス、`CKeyboardManager`状態です。  
  
 [入力] `pDefaultFrame`  
 既定のウィンドウになるフレーム ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 キーボードのマネージャーの状態が正常に保存されている場合は 0 以外。 それ以外の場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 場合、`lpszProfileName`パラメーターは`NULL`、このメソッドは、書き込み、`CKeyboardManager`で指定された既定の場所に状態、 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)です。 場所を指定する場合は、後で、メソッドを使用してデータを読み込むことができます[CKeyboardManager::LoadState](#loadstate)です。  
  
 既定のウィンドウを指定しない場合、メイン フレーム ウィンドウは既定のウィンドウとしてために使用されます。  
  
##  <a name="showallaccelerators"></a>  CKeyboardManager::ShowAllAccelerators  
 メニュー コマンドに関連付けられているすべてのショートカット キーを示します。  
  
```  
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,  
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bShowAll`  
 場合`true`、ショートカット キーのすべてが表示されます。 場合`false`、最初のショートカット キーのみが表示されます。  
  
 [入力] `lpszDelimiter`  
 ショートカット キーの間に挿入する文字列。 1 つのショートカット キーが表示されるだけの場合は、この区切り記号を指定しても効果はありません。  
  
### <a name="remarks"></a>コメント  
 既定では、コマンドは、1 つ以上のショートカット キーに関連付けられている場合、最初のショートカット キーのみ表示されます。 この関数では、すべてのコマンドに関連付けられているすべてのショートカット キーを一覧表示することができます。  
  
 ショートカット キーは、メニュー バーのコマンドの横に表示されます。 ショートカット キーのすべてが表示され場合、によって、文字列を提供`lpszDelimiter`個々 のショートカット キーを区切ります。  
  
##  <a name="translatechartoupper"></a>  CKeyboardManager::TranslateCharToUpper  
 文字を大文字レジスタに変換します。  
  
```  
static UINT TranslateCharToUpper(const UINT nChar);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nChar`  
 変換する文字。  
  
### <a name="return-value"></a>戻り値  
 入力パラメーターの大文字のレジスタである文字。  
  
##  <a name="updateacceltable"></a>  CKeyboardManager::UpdateAccelTable  
 新しいショートカット キー テーブルのショートカット キーのテーブルを更新します。  
  
```  
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    LPACCEL lpAccel,  
    int nSize,  
    CFrameWnd* pDefaultFrame = NULL);

 
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,  
    HACCEL hAccelNew,  
    CFrameWnd* pDefaultFrame = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTemplate`  
 ドキュメント テンプレートへのポインター。  
  
 [入力] `lpAccel`  
 新しいショートカット キーへのポインター。  
  
 [入力] `nSize`  
 新しいショートカット テーブルのサイズ。  
  
 [入力] `pDefaultFrame`  
 既定のフレーム ウィンドウへのポインター。  
  
 [入力] `hAccelNew`  
 新しいショートカット テーブルへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、複数のフレーム ウィンドウ オブジェクトの新しいショートカット キーを持つ既存のショートカットの表を置換できます。 関数は、ドキュメント テンプレートを特定のドキュメント テンプレートに接続されているすべてのフレーム ウィンドウ オブジェクトへのアクセスを取得するパラメーターとして受け取ります。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)   
 [キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)



