---
title: ダイアログ ボックスのコントロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], dialog boxes
- dialog box controls, about dialog box controls
- dialog box controls
ms.assetid: e216c4f9-2fd4-429d-889a-8ebce7bad177
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a837766bbbe57186f8355895c98ff04d8048bdc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873122"
---
# <a name="controls-in-dialog-boxes"></a>ダイアログ ボックスのコントロール
コントロールを追加すると、ダイアログ ボックスを使用して、[ダイアログ エディターのタブ](../windows/dialog-editor-tab-toolbox.md)で、[ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox)を使用すると、ダイアログ ボックスにドラッグしてコントロールを選択します。 既定では、[ツールボックス] ウィンドウは自動非表示に設定されます。 ダイアログ エディターが開いているときに、ソリューションの左余白のタブとして表示されます。 ただし、ピン留めできる [ツールボックス] ウィンドウの位置をクリックして、**自動的に隠す**ウィンドウの右上隅のボタンをクリックします。 このウィンドウの動作を制御する方法の詳細については、次を参照してください。[ウィンドウ管理](/visualstudio/ide/customizing-window-layouts-in-visual-studio)です。  
  
 ダイアログ ボックスにコントロールを追加、既存のコントロールの位置を変更または 1 つのダイアログ ボックスから、コントロールを移動する最も簡単な方法では、ドラッグ アンド ドロップ メソッドを使用します。 コントロールの位置は、ダイアログ ボックスに、削除されるまで点線で囲まれます。 ダイアログ ボックスにドラッグ アンド ドロップ メソッドを使用して、コントロールを追加する場合、コントロールには、その種類のコントロールを適切な標準の高さが与えられます。  
  
 ガイドや余白によって、最終的な配置を判断できます ダイアログ ボックスにコントロールを追加または位置を変更するときにオンになっているレイアウト グリッドがあるかどうか。  
  
 キャプションなどのプロパティを変更するには、ダイアログ ボックスにコントロールを追加した後、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 複数のコントロールを選択し、それらのプロパティをすべて一度に変更できます。  
  
-   [コントロールの追加、編集、または削除](adding-editing-or-deleting-controls.md)  
  
-   [コントロールの選択](../windows/selecting-controls.md)  
  
-   [各コントロールのサイズ変更](../windows/sizing-individual-controls.md)  
  
-   [複数のコントロールに対する同一の幅、高さ、またはサイズの設定](../windows/making-controls-the-same-width-height-or-size.md)  
  
-   [コンボ ボックスとドロップダウン リストのサイズの設定](setting-the-size-of-the-combo-box-and-its-drop-down-list.md)  
  
-   [コンボ ボックス コントロールへの値の追加](../windows/adding-values-to-a-combo-box-control.md)  
  
-   [水平スクロール バーの幅の設定](../windows/setting-the-width-of-a-horizontal-scroll-bar.md)  
  
-   [ダイアログ ボックスのコントロールの配置](../windows/arrangement-of-controls-on-dialog-boxes.md)  
  
-   [ダイアログ エディターのカスタム コントロール](custom-controls-in-the-dialog-editor.md)  
  
-   [ニーモニック (アクセス キー) の定義](../windows/defining-mnemonics-access-keys.md)  
  
-   [ダイアログ ボックスの位置とサイズの指定](../windows/specifying-the-location-and-size-of-a-dialog-box.md)  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックス コントロールのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)

