---
title: メンバー クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
dev_langs:
- C++
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d292c3f48f0a375fbd914cf287f1e8d2cef5c6c3
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952386"
---
# <a name="ccommandlineinfo-class"></a>メンバー クラス
アプリケーション起動時のコマンド ライン解析を補助します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCommandLineInfo : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|既定値を構築`CCommandLineInfo`オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[後](#parseparam)|個別のパラメーターを解析するには、このコールバックをオーバーライドします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|コマンドラインを示します`/Automation`オプションが見つかりました。|  
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|コマンドラインを示します`/Embedding`オプションが見つかりました。|  
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|スプラッシュ画面を表示するかどうかを示します。|  
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|処理するシェル コマンドを示します。|  
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|ドライバーを示す場合は印刷するには、シェル コマンドの名前を付けますそれ以外の場合は空です。|  
|[CCommandLineInfo::m_strFileName](#m_strfilename)|開くファイルまたは印刷; ファイル名を示しますシェル コマンドは、新規または DDE 場合は空です。|  
|[CCommandLineInfo::m_strPortName](#m_strportname)|ポートを示す場合は印刷するには、シェル コマンドの名前を付けますそれ以外の場合は空です。|  
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|プリンターを示す場合は印刷するには、シェル コマンドの名前を付けますそれ以外の場合は空です。|  
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|再起動マネージャーは、アプリケーションを再起動する場合は、再起動マネージャーの一意の再起動識別子を示します。|  
  
## <a name="remarks"></a>Remarks  
 MFC アプリケーションはこのクラスでのローカル インスタンスを作成して通常、 [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)アプリケーション オブジェクトの関数。 このオブジェクトに渡され[CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)、繰り返し呼び出す[ParseParam](#parseparam)を埋める、`CCommandLineInfo`オブジェクト。 `CCommandLineInfo`にオブジェクトが渡され[CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)フラグとコマンドライン引数を処理します。  
  
 このオブジェクトを使用すると、次のコマンド ライン オプションとパラメーターをカプセル化します。  
  
|コマンドライン引数|実行されたコマンド|  
|----------------------------|----------------------|  
|*app*|新しいファイル。|  
|*アプリ*ファイル名|ファイルを開く。|  
|*アプリ*`/p`ファイル名|既定のプリンターにファイルを印刷します。|  
|*アプリ* `/pt` filename プリンター ドライバーのポート|指定されたプリンターにファイルを印刷します。|  
|*アプリ* `/dde`|起動し、DDE コマンドを待機します。|  
|*アプリ* `/Automation`|OLE オートメーション サーバーとして起動します。|  
|*アプリ* `/Embedding`|OLE 埋め込みアイテムを編集するのを起動します。|  
|*アプリ* `/Register`<br /><br /> *アプリ* `/Regserver`|登録タスクを実行するアプリケーションに通知します。|  
|*アプリ* `/Unregister`<br /><br /> *アプリ* `/Unregserver`|任意の登録を解除したタスクを実行するアプリケーションに通知します。|  
  
 新しいクラスを派生`CCommandLineInfo`を他のフラグとパラメーターの値を処理します。 オーバーライド[ParseParam](#parseparam)を新しいフラグを処理します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCommandLineInfo`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="ccommandlineinfo"></a>  CCommandLineInfo::CCommandLineInfo  
 このコンス トラクターを作成、`CCommandLineInfo`既定値を持つオブジェクト。  
  
```  
CCommandLineInfo();
```  
  
### <a name="remarks"></a>Remarks  
 既定値は、スプラッシュ画面を表示するのには ( `m_bShowSplash=TRUE`) とコマンドを実行する、新しい [ファイル] メニュー ( `m_nShellCommand` **NewFile =**)。  
  
 アプリケーション フレームワーク[ParseParam](#parseparam)このオブジェクトのデータ メンバーを入力します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]  
  
##  <a name="m_brunautomated"></a>  CCommandLineInfo::m_bRunAutomated  
 示します、`/Automation`コマンドラインにフラグが見つかりました。  
  
```  
BOOL m_bRunAutomated;  
```  
  
### <a name="remarks"></a>Remarks  
 場合`TRUE`、つまり、OLE オートメーション サーバーとして起動します。  
  
##  <a name="m_brunembedded"></a>  CCommandLineInfo::m_bRunEmbedded  
 示します、`/Embedding`コマンドラインにフラグが見つかりました。  
  
```  
BOOL m_bRunEmbedded;  
```  
  
### <a name="remarks"></a>Remarks  
 場合`TRUE`、つまり OLE 埋め込みアイテムの編集開始します。  
  
##  <a name="m_bshowsplash"></a>  CCommandLineInfo::m_bShowSplash  
 スプラッシュ画面を表示することを示します。  
  
```  
BOOL m_bShowSplash;  
```  
  
### <a name="remarks"></a>Remarks  
 場合`TRUE`、これは、意味、スプラッシュ スクリーンの起動中にこのアプリケーションを表示する必要があります。 既定の実装[ParseParam](#parseparam)このデータ メンバーを設定`TRUE`場合[m_nShellCommand](#m_nshellcommand)と等しい`CCommandLineInfo::FileNew`です。  
  
##  <a name="m_nshellcommand"></a>  CCommandLineInfo::m_nShellCommand  
 アプリケーションのこのインスタンスのシェル コマンドを示します。  
  
```  
m_nShellCommand;  
```  
  
### <a name="remarks"></a>Remarks  
 このデータ メンバーの型は、次の列挙型で定義されている、`CCommandLineInfo`クラスです。  
  
```  
enum {  
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1  
    };  
```  
  
 これらの値の簡単な説明は、次の一覧を参照してください。  
  
- `CCommandLineInfo::FileNew` ファイル名が見つからなかったというコマンドラインを示します。  
  
- `CCommandLineInfo::FileOpen` コマンドラインでファイル名が存在して、次のフラグのいずれも、コマンドラインで検出されたことを示す: `/p`、 `/pt`、`/dde`です。  
  
- `CCommandLineInfo::FilePrint` 示します、`/p`コマンドラインにフラグが見つかりました。  
  
- `CCommandLineInfo::FilePrintTo` 示します、`/pt`コマンドラインにフラグが見つかりました。  
  
- `CCommandLineInfo::FileDDE` 示します、`/dde`コマンドラインにフラグが見つかりました。  
  
- `CCommandLineInfo::AppRegister` 示します、`/Register`または`/Regserver`フラグがコマンドラインで検出されたため、アプリケーションを登録するように要求されました。  
  
- `CCommandLineInfo::AppUnregister` 示します、`/Unregister`または`/Unregserver`アプリケーションは、登録を解除するように要求されました。  
  
- `CCommandLineInfo::RestartByRestartManager` 再起動マネージャーによって、アプリケーションが再起動されたことを示します。  
  
- `CCommandLineInfo::FileNothing` スタートアップ時に新しい MDI 子ウィンドウの表示をオフにします。 仕様では、アプリケーションのウィザードで生成された MDI アプリケーションは起動時に新しい子ウィンドウを表示します。 この機能を無効にするアプリケーションで使用できます`CCommandLineInfo::FileNothing`呼び出したときにシェル コマンドとして[ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)です。 `ProcessShellCommand` によって呼び出される、`InitInstance( )`すべて`CWinApp`クラスを派生します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]  
  
##  <a name="m_strdrivername"></a>  CCommandLineInfo::m_strDriverName  
 コマンドラインで 3 番目のフラグではないパラメーターの値を格納します。  
  
```  
CString m_strDriverName;  
```  
  
### <a name="remarks"></a>Remarks  
 このパラメーターは、通常、印刷シェル コマンドのプリンタ ドライバの名前です。 既定の実装[ParseParam](#parseparam)データ メンバー場合のみ、この設定は`/pt`コマンドラインにフラグが見つかりました。  
  
##  <a name="m_strfilename"></a>  CCommandLineInfo::m_strFileName  
 コマンドラインで最初のフラグではないパラメーターの値を格納します。  
  
```  
CString m_strFileName;  
```  
  
### <a name="remarks"></a>Remarks  
 このパラメーターは、通常に開かれるファイルの名前です。  
  
##  <a name="m_strportname"></a>  CCommandLineInfo::m_strPortName  
 コマンドラインでは、4 番目のフラグではないパラメーターの値を格納します。  
  
```  
CString m_strPortName;  
```  
  
### <a name="remarks"></a>Remarks  
 このパラメーターは、通常、印刷シェル コマンドのプリンター ポートの名前です。 既定の実装[ParseParam](#parseparam)データ メンバー場合のみ、この設定は`/pt`コマンドラインにフラグが見つかりました。  
  
##  <a name="m_strprintername"></a>  CCommandLineInfo::m_strPrinterName  
 コマンドラインで 2 つ目の非フラグ パラメーターの値を格納します。  
  
```  
CString m_strPrinterName;  
```  
  
### <a name="remarks"></a>Remarks  
 このパラメーターは、通常、印刷シェル コマンドのプリンターの名前です。 既定の実装[ParseParam](#parseparam)データ メンバー場合のみ、この設定は`/pt`コマンドラインにフラグが見つかりました。  
  
##  <a name="m_strrestartidentifier"></a>  CCommandLineInfo::m_strRestartIdentifier  
 一意の識別子は、コマンドラインでを再起動します。  
  
```  
CString m_strRestartIdentifier;  
```  
  
### <a name="remarks"></a>Remarks  
 再起動識別子は、アプリケーションの各インスタンスに対して一意です。  
  
 再起動マネージャーが、アプリケーションを終了、再起動するように構成された場合は、再起動マネージャーは、省略可能なパラメーターとして再起動識別子をコマンドラインからアプリケーションを実行します。 再起動マネージャーは、再起動の識別子を使用する場合、アプリケーションで開いていたドキュメントを閉じて再度開きますおよび自動保存されたファイルを回復します。  
  
##  <a name="parseparam"></a>  後  
 フレームワークは、コマンドラインからの個別のパラメーターの解析と解釈するには、この関数を呼び出します。 最初の 2 つ目のバージョンと一致しない Unicode プロジェクトでのみです。  
  
```  
virtual void ParseParam(
    const char* pszParam,  
    BOOL bFlag,  
    BOOL bLast);

 
virtual void ParseParam(
    const TCHAR* pszParam,  
    BOOL bFlag,  
    BOOL bLast);
```  
  
### <a name="parameters"></a>パラメーター  
 *pszParam*  
 パラメーターまたはフラグです。  
  
 *bFlag*  
 示すかどうか*pszParam*パラメーターまたはフラグ。  
  
 *爆発*  
 これは最後のパラメーターまたはコマンド ラインでフラグを示します。  
  
### <a name="remarks"></a>Remarks  
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)呼び出し`ParseParam`1 回ごとのパラメーターまたはコマンド ラインでフラグを使用して、引数を渡す*pszParam*です。 パラメーターの最初の文字がある場合、' **-**'または' **/**' が削除および*bFlag*に設定されている`TRUE`です。 最後のパラメーターを解析するときに*爆発*に設定されている`TRUE`です。  
  
 この関数の既定の実装は、次のフラグを認識: `/p`、 `/pt`、 `/dde`、 `/Automation`、および`/Embedding`次の表に示すように、します。  
  
|コマンドライン引数|実行されたコマンド|  
|----------------------------|----------------------|  
|*app*|新しいファイル。|  
|*アプリ*ファイル名|ファイルを開く。|  
|*アプリ*`/p`ファイル名|既定のプリンターにファイルを印刷します。|  
|*アプリ* `/pt` filename プリンター ドライバーのポート|指定されたプリンターにファイルを印刷します。|  
|*アプリ* `/dde`|起動し、DDE コマンドを待機します。|  
|*アプリ* `/Automation`|OLE オートメーション サーバーとして起動します。|  
|*アプリ* `/Embedding`|OLE 埋め込みアイテムを編集するのを起動します。|  
|*アプリ* `/Register`<br /><br /> *アプリ* `/Regserver`|登録タスクを実行するアプリケーションに通知します。|  
|*アプリ* `/Unregister`<br /><br /> *アプリ* `/Unregserver`|任意の登録を解除したタスクを実行するアプリケーションに通知します。|  
  
 この情報が格納されている[m_bRunAutomated](#m_brunautomated)、 [m_bRunEmbedded](#m_brunembedded)、および[m_nShellCommand](#m_nshellcommand)です。 フラグがマークされているいずれかでスラッシュ '  **/** またはハイフン' **-**' です。  
  
 既定の実装には、最初のフラグではないパラメーターを格納する[m_strFileName](#m_strfilename)です。 場合、`/pt`フラグは、既定の実装は、2 番目、3 番目、および 4 番目のフラグではないパラメーターを[m_strPrinterName](#m_strprintername)、 [m_strDriverName](#m_strdrivername)、および[m _strPortName](#m_strportname)、それぞれします。  
  
 既定の実装も設定[m_bShowSplash](#m_bshowsplash)に`TRUE`新しいファイルの場合のみです。 新しいファイルの場合、ユーザーは、アプリケーション自体に関連するアクションを取得しました。 シェルを使用して既存のファイルを開くことを含め、その他の状況では、ユーザーの操作は、ファイルを直接はします。 ドキュメント中心の観点で、スプラッシュ スクリーンは、アプリケーションの起動を通知する必要はありません。  
  
 その他のフラグとパラメーターの値を処理する派生クラスでは、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWinApp::ParseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)   
 [CWinApp::ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)

