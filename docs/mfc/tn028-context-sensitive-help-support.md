---
title: 'TN028: 状況依存のヘルプのサポート |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.help
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45a8835b43225a8e134da0f983f7c86d461a0636
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954898"
---
# <a name="tn028-context-sensitive-help-support"></a>テクニカル ノート 28: 状況依存のヘルプのサポート
ここでは、ヘルプ コンテキスト Id と MFC では、その他のヘルプ問題の割り当ての規則について説明します。 状況依存のヘルプのサポートには、Visual C で使用可能なヘルプ コンパイラが必要です。  
  
> [!NOTE]
>  WinHelp を使用して、状況依存のヘルプを実装するだけでなく、HTML ヘルプの使用を MFC もサポートします。 このサポートおよび HTML ヘルプを使用したプログラミングの詳細については、次を参照してください。 [HTML ヘルプ: プログラムの状況依存のヘルプ](../mfc/html-help-context-sensitive-help-for-your-programs.md)です。  
  
## <a name="types-of-help-supported"></a>サポートされているヘルプの種類  
 Windows アプリケーションで実装される状況依存のヘルプの 2 種類あります。 1 つ目と呼ばれる"F1 Help"は現在アクティブなオブジェクトに基づき、適切なコンテキストです。 2 つ目は、"shift キーを押しながら F1"モードです。 このモードで、マウスのカーソルに変わりヘルプ カーソル、そのユーザーにオブジェクトをクリックします。 その時点で、ユーザーがクリックしたオブジェクトに関するヘルプ WinHelp が起動されます。  
  
 Microsoft Foundation Classes は、これらの形式のヘルプの両方を実装します。 さらに、フレームワークでは、ヘルプのキーワードとヘルプを使用して、2 つの簡単なヘルプ コマンドをサポートしています。  
  
## <a name="help-files"></a>ヘルプ ファイル  
 Microsoft Foundation classes には、単一のヘルプ ファイルがあるとします。 ヘルプ ファイルは、アプリケーションと同じ名前とパスが必要です。 たとえば、実行可能ファイルは C:\MyApplication\MyHelp.exe ヘルプ ファイルは C:\MyApplication\MyHelp.hlp をする必要があります。 経由のパスを設定する、*ポインター*のメンバー変数、 [CWinApp クラス](../mfc/reference/cwinapp-class.md)です。  
  
## <a name="help-context-ranges"></a>ヘルプ コンテキストの範囲  
 MFC の既定の実装には、次のヘルプ コンテキスト Id の割り当てに関する一部のルールをプログラムが必要です。 これらの規則は、特定のコントロールに割り当てられている Id の範囲です。 これらのルールを上書きするには、さまざまなヘルプに関連するメンバー関数のさまざまな実装を提供します。  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
0x00010000 + ID_  
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)  
0x00020000 - 0x0002FFFF : windows and dialogs  
0x00020000 + IDR_  
(note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)  
0x00030000 - 0x0003FFFF : error messages (based on error string ID)  
0x00030000 + IDP_  
0x00040000 - 0x0004FFFF : special purpose (non-client areas)  
0x00040000 + HitTest area  
0x00050000 - 0x0005FFFF : controls (those that are not commands)  
0x00040000 + IDW_  
```  
  
## <a name="simple-help-commands"></a>単純な"Help"コマンド  
 Microsoft Foundation Classes によって実装される 2 つの単純なヘルプ コマンドがあります。  
  
-   によって実装される ID_HELP_INDEX [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)  
  
-   によって実装される ID_HELP_USING [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)  
  
 最初のコマンドは、アプリケーションのヘルプ インデックスを示しています。 2 つ目は、WinHelp プログラムを使用してユーザーのヘルプを示します。  
  
## <a name="context-sensitive-help-f1-help"></a>状況依存のヘルプ (F1 ヘルプ)  
 F1 キーを押すは通常、メイン ウィンドウのアクセラレータ テーブルにアクセラレータで ID の ID_HELP コマンドに変換されます。 ID_HELP コマンドは、メイン ウィンドウまたはダイアログ ボックスに ID の ID_HELP いるボタンを生成することも可能性があります。  
  
 ID_HELP コマンドの生成方法に関係なく、コマンド ハンドラーに到達するまで、通常のコマンドとしてルーティングされます。 MFC のコマンド ルーティングのアーキテクチャの詳細についてを参照してください[テクニカル ノート 21](../mfc/tn021-command-and-message-routing.md)です。 ID_HELP コマンドで処理するアプリケーションのヘルプを有効になっている場合は、 [:onhelp](../mfc/reference/cwinapp-class.md#onhelp)です。 アプリケーション オブジェクトは、ヘルプ メッセージを受信し、コマンドを適切にルーティングします。 これは、機能は、既定のコマンド ルーティングが十分に具体的なコンテキストを判別できないため必要です。  
  
 `CWinApp::OnHelp` 次の順序で WinHelp を起動しようとしています。  
  
1.  アクティブなチェック`AfxMessageBox`ヘルプ ID を呼び出す メッセージ ボックスが現在アクティブな場合は、そのメッセージ ボックスに適切なコンテキストを持つ WinHelp が起動します。  
  
2.  アクティブなウィンドウをようメッセージを送信します。 WinHelp を起動してそのウィンドウが応答しなかった場合に、メッセージが処理されるか、現在のウィンドウがトップレベル ウィンドウまで同じメッセージはそのウィンドウの祖先に送信されます。  
  
3.  メイン ウィンドウを ID_DEFAULT_HELP コマンドを送信します。 これは、既定のヘルプを起動します。 このコマンドは通常を`CWinApp::OnHelpIndex`です。  
  
 グローバルに既定の ID ベース値 (0x10000 コマンドなどの 0x20000 ダイアログ ボックスなどのリソース) を無効にするアプリケーションをオーバーライドする必要があります[cwinapp::winhelp](../mfc/reference/cwinapp-class.md#winhelp)です。  
  
 この機能およびヘルプ コンテキストが決定される方法をオーバーライドするには、ようメッセージを処理する必要があります。 具体的なヘルプをルーティング フレームワークで提供される、それのみに出ると、現在の MDI 子ウィンドウとして深いする可能性があります。 特定のウィンドウまたはダイアログ ボックスで、そのオブジェクトまたはダイアログ内でアクティブなコントロールの現在の内部状態に基づくなどの特定のヘルプを提供することもできます。  
  
## <a name="wmcommandhelp"></a>よう  
  
```  
 
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
 
