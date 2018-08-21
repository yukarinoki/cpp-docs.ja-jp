---
title: シンボル ヘッダー ファイルの名前を変更する |Microsoft Docs
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
ms.openlocfilehash: 6d1c3436190ff36724eba1601a51608371b8d0a4
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649947"
---
# <a name="changing-the-names-of-symbol-header-files"></a>シンボル ヘッダー ファイル名の変更
通常、すべてのシンボルが定義に保存`Resource.h`します。 ただし、同じディレクトリ内の複数のリソース ファイルを使用する場合などに、このインクルード ファイル名の変更が必要になることがあります。  
  
### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>リソースのシンボル用のヘッダー ファイルの名前を変更するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)を .rc ファイルを右クリックして[リソース ファイルのインクルード](../windows/resource-includes-dialog-box.md)ショートカット メニューから。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  **シンボル ヘッダー ファイル**ボックスに、インクルード ファイルの新しい名前を入力します。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。  
  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース シンボルの表示](../windows/viewing-resource-symbols.md)   
 [定義済みシンボル ID](../windows/predefined-symbol-ids.md)