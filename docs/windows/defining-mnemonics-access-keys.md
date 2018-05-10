---
title: ニーモニック (アクセス キー) を定義する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls, mnemonics
- access keys [C++], checking
- mnemonics, checking for duplicate
- mnemonics
- mnemonics, dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a60cf597a88fcf7038848be6c9e2d31269f6a906
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="defining-mnemonics-access-keys"></a>ニーモニック (アクセス キー) の定義
通常は、ユーザーがキーボード入力フォーカス間を移動 1 つのコントロール ダイアログ ボックスで、TAB キーと方向キーとします。 ただし、ユーザーを 1 つのキーを押して、コントロールを選択できるようにするアクセス キー (またはニーモニック覚えやすい名前) を定義することができます。  
  
### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>表示されるキャプション (プッシュ ボタン、チェック ボックス、およびオプション ボタン) を持つコントロールのアクセス キーを定義するには  
  
1.  ダイアログ ボックス コントロールを選択します。  
  
2.  [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)で、**キャプション**プロパティ、コントロールは、アンパサンドを入力する新しい名前を入力 (**&**) として設定文字の前に、そのコントロールのアクセス キー。 たとえば、`&Radio1` のようにします。  
  
3.  **Enter** キーを押します。  
  
     アクセス キーを示すために表示されるキャプションに下線が表示されます**R**adio1 です。  
  
### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>表示されるキャプションなしコントロールのアクセス キーを定義するには  
  
1.  使用して、コントロールのキャプションを加える、**静的テキスト**内の制御、[ツールボックス](/visualstudio/ide/reference/toolbox)です。  
  
2.  静的なテキスト キャプションのアンパサンドを入力します (**&**) アクセス キーとして設定文字の前にします。  
  
3.  静的なテキスト コントロールの直前に、タブ オーダーのラベルとなるコントロールを確認します。  
  
 ダイアログ ボックス内のすべてのアクセス キーは一意である必要があります。  
  
#### <a name="to-check-for-duplicate-access-keys"></a>重複するアクセス キーを確認するには  
  
1.  **形式** メニューのをクリックして**ニーモニックの確認**です。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
### <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