```  
  
 ようは、ヘルプが要求されたときにアクティブなウィンドウによって受信されるプライベート Windows MFC メッセージです。 呼び出す必要があります、ウィンドウは、このメッセージを受信したときに`CWinApp::WinHelp`ウィンドウの内部状態と一致するコンテキストを使用します。  
  
 *lParam*  
 現在使用可能なヘルプ コンテキストが含まれています。 *lParam*ヘルプ コンテキストが特定されていない場合は 0 です。 実装`OnCommandHelp`でコンテキスト ID を使用して*lParam*にさまざまなコンテキストを決定するかに渡すことができますのみ`CWinApp::WinHelp`です。  
  
 *wParam*  
 使用されず、0 になります。  
  
 場合、`OnCommandHelp`関数呼び出し`CWinApp::WinHelp`、返すか**TRUE**です。 返す**TRUE**他のクラスやその他の windows には、このコマンドのルーティングを停止します。  
  
## <a name="help-mode-shiftf1-help"></a>ヘルプ モード (shift キーを押しながら F1 ヘルプ)  
 これは、状況依存のヘルプの 2 番目の形式です。 一般に、このモードは、shift キーを押しながら F1 キーを押すかメニュー/ツールバーを使用して入力されます。 コマンド (ID_CONTEXT_HELP) として実装されます。 モーダル ダイアログ ボックスの中にこのコマンドを変換するメッセージ フィルターのフックは使用されませんまたはメニューがアクティブなしたがってこのコマンドはユーザーが利用できる場合にのみアプリケーションのメイン メッセージ ポンプを実行 (`CWinApp::Run`)。  
  
 このモードを入力すると、ヘルプのマウス カーソルが (ウィンドウの周囲のサイズ変更境界) などの領域のカーソルと、アプリケーションは通常表示する場合でも、アプリケーションのすべての領域に表示されます。 ユーザーは、コマンドを選択するマウスやキーボードを使用することができます。 コマンドを実行するには、代わりにそのコマンドのヘルプが表示されます。 また、ユーザーは、ツールバーのボタンなど、画面に表示されるオブジェクトをクリックして、そのオブジェクトのヘルプが表示されます。 このモードのヘルプがによって提供される`CWinApp::OnContextHelp`です。  
  
 このループの実行中には、すべてのキーボード入力メニューにアクセス キーを除く、アクティブではありません。 また、コマンドはまだ変換を介して`PreTranslateMessage`アクセラレータ キーを押すし、そのコマンドのヘルプを受信するユーザーを許可します。  
  
 翻訳または実行されているアクションが配置の特定がある場合、`PreTranslateMessage`関数はならない中に行われる shift キーを押しながら F1 ヘルプ モードを確認してください、 *m_bHelpMode*のメンバー`CWinApp`ものを実行する前に操作です。 `CDialog`の実装`PreTranslateMessage`これを呼び出す前にチェック`IsDialogMessage`、例を示します。 これには、shift キーを押しながら F1 モード中にモードレス ダイアログ ボックスの「ダイアログ ナビゲーション」キーが無効にします。 さらに、`CWinApp::OnIdle`はこのループの中に呼び出されます。  
  
 ユーザー選択した場合、コマンド、メニューから、そのコマンドに関するヘルプを参照として扱われます (よう、を通じて以下を参照)。 ユーザーには、アプリケーション ウィンドウの表示領域がクリックすると、非クライアント領域と、クライアントのクリックであるかについて判断が行われます。 `OnContextHelp` 非クライアントのハンドルの割り当てを自動的にクライアントをクリックしてクリックします。 クライアントの場合、領域をクリックしたウィンドウに送信します。 そのウィンドウが 0 以外の値を返す場合、その値はヘルプのコンテキストとして使用します。 0 を返した場合`OnContextHelp`親ウィンドウを試みます (とそれがない場合、その親、およびなど)。 ヘルプ コンテキストを特定できない場合、既定は ID_DEFAULT_HELP コマンドにマップされます (通常は) のメイン ウィンドウを送信するのには`CWinApp::OnHelpIndex`します。  
  
## <a name="wmhelphittest"></a>領域  
  
```  
 
afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)  
```  
  
 領域は、shift キーを押しながら F1 ヘルプ モードの実行時にアクティブなウィンドウによって受信される MFC プライベート windows メッセージです。 返します、ウィンドウは、このメッセージを受信した場合、 **DWORD** WinHelp で使用するためのヘルプの ID。  
  
 LOWORD(lParam)  
 ウィンドウのクライアント領域と相対的マウスがクリックしてされた位置の x 軸デバイス座標が含まれています。  
  
 HIWORD(lParam)  
 y 軸座標が含まれています。  
  
 *wParam*  
 使用されず、0 になります。 戻り値が 0 以外の場合は、そのコンテキストで WinHelp が呼び出されます。 戻り値が 0 の場合は、ヘルプの親ウィンドウが照会されます。  
  
 多くの場合が既に手元にヒット テストのコードを利用できます。 実装を参照してください`CToolBar::OnHelpHitTest`領域メッセージの処理の例については (コードでボタンおよびツールヒントで使用するヒット テストのコードを利用して`CControlBar`)。  
  
## <a name="mfc-application-wizard-support-and-makehm"></a>MFC アプリケーション ウィザードでサポートおよび MAKEHM  
 MFC アプリケーション ウィザードでは、ヘルプ ファイル (.cnt および .hpj ファイル) をビルドするために必要なファイルを作成します。 Microsoft ヘルプ コンパイラによって受け入れられる構築済みの .rtf ファイルの数も含まれています。 完了したら、多くのトピックがいくつか、特定のアプリケーション用に変更する必要があります。  
  
 "マッピング help"のファイルの自動作成は、makehm ユーティリティでサポートされます。 MAKEHM ユーティリティは、アプリケーションのリソースを翻訳できます。ヘルプ マップ ファイルへのファイルを H します。 例えば:  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 変換されます。  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 この形式は、トピック名 (左側にあるシンボル) を持つコンテキスト Id (右側の数字) をマップするためにヘルプ コンパイラの機能と互換性です。  
  
 MAKEHM のソース コードが MFC プログラミング ユーティリティ サンプルで使用可能な[MAKEHM](../visual-cpp-samples.md)です。  
  
## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC アプリケーション ウィザードを実行した後、ヘルプのサポートを追加します。  
 アプリケーションにヘルプを追加する最善の方法では、アプリケーションを作成する前に、高度な機能、MFC アプリケーション ウィザードのページで、状況依存のヘルプ」オプションを確認します。 このように、MFC アプリケーション ウィザードは自動的に、必要なメッセージ マップ エントリを追加、 `CWinApp`-ヘルプをサポートするクラスを派生します。  
  
## <a name="help-on-message-boxes"></a>メッセージ ボックスをヘルプします。  
 メッセージ ボックス (アラートとも呼ばれます) に関するヘルプはによってサポートされて、`AfxMessageBox`関数、用のラッパー、 `MessageBox` Windows API。  
  
 2 つのバージョンがある`AfxMessageBox`、1 つは文字列へのポインターを使用するための別の文字列 ID と用途 (`LPCSTR`)。  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```  
  
 どちらの場合は、省略可能なヘルプ id です。  
  
 最初のケースでは、nIDHelp の既定値は 0 で、このメッセージ ボックスのヘルプを示しません。 場合など、メッセージ ボックスがアクティブな間は、f1 キーを押す、ユーザーは受け取りませんヘルプ (アプリケーションでは、ヘルプをサポートしている) 場合も同様です。 これが望ましくない場合は、nIDHelp のヘルプ ID を指定する必要があります。  
  
 2 番目のケースでは、nIDHelp の既定値は、ヘルプ ID が nIDPrompt と同じことを示す-1 です。 ヘルプは機能のみ、アプリケーションのヘルプが有効な場合、当然のことながら)。 メッセージ ボックスにヘルプをサポートしていないことを希望する場合は、0 を nIDHelp の入力が必要です。 メッセージを有効になっているのヘルプが nIDPrompt よりヘルプ ID を必要に応じて、単に nIDHelp nIDPrompt のされるものと異なるは正の値を提供する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

