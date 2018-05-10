---
title: CDataConnection クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataConnection
- ATL.CDataConnection
- CDataConnection
dev_langs:
- C++
helpviewer_keywords:
- CDataConnection class
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 945fed5edd59da93aabb1d22e4830417fc4a2518
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnection-class"></a>CDataConnection クラス
データ ソースとの接続を管理します。  
  
## <a name="syntax"></a>構文

```cpp
class CDataConnection  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|コンストラクターです。 インスタンスを作成し、初期化、`CDataConnection`オブジェクト。|  
|[コピー](../../data/oledb/cdataconnection-copy.md)|既存のデータ接続のコピーを作成します。|  
|[開く](../../data/oledb/cdataconnection-open.md)|初期化文字列を使用してデータ ソースへの接続を開きます。|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|現在の接続で新しいセッションを開きます。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[BOOL 演算子](../../data/oledb/cdataconnection-operator-bool.md)|か、現在のセッションが開いているかどうかを判断します。|  
|[operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|か、現在のセッションが開いているかどうかを判断します。|  
|[CDataSource 演算子 (& a)](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|格納されている参照を返します`CDataSource`オブジェクト。|  
|[CDataSource * 演算子](../../data/oledb/cdataconnection-operator-cdatasource-star.md)|格納されているポインターを返します`CDataSource`オブジェクト。|  
|[演算子 CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md)|格納されている参照を返します`CSession`オブジェクト。|  
|[演算子 CSession *](../../data/oledb/cdataconnection-operator-csession-star.md)|格納されているポインターを返します`CSession`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 `CDataConnection` クラスは、必要なオブジェクト (データ ソースとセッション) とデータ ソースに接続する場合に行う必要がある作業の一部をカプセル化するためにクライアントを作成するには  
  
 せず`CDataConnection`、作成する必要が、`CDataSource`オブジェクトを呼び出すその[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)メソッドのインスタンスを作成、 [CSession](../../data/oledb/csession-class.md)オブジェクトを呼び出してその[開いている](../../data/oledb/csession-open.md)メソッド、作成し、 [CCommand](../../data/oledb/ccommand-class.md)オブジェクトと呼び出しその**開く*** メソッドです。  
  
 `CDataConnection`、のみ、接続オブジェクトを作成し、初期化文字列を渡す、コマンドを開く、その接続を使用する必要があります。 接続を開き、維持することをお勧めは、データベースへの接続を繰り返し使用する場合と`CDataConnection`を行うには便利な方法を提供します。  
  
> [!NOTE]
>  複数のセッションを処理する必要があるデータベース アプリケーションを作成する場合は、使用する必要があります[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)