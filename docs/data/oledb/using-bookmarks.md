---
description: 詳細については、ブックマークの使用
title: ブックマークを使用する
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- OLE DB providers, bookmark support
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
ms.openlocfilehash: d0cf27a5f93b3e6b00fa6f8cbb69ae7414f4d819
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319158"
---
# <a name="using-bookmarks"></a>ブックマークを使用する

行セットを開く前に、ブックマークを使用するようにプロバイダーに指示する必要があります。 これを行うには、プロパティ `DBPROP_BOOKMARKS` セットでプロパティをに設定 **`true`** します。 プロバイダーはブックマークを列0として取得するので、 `CBookmark` 静的アクセサーを使用している場合は、特殊なマクロ BOOKMARK_ENTRY とクラスを使用する必要があります。 `CBookmark` は、引数がブックマークバッファーの長さ (バイト単位) であるテンプレートクラスです。 ブックマークに必要なバッファーの長さは、プロバイダーによって異なります。 次の例に示すように、ODBC OLE DB プロバイダーを使用している場合は、バッファーが4バイトである必要があります。

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

を使用する場合、 `CDynamicAccessor` バッファーは実行時に動的に設定されます。 この場合、バッファーの長さを指定しないの特殊化されたバージョンを使用でき `CBookmark` ます。 次のコード例に示すように、関数を使用し `GetBookmark` て、現在のレコードからブックマークを取得します。

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

プロバイダーでのブックマークのサポートについては、「 [プロバイダーによるブックマークのサポート](../../data/oledb/provider-support-for-bookmarks.md)」を参照してください。

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)
