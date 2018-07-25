---
title: バイナリ編集するリソースのオープン |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- resources [Visual Studio], opening for binary editing
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c09cd825a5974422eaf757419f4ce890f5123100
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878487"
---
# <a name="opening-a-resource-for-binary-editing"></a>バイナリ編集するリソースのオープン
### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>バイナリ編集用に Windows デスクトップ リソースを開くには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)で、編集の対象となる特定のリソース ファイルを選択します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  リソースを右クリックし、ショートカット メニューから **[バイナリー データを開く]** をクリックします。  
  
    > [!NOTE]
    >  [リソース ビュー](../windows/resource-view-window.md) ウィンドウを使用して Visual Studio で認識されない書式のリソースを開く場合 (RCDATA やカスタム リソースなど)、リソースは自動的にバイナリ エディターで開かれます。  
  
### <a name="to-open-a-managed-resource-for-binary-editing"></a>バイナリ編集の対象となるマネージ リソースを開くには  
  
1.  ソリューション エクスプローラーで、編集の対象となる特定のリソース ファイルを選択します。  
  
2.  リソースを右クリックして、ショートカット メニューから **[プログラムから開く]** を選択します。  
  
3.  **[プログラムから開く]** ダイアログ ボックスで、 **バイナリ エディター**を選択します。  
  
    > [!NOTE]
    >  [イメージ エディター](../windows/image-editor-for-icons.md) と [バイナリ エディター](binary-editor.md) を使用して、マネージ プロジェクトのリソース ファイルを操作できます。 編集の対象となるマネージ リソースは、リンク リソースである必要があります。 Visual Studio のリソース エディターでは、埋め込みリソースの編集はサポートしていません。  
  
    > [!NOTE]
    >  マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](/dotnet/standard/globalization-localization/index)です。   
  
 ![バイナリ エディター](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")  
バイナリ エディターに表示されるダイアログ ボックスのバイナリ データ  
  
 バイナリ エディターでは、特定の ASCII 値のみが表されます (0x20 ～ 0x7E)。 拡張文字は、バイナリ エディターの ASCII 値セクション (右側のパネル) にピリオドで表示されます。 "印刷可能" な文字は、ASCII 値の 32 ～ 126 です。  
  
> [!NOTE]
>  別のエディター ウィンドウで既に編集中のリソースに対してバイナリ エディターを使用する場合、他のエディター ウィンドウをまず閉じてください。  
  
 **必要条件**  
  
 なし  
  
## <a name="see-also"></a>関連項目  
 [Binary Editor](binary-editor.md)

