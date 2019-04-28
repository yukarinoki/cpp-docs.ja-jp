---
title: CWinApp のその他のサービス
ms.date: 11/04/2016
f1_keywords:
- LoadStdProfileSettings
- EnableShellOpen
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
ms.openlocfilehash: 910660253c9d306b13294a710021a6bbd36c1952
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307316"
---
# <a name="special-cwinapp-services"></a>CWinApp のその他のサービス

メッセージ ループの実行をアプリケーションの初期化し、その後、クリーンアップする機会を提供することだけでなく[CWinApp](../mfc/reference/cwinapp-class.md)いくつかのサービスを提供します。

##  <a name="_core_shell_registration"></a> シェル登録

MFC アプリケーション ウィザードは既定では、により、ユーザーはファイル エクスプ ローラーまたはファイル マネージャーでダブルクリックして、作成したアプリケーション データ ファイルを開きます。 MFC アプリケーション ウィザードが呼び出しを追加するアプリケーションが MDI アプリケーションであり、アプリケーションが作成されるファイルの拡張子を指定する場合、 [RegisterShellFileTypes](../mfc/reference/cwinapp-class.md#registershellfiletypes)と[EnableShellOpen](../mfc/reference/cwinapp-class.md#enableshellopen)のメンバー関数[CWinApp](../mfc/reference/cwinapp-class.md)を`InitInstance`書き込みを上書きします。

`RegisterShellFileTypes` ファイル エクスプ ローラーまたはファイル マネージャーで、アプリケーションのドキュメントの種類を登録します。 関数は、Windows を管理する登録データベースにエントリを追加します。 エントリは、各ドキュメントの種類を登録、ファイル拡張子をファイルの種類に関連付けるし、アプリケーションを開くためのコマンドラインを指定したうえで、その種類のドキュメントを開くダイナミック データ エクス (チェンジ DDE) コマンドを指定します。

`EnableShellOpen` DDE コマンドをユーザーが選択したファイルを開くには、ファイル エクスプ ローラーまたはファイル マネージャーから受信するアプリケーションを許可することで、プロセスを完了します。

この自動登録のサポートで`CWinApp`.reg ファイルは、アプリケーションと共に出荷するまたは特殊なインストール作業を行う必要がなくなります。

アプリの GDI + を初期化するかどうか (呼び出して[GdiplusStartup](/windows/desktop/api/gdiplusinit/nf-gdiplusinit-gdiplusstartup)で、 [InitInstance](../mfc/reference/cwinapp-class.md#initinstance)関数)、GDI + のバック グラウンド スレッドを抑制する必要があります。

設定してこれを行う、`SuppressBackgroundThread`のメンバー、 [GdiplusStartupInput](/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupinput)構造体を**TRUE**します。 ときに、スレッドがバック グラウンド GDI + の抑制、`NotificationHook`と`NotificationUnhook`呼び出しが行われる直前に入力し、アプリケーションのメッセージ ループを終了します。 これらの呼び出しの詳細については、次を参照してください。 [GdiplusStartupOutput](/windows/desktop/api/gdiplusinit/ns-gdiplusinit-gdiplusstartupoutput)します。 そのため、適してを呼び出す`GdiplusStartup`フックの通知関数は仮想関数のオーバーライドでは[使わ](../mfc/reference/cwinapp-class.md#run)以下に示すように。

[!code-cpp[NVC_MFCDocView#6](../mfc/codesnippet/cpp/special-cwinapp-services_1.cpp)]

場合は、バック グラウンド スレッド GDI + を抑制しないでください DDE コマンド処理の途中で実行できるアプリケーションにメイン ウィンドウが作成される前に。 シェルによって発行された DDE コマンドことができますが途中で中止、エラー メッセージします。

##  <a name="_core_file_manager_drag_and_drop"></a> ファイル マネージャーでのドラッグ アンド ドロップ

ファイルは、ファイル マネージャーまたはファイル エクスプ ローラーで、ファイル ビュー ウィンドウから、アプリケーションのウィンドウにドラッグできます。 アプリケーションでしたファイル名を取得し、それらのファイルの MDI 子ウィンドウを開き、MDI アプリケーションのメイン ウィンドウにドラッグする 1 つまたは複数のファイルなどを有効にする場合があります。

ファイルのドラッグを有効にし、アプリケーションの削除、MFC アプリケーション ウィザードがへの呼び出しを書き込みます、 [CWnd](../mfc/reference/cwnd-class.md)メンバー関数は[DragAcceptFiles](../mfc/reference/cwnd-class.md#dragacceptfiles)でメイン フレーム ウィンドウ、`InitInstance`します。 ドラッグ アンド ドロップ機能を実装する必要がない場合は、その呼び出しを削除できます。

> [!NOTE]
>  全般的なドラッグ アンド ドロップ機能を実装することもできます。- またはドキュメント内の間でデータをドラッグする — ole します。 については、この記事を参照してください。[ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)します。

##  <a name="_core_keeping_track_of_the_most_recently_used_documents"></a> 最近使ったドキュメントのほとんどの管理

ように、ユーザーは、開くし、ファイルを閉じ、アプリケーション オブジェクトの追跡、4 つの最近使用したファイル。 これらのファイル名では、ファイル メニューに追加され、変更するときに更新します。 フレームワークは、レジストリまたは .ini ファイルに、プロジェクトと同じ名前では、これらのファイル名を格納しに、アプリケーションの起動時に、ファイルから読み取らします。 `InitInstance`オーバーライドへの呼び出しを含む MFC アプリケーション ウィザードが作成される、 [CWinApp](../mfc/reference/cwinapp-class.md)メンバー関数は[LoadStdProfileSettings](../mfc/reference/cwinapp-class.md#loadstdprofilesettings)情報をレジストリまたは .ini からが読み込まれますファイルには、ファイル名を使用群など。

これらのエントリは、次のように格納されます。

- Windows nt、Windows 2000、およびそれ以降、レジストリ キー値が格納されます。

- Windows で勝利に 3.x、値が格納されます。INI ファイルです。

- Windows 95 以降では、値は、WIN のキャッシュされたバージョンに格納されます。INI します。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
