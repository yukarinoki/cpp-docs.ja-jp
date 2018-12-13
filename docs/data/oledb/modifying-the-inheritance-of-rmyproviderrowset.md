---
title: RCustomRowset の継承の変更
ms.date: 10/26/2018
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
ms.openlocfilehash: 34eb07611ebfff09918d62273d4ca4a8c9cf4f7b
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265153"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset の継承の変更

追加する、`IRowsetLocate`インターフェイスの単純な読み取り専用プロバイダーの例の継承を変更する`CCustomRowset`します。 最初に、`CCustomRowset`継承`CRowsetImpl`します。 継承するように変更する必要がある`CRowsetBaseImpl`します。

これを行うには、新しいクラスを作成`CCustomRowsetImpl`の*カスタム*RS.h:

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

これで、COM インターフェイス マップを編集*カスタム*RS.h するようになります。

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

このコードに指示する COM インターフェイス マップを作成します`CMyRowsetImpl`を呼び出す`QueryInterface`両方に対して、`IRowset`と`IRowsetLocate`インターフェイス。 その他の行セットの実装のすべてを取得するクラスをマップのリンク、`CMyRowsetImpl`クラスを`CRowsetBaseImpl`OLE DB テンプレートで定義されているクラスは、map の COM マップをスキャンする OLE DB テンプレートに伝える COM_INTERFACE_ENTRY_CHAIN マクロを使用します。`CRowsetBaseImpl`への応答を`QueryInterface`呼び出します。

最後に、リンク`CCustomRowset`に`CMyRowsetBaseImpl`を変更して`CCustomRowset`から継承する`CMyRowsetImpl`、次のようにします。

```cpp
class CCustomRowset : public CMyRowsetImpl<CCustomRowset, CCustomWindowsFile, CCustomCommand>
```

`CCustomRowset` 使用できるように、`IRowsetLocate`行セット クラスの実装の残りの部分を活用しながらインターフェイス。

これは、ときに[コンシューマーに返される列を動的に決定](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)します。

## <a name="see-also"></a>関連項目

[単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
