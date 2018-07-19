---
title: 複数のアクセラレータ キーのプロパティの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11705fcbcdb3dc73fe5c3a87844b2bc5d90cd135
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33913019"
---
# <a name="changing-the-properties-of-multiple-accelerator-keys"></a>複数のアクセラレータ キーのプロパティの変更
### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>複数のアクセラレータ キーのプロパティを変更するには  
  
1.  アイコンをダブルクリックして、アクセラレータ テーブルを開く[リソース ビュー](../windows/resource-view-window.md)です。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  押しながら変更するアクセラレータ キーを選択して、 **CTRL**キーのそれぞれをクリックするとします。  
  
3.  移動して、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)したいすべてを共有する、選択されたアクセラレータの値を入力します。  
  
    > [!NOTE]
    >  各修飾子の値は、[プロパティ] ウィンドウで、ブール型プロパティとして表示されます。 変更した場合、[修飾子](../windows/accelerator-modifier-property.md)プロパティ ウィンドウで、アクセラレータ テーブル内の値が使用されていた以前の修飾子の追加として新しい修飾子を扱います。 このため場合は、修飾子の値を設定する必要がありますすべて各アクセラレータ キーが、同じ修飾子 の設定を共有していることを確認するように設定します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。  
  
 **必要条件**  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [アクセラレータ テーブルの編集](../windows/editing-accelerator-tables.md)   
 [アクセラレータ エディター](../windows/accelerator-editor.md)