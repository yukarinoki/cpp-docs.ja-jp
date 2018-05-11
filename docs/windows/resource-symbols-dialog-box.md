---
title: リソース シンボル ダイアログ ボックス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourcesymbols
dev_langs:
- C++
helpviewer_keywords:
- New Symbol dialog box
- Resource Symbols dialog box
- Change Symbol dialog box
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 486d4c6c89a43c9d91c655911fa7fee8a31ebd32
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="resource-symbols-dialog-box"></a>[リソース シンボル] ダイアログ ボックス
**リソース シンボル**ダイアログ ボックスでは、新しいリソース シンボルの追加が表示され、またはソース コード内のシンボルは使用されている場所にスキップするシンボルを変更することができます。  
  
 **Name**  
 シンボルの名前を表示します。 詳細については、次を参照してください。[シンボル名の制限](../windows/symbol-name-restrictions.md)です。  
  
 **[値]**  
 シンボルの数値を表示します。 詳細については、次を参照してください。[シンボル値の制限](../windows/symbol-value-restrictions.md)です。  
  
 **使用中**  
 シンボルが 1 つ以上のリソースで使用されることを指定する場合にオンにします。 リソースの一覧が [次のリソースで使用] ボックスに表示されます。  
  
 **読み取り専用のシンボルを表示します。**  
 読み取り専用のリソースを表示する場合にオンにします。 既定では、[リソース シンボル] ダイアログ ボックスには、リソース スクリプト ファイル内の変更可能なリソースのみが表示されます。このオプションをオンにすると、変更可能なリソースは太字で表示され、読み取り専用リソースはプレーン テキストで表示されます。  
  
 **によって使用されます。**  
 シンボル一覧で選択したシンボルを使用するリソースが表示されます。 指定されたリソースのエディターに移動するには、内のリソースを選択、**によって使用される**ボックスし、をクリックして**ビューを使用して**です。 詳細については、次を参照してください。[特定のシンボル用のリソース エディターを開く](../windows/opening-the-resource-editor-for-a-given-symbol.md)です。  
  
 **新規**  
 [新規シンボル] ダイアログ ボックスが開きます。このダイアログ ボックスで、新しいシンボル リソース識別子の名前を定義します。必要に応じて、値も定義できます。 詳細については、次を参照してください。[シンボルの新規作成](../windows/creating-new-symbols.md)です。  
  
 **変更**  
 [シンボルの変更] ダイアログ ボックスが開きます。このダイアログ ボックスで、シンボルの名前または値を変更できます。 使用中のコントロールまたはリソースのシンボルを変更するには、対応するリソース エディターを使用する必要があります。 詳細については、次を参照してください。[未使用のシンボルを変更する](../windows/changing-unassigned-symbols.md)です。  
  
 **ビューの使用**  
 対応するリソース エディターで、シンボルが含まれたリソースを開きます。 詳細については、次を参照してください。[特定のシンボル用のリソース エディターを開く](../windows/opening-the-resource-editor-for-a-given-symbol.md)です。  
  

  
## <a name="requirements"></a>要件  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [リソース シンボルの表示](../windows/viewing-resource-symbols.md)