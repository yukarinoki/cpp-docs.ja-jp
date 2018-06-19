---
title: シンボル ヘッダー ファイルの名前を変更する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.header
dev_langs:
- C++
helpviewer_keywords:
- resource files, multiple
- Resource Includes dialog box
- symbol header files, changing names
- symbol header files
- header files, changing names
- names [C++], symbol header files
- symbols, symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 953ac59958748bd58fa7e9027c595bf7905e5f27
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864230"
---
# <a name="changing-the-names-of-symbol-header-files"></a>シンボル ヘッダー ファイル名の変更
通常は、すべてのシンボル定義が Resource.h に保存されます。 ただし、同じディレクトリ内の複数のリソース ファイルを使用する場合などに、このインクルード ファイル名の変更が必要になることがあります。  
  
### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>リソースのシンボル用のヘッダー ファイルの名前を変更するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)を .rc ファイルを右クリックして[リソースが含まれています](../windows/resource-includes-dialog-box.md)ショートカット メニューからです。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  **シンボル ヘッダー ファイル**ボックスに、インクルード ファイルの新しい名前を入力します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド 』。*  
  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース シンボルの表示](../windows/viewing-resource-symbols.md)   
 [定義済みシンボル ID](../windows/predefined-symbol-ids.md)