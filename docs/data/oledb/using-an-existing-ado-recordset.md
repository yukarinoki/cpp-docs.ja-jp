---
title: 既存の ADO レコードセットの使用
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 48f6eb3bac34b37f495b9492e19b4197ed69cca3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209353"
---
# <a name="using-an-existing-ado-recordset"></a>既存の ADO レコードセットの使用

OLE DB のコンシューマーテンプレートと Active Data Objects (ADO) を混在させるには、ADO を使用してレコードセットを開きます (OLE DB コンシューマーテンプレートの行セットに対応します)。 レコードセットがある場合は、次の手順に従って OLE DB 行セットに接続します。

1. `IRowset` および `IAccessor` ポインターの `QueryInterface` を呼び出します。

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *Lpunk*は、ADO レコードセットの `IUnknown` オブジェクトを指します。

1. アクセサーと行セットを適切な OLE DB コンシューマーテンプレートクラスにアタッチします。

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>参照

[アクセサーの使用](../../data/oledb/using-accessors.md)
