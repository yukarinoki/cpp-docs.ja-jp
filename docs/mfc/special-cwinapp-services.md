---
title: CWinApp サービス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
dev_langs:
- C++
helpviewer_keywords:
- files [MFC], most recently used
- DragAcceptFiles method [MFC]
- MRU lists
- GDI+, initializing for MFC
- GDI+, suppressing background thread [MFC]
- CWinApp class [MFC], shell registration
- application objects [MFC], services
- CWinApp class [MFC], initializing GDI+
- MFC, shell registration
- CWinApp class [MFC], File Manager drag and drop
- LoadStdProfileSettings method [MFC]
- MFC, most-recently-used file list
- RegisterShellFileTypes method [MFC]
- drag and drop [MFC], files
- registering file types
- Shell, registering file types
- services, provided by CWinApp
- CWinApp class [MFC], recently used documents
- CWinApp class [MFC], services
- files [MFC], drag and drop
- EnableShellOpen method [MFC]
- registry [MFC], most recently used files
- MFC, file operations
- registration [MFC], shell
ms.assetid: 0480cd01-f629-4249-b221-93432d95b431
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81c3804ccc4f9e30e2d287102c408c98a77c6833
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382932"
---
# <a name="special-cwinapp-services"></a>CWinApp のその他のサービス
メッセージ ループの実行をアプリケーションを初期化し、その後をクリーンアップする機会を提供することだけでなく[CWinApp](../mfc/reference/cwinapp-class.md)他のいくつかのサービスを提供します。  
  
##  <a name="_core_shell_registration"></a> シェル登録  
 既定では、MFC アプリケーション ウィザードでは、ファイル エクスプ ローラーまたはファイル マネージャーでダブルクリックして、作成したアプリケーションをデータ ファイルを開くユーザーは、します。 MFC アプリケーション ウィザードが呼び出しを追加するアプリケーションが MDI アプリケーションであり、アプリケーションが作成されるファイルの拡張子を指定する場合、 [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes)と[EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)のメンバー関数は[CWinApp](../mfc/reference/cwinapp-class.md)を`InitInstance`を書き込むオーバーライドします。  
  
 `RegisterShellFileTypes` ファイル エクスプ ローラーまたはファイル マネージャーで、アプリケーションのドキュメントの種類を登録します。 関数は、Windows が保持している登録データベースにエントリを追加します。 エントリで、各ドキュメントの種類を登録、ファイル拡張子をファイルの種類に関連付けるを開くには、アプリケーションのコマンドラインを指定、およびその型のドキュメントを開くダイナミック データ エクス (チェンジ DDE) コマンドを指定します。  
  
 `EnableShellOpen` アプリケーションで、ユーザーが選択したファイルを開くには、ファイル エクスプ ローラーまたはファイル マネージャーから DDE コマンドを受け取るようにすることで、プロセスを完了します。  
  
 この自動登録のサポートで`CWinApp`アプリケーションを使用して .reg ファイルを出荷するまたは特殊なインストール作業を行う必要があります。  
  
 GDI + アプリケーションを初期化するかどうか (を呼び出して[GdiplusStartup](https://msdn.microsoft.com/library/ms534077)で、 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance)関数)、GDI + のバック グラウンド スレッドを抑制する必要があります。  
  
 これを行うことができます、 **SuppressBackgroundThread**のメンバー、 [GdiplusStartupInput](https://msdn.microsoft.com/library/ms534067)構造の**TRUE**です。 スレッド、バック グラウンド GDI + を抑制する場合、 **NotificationHook**と**NotificationUnhook**呼び出しが行われる直前に入力して、アプリケーションのメッセージ ループを終了します。 これらの呼び出しの詳細については、次を参照してください。 [GdiplusStartupOutput](https://msdn.microsoft.com/library/ms534068)です。 そのためを呼び出すことをおすすめ**GdiplusStartup**フック通知関数は仮想関数のオーバーライドで、 [:run](../mfc/reference/cwinapp-class.md#run)次のように。  
  
 [!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]  
  
 場合は、バック グラウンド スレッド GDI + を抑制しないでください DDE コマンド処理の途中でに発行できるアプリケーションのメイン ウィンドウが作成される前にします。 シェルによって発行された DDE コマンド処理の途中で中止できます、エラー メッセージします。  
  
##  <a name="_core_file_manager_drag_and_drop"></a> ファイル マネージャーでのドラッグ アンド ドロップ  
 ファイルは、ファイル マネージャーまたはファイル エクスプ ローラーで、ファイル ビュー ウィンドウから、アプリケーションのウィンドウにドラッグできます。 アプリケーションでしたファイル名を取得し、それらのファイルの MDI 子ウィンドウを開く場所 MDI アプリケーションのメイン ウィンドウにドラッグできる 1 つまたは複数のファイルを有効にすることがありますなど。  
  
 ファイルのドラッグを有効にし、アプリケーションの削除、MFC アプリケーション ウィザードがへの呼び出しを書き込み、 [CWnd](../mfc/reference/cwnd-class.md)メンバー関数は、 [DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles)でメイン フレーム ウィンドウの`InitInstance`です。 ドラッグ アンド ドロップ機能を実装したくない場合は、その呼び出しを削除できます。  
  
> [!NOTE]
>  一般的なドラッグ アンド ドロップ機能を実装することもできます。-データ間またはドキュメント内でのドラッグ — ole です。 については、記事を参照してください。[ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)です。  
  
##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> 最近使ったドキュメントのほとんどの追跡  
 ように、ユーザーは、開くし、ファイルを閉じ、アプリケーション オブジェクトの追跡、4 つの最近使用したファイルです。 これらのファイルの名前が [ファイル] メニューに追加され、変更されるときに更新します。 フレームワークは、レジストリまたは .ini ファイルに、プロジェクトと同じ名前で、これらのファイル名を格納し、アプリケーションの起動時にファイルを読み取るにします。 `InitInstance`オーバーライドへの呼び出しが含まれていますが、MFC アプリケーション ウィザードが作成される、 [CWinApp](../mfc/reference/cwinapp-class.md)メンバー関数は、 [LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings)情報をレジストリまたは .ini からが読み込まれますファイルは、最もを最近などファイル名を使用します。  
  
 これらのエントリは、次のように格納されます。  
  
-   Windows NT、2000、およびそれ以降、Windows のレジストリ キー値が格納されます。  
  
-   Windows 3.x、値は、WIN に格納します。INI ファイルです。  
  
-   Windows 95 以降では、値は、WIN のキャッシュされたバージョンに格納されます。INI です。  
  
## <a name="see-also"></a>関連項目  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)