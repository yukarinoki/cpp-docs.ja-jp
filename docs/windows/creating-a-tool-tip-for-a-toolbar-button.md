---
title: ツール バー ボタンのツール ヒントの作成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41c2fa538a7888a2f14ae34fde9133b2872d13ba
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="creating-a-tool-tip-for-a-toolbar-button"></a>ツール バー ボタンのツール ヒントの作成
### <a name="to-create-a-tool-tip"></a>ツール ヒントを作成するには  
  
1.  ツール バー ボタンを選択します。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)で、**プロンプト**プロパティ フィールドのステータス バーの以外の場合はメッセージが表示されたら、ボタンの説明を追加、\n とツール ヒントの名前を追加します。  
  
 ツール ヒントの一般的な例では、ワードパッドの [印刷] ボタンを示します。  
  
 1. ワードパッドを開きます。  
  
 2. マウス ポインターを合わせ、**印刷**ツールバー ボタンをクリックします。  
  
 3. 単語 '印刷' ようになりましたがフローティング マウス ポインターの下に注意してください。  
  
 4. ([ワードパッド] ウィンドウの一番下) にあるステータス バーを見て - 現在表示されていること、テキスト「アクティブな文書を印刷する」ことを確認します。  
  
 手順 3 で '印刷'「ツール ヒントの名前、」であり、' アクティブ文書を印刷' 手順 4 から「の説明、ステータス バーのボタンをクリックします」。  
  
 この効果を使用する場合、**ツールバー**エディター、設定、**プロンプト**プロパティを **\n を印刷**です。  
  
> [!NOTE]
>  プロンプト テキストを使用して行うことができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 MFC または ATL  
  
## <a name="see-also"></a>関連項目  
 [作成、移動、およびツール バー ボタンの編集](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [ツール バー エディター](../windows/toolbar-editor.md)

