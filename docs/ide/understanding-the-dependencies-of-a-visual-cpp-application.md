---
title: Visual C++ アプリケーションの依存関係の理解
ms.date: 11/04/2016
helpviewer_keywords:
- application deployment [C++], dependencies
- Dependency Walker
- dependencies [C++], application deployment and
- deploying applications [C++], dependencies
- DUMPBIN utility
- DLLs [C++], dependencies
- depends.exe
- libraries [C++], application deployment issues
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
ms.openlocfilehash: 8ed340bed62d3b2cfcf32e0b98f032c9146b6bb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629269"
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Visual C++ アプリケーションの依存関係の理解

アプリケーションがどの Visual C++ ライブラリに依存しているかを確認するには、プロジェクトのプロパティを表示します  (ソリューション エクスプローラーでプロジェクトを右クリックし、**[プロパティ]** を選択して、**[プロパティ ページ]** ダイアログ ボックスを開きます)。また、Dependency Walker (depends.exe) を使用して、全体的な依存関係をより包括的に把握することもできます。

**[プロパティ ページ]** ダイアログ ボックスで、**[構成プロパティ]** にあるさまざまなページを確認して、依存関係を把握できます。 たとえば、プロジェクトで MFC ライブラリが使用されている状態で、**[構成プロパティ]**、**[全般]** ページで **[MFC の使用]**、**[共有 DLL で MFC を使う]** を選択した場合、実行時のアプリケーションは mfc\<バージョン>.dll などの MFC DLL に依存します。 アプリケーションで MFC が使用されていない状態で、**[構成プロパティ]**、**[C/C++]**、**[コード生成]** ページで **[ランタイム ライブラリ]** の値として **[マルチスレッド デバッグ DLL (/MDd)]** または **[マルチスレッド DLL (/MD)]** を選択した場合、そのアプリケーションは CRT ライブラリに依存する可能性があります。

アプリケーションが依存する DLL を確認する包括的な方法は、Dependency Walker (depends.exe) を使用してアプリケーションを開くことです。 このツールは [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640) の Web サイトからダウンロードできます。

depends.exe を使用すると、読み込み時にアプリケーションにリンクされた DLL の一覧と、遅延読み込みされた DLL の一覧を確認できます。 実行時に動的に読み込まれた DLL の完全な一覧を取得する必要がある場合は、depends.exe のプロファイル機能を使用して、すべてのコード パスが確実に実行されるまでアプリケーションをテストします。 プロファイル セッションを終了すると、実行時に動的に読み込まれた DLL が表示されます。

depends.exe を使用する場合は、DLL が、他の DLL や特定の DLL バージョンに依存している場合があることに注意してください。 depends.exe は、開発用コンピューターとターゲット コンピューターのどちらでも使用できます。 開発用コンピューターでは、アプリケーションのサポートに必要な DLL を報告します。 ターゲット コンピューターでアプリケーションを実行できない場合は、必要な DLL が見つからないのか、不適切なのかを判断できるように、depends.exe をターゲット コンピューターにコピーして、ツールでアプリケーションを開きます。

アプリケーションが依存する DLL がわかったら、アプリケーションを別のコンピューターに配置するときに共に再頒布する必要がある DLL を判断できます。 ほとんどの場合、システム DLL を再配布する必要はありませんが、Visual C++ ライブラリの DLL の再配布が必要である可能性があります。 詳細については、「[再配布する DLL の決定](../ide/determining-which-dlls-to-redistribute.md)」を参照してください。

## <a name="see-also"></a>参照

[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)