---
description: 詳細については、「既存の ADO レコードセットの使用」を参照してください。
title: 既存の ADO レコードセットの使用
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 4b5c3b5f621f3cbdba6f2d42fd95436495a5661e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160949"
---
# <a name="using-an-existing-ado-recordset"></a>既存の ADO レコードセットの使用

OLE DB のコンシューマーテンプレートと Active Data Objects (ADO) を混在させるには、ADO を使用してレコードセットを開きます (OLE DB コンシューマーテンプレートの行セットに対応します)。 レコードセットがある場合は、次の手順に従って OLE DB 行セットに接続します。

1. `QueryInterface`ポインターとポインターに対してを呼び出し `IRowset` `IAccessor` ます。

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *Lpunk* `IUnknown` は、ADO レコードセットのオブジェクトを指します。

1. アクセサーと行セットを適切な OLE DB コンシューマーテンプレートクラスにアタッチします。

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>関連項目

[アクセサーの使用](../../data/oledb/using-accessors.md)
