---
title: ブックマークを使用する
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: 5a4a2d65ba7367b5568603b5f08a07c6d85cc4a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209315"
---
# <a name="using-bookmarks"></a>ブックマークを使用する

行セットを開く前に、ブックマークを使用するようにプロバイダーに指示する必要があります。 これを行うには、プロパティセットで `DBPROP_BOOKMARKS` プロパティを**true**に設定します。 プロバイダーはブックマークを列0として取得するので、静的アクセサーを使用している場合は、特殊なマクロ BOOKMARK_ENTRY と `CBookmark` クラスを使用する必要があります。 `CBookmark` は、引数がブックマークバッファーの長さ (バイト単位) であるテンプレートクラスです。 ブックマークに必要なバッファーの長さは、プロバイダーによって異なります。 次の例に示すように、ODBC OLE DB プロバイダーを使用している場合は、バッファーが4バイトである必要があります。

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

その後、次のコードによって使用されます。

```cpp
CDBPropSet propset(DBPROPSET_ROWSET);
propset.AddProperty(DBPROP_BOOKMARKS, true);

CTable<CAccessor<CProducts>> product;
CSession session;
product.Open(session, "Products", &propset);
```

`CDynamicAccessor`を使用する場合、バッファーは実行時に動的に設定されます。 この場合は、バッファーの長さを指定しない特殊なバージョンの `CBookmark` を使用できます。 次のコード例に示すように、関数 `GetBookmark` を使用して、現在のレコードからブックマークを取得します。

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

プロバイダーでのブックマークのサポートについては、「[プロバイダーによるブックマークのサポート](../../data/oledb/provider-support-for-bookmarks.md)」を参照してください。

## <a name="see-also"></a>参照

[アクセサーの使用](../../data/oledb/using-accessors.md)
