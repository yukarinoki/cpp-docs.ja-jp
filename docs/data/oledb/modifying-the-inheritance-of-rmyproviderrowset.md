---
description: '詳細情報: RCustomRowset の継承の変更'
title: RCustomRowset の継承の変更
ms.date: 10/26/2018
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
ms.openlocfilehash: c54533122083c526ad12ac6514efa3ad9ba47cf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287009"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset の継承の変更

`IRowsetLocate`単純な読み取り専用プロバイダーの例にインターフェイスを追加するには、の継承を変更し `CCustomRowset` ます。 最初は、 `CCustomRowset` から継承 `CRowsetImpl` します。 を継承するように変更する必要があり `CRowsetBaseImpl` ます。

これを行うには、 `CCustomRowsetImpl` *カスタム* の RS. h で新しいクラスを作成します。

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

次のように、 *カスタム* の RS で COM インターフェイスマップを編集します。

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

このコードは、 `CMyRowsetImpl` `QueryInterface` インターフェイスとインターフェイスの両方に対してを呼び出すように指示する COM インターフェイスマップを作成し `IRowset` `IRowsetLocate` ます。 このマップでは、他の行セットクラスのすべての実装を取得するために、 `CMyRowsetImpl` クラスを `CRowsetBaseImpl` OLE DB テンプレートによって定義されているクラスにリンクします。このマップでは、 `CRowsetBaseImpl` 呼び出しに応答して、で COM マップをスキャンするように OLE DB テンプレートに指示する COM_INTERFACE_ENTRY_CHAIN マクロを使用します。 `QueryInterface`

最後に、次のようにをに変更して、を継承するようにリンクし `CCustomRowset` `CMyRowsetBaseImpl` `CCustomRowset` `CMyRowsetImpl` ます。

```cpp
class CCustomRowset : public CMyRowsetImpl<CCustomRowset, CCustomWindowsFile, CCustomCommand>
```

`CCustomRowset` では、 `IRowsetLocate` 行セットクラスの残りの実装を利用しながら、インターフェイスを使用できるようになりました。

この処理が完了すると、 [コンシューマーに返される列を動的に特定](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)できます。

## <a name="see-also"></a>関連項目

[単純な Read-Only プロバイダーの拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
