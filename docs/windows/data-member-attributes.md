---
title: データ メンバー属性 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attributes [C++], reference topics
- data members [C++], attributes
- data members [C++]
ms.assetid: 95b2397d-1daf-4ae4-8cd0-06956d005b13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 490f8f20a6e1fcee476a6bbeb18ec6f6164389fc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871706"
---
# <a name="data-member-attributes"></a>データ メンバー属性
次の属性は、クラス、コクラス、またはインターフェイス内のデータ メンバーに適用されます。  
  
|属性|説明|  
|---------------|-----------------|  
|[db_accessor](../windows/db-accessor.md)|グループ**db_column**に参加している属性`IAccessor`-ベースのバインディングです。|  
|[db_column](../windows/db-column.md)|行セットに指定された列をバインドします。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[db_param](../windows/db-param.md)|入力または出力パラメーターを持つ指定したメンバー変数を関連付けるし、変数を区切ります。|  
|[db_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db_table](../windows/db-table.md)|OLE DB テーブルを開きます。|  
|[defaultbind](../windows/defaultbind.md)|1 つのバインド可能なプロパティ オブジェクトを最も良く表すものを示します。|  
|[displaybind](../windows/displaybind.md)|バインド可能なとしてユーザーに表示されるプロパティを示します。|  
|[ID](../windows/id.md)|メンバー関数 (プロパティまたはメソッド、インターフェイスまたはディスパッチ インターフェイス) の DISPID を指定します。|  
|[range](../windows/range-cpp.md)|引数または値が設定される実行時にフィールドに使用できる値の範囲を指定します。|  
|[rdx](../windows/rdx.md)|レジストリ キーを作成するか、既存のレジストリ キーを変更します。|  
|[readonly](../windows/readonly-cpp.md)|データ メンバーへの割り当てを禁止します。|  
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、 **OnRequestEdit**通知します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)