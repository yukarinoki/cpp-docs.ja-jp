---
title: '[高度な機能]\ (MFC アプリケーション ウィザード)'
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.advanced
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
ms.openlocfilehash: 44d85e7614f6a82af2e58f03a6d65d5d7740ab9b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816439"
---
# <a name="advanced-features-mfc-application-wizard"></a>[高度な機能]\ (MFC アプリケーション ウィザード)

このトピックでは、ヘルプや印刷サポートなど、アプリケーションの追加機能のためのオプションを示します。 各セクションで、これらの高度な機能の追加サポートを指定します。

- **状況依存のヘルプ (HTML)**

   F1 とヘルプ メニューを使用して、またはをクリックして利用できる状況依存のヘルプのヘルプ ファイルのセットを生成、**ヘルプ** ダイアログ ボックスのボタン。 ヘルプ サポートにはヘルプ コンパイラが必要です。 ヘルプ コンパイラがない場合は、セットアップを再実行することによってインストールできます。

   参照してください[HTML ヘルプ。プログラムの状況依存のヘルプ](../../mfc/html-help-context-sensitive-help-for-your-programs.md)と[ヘルプ ファイル (HTML ヘルプ)](../../build/reference/help-files-html-help.md)詳細についてはします。

- **印刷と印刷プレビュー**

   メンバー関数を呼び出すことによって、設定、および印刷プレビュー コマンドを印刷、印刷を処理するコードを生成、 [CView クラス](../../mfc/reference/cview-class.md)MFC ライブラリから。 これらの関数に対するコマンドも、ウィザードによってアプリケーションのメニューに追加されます。 印刷サポートは指定されたアプリケーションでのみ使用できます**ドキュメント/ビュー アーキテクチャ サポート**で、[アプリケーションの種類、MFC アプリケーション ウィザード](../../mfc/reference/application-type-mfc-application-wizard.md)ウィザードのページ。 既定では、ドキュメント/ビュー アプリケーションには印刷サポートが含まれます。

- **オートメーション**

   アプリケーションが別のアプリケーションに実装されているオブジェクトを操作したり、アプリケーションをオートメーション クライアントに公開したりできるように指定します。

- **ActiveX コントロール**

   ActiveX コントロールをサポートします (既定値)。 このオプションを選択せず、後で、プロジェクトに ActiveX コントロールを挿入する場合は場合にへの呼び出しを追加する必要があります[AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer)アプリケーションの[:initinstance](../../mfc/reference/cwinapp-class.md#initinstance)メンバー関数。

- **MAPI (メッセージ API)**

   アプリケーションでメール メッセージの作成、操作、転送、および格納ができるように指定します。

- **Windows ソケット**

   TCP/IP ネットワークで通信するアプリケーションを作成するために使用できる Windows ソケットをサポートします。

- **Active Accessibility**

   サポートが追加されて[IAccessible](/windows/desktop/api/oleacc/nn-oleacc-iaccessible)に[CWnd](../../mfc/reference/cwnd-class.md)-派生クラスで、操作性が向上ユーザー補助クライアント ユーザー インターフェイスのカスタマイズに使用できます。

- **コモン コントロール マニフェスト**

   既定で有効になります。 Microsoft Windows XP 以降のオペレーティング システムに同梱されているコモン コントロール DLL を使用するためのアプリケーション マニフェストを生成します。

   既存のアプリケーションで使用されている以前のバージョンのコモン コントロールが、Version 6 のコモン コントロール DLL によって自動的に更新されることはありません。 Version 6 のコモン コントロール DLL を使用するには、アプリケーションが DLL を読み込むことができるようにするためのアプリケーション マニフェストを作成する必要があります。 Version 6 のコモン コントロール DLL は、Windows XP のテーマもサポートしています。

   また、アプリケーション マニフェストによって、アプリケーションに必要なその他の DLL やその他のバージョンも指定できます。 アプリケーション マニフェストの詳細については、次を参照してください。[分離アプリケーションとサイド バイ サイド アセンブリ](/windows/desktop/SbsCs/isolated-applications-and-side-by-side-assemblies-portal)Windows SDK に含まれています。

- **再起動マネージャーのサポート**

   サポートが追加されて、 [Windows 再起動マネージャー](/windows/desktop/RstMgr/using-restart-manager)します。 このビデオでは、MFC から再起動マネージャーを使用する方法を示します。[How Do i:新しい再起動マネージャーを使用して、](/previous-versions/visualstudio/visual-studio-2010/dd831853(v%3dvs.100))します。

- **高度なフレーム ペイン**

   |オプション|説明|
   |------------|-----------------|
   |**エクスプ ローラーのドッキング ペイン**|Visual Studio のようなドッキング ペインを作成します**ソリューション エクスプ ローラー**メイン フレーム ウィンドウの左側にします。|
   |**ドッキングのフレームの出力**|Visual Studio のようなドッキング ペインを作成します**出力**メイン フレーム ウィンドウの下にあるウィンドウ。|
   |**ウィンドウをドッキング可能なプロパティ**|Visual Studio のようなドッキング ペインを作成します**プロパティ**メイン フレーム ウィンドウの右側のウィンドウ。|
   |**ナビゲーション ウィンドウ**|メイン フレーム ウィンドウの左側に、Outlook のナビゲーション バーのようなドッキング ペインを作成します。|
   |**キャプション バー**|メイン フレーム ウィンドウの上に、Office 形式のキャプション バーを作成します。|

- **最近使ったファイルのファイルの数**

   最近使ったファイルの一覧に表示するファイル数を指定します。 既定値は 4 です。

## <a name="see-also"></a>関連項目

[MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)
