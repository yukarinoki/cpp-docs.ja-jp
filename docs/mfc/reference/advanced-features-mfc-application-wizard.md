---
title: 拡張機能、MFC アプリケーション ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.advanced
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5094c18f72182929565e7c23c38b63443839da1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="advanced-features-mfc-application-wizard"></a>[高度な機能]\ (MFC アプリケーション ウィザード)
このトピックでは、ヘルプや印刷サポートなど、アプリケーションの追加機能のためのオプションを示します。 各セクションで、これらの高度な機能の追加サポートを指定します。  
  
 **状況依存のヘルプ (HTML)**  
 状況依存のヘルプ、f1 キーと、ヘルプ メニューを使用して、またはをクリックして利用可能なヘルプ ファイルのセットを生成、**ヘルプ** ダイアログ ボックスにボタンをクリックします。 ヘルプ サポートにはヘルプ コンパイラが必要です。 ヘルプ コンパイラがない場合は、セットアップを再実行することによってインストールできます。  
  
 参照してください[HTML ヘルプ: プログラムの状況依存のヘルプ](../../mfc/html-help-context-sensitive-help-for-your-programs.md)と[ヘルプ ファイル (HTML ヘルプ)](../../ide/help-files-html-help.md)詳細についてはします。  
  
 **印刷と印刷プレビュー**  
 印刷と印刷プレビュー コマンド メンバー関数を呼び出すことによって、印刷を処理するコードを生成、 [CView クラス](../../mfc/reference/cview-class.md)MFC ライブラリからです。 これらの関数に対するコマンドも、ウィザードによってアプリケーションのメニューに追加されます。 印刷のサポートは指定しているアプリケーションに対してのみ使用可能な**ドキュメント/ビュー アーキテクチャ サポート**で、[アプリケーションの種類、MFC アプリケーション ウィザード](../../mfc/reference/application-type-mfc-application-wizard.md)ウィザードのページです。 既定では、ドキュメント/ビュー アプリケーションには印刷サポートが含まれます。  
  
 **オートメーション**  
 アプリケーションが別のアプリケーションに実装されているオブジェクトを操作したり、アプリケーションをオートメーション クライアントに公開したりできるように指定します。  
  
 **ActiveX コントロール**  
 ActiveX コントロールをサポートします (既定値)。 このオプションを選択しないで後で、プロジェクトに ActiveX コントロールを挿入して場合、への呼び出しを追加する必要があります[AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer)アプリケーションの[場合は](../../mfc/reference/cwinapp-class.md#initinstance)メンバー関数。  
  
 **MAPI (メッセージ API)**  
 アプリケーションでメール メッセージの作成、操作、転送、および格納ができるように指定します。  
  
 **Windows ソケット**  
 TCP/IP ネットワークで通信するアプリケーションを作成するために使用できる Windows ソケットをサポートします。  
  
 **Active Accessibility**  
 サポートが追加[IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466)に[CWnd](../../mfc/reference/cwnd-class.md)-派生クラスで、ユーザー補助クライアントと相互運用性ものユーザー インターフェイスのカスタマイズを行うこともできます。  
  
 **コモン コントロール マニフェスト**  
 既定で有効になります。 Microsoft Windows XP 以降のオペレーティング システムに同梱されているコモン コントロール DLL を使用するためのアプリケーション マニフェストを生成します。  
  
 既存のアプリケーションで使用されている以前のバージョンのコモン コントロールが、Version 6 のコモン コントロール DLL によって自動的に更新されることはありません。 Version 6 のコモン コントロール DLL を使用するには、アプリケーションが DLL を読み込むことができるようにするためのアプリケーション マニフェストを作成する必要があります。 Version 6 のコモン コントロール DLL は、Windows XP のテーマもサポートしています。  
  
 また、アプリケーション マニフェストによって、アプリケーションに必要なその他の DLL やその他のバージョンも指定できます。 アプリケーション マニフェストの詳細については、次を参照してください。[分離アプリケーションとサイド バイ サイド アセンブリ](http://msdn.microsoft.com/library/dd408052)Windows SDK に含まれています。  
  
 **再起動マネージャーのサポート**  
 サポートを追加、 [Windows 再起動マネージャー](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx)です。 このビデオは、MFC から再起動マネージャーを使用する方法を示します:[方法: 新しい再起動マネージャーを使用](http://msdn.microsoft.com/vstudio/ee886407)です。  
  
 **高度なフレーム ペイン**  
 |オプション|説明|  
|------------|-----------------|  
|**エクスプ ローラーのドッキング ウィンドウ**|Visual Studio のようなドッキング ペインを作成**ソリューション エクスプ ローラー**メイン フレーム ウィンドウの左側にします。|  
|**出力のドッキング フレーム**|Visual Studio のようなドッキング ペインを作成**出力**メイン フレーム ウィンドウの下にあるウィンドウです。|  
|**ウィンドウをドッキング可能なプロパティ**|Visual Studio のようなドッキング ペインを作成**プロパティ**メイン フレーム ウィンドウの右側のウィンドウ。|  
|**ナビゲーション ウィンドウ**|メイン フレーム ウィンドウの左側に、Outlook のナビゲーション バーのようなドッキング ペインを作成します。|  
|**キャプション バー**|メイン フレーム ウィンドウの上に、Office 形式のキャプション バーを作成します。|  
  
 **最近使ったファイルのファイルの数**  
 最近使ったファイルの一覧に表示するファイル数を指定します。 既定値は 4 です。  
  
## <a name="see-also"></a>関連項目  
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)

