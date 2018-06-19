---
title: Cdatasource::openwithpromptfilename |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
dev_langs:
- C++
helpviewer_keywords:
- OpenWithPromptFileName method
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 318ec8fbba3845fd3e7a15d2efea6ba658712cf0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094271"
---
# <a name="cdatasourceopenwithpromptfilename"></a>CDataSource::OpenWithPromptFileName
このメソッドは、ダイアログ ボックスをユーザーに表示し、ユーザーが指定したファイルを使用してデータ ソースを開きます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [入力] ダイアログ ボックスの親であるウィンドウへのハンドル。  
  
 `dwPromptOptions`  
 [入力] 表示するロケーター ダイアログ ボックスのスタイルを指定します。 使用できる値については、Msdasc.h を参照してください。  
  
 *szInitialDirectory*  
 [入力] ロケーター ダイアログ ボックスに表示される初期ディレクトリ。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。 詳細については、"の OLE DB サービスでの OLE DB プログラマーズ リファレンスを参照してください。 [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)