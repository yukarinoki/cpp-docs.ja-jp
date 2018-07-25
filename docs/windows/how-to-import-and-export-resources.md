---
title: '方法: インポートおよびエクスポートのリソース |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.importing
- vc.resvw.resource.importing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [Visual Studio], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e526ab335436730f4132b5b7127ec9079432a4a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879179"
---
# <a name="how-to-import-and-export-resources"></a>方法: リソースをインポートおよびエクスポートする
グラフィカル リソース (ビットマップ、アイコン、カーソル、ツール バー)、HTML ファイル、および Visual C++ で使用するためのカスタム リソースをインポートすることができます。 Visual C++ プロジェクトから、同じ種類のファイルを別のファイルにエクスポートして、開発環境の外部で使用することができます。  
  
> [!NOTE]
>  アクセラレータ、ダイアログ ボックス、文字列テーブルなどのリソースの種類は、スタンドアロンのファイルの種類ではないため、インポートまたはエクスポートすることはできません。  
  
### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>1 つのリソースを現在のリソース ファイルにインポートするには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)、リソース スクリプトのノードを右クリックし (* .rc) ファイル、リソースを追加します。  
  
2.  をクリックして**インポート**ショートカット メニューの します。  
  
3.  インポートするビットマップ (.bmp)、アイコン (.ico)、カーソル (.cur)、Html ファイル (.htm)、またはその他のファイルを見つけてそのファイル名を選択します。  
  
4.  をクリックして**OK**で選択したファイルにリソースを追加する**リソース**ビュー。  
  
    > [!NOTE]
    >  どの種類のリソースを選択した場合も、インポート プロセスは同じように実行されます。 インポートされたリソースは、そのリソースの種類の適切なノードに自動的に追加されます。  
  
### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>(Visual C++ の外部で使用するために) ビットマップ、アイコン、またはカーソルを別のファイルとしてエクスポートするには  
  
1.  **リソース**ビューで、エクスポートするリソースを右クリックします。  
  
2.  をクリックして**エクスポート**ショートカット メニューの します。  
  
3.  **リソースのエクスポート** ダイアログ ボックスで、現在のファイル名をそのまま使用するか、新しい名前を入力します。  
  
4.  ファイルを保存し、をクリックする場所のフォルダーに移動**エクスポート**です。  
  

  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)