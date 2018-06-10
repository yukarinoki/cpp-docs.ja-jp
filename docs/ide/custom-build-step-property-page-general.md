---
title: '[カスタム ビルド ステップ] プロパティ ページ: 全般 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs:
- C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d88bd738711058794a525217ba2640e8d52356d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "33325930"
---
# <a name="custom-build-step-property-page-general"></a>[カスタム ビルド ステップ] プロパティ ページ: 全般
プロジェクトにおけるプロジェクト構成とターゲット プラットフォームの組み合わせごとに、プロジェクトをビルドするときに実行するカスタム ステップを指定できます。  

このページの Linux バージョンについては、「[カスタム ビルド ステップのプロパティ (Linux C++)](../linux/prop-pages/custom-build-step-linux.md)」を参照してください。
  
## <a name="uielement-list"></a>UIElement の一覧  
 **コマンド ライン**  
 カスタム ビルド ステップによって実行されるコマンド。  
  
 **説明**  
 カスタム ビルド ステップを実行するときに表示されるメッセージ。  
  
 **出力**  
 カスタム ビルド ステップが生成する出力ファイル。 この設定は、インクリメンタル ビルドが正しく機能するために必要です。  
  
 **追加の依存ファイル**  
 カスタム ビルド ステップで使用する追加の入力ファイルの、セミコロンで区切られた一覧。  
  
 **[以後に実行] および [以前に実行]**  
 ビルド プロセスでカスタム ビルド ステップが実行されるタイミングを、表示されているターゲットを基準にして定義します。 最もよく表示されるターゲットは BuildGenerateSources、BuildCompile、および BuildLink です。これらはビルド プロセスの主なステップを表しています。 また、Midl、CLCompile、および Link もよく表示されるターゲットです。  
  
 [出力をコンテンツとして扱う]  
 このオプションは、.appx パッケージにすべてのコンテンツ ファイルが含まれるユニバーサル Windows プラットフォームまたは Windows Phone アプリに対してのみ意味を持ちます。  
  
### <a name="to-specify-a-custom-build-step"></a>カスタム ビルド ステップを指定するには  
  
1.  メニュー バーで、**[プロジェクト]**、**[プロパティ]** の順に選びます。 詳細については、「[プロジェクト プロパティの操作](../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **[プロパティ ページ]** ダイアログ ボックスで、**[構成プロパティ]**、**[カスタム ビルド ステップ]**、**[全般]** ページの順に移動します。  
  
3.  設定を変更します。  
  
## <a name="see-also"></a>参照  
 [プロパティ ページ](../ide/property-pages-visual-cpp.md)