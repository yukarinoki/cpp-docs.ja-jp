---
title: Cdatasource::openfromfilename |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
dev_langs:
- C++
helpviewer_keywords:
- OpenFromFileName method
ms.assetid: c4226de6-59da-4368-9c15-c5afab86f68b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6dfa5411373ab4a5c80c493ad876926620c4f9a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090771"
---
# <a name="cdatasourceopenfromfilename"></a>CDataSource::OpenFromFileName
ユーザー指定のファイル名で指定されたファイルからデータ ソースを開きます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `szFileName`  
 [in] ファイル名、通常はデータ ソース接続 (.UDL) ファイル。  
  
 データ リンク ファイル (.udl ファイル) の詳細については、次を参照してください。[データ リンク API の概要](https://msdn.microsoft.com/en-us/library/ms718102.aspx)Windows SDK に含まれています。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。 詳細については、"の OLE DB サービスでの OLE DB プログラマーズ リファレンスを参照してください。 [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)