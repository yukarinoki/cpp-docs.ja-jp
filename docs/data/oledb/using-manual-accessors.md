---
title: 手動アクセサーの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5aa7f72cc76f80e2304faf93ca0c6198c505e88a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101645"
---
# <a name="using-manual-accessors"></a>手動アクセサーの使用

不明なコマンドを処理する場合は、次の 4 つあります。  
  
- パラメーターを確認します。  
  
- コマンドを実行します  
  
- 出力列を決定します。  
  
- 複数の行セットを返すかを参照してください。  
  
OLE DB コンシューマー テンプレートを使用して、`CManualAccessor`クラスし、これらの手順に従います。  
  
1. 開く、`CCommand`オブジェクト`CManualAccessor`テンプレート パラメーターとして。  
  
    ```cpp  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
1. クエリのセッション、`IDBSchemaRowset`インターフェイスし、プロシージャ パラメーター行セットを使用します。 場合、`IDBSchemaRowset`インターフェイスが使用できないクエリを実行、`ICommandWithParameters`インターフェイス。 呼び出す`GetParameterInfo`について。 どちらのインターフェイスを使用できる場合は、パラメーターがないと想定することができます。  
  
1. 各パラメーターでは、呼び出す`AddParameterEntry`パラメーターを追加し、それらを設定します。  
  
1. 行セットを開きますが、バインド パラメーターを設定**false**します。  
  
1. 呼び出す`GetColumnInfo`出力列を取得します。 使用`AddBindEntry`バインドに出力列を追加します。  
  
1. 呼び出す`GetNextResult`複数行セットが使用可能なかどうかを判断します。 手順 2 ~ 5 を繰り返します。  
  
手動アクセサーの例は、次を参照してください。`CDBListView::CallProcedure`で、 [DBVIEWER](https://github.com/Microsoft/VCSamples)サンプル。  
  
## <a name="see-also"></a>関連項目  

[アクセサーの使用](../../data/oledb/using-accessors.md)