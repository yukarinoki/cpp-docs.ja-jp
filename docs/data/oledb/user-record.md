---
title: ユーザー レコード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- records, user
- OLE DB providers, user record
- user records
- user records, described
- rowsets, user record
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b53410c8116f88d51734bb302026a03994e520a
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338195"
---
# <a name="user-record"></a>ユーザー レコード
ユーザー レコードは、行セットの列のデータを表すコードとデータ構造を提供します。 コンパイル時または実行時に、ユーザー レコードを作成することができます。 ATL OLE DB プロバイダー ウィザードを使用してプロバイダーを作成するときに、ウィザードには、次のような ("MyProvider"のプロバイダー名 [短い名前] を指定したと仮定)、既定のユーザー レコードが作成されます。  
  
```cpp  
class CWindowsFile:  
   public WIN32_FIND_DATA  
{  
public:  
  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
  
};  
```  
  
 OLE DB プロバイダー テンプレートは、クライアントとのやり取りに関するすべての OLE DB 仕様を処理します。 プロバイダーの呼び出しの応答を必要な列のデータを取得するために、`GetColumnInfo`関数で、ユーザー レコード内に配置する必要があります。 明示的にオーバーライドする`GetColumnInfo`ユーザーのレコードのなど宣言するで、.h ファイルに次に示すよう。  
  
```cpp  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 このようにすると、次の記述と同じ結果が得られます。  
  
```cpp  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 実装する必要がありますも`GetColumnInfo`ユーザー レコードの .cpp ファイルにします。  
  
 PROVIDER_COLUMN_MAP マクロは作成を支援する`GetColumnInfo`関数。  
  
-   BEGIN_PROVIDER_COLUMN_MAP 関数プロトタイプとの静的配列を定義する`ATLCOLUMNINFO`構造体。  
  
-   PROVIDER_COLUMN_ENTRY を定義し、1 つを初期化します`ATLCOLUMNINFO`します。  
  
-   END_PROVIDER_COLUMN_MAP では、配列と関数を閉じます。 配列の要素数にも配置、 *pcCols*パラメーター。  
  
 ユーザー レコードが、実行時に作成されたときに`GetColumnInfo`を使用して、 *pThis*行セットまたはコマンドのインスタンスへのポインターを受け取るパラメーター。 コマンドおよび行セットをサポートする必要があります、`IColumnsInfo`インターフェイスのため、このポインターから列情報を取得できます。  
  
 `CommandClass` `RowsetClass`は、コマンドと、ユーザー レコードを使用する行セット。  
  
 オーバーライドする方法の詳細な例については`GetColumnInfo`ユーザー レコードでは、次を参照してください。[動的に決定する列に返されるコンシューマー](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)