---
title: ブックマークの使用 |Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 6eeb2b6d0c9aa82a6304225b4de14c4d387bfc96
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50072175"
---
# <a name="using-bookmarks"></a>ブックマークの使用

行セットを開く前に、ブックマークを使用することをプロバイダーに指示する必要があります。 これを行うには、設定、`DBPROP_BOOKMARKS`プロパティを**true**プロパティ セットします。 BOOKMARK_ENTRY 特殊なマクロを使用する必要がありますので、プロバイダーが列 0 としてブックマークを取得し、`CBookmark`クラスの静的アクセサーを使用している場合。 `CBookmark` テンプレート クラスは、引数がブックマーク バッファーの長さ (バイト単位) です。 ブックマークに必要なバッファーの長さは、プロバイダーによって異なります。 使用する場合、ODBC OLE DB プロバイダーでは、次の例に示すように、バッファーは 4 バイトである必要があります。

```cpp
class CProducts
{
public:
   CBookmark<4> bookmark;

   BEGIN_COLUMN_MAP(CProducts)
      BOOKMARK_ENTRY(bookmark)
   END_COLUMN_MAP()
};
```

次に、次のコードで使用されます。

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

使用する場合`CDynamicAccessor`バッファーは実行時に動的に設定します。 特殊なバージョンを使用するこの例では、`CBookmark`バッファー長を指定しません。 関数を使用して`GetBookmark`このコード サンプルで示すように、現在のレコードからブックマークを取得します。

```cpp
CTable<CDynamicAccessor> product;
CBookmark<> bookmark;
CDBPropSet propset(DBPROPSET_ROWSET);
CSession session;

propset.AddProperty(DBPROP_BOOKMARKS, true);
product.Open(session, "Products", &propset);
product.MoveNext();
product.GetBookmark(&bookmark);
```

プロバイダーのブックマークのサポートについては、次を参照してください。[プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)します。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)