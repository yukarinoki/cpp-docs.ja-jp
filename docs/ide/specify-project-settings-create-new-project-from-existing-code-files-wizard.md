---
title: '[プロジェクト設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.importwiz.appsettings
dev_langs:
- C++
helpviewer_keywords:
- Create New Project From Existing Code Files Wizard, project settings
ms.assetid: 9b8860c9-d35f-4f18-9565-2934d3d7f569
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a75bb6034c8f4c5a80bb64238c26ea599395ff96
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705616"
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>[プロジェクト設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)
既存コード ファイルからの新しいプロジェクトの作成ウィザードのこのページを使用して、以下を指定します。  
  
-   新しいプロジェクトのビルド環境  
  
-   生成する新しいプロジェクトの特定の種類に合わせたビルド設定  
  
## <a name="task-list"></a>タスク一覧  

[方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement の一覧  
- **Visual Studio を使用する**

   新しいプロジェクトをビルドするため、Visual Studio に含まれているビルド ツールを使用するように指定します。 既定では、このオプションはオンです。  
  
- **プロジェクトの種類**

   ウィザードにより生成されるプロジェクトの種類を指定します。  
  
- **Windows アプリケーション プロジェクト**

   ウィザードが実行可能な Windows アプリケーション用にプロジェクトを生成することを示します。 このオプションは **[プロジェクトの種類]** ドロップダウン リスト ボックスから使用できます。  
  
- **コンソール アプリケーション プロジェクト**

   ウィザードがコンソール アプリケーション用にプロジェクトを生成することを示します。 このオプションは **[プロジェクトの種類]** ドロップダウン リスト ボックスから使用できます。  
  
- **ダイナミック リンク ライブラリ (DLL) プロジェクト**

   ウィザードが空のダイナミック リンク ライブラリ アプリケーション用にプロジェクトを生成することを示します。 このオプションは **[プロジェクトの種類]** ドロップダウン リスト ボックスから使用できます。  
  
- **スタティック ライブラリ (LIB) プロジェクト**

   ウィザードがスタティック ライブラリ アプリケーション用にプロジェクトを生成することを示します。 このオプションは **[プロジェクトの種類]** ドロップダウン リスト ボックスから使用できます。  
  
- **ATL のサポートの追加**

   新しいプロジェクトに ATL サポートを追加します。  
  
- **MFC のサポートの追加**

   新しいプロジェクトに MFC サポートを追加します。  
  
- **共通言語ランタイムのサポートの追加**

   新しいプロジェクトに CLR プログラミングのサポートを追加します。  
  
- **共通言語ランタイム**

   CLR 機能に準拠する新しいプロジェクトを指定します。  
  
- **共通言語ランタイム (古い構文)**

   Managed Extensions for C++ 構文 (Visual C++ 2005 より前の CLR プログラミング構文) に準拠する新しいプロジェクトを指定します。  
  
- **外部のビルドシステムを使用する**

   新しいプロジェクトをビルドするため、Visual Studio に含まれていないビルド ツールを使用するように指定します。 このオプションを選択すると、**[デバッグの構成設定の指定]** ページと **[リリースの構成設定の指定]** ページでビルドのコマンド ラインを指定できます。  
  
   > [!NOTE]
   > **[外部のビルドシステムを使用する]** オプションがオンになっていると、IDE が新しいプロジェクトをビルドしないため、コンパイルに /D、/I、/FI、/AI、または /FU オプションは必要ありません。 ただし、IntelliSense が正常に機能するためには、これらのオプションを正しく設定する必要があります。  
  
## <a name="see-also"></a>参照  
 [[デバッグ構成の設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-debug-configuration-settings.md)   
 [[リリースの構成の設定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-release-configuration.md)