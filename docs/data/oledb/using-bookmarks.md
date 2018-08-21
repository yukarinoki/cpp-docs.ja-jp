---
title: ブックマークの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e6570e82c7cd50c03530b085ee9497fbc974fd58
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338741"
---
# <a name="using-bookmarks"></a>ブックマークの使用
行セットを開く前に、ブックマークを使用することをプロバイダーに指示する必要があります。 これを行うには、設定、`DBPROP_BOOKMARKS`プロパティを**true**プロパティ セットします。 BOOKMARK_ENTRY 特殊なマクロを使用する必要がありますので、プロバイダーが列 0 としてブックマークを取得し、`CBookmark`クラスの静的アクセサーを使用している場合。 `CBookmark` テンプレート クラスは、引数がブックマーク バッファーの長さ (バイト単位) です。 ブックマークに必要なバッファーの長さは、プロバイダーによって異なります。 次の例に示すように、ODBC OLE DB プロバイダーを使用する場合、バッファーは 4 バイトである必要があります。  
  
```cpp  
class CProducts  
{  
public:  
   CBookmark<4>   bookmark;  
  
   BEGIN_COLUMN_MAP(CProducts)  
      BOOKMARK_ENTRY(bookmark)  
   END_COLUMN_MAP()  
};  
  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_BOOKMARKS, true);  
  

CTable<CAccessor<CProducts>> product;  
product.Open(session, "Products", &propset);  
```  
  
 使用する場合`CDynamicAccessor`バッファーが実行時に動的に割り当てられます。 特殊なバージョンを使用するこの例では、`CBookmark`バッファー長を指定しないでください。 関数を使用して`GetBookmark`このコード サンプルで示すように、現在のレコードからブックマークを取得します。  
  
```cpp  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  

propset.AddProperty(DBPROP_BOOKMARKS, true);  

product.Open(session, "Products", &propset);  

product.MoveNext();  

product.GetBookmark(&bookmark);  
```  
  
 プロバイダーのブックマークのサポートについては、次を参照してください。[プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)します。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)