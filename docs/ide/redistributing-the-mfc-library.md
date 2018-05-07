---
title: MFC ライブラリの再配布 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a49bf18721f605abe0c6e496d3532012c9c92c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-the-mfc-library"></a>MFC ライブラリの再配布
アプリケーションを MFC ライブラリを動的にリンクする場合は、一致する MFC DLL を再配布する必要があります。 たとえば、MFC アプリが Visual Studio 2015 に同梱されている MFC のバージョンを使用して組み込まれている場合必要があります再配布する mfc140.dll または mfc140u.dll、ナロー文字または Unicode のサポート用にアプリをコンパイルするかどうかによって異なります。  
  
> [!NOTE]
>  Mfc140.dll ファイルは、Visual Studio 2015 RTM で再頒布可能ファイルのディレクトリから省略されました。 Windows \system32 と Windows\syswow64 ディレクトリに代わりに Visual Studio 2015 でインストールのバージョンを使用することができます。  
  
 すべての MFC Dll は、C ランタイム ライブラリ (CRT) の共有バージョンを使用するため、CRT を再配布する必要もあります。 Visual Studio 2015 に付属する MFC のバージョンでは、Windows 10 の一部として配布される、ユニバーサル CRT ライブラリを使用します。 以前のバージョンの Windows で Visual Studio 2015 を使用してビルドされた MFC アプリケーションを実行するには、ユニバーサル CRT を再配布する必要があります。 オペレーティング システム コンポーネントとして、またはローカル配置を使用して、ユニバーサル CRT を再配布する方法については、次を参照してください。 [Universal CRT を導入](http://go.microsoft.com/fwlink/p/?linkid=617977)です。 一元的な展開でサポートされているバージョンの Windows のユニバーサル CRT をダウンロードするを参照してください。 [Windows 10 の Universal C Runtime](http://go.microsoft.com/fwlink/p/?LinkId=619489)です。 Windows SDK のローカル展開 ucrtbase.dll の再頒布可能パッケージ アーキテクチャ固有のバージョンはあります。 既定では、Visual Studio は、C:\Program Files (x86) \Windows Kits\10\Redist\ucrt\DLLs\ でこれらをアーキテクチャ固有のサブディレクトリにインストールします。  
  
 アプリが以前のバージョンの MFC ライブラリを使用して組み込まれている場合は、再頒布可能ファイルのディレクトリから一致する CRT DLL を再配布する必要があります。 たとえば、MFC アプリケーションが Visual Studio 2013 (vc120) ツールセットを使用して組み込まれている場合、msvcr120.dll を再配布する必要があります。 一致する mfc の再配布する必要があるも`<version>`u.dll または mfc`<version>`.dll です。  
  
 アプリケーションを MFC を静的にリンクする場合 (を指定する場合は、**スタティック ライブラリで MFC を使用する**上、**全般** タブで、**プロパティ ページ** ダイアログ ボックス)、することはありませんMFC DLL を再配布します。 静的リンクはアプリケーションのテストや内部での配置を行う場合でも該当しますが、MFC の再配布にはそれを使用しないことをお勧めします。 Visual C ライブラリを展開するための推奨される方法の詳細については、次を参照してください。[配置方法の選択](../ide/choosing-a-deployment-method.md)です。  
  
 アプリケーションで WebBrowser コントロールを実装する MFC クラスを使用するかどうか (たとえば、 [CHtmlView クラス](../mfc/reference/chtmlview-class.md)または[CHtmlEditView クラス](../mfc/reference/chtmleditview-class.md)) の最新バージョンをインストールすることをお勧めします。Microsoft Internet Explorer を対象となるコンピューターが最新の共通のコントロール ファイルを保持するようです。 (少なくとも、Internet Explorer 4.0 以降が必要です)。Internet Explorer コンポーネントの最小インストールの方法については、マイクロソフト サポート オンラインの 「Article 185375: How To Create a Single EXE Install of Internet Explorer (記事 185375: Internet Explorer のインストール ファイルである単一の exe ファイルの作成方法)」を参照してください。  
  
 アプリケーションは、MFC データベース クラスを使用する場合 (たとえば、 [CRecordset クラス](../mfc/reference/crecordset-class.md)と[CRecordView クラス](../mfc/reference/crecordview-class.md))、ODBC と ODBC ドライバー、アプリケーションが使用する再配布する必要があります。 詳細については、次を参照してください。[データベース サポート ファイルの再配布](../ide/redistributing-database-support-files.md)です。  
  
 MFC アプリケーションが Windows フォーム コントロールを使用している場合は、アプリケーションと共に mfcmifc80.dll を再配布する必要があります。 この DLL は、そのアプリケーションのローカル フォルダーまたはを使用してグローバル アセンブリ キャッシュ (GAC) に展開することで、アプリケーションと共に再配布できる厳密名署名の .NET アセンブリ、 [Gacutil.exe (グローバル アセンブリ キャッシュ ツール)](/dotnet/framework/tools/gacutil-exe-gac-tool)です。  
  
 MFC DLL を再配布する場合は、デバッグ バージョンではなく、リテール バージョンを再配布することを確認してください。 DLL のデバッグ バージョンは再配布できません。 MFC Dll のデバッグ バージョンの名前が付いて、"d"、たとえば、Mfc140d.dll です。  
  
 いずれかの vcredist _ を使用して、再配布する MFC*アーキテクチャ*.exe、Visual Studio を使用または MFC DLL をアプリケーションと同じフォルダーに配置することによってインストールされているマージ モジュール。 MFC の再配布する方法の詳細については、次を参照してください。 [Visual c ファイルの再配布](../ide/redistributing-visual-cpp-files.md)です。  
  
## <a name="installation-of-localized-mfc-components"></a>テクニカル ノート 56: ローカライズされた MFC コンポーネントのインストール  
 MFC ローカリゼーション DLL をインストールしてアプリケーションをローカライズする場合は、再頒布可能マージ ファイル (.msm) を使用する必要があります。 例では、x86 アプリケーションをローカライズする場合のコンピューター、Microsoft_VC をマージする必要があります`<version>`x86 のインストール パッケージに _MFCLOC_x86.msm コンピューター。  
  
 再頒布可能 .msm ファイルには、ローカライズに使用される DLL が含まれます。 サポートされているそれぞれの言語に対して、1 つの DLL があります。 これらの DLL は、インストール プロセスによって、ターゲット コンピューターの %windir%\system32\ フォルダーにインストールされます。  
  
 MFC アプリケーションをローカライズする方法の詳細については、次を参照してください。 [TN057: MFC コンポーネントのローカライズ](../mfc/tn057-localization-of-mfc-components.md)、も[記事 208983: MFC LOC Dll を使用する方法](http://go.microsoft.com/fwlink/p/?linkid=198025)、Microsoft サポート web サイトです。  
  
 MFC のローカライズ用 DLL を再配布するには、MFC DLL をアプリケーションのローカル フォルダーに配置します。 Visual C ライブラリを再配布する方法の詳細については、次を参照してください。 [Visual c ファイルの再配布](../ide/redistributing-visual-cpp-files.md)です。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)