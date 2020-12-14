---
description: 詳細については、「高度な機能」、「MFC アプリケーションウィザード」を参照してください。
title: '[高度な機能] (MFC アプリケーション ウィザード)'
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.advanced
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
ms.openlocfilehash: f709f933549c9cc1aa4a53a361682f1c444bbcbf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248256"
---
# <a name="advanced-features-mfc-application-wizard"></a>[高度な機能] (MFC アプリケーション ウィザード)

このトピックでは、ヘルプや印刷サポートなど、アプリケーションの追加機能のためのオプションを示します。 各セクションで、これらの高度な機能の追加サポートを指定します。

- **状況依存のヘルプ (HTML)**

   F1 とヘルプメニューを使用するか、ダイアログボックスの [ **ヘルプ** ] ボタンをクリックして、状況依存のヘルプ用のヘルプファイルのセットを生成します。 ヘルプ サポートにはヘルプ コンパイラが必要です。 ヘルプ コンパイラがない場合は、セットアップを再実行することによってインストールできます。

   詳細については [、「Html ヘルプ: プログラムおよびヘルプファイルの Context-Sensitive ヘルプ](../../mfc/html-help-context-sensitive-help-for-your-programs.md) [(html ヘルプ)](../../build/reference/help-files-html-help.md) 」を参照してください。

- **印刷および印刷プレビュー**

   MFC ライブラリから [CView クラス](../../mfc/reference/cview-class.md) のメンバー関数を呼び出すことによって、印刷、印刷設定、および印刷プレビューのコマンドを処理するコードを生成します。 これらの関数に対するコマンドも、ウィザードによってアプリケーションのメニューに追加されます。 印刷のサポートは、ウィザードの [[アプリケーションの種類] の [MFC アプリケーションウィザード](../../mfc/reference/application-type-mfc-application-wizard.md)] ページで、**ドキュメント/ビューアーキテクチャのサポート** を指定するアプリケーションでのみ使用できます。 既定では、ドキュメント/ビュー アプリケーションには印刷サポートが含まれます。

- **Automation**

   アプリケーションが別のアプリケーションに実装されているオブジェクトを操作したり、アプリケーションをオートメーション クライアントに公開したりできるように指定します。

- **ActiveX コントロール**

   ActiveX コントロールをサポートします (既定値)。 このオプションを選択せず、後で ActiveX コントロールをプロジェクトに挿入する場合は、アプリケーションの[CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance)メンバー関数で[AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer)の呼び出しを追加する必要があります。

- **MAPI (メッセージング API)**

   アプリケーションでメール メッセージの作成、操作、転送、および格納ができるように指定します。

- **Windows ソケット**

   TCP/IP ネットワークで通信するアプリケーションを作成するために使用できる Windows ソケットをサポートします。

- **Active Accessibility**

   [IAccessible](/windows/win32/api/oleacc/nn-oleacc-iaccessible)のサポートを[CWnd](../../mfc/reference/cwnd-class.md)の派生クラスに追加します。これを使用すると、ユーザー補助クライアントとの対話性を高めるために、ユーザーインターフェイスをカスタマイズできます。

- **[コモン コントロール マニフェスト]**

   既定で有効です。 Microsoft Windows XP 以降のオペレーティング システムに同梱されているコモン コントロール DLL を使用するためのアプリケーション マニフェストを生成します。

   既存のアプリケーションで使用されている以前のバージョンのコモン コントロールが、Version 6 のコモン コントロール DLL によって自動的に更新されることはありません。 Version 6 のコモン コントロール DLL を使用するには、アプリケーションが DLL を読み込むことができるようにするためのアプリケーション マニフェストを作成する必要があります。 Version 6 のコモン コントロール DLL は、Windows XP のテーマもサポートしています。

   また、アプリケーション マニフェストによって、アプリケーションに必要なその他の DLL やその他のバージョンも指定できます。 アプリケーションマニフェストの詳細については、「Windows SDK での [分離アプリケーションと Side-by-side アセンブリ](/windows/win32/SbsCs/isolated-applications-and-side-by-side-assemblies-portal) 」を参照してください。

- **再起動マネージャーのサポート**

   [Windows 再起動マネージャー](/windows/win32/RstMgr/using-restart-manager)のサポートを追加します。 このビデオでは、MFC から再起動マネージャーを使用する方法について説明します。操作 [方法: 新しい再起動マネージャーを使用](/previous-versions/visualstudio/visual-studio-2010/dd831853(v%3dvs.100))します。

- **[高度なフレーム ペイン]**

   |オプション|説明|
   |------------|-----------------|
   |**[ドッキング可能なエクスプローラー ペイン]**|メインフレームウィンドウの左側にある Visual Studio **ソリューションエクスプローラー** に似たドッキングペインを作成します。|
   |**[ドッキング可能な出力ペイン]**|メインフレームウィンドウの下にある Visual Studio の **出力** ウィンドウに似たドッキングペインを作成します。|
   |**[ドッキング可能なプロパティ ペイン]**|メインフレームウィンドウの右側にある Visual Studio の **プロパティ** ペインに似たドッキングペインを作成します。|
   |**ナビゲーション ウィンドウ**|メイン フレーム ウィンドウの左側に、Outlook のナビゲーション バーのようなドッキング ペインを作成します。|
   |**[キャプション バー]**|メイン フレーム ウィンドウの上に、Office 形式のキャプション バーを作成します。|

- **[[最近使ったファイル] のファイル数]**

   最近使ったファイルの一覧に表示するファイル数を指定します。 既定値は 4 です。

## <a name="see-also"></a>関連項目

[MFC アプリケーションウィザード](../../mfc/reference/mfc-application-wizard.md)
