---
title: Visual C アプリケーションの依存関係を理解する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da2aadeba69a8be29627650ba6ef24516098a8e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="understanding-the-dependencies-of-a-visual-c-application"></a>Visual C++ アプリケーションの依存関係の理解
アプリケーションに依存する Visual C ライブラリを確認するのには、プロジェクトのプロパティを表示できます。 (ソリューション エクスプ ローラーでプロジェクトを右クリックして選択**プロパティ**を開くには、**プロパティ ページ** ダイアログ ボックス)。また、Dependency Walker (depends.exe) を使用して、全体的な依存関係をより包括的に把握することもできます。  
  
 **プロパティ ページ** ダイアログ ボックスの下のさまざまなページを調べることができます**構成プロパティ**依存関係を理解します。 例では、プロジェクトで MFC ライブラリを使用し、選択した場合の**の MFC を使用する**、**共有 DLL で MFC を使用する**上、**構成プロパティ**、**全般**  ページで、実行時に依存するアプリケーション MFC Dll mfc など\<バージョン > .dll です。 アプリケーションで MFC を使用していない場合、依存 CRT ライブラリを選択した場合、**ランタイム ライブラリ**値**マルチ スレッド デバッグ DLL (/MDd)** または**マルチ スレッド DLL (/MD)** 上、**構成プロパティ**、 **C/C++**、**コード生成**ページ。  
  
 アプリケーションが依存する DLL を確認する包括的な方法は、Dependency Walker (depends.exe) を使用してアプリケーションを開くことです。 ツールをダウンロードすることができます、 [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640) web サイトです。  
  
 depends.exe を使用すると、読み込み時にアプリケーションにリンクされた DLL の一覧と、遅延読み込みされた DLL の一覧を確認できます。 実行時に動的に読み込まれた DLL の完全な一覧を取得する必要がある場合は、depends.exe のプロファイル機能を使用して、すべてのコード パスが確実に実行されるまでアプリケーションをテストします。 プロファイル セッションを終了すると、実行時に動的に読み込まれた DLL が表示されます。  
  
 depends.exe を使用する場合は、DLL が、他の DLL や特定の DLL バージョンに依存している場合があることに注意してください。 depends.exe は、開発用コンピューターとターゲット コンピューターのどちらでも使用できます。 開発用コンピューターでは、アプリケーションのサポートに必要な DLL を報告します。 ターゲット コンピューターでアプリケーションを実行できない場合は、必要な DLL が見つからないのか、不適切なのかを判断できるように、depends.exe をターゲット コンピューターにコピーして、ツールでアプリケーションを開きます。  
  
 アプリケーションが依存する DLL がわかったら、アプリケーションを別のコンピューターに配置するときに共に再頒布する必要がある DLL を判断できます。 ほとんどの場合、システム Dll を再配布する必要はありませんが、Visual C ライブラリ Dll を再配布する必要があります。 詳細については、次を参照してください。[再配布する Dll の決定](../ide/determining-which-dlls-to-redistribute.md)です。  
  
## <a name="see-also"></a>関連項目  
 [デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)