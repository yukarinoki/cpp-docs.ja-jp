---
title: 使用するアクセサーの種類の決定 |Microsoft Docs
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
ms.openlocfilehash: 720a72406bec5672757c1b2c5713586b7fc7f1ca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086968"
---
# <a name="determining-which-type-of-accessor-to-use"></a>使用するアクセサーの種類の決定

コンパイル時または実行時に、行セットでのデータ型を指定できます。  
  
コンパイル時にデータ型を決定する必要がある場合は、静的アクセサーを使用して (よう`CAccessor`)。 手動または ATL OLE DB コンシューマー ウィザードを使用して、データ型を指定できます。  
  
実行時にデータ型を決定する必要がある場合は、動的なを使用して (`CDynamicAccessor`またはその子) または手動のアクセサー (`CManualAccessor`)。 このような場合を呼び出すことができます`GetColumnInfo`元の型を判断することができます、列のバインド情報を返す行セットにします。  
  
次の表では、コンシューマー テンプレートで指定されたアクセサーの種類を示します。 各アクセサーには長所と短所。 自分の状況に応じてアクセサーの種類はニーズに合う必要があります。  
  
|アクセサー クラス|バインド|パラメーター|コメント|  
|--------------------|-------------|---------------|-------------|  
|`CAccessor`|COLUMN_ENTRY マクロでは、ユーザー レコードを作成します。 マクロは、アクセサーに、そのレコードのデータ メンバーをバインドします。 行セットが作成されると、列をバインド解除できません。|はい、PARAM_MAP マクロのエントリを使用しています。 バインドされた後、パラメーターをバインド解除できません。|少量のコードのための最も高速なアクセサー。|  
|`CDynamicAccessor`|自動。|いいえ。|行セット内のデータ型がわからない場合に役立ちます。|  
|`CDynamicParameterAccessor`|自動、することができますが、[オーバーライド](../../data/oledb/overriding-a-dynamic-accessor.md)します。|はい、プロバイダーがサポートしている場合`ICommandWithParameters`します。 パラメーターが自動的にバインドします。|も低速`CDynamicAccessor`ですがジェネリックのストアド プロシージャを呼び出すために便利です。|  
|`CDynamicStringAccessor[A,W]`|自動。|いいえ。|文字列データとしてデータ ストアからデータを取得します。|  
|`CManualAccessor`|使用して手動`AddBindEntry`します。|使用して手動で`AddParameterEntry`します。|非常に高速です。パラメーターと列が 1 回だけバインドされます。 使用するデータの種類を決定します。 (を参照してください[DBVIEWER](https://github.com/Microsoft/VCSamples)例については、サンプル)。以上のコードを必要と`CDynamicAccessor`または`CAccessor`します。 OLE DB を直接呼び出すことのようになります。|  
|`CXMLAccessor`|自動。|いいえ。|文字列データとしてデータ ストアからデータを取得し、データの XML タグを付けるように書式設定します。|  
  
## <a name="see-also"></a>関連項目  

[アクセサーの使用](../../data/oledb/using-accessors.md)