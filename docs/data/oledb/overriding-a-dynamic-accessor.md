---
title: 動的アクセサーのオーバーライド
ms.date: 10/19/2018
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
- overriding, dynamic accessors
ms.assetid: cbefd156-6da5-490d-b795-c2d7d874f7ce
ms.openlocfilehash: d46531f2d4075df98081886dfdfd1f2cf65d9948
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209847"
---
# <a name="overriding-a-dynamic-accessor"></a>動的アクセサーのオーバーライド

`CDynamicAccessor`などの動的アクセサーを使用すると、コマンド `Open` メソッドによって、開いている行セットの列情報に基づいて、アクセサーが自動的に作成されます。 動的アクセサーをオーバーライドして、列のバインド方法を厳密に制御することができます。

動的アクセサーをオーバーライドするには、`CCommand::Open` メソッドに最後のパラメーターとして**false**を渡します。 これにより、`Open` によってアクセサーが自動的に作成されなくなります。 その後、`GetColumnInfo` を呼び出して、バインドする各列に対して `AddBindEntry` を呼び出すことができます。 次のコードは、その方法を示しています。

```cpp
USES_CONVERSION;
double   dblProductID;

CCommand<CDynamicAccessor> product;
// Open the table, passing false to prevent automatic binding
product.Open(session, _T("Select * FROM Products"), NULL, NULL, DBGUID_DEFAULT, false);


ULONG         nColumns;
DBCOLUMNINFO*   pColumnInfo;
// Get the column information from the opened rowset.
product.GetColumnInfo(&nColumns, &pColumnInfo);

// Bind the product ID as a double.
pColumnInfo[0].wType          = DBTYPE_R8;
pColumnInfo[0].ulColumnSize = 8;
product.AddBindEntry(pColumnInfo[0]);

// Bind the product name as it is.
product.AddBindEntry(pColumnInfo[1]);

// Bind the reorder level as a string.
pColumnInfo[8].wType          = DBTYPE_STR;
pColumnInfo[8].ulColumnSize = 10;
product.AddBindEntry(pColumnInfo[8]);

// You have finished specifying the bindings. Go ahead and bind.
product.Bind();
// Free the memory for the column information that was retrieved in
// previous call to GetColumnInfo.
CoTaskMemFree(pColumnInfo);


char*   pszProductName;
char*   pszReorderLevel;
bool   bRC;

// Loop through the records tracing out the information.
while (product.MoveNext() == S_OK)
{
   bRC = product.GetValue(1, &dblProductID);
   pszProductName   = (char*)product.GetValue(2);
   pszReorderLevel  = (char*)product.GetValue(9);

   ATLTRACE(_T("Override = %lf \"%s\" \"%s\"\n"), dblProductID,
      A2T(pszProductName), A2T(pszReorderLevel));
}
```

## <a name="see-also"></a>参照

[アクセサーの使用](../../data/oledb/using-accessors.md)
