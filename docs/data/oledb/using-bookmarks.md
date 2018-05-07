---
title: ブックマークの使用 |Microsoft ドキュメント
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
ms.openlocfilehash: 5aa16d5f2a3a02d0e9fd6bb3dd5de71494e81d4a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="using-bookmarks"></a>ブックマークの使用
行セットを開く前に、ブックマークを使用することをプロバイダーに指示する必要があります。 これを行うには、次のように設定します。、 **DBPROP_BOOKMARKS**プロパティを**true**プロパティで設定します。 特殊マクロを使用する必要がありますので、プロバイダーが列 0 としてブックマークを取得`BOOKMARK_ENTRY`と`CBookmark`クラスの静的アクセサーを使用している場合。 `CBookmark` 引数がブックマーク バッファーの長さ (バイト単位) は、テンプレート クラスです。 ブックマークに必要なバッファーの長さは、プロバイダーによって異なります。 次の例で示すように、ODBC OLE DB プロバイダーを使用する場合、バッファーは 4 バイトにする必要があります。  
  
```  
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
  
 使用する場合`CDynamicAccessor`バッファーが実行時に動的に割り当てられます。 特殊なバージョンを使用するこの例では、`CBookmark`バッファー長を指定しません。 関数を使用して`GetBookmark`このコード サンプルで示すように、現在のレコード、ブックマークを取得します。  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  

propset.AddProperty(DBPROP_BOOKMARKS, true);  

product.Open(session, "Products", &propset);  

product.MoveNext();  

product.GetBookmark(&bookmark);  
```  
  
 プロバイダーのブックマークをサポートする方法については、次を参照してください。[プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)です。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)