---
title: CSession クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
dev_langs:
- C++
helpviewer_keywords:
- CSession class
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03c0bfec758bb663803b05b1f690816394f61239
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="csession-class"></a>CSession クラス
1 つのデータベース アクセスのセッションを表します。  
  
## <a name="syntax"></a>構文

```cpp
class CSession  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[中止](../../data/oledb/csession-abort.md)|キャンセル (終了) トランザクション。|  
|[閉じる](../../data/oledb/csession-close.md)|セッションを閉じます。|  
|[コミット](../../data/oledb/csession-commit.md)|トランザクションをコミットします。|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|トランザクションに関する情報を返します。|  
|[開く](../../data/oledb/csession-open.md)|データ ソース オブジェクトの新しいセッションを開きます。|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|このセッション用の新しいトランザクションを開始します。|  
  
## <a name="remarks"></a>コメント  
 各プロバイダー接続 (データ ソース) で表される 1 つまたは複数のセッションを関連付けることができます、 [CDataSource](../../data/oledb/cdatasource-class.md)オブジェクト。 新しい`CSession`の`CDataSource`、呼び出す[csession::open](../../data/oledb/csession-open.md)です。 データベース トランザクションを開始する`CSession`提供、`StartTransaction`メソッドです。 トランザクションが開始されるを使用してコミットすることができます、**コミット**メソッド、またはキャンセルを使用して、**中止**メソッドです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CatDB](../../visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)