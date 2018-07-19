---
title: 使用するアクセサーの種類の決定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets [C++], data types
- accessors [C++], types
ms.assetid: 22483dd2-f4e0-4dcb-8e4d-cd43a9c1a3db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 89a55127b8f7e5e0e7d338a9e7ba4f85e8c568d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104010"
---
# <a name="determining-which-type-of-accessor-to-use"></a>使用するアクセサーの種類の決定
コンパイル時または実行時に、行セットでのデータ型を指定できます。  
  
 コンパイル時にデータ型を判断する必要がある場合は、静的アクセサーを使用して (など`CAccessor`)。 手動または ATL OLE DB コンシューマー ウィザードを使用して、データ型を指定できます。  
  
 実行時に、データ型を判断する必要がある場合は、動的なを使用して (`CDynamicAccessor`またはその子) または手動のアクセサー (`CManualAccessor`)。 このような場合を呼び出すことができます`GetColumnInfo`元の型を判断することができます、列のバインド情報を返す行セットにします。  
  
 次の表は、コンシューマー テンプレートで提供されるアクセサーの種類を一覧表示します。 各アクセサーでは、長所と短所がします。 1 つのアクセサーの種類、状況に応じてニーズに合う必要があります。  
  
|アクセサー クラス|バインド|パラメーター|コメント|  
|--------------------|-------------|---------------|-------------|  
|`CAccessor`|ユーザー レコードを作成する`COLUMN_ENTRY`マクロです。 マクロは、そのレコード内のデータ メンバーをアクセサーにバインドします。 行セットの作成時に列をバインド解除できません。|使用して、はい、 **PARAM_MAP**マクロ エントリです。 バインドされると、パラメーターをバインド解除できません。|少量のコードのための最も高速なアクセサー。|  
|`CDynamicAccessor`|自動。|いいえ。|行セット内のデータの種類がわからない場合に役立ちます。|  
|`CDynamicParameterAccessor`|自動を指定できますが、[オーバーライド](../../data/oledb/overriding-a-dynamic-accessor.md)です。|プロバイダーをサポートしている場合は、yes`ICommandWithParameters`です。 パラメーターが自動的に連結します。|も低速`CDynamicAccessor`ですがジェネリックのストアド プロシージャを呼び出すために便利です。|  
|**CDynamicStringAccessor [W]**|自動。|いいえ。|文字列データとしてデータ ストアからアクセスされるデータを取得します。|  
|`CManualAccessor`|使用して手動`AddBindEntry`です。|使用して手動で`AddParameterEntry`です。|非常に高速です。パラメーターと列が 1 回のみバインドされます。 使用するデータの種類を指定します。 (を参照してください[DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832)例については、サンプルです)。以上のコードを必要と`CDynamicAccessor`または`CAccessor`です。 OLE DB を直接呼び出すようになります。|  
|`CXMLAccessor`|自動。|いいえ。|文字列データとしてデータ ストアからアクセスされるデータを取得し、データの XML タグの付いたとして書式設定します。|  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)