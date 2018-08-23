---
title: CUserTool クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
dev_langs:
- C++
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51933ac5aeb3c14a25b3989809aab2e09686b9a3
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539085"
---
# <a name="cusertool-class"></a>CUserTool クラス
ユーザー ツールは、外部アプリケーションを実行するメニュー項目です。 **ツール**のタブ、**カスタマイズ** ダイアログ ボックス ( [CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) により、ユーザー ツールのユーザーを追加し、名前、コマンド、引数を指定し、各ユーザー ツールの初期ディレクトリ。  
  
## <a name="syntax"></a>構文  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|指定した四角形でユーザーの [ツール] アイコンを描画します。|  
|[CUserTool::GetCommand](#getcommand)|ユーザー ツールに関連付けられているコマンドのテキストを含む文字列を返します。|  
|[CUserTool::GetCommandId](#getcommandid)|ユーザー ツールのメニュー項目のコマンド ID を返します。|  
|[Cusertool:](#invoke)|ユーザー ツールに関連付けられているコマンドを実行します。|  
|[CUserTool::Serialize](#serialize)|アーカイブに対して、このオブジェクトの読み取りまたは書き込みを行います。 ( [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize)をオーバーライドします)。|  
|[CUserTool::SetCommand](#setcommand)|ユーザー ツールに関連付けられているコマンドを設定します。|  
|[CUserTool::SetToolIcon](#settoolicon)|このツールに関連付けられているアプリケーションからユーザー ツールのアイコンを読み込みます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|ユーザー ツールの既定のアイコンを読み込みます。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|ユーザー ツールのコマンドライン引数。|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|ユーザー ツールの初期ディレクトリ。|  
|[CUserTool::m_strLabel](#m_strlabel)|ツールのメニュー項目に表示されるツールの名前。|  
  
## <a name="remarks"></a>Remarks  
 アプリケーションでユーザー ツールを有効にする方法の詳細については、次を参照してください。 [CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)します。  
  
## <a name="example"></a>例  
 次の例からツールを作成する方法を示します、`CUserToolsManager`オブジェクト、設定、`m_strLabel`メンバー変数、およびユーザー ツールを実行するアプリケーションを設定します。 このコード スニペットの一部、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxusertool.h  
  
##  <a name="copyicontoclipboard"></a>  CUserTool::CopyIconToClipboard  
 詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="drawtoolicon"></a>  CUserTool::DrawToolIcon  
 指定した四角形の中心にユーザーの [ツール] アイコンを描画します。  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pDC*  
 デバイス コンテキストへのポインター。  
  
 [in]*rectImage*  
 アイコンを表示する領域の座標を指定します。  
  
##  <a name="getcommand"></a>  CUserTool::GetCommand  
 ユーザー ツールに関連付けられているコマンドのテキストを含む文字列を返します。  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>戻り値  
 参照を`CString`ユーザー ツールに関連付けられているコマンドのテキストを格納しているオブジェクト。  
  
##  <a name="getcommandid"></a>  CUserTool::GetCommandId  
 ユーザー ツールのコマンド ID を返します。  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 このユーザー ツールのコマンド ID。  
  
##  <a name="invoke"></a>  Cusertool:  
 ユーザー ツールに関連付けられているコマンドを実行します。  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>戻り値  
 コマンドが正常に実行された場合、0 以外の場合それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 呼び出し[ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153)ユーザー ツールに関連付けられているコマンドを実行します。 または、コマンドが空の場合、関数は失敗[ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153)は失敗します。  
  
##  <a name="loaddefaulticon"></a>  CUserTool::LoadDefaultIcon  
 ユーザー ツールの既定のアイコンを読み込みます。  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>戻り値  
 読み込まれたアイコン (HICON)、または既定のアイコンを読み込むことができない場合は NULL へのハンドル。  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、ツールの実行可能ファイルからユーザー定義のツールのアイコンを読み込むことができない場合、このメソッドを呼び出します。  
  
 独自の既定ツール アイコンを指定するには、このメソッドをオーバーライドします。  
  
##  <a name="m_strarguments"></a>  CUserTool::m_strArguments  
 ユーザー ツールのコマンドライン引数。  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>Remarks  
 この文字列は、呼び出すときに、ツールに渡された[cusertool:](#invoke)またはユーザーがこのツールに関連付けられているコマンドをクリックしたとき。  
  
##  <a name="m_strinitialdirectory"></a>  CUserTool::m_strInitialDirectory  
 ユーザー ツールの初期ディレクトリを指定します。  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>Remarks  
 この変数を呼び出すときに、ツールを実行する初期ディレクトリを指定する[cusertool:](#invoke)またはユーザーがこのツールに関連付けられているコマンドをクリックしたとき。  
  
##  <a name="m_strlabel"></a>  CUserTool::m_strLabel  
 ツールのメニュー項目に表示されるラベルです。  
  
```  
CString m_strLabel;  
```  
  
##  <a name="serialize"></a>  CUserTool::Serialize  
 詳細についてにあるソース コードを参照してください、 **VC\\atlmfc\\src\\mfc** Visual Studio のインストールのフォルダー。  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ar*  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setcommand"></a>  CUserTool::SetCommand  
 ユーザー ツールを実行するアプリケーションを設定します。  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszCmd*  
 ユーザー ツールに関連する新しいアプリケーションを指定します。  
  
### <a name="remarks"></a>Remarks  
 ユーザー ツールを実行する新しいアプリケーションを設定するには、このメソッドを呼び出します。 このメソッドは、古いアイコンを破棄し、特定のアプリケーションから、新しいアイコンを読み込みます。 場合は、アプリケーションからそのアイコンを読み込むことができません、呼び出すことによって、ユーザー ツールの既定のアイコンを読み込む[CUserTool::LoadDefaultIcon](#loaddefaulticon)します。  
  
##  <a name="settoolicon"></a>  CUserTool::SetToolIcon  
 このツールを使用するアプリケーションからユーザー ツールのアイコンを読み込みます。  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>戻り値  
 読み込まれたアイコンへのハンドル。  
  
### <a name="remarks"></a>Remarks  
 メニュー項目に表示されるアイコンの読み込みには、このメソッドを呼び出します。 このメソッドは、ツールで使用される実行可能ファイルのアイコンを検索します。 アイコンは、によって提供される既定のアイコンを持たない場合[CUserTool::LoadDefaultIcon](#loaddefaulticon)代わりに使用されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)   
 [CUserToolsManager クラス](../../mfc/reference/cusertoolsmanager-class.md)
