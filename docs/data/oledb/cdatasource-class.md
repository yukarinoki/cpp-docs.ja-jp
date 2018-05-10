---
title: CDataSource クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
dev_langs:
- C++
helpviewer_keywords:
- CDataSource class
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7835cd7401c13ab167a9236db4f7e2fc98f3e175
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasource-class"></a>CDataSource クラス
データ ソースにプロバイダーを経由して接続を表す OLE DB データ ソース オブジェクトに対応しています。  
  
## <a name="syntax"></a>構文

```cpp
class CDataSource  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[閉じる](../../data/oledb/cdatasource-close.md)|接続を閉じます。|  
|[GetInitializationString](../../data/oledb/cdatasource-getinitializationstring.md)|現在開かれているデータ ソースの初期化文字列を取得します。|  
|[GetProperties](../../data/oledb/cdatasource-getproperties.md)|現在接続されているデータ ソースの設定のプロパティの値を取得します。|  
|[GetProperty](../../data/oledb/cdatasource-getproperty.md)|接続されたデータ ソースに設定されている 1 つのプロパティの値を取得します。|  
|[開く](../../data/oledb/cdatasource-open.md)|いずれかを使用して、プロバイダー (データ ソース) への接続を作成、 **CLSID**、 **ProgID**、または`CEnumerator`モニカーは、呼び出し元によって提供されます。|  
|[OpenFromFileName](../../data/oledb/cdatasource-openfromfilename.md)|ユーザー指定のファイル名で指定されたファイルからデータ ソースを開きます。|  
|[OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md)|初期化文字列で指定されたデータ ソースを開きます。|  
|[OpenWithPromptFileName](../../data/oledb/cdatasource-openwithpromptfilename.md)|以前に作成したデータ リンク ファイルを開くには、対応するデータ ソースを選択することができます。|  
|[OpenWithServiceComponents](../../data/oledb/cdatasource-openwithservicecomponents.md)|データ リンク ダイアログ ボックスを使用してデータ ソース オブジェクトを開きます。|  
  
## <a name="remarks"></a>コメント  
 1 つまたは複数のデータベース セッションは、1 つの接続を作成できます。 これらのセッションがによって表される`CSession`です。 呼び出す必要があります[cdatasource::open](../../data/oledb/cdatasource-open.md)とのセッションを作成する前に、接続を開く`CSession::Open`です。  
  
 使用する方法の例については`CDataSource`を参照してください、 [CatDB](../../visual-cpp-samples.md)サンプルです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)