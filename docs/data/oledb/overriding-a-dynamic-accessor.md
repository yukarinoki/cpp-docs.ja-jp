---
title: 動的アクセサーのオーバーライド |Microsoft Docs
ms.custom: ''
ms.date: 10/19/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
- overriding, dynamic accessors
ms.assetid: cbefd156-6da5-490d-b795-c2d7d874f7ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0f54efa301379f003a4fc35643ad6815e2faf3aa
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056414"
---
# <a name="overriding-a-dynamic-accessor"></a>動的アクセサーのオーバーライド

など、動的なアクセサーを使用すると`CDynamicAccessor`のコマンドは、`Open`メソッドを自動的に開かれた行セットの列情報を基にアクセサーを作成します。 列の連結方法だけを制御する動的なアクセサーをオーバーライドできます。

動的アクセサーをオーバーライドするには、渡す**false**最後のパラメーターとして、`CCommand::Open`メソッド。 これにより、`Open`から自動的にアクセサーを作成します。 呼び出して`GetColumnInfo`を呼び出すと`AddBindEntry`列ごとにバインドします。 次のコードでは、これを行う方法を示します。

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

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)