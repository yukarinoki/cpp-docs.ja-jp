---
title: ガイドのコントロールの配置 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLUs (dialog units)
- controls [C++], aligning
- Dialog editor, snap to guides
- guides, tick mark interval
- dialog box controls, placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a7c8cc57b4d2e7150ff09858cfd5b315beb37962
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857839"
---
# <a name="aligning-controls-on-a-guide"></a>ガイドのコントロールの配置
コントロールのサイズ変更ハンドルは、コントロールが移動され、(ガイドに合わせてコントロールが存在しない) 場合に、ガイドがコントロールに合わせるときに、ガイドにスナップされます。 ガイドを移動するとときに、スナップしたコントロールはも移動します。 1 つ以上のガイドにスナップ コントロールは、ガイドでは、いずれかが移動されるときにサイズ変更されます。  
  
 目盛りは定規ガイドとコントロールの間隔を決定するには、ダイアログ単位 (Dlu) によって定義されます。 DLU は通常 8 ポイント MS Shell Dlg、ダイアログ ボックス フォントのサイズに基づいています。 水平 DLU は、4 で割った値 ダイアログ ボックスのフォントの幅の平均です。 垂直 DLU は 8 で割った値のフォントの高さの平均値です。  
  
### <a name="to-size-a-group-of-controls-with-guides"></a>ガイドを使用してコントロールのグループのサイズを変更するには  
  
1.  コントロール (またはコントロール) の一方の側をスナップをガイドします。  
  
2.  コントロール (またはコントロール) の相手側のガイドをドラッグします。  
  
     必要に応じて複数のコントロールに、それぞれ 2 つ目のガイドに合わせてのサイズを変更します。  
  
3.  コントロール (またはコントロール) のサイズをいずれかのガイドに移動します。  
  
### <a name="to-change-the-intervals-of-the-tick-marks"></a>目盛りの間隔を変更するには  
  
1.  **形式** メニューの 選択**ガイド設定**です。  
  
2.  [ガイドの設定 ダイアログ ボックス](../windows/guide-settings-dialog-box.md)で、**グリッド間隔**フィールドに、Dlu で新しい幅と高さを指定します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ エディターの状態 (ガイドとグリッド)](../windows/dialog-editor-states-guides-and-grids.md)   
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)

