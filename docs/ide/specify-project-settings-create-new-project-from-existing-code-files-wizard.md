---
title: 既存コード ファイル ウィザードから新しいプロジェクトを作成するプロジェクト設定の指定 |Microsoft ドキュメント
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
ms.openlocfilehash: f0f59b802b5a24c1b449f78cccee4744538a5a0e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="specify-project-settings-create-new-project-from-existing-code-files-wizard"></a>[プロジェクト設定の指定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)
指定するには、既存のコード ファイルからの新しいプロジェクトの作成ウィザードのこのページを使用します。  
  
-   新しいプロジェクトのビルド環境  
  
-   ビルドを生成する新しいプロジェクトの特定の種類に一致する設定  
  
## <a name="task-list"></a>タスク一覧  
 [方法 : 既存のコードから C++ プロジェクトを作成する](../ide/how-to-create-a-cpp-project-from-existing-code.md)  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **Visual Studio の使用**  
 新しいプロジェクトを作成するための Visual Studio に含まれているビルド ツールを使用して指定します。 既定では、このオプションはオンです。  
  
 **プロジェクトの種類**  
 ウィザードにより生成されるプロジェクトの種類を指定します。  
  
 **Windows アプリケーション プロジェクト**  
 ウィザードが実行可能な Windows アプリケーション用のプロジェクトを生成することを示します。 このオプションはから利用可能な**プロジェクトの種類**ドロップダウン リスト ボックス。  
  
 **コンソール アプリケーション プロジェクト**  
 ウィザードはコンソール アプリケーション用のプロジェクトを生成することを示します。 このオプションはから利用可能な**プロジェクトの種類**ドロップダウン リスト ボックス。  
  
 **ダイナミック リンク ライブラリ (DLL) プロジェクト**  
 ウィザードで空のダイナミック リンク ライブラリ アプリケーション用のプロジェクトを生成することを示します。 このオプションはから利用可能な**プロジェクトの種類**ドロップダウン リスト ボックス。  
  
 **スタティック ライブラリ (LIB) プロジェクト**  
 ウィザードが、スタティック ライブラリ アプリケーション用のプロジェクトを生成することを示します。 このオプションはから利用可能な**プロジェクトの種類**ドロップダウン リスト ボックス。  
  
 **ATL のサポートを追加します。**  
 新しいプロジェクトに ATL サポートを追加します。  
  
 **MFC のサポートを追加します。**  
 新しいプロジェクトに MFC サポートを追加します。  
  
 **共通言語ランタイムのサポートを追加します。**  
 CLR プログラミングの新しいプロジェクトに、サポートを追加します。  
  
 **共通言語ランタイム**  
 CLR 機能に準拠する新しいプロジェクトを指定します。  
  
 **共通言語ランタイム (古い構文)**  
 Visual C 2005 より前の CLR プログラミングの構文は、C++ 構文のマネージ拡張に準拠する新しいプロジェクトを指定します。  
  
 **外部ビルド システムを使用します。**  
 含まれていない Visual Studio で新しいプロジェクトのビルドのビルド ツールを使用するように指定します。 ビルドのコマンドラインを指定するには、このオプションを選択すると、**デバッグの構成設定の指定**と**リリース構成設定の指定**ページ。  
  
> [!NOTE]
>  ときに、**外部ビルド システムを使用して**オプションがオンになって、IDE は、新しいプロジェクトをビルドしていないため、/D、すれば、/FI、/AI、または/FU オプションはコンパイルに必要です。 ただし、これらのオプションは、IntelliSense が正常に機能するために正しく設定する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [デバッグ構成の設定を指定して、既存のコード ファイル ウィザードから新しいプロジェクトの作成](../ide/specify-debug-configuration-settings.md)   
 [[リリースの構成の設定] (既存コード ファイルからの新しいプロジェクトの作成ウィザード)](../ide/specify-release-configuration.md)