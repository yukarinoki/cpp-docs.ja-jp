---
title: Cdatasource::open |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3196aa89426e895dd6b73b28ce197e8f271a0262
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097069"
---
# <a name="cdatasourceopen"></a>CDataSource::Open
使用してデータ ソースへの接続を開き、 **CLSID**、 **ProgID**、または`CEnumerator`モニカー ロケーター ダイアログ ボックスを持つユーザーを求められます。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT Open(const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();  


HRESULT Open(const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,  
  DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,  
   LPCTSTR pName,  LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();  

HRESULT Open(const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();  

HRESULT Open(const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();  

HRESULT Open(HWND hWnd = GetActiveWindow(),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID,   
  DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID,   
   LPCTSTR pName,LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `clsid`  
 [in]**CLSID**データ プロバイダーのです。  
  
 *pPropSet*  
 [in]配列へのポインター [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)プロパティと設定する値を含む構造体。 参照してください[プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/en-us/library/ms713696.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK にします。  
  
 *nPropertySets*  
 [in]数[DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)に渡された構造体、 *pPropSet*引数。  
  
 *pName*  
 [入力] 接続先のデータベース名。  
  
 *pUserName*  
 [入力] ユーザーの名前。  
  
 *pPassword*  
 [入力] ユーザーのパスワード。  
  
 `nInitMode`  
 [入力] データベースの初期化モード。 参照してください[初期化プロパティ](https://msdn.microsoft.com/en-us/library/ms723127.aspx)で、 *OLE DB プログラマーズ リファレンス*有効な初期化モードの一覧については、Windows SDK に含まれています。 `nInitMode` がゼロの場合、接続を開くために使用されるプロパティ セットには初期化モードが含まれません。  
  
 `szProgID`  
 [入力] プログラム ID。  
  
 `enumerator`  
 [in]A [CEnumerator](../../data/oledb/cenumerator-class.md) 、呼び出し元が指定されていない場合は、接続を開くためのモニカーを取得するために使用するオブジェクト、 **CLSID**です。  
  
 `hWnd`  
 [入力] ダイアログ ボックスの親であるウィンドウへのハンドル。 `hWnd` パラメーターを使用する関数のオーバーロードを使用すると、サービス コンポーネントが自動的に呼び出されます。詳細については、「解説」を参照してください。  
  
 `dwPromptOptions`  
 [入力] 表示するロケーター ダイアログ ボックスのスタイルを指定します。 使用できる値については、Msdasc.h を参照してください。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 `hWnd` パラメーターを使用するメソッド オーバーロードは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。 詳細については、"の OLE DB サービスでの OLE DB プログラマーズ リファレンスを参照してください。 [ http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true)です。  
  
 `hWnd` パラメーターを使用しないメソッド オーバーロードは、oledb32.dll 内のサービス コンポーネントを使用せずに、データ ソース オブジェクトを開きます。 A [CDataSource](../../data/oledb/cdatasource-class.md)これらの関数オーバー ロードで開かれたオブジェクトは任意のサービス コンポーネントの機能を利用することはできません。  
  
## <a name="example"></a>例  
 次のコードは、OLE DB テンプレートを使用して Jet 4.0 データ ソースを開く方法を示します。 Jet データ ソースは、OLE DB データ ソースとして扱います。 ただし、呼び出しに**開く**2 つのプロパティ セットが必要: のいずれかの**DBPROPSET_DBINIT**およびその他の**DBPROPSET_JETOLEDB_DBINIT**設定できるように、 **DBPROP_JETOLEDB_DATABASEPASSWORD**です。  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDataSource クラス](../../data/oledb/cdatasource-class.md)
