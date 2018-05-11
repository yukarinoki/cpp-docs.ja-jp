---
title: '方法: コピー中に、言語またはリソースの条件を変更する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.changing
dev_langs:
- C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fcddbc0bb5a2afe807cbe8ca7643a831c28ad50f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying"></a>方法: コピー時におけるリソースの言語または条件を変更する
リソースのコピー時に、リソースの言語プロパティ、条件プロパティ、またはその両方を変更できます。  
  
-   リソースの言語では、そのリソースで使用する言語のみを識別します。 これは、使用して[FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042)を表示されているリソースを識別できるようにします。 (ただし、各言語でテキストに関連していない違いをリソースに含めることができます。たとえば、日本語キーボードのみで動作するアクセラレータや中国語でローカライズされたビルドのみに対応するビットマップなどです)。  
  
-   リソースの条件とは、リソースの特定のコピーが使用される条件を識別する定義済みのシンボルです。  
  
 リソースの言語と条件は、[ワークスペース] ウィンドウで、リソース名の後に、かっこで囲んで表示されます。 次の例では、リソース IDD_AboutBox が言語として Finnish、条件として XX33 を使用しています。  
  
```  
IDD_AboutBox (Finnish - XX33)  
```  
  
### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>既存のリソースをコピーして、そのリソースの言語または条件を変更するには  
  
1.  .Rc ファイルにまたは、[リソース ビュー](../windows/resource-view-window.md)ウィンドウで、コピーするリソースを右クリックします。  
  
2.  選択**コピーの挿入**ショートカット メニューからです。  
  
3.  **リソース コピーの挿入** ダイアログ ボックス。  
  
    -   **言語**ボックスの一覧で、言語を選択します。  
  
    -   **条件**ボックスで、条件を入力します。  
  

  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [方法: リソースをコピー](../windows/how-to-copy-resources.md)   
 [リソース ファイル (Visual Studio)](../windows/resource-files-visual-studio.md)   
 [リソース エディター](../windows/resource-editors.md)