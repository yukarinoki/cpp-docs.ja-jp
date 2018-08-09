---
title: ダイアログ ボックスのコントロール |Microsoft Docs
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
ms.openlocfilehash: acbbbe0ecf1151f6159799592a8211bcf11fe7a1
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646944"
---
# <a name="controls-in-dialog-boxes"></a>ダイアログ ボックスのコントロール
コントロールを使用して、ダイアログ ボックスを追加することができます、[ダイアログ エディターのタブ](../windows/dialog-editor-tab-toolbox.md)で、[ツールボックス ウィンドウ](/visualstudio/ide/reference/toolbox)、ダイアログ ボックスにドラッグしてコントロールを選択できます。 既定では、[ツールボックス] ウィンドウは、自動非表示に設定されます。 ダイアログ エディターが開いたとき、ソリューションの左余白のタブとして表示されます。 ただし、ピン留めできます、**ツールボックス**ウィンドウ位置をクリックして、**自動的に隠す**ウィンドウの右上隅のボタンをクリックします。 このウィンドウの動作を制御する方法の詳細については、次を参照してください。[ウィンドウ管理](/visualstudio/ide/customizing-window-layouts-in-visual-studio)します。  
  
 ダイアログ ボックスにコントロールを追加、既存のコントロールの位置を変更または 1 つのダイアログ ボックスから、コントロールを移動する最も簡単な方法では、ドラッグ アンド ドロップを使用します。 ダイアログ ボックスに、削除されるまで、コントロールの位置は点線で囲まれます。 ドラッグ アンド ドロップしてダイアログ ボックスにコントロールを追加すると、コントロールには、その種類のコントロールに適切な標準の高さが与えられます。  
  
 ガイドや、余白によって決定されます、最終的な配置 ダイアログ ボックスにコントロールを追加または位置を変更するときまたはレイアウト グリッドをオンにする必要があるかどうか。  
  
 キャプションなどのプロパティを変更するには、ダイアログ ボックスにコントロールを追加した後、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)します。 複数のコントロールを選択し、そのプロパティをすべて一度に変更できます。  
  
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
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロールのイベント ハンドラーの追加](../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [ダイアログ ボックス コントロールおよび変数の型](../ide/dialog-box-controls-and-variable-types.md)   
 [ダイアログ エディター](../windows/dialog-editor.md)