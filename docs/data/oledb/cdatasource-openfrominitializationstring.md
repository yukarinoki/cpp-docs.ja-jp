---
title: Cdatasource::openfrominitializationstring |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
dev_langs:
- C++
helpviewer_keywords:
- OpenFromInitializationString method
ms.assetid: 5ef1f1fd-92a9-4e1c-ad80-d3601b094b8c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dac964f7c6c863f85769a164fab8c418e1c45430
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090935"
---
# <a name="cdatasourceopenfrominitializationstring"></a>CDataSource::OpenFromInitializationString
ユーザーが指定した初期化文字列で指定されたデータ ソースを開きます。  
  
## <a name="syntax"></a>構文  
  
```
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,   
   bool fPromptForInfo= false) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *szInitializationString*  
 [in]初期化文字列。  
  
 *fPromptForInfo*  
 [in]この引数に設定されている場合**true**、し`OpenFromInitializationString`設定は、 **DBPROP_INIT_PROMPT**プロパティを**DBPROMPT_COMPLETEREQUIRED**ユーザーがあることを指定します。詳細については、必要な場合にのみを要求します。 これは、初期化文字列が、パスワードが必要なデータベースを指定する場合に便利ですが、文字列にパスワードが含まれていません。 ユーザーはパスワード (またはその他の不足している情報) を要求する、データベースに接続しようとしています。  
  
 既定値は**false**を指定することが求められます (設定**DBPROP_INIT_PROMPT**に**DBPROMPT_NOPROMPT**)。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)