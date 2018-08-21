---
title: データ メンバーの属性 |Microsoft Docs
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
ms.openlocfilehash: cf8dab858b98e1f1a0433eabaa25a94275ee53ec
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570731"
---
# <a name="data-member-attributes"></a>データ メンバー属性
次の属性は、クラス、コクラスまたはインターフェイス内のデータ メンバーに適用されます。  
  
|属性|説明|  
|---------------|-----------------|  
|[db_accessor](../windows/db-accessor.md)|グループ`db_column`に参加している属性`IAccessor`-ベースのバインド。|  
|[db_column](../windows/db-column.md)|行セットに指定された列をバインドします。|  
|[db_command](../windows/db-command.md)|OLE DB コマンドを作成します。|  
|[db_param](../windows/db-param.md)|入力または出力パラメーターを使用して、指定したメンバー変数を関連付けるし、変数を区切ります。|  
|[db_source](../windows/db-source.md)|データ ソースへの接続を作成します。|  
|[db_table](../windows/db-table.md)|OLE DB、テーブルを開きます。|  
|[defaultbind](../windows/defaultbind.md)|オブジェクトを最もよく表す単一のバインド可能なプロパティを示します。|  
|[displaybind](../windows/displaybind.md)|バインド可能なユーザーに表示されるプロパティを示します。|  
|[ID](../windows/id.md)|メンバー関数 (プロパティまたはメソッド、インターフェイスまたは dispinterface) のように DISPID を指定します。|  
|[range](../windows/range-cpp.md)|引数または値を持つが実行時に設定されているフィールドに使用できる値の範囲を指定します。|  
|[rdx](../windows/rdx.md)|レジストリ キーを作成または既存のレジストリ キーを変更します。|  
|[readonly](../windows/readonly-cpp.md)|データ メンバーへの割り当てを禁止します。|  
|[requestedit](../windows/requestedit.md)|プロパティをサポートしていることを示します、`OnRequestEdit`通知します。|  
  
## <a name="see-also"></a>関連項目  
 [使用法別の属性](../windows/attributes-by-usage.md)