---
title: RCustomRowset の継承の変更 |マイクロソフトのドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1a9b6e238d3824451ab0f820917c34c97826ffab
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060391"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset の継承の変更

追加する、`IRowsetLocate`インターフェイスの単純な読み取り専用プロバイダーの例の継承を変更する`RCustomRowset`します。 最初に、`RCustomRowset`継承`CRowsetImpl`します。 継承するように変更する必要がある`CRowsetBaseImpl`します。

これを行うには、新しいクラスを作成`CCustomRowsetImpl`CustomRS.h で。

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CCustomRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

次に、ように CustomRS.h の COM インターフェイス マップを編集します。

```cpp
BEGIN_COM_MAP(CCustomRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

これに指示する COM インターフェイス マップを作成します`CCustomRowsetImpl`を呼び出す`QueryInterface`両方に対して、`IRowset`と`IRowsetLocate`インターフェイス。 その他の行セットの実装のすべてを取得するクラスをマップのリンク、`CCustomRowsetImpl`クラスを`CRowsetBaseImpl`OLE DB テンプレートで定義されているクラスは、map の COM マップをスキャンする OLE DB テンプレートに伝える COM_INTERFACE_ENTRY_CHAIN マクロを使用します。`CRowsetBaseImpl`への応答を`QueryInterface`呼び出します。

最後に、リンク`RAgentRowset`に`CCustomRowsetBaseImpl`を変更して`RAgentRowset`から継承する`CCustomRowsetImpl`、次のようにします。

```cpp
class RAgentRowset : public CCustomRowsetImpl<RAgentRowset, CAgentMan, CCustomCommand>
```

`RAgentRowset` 使用できるように、`IRowsetLocate`行セット クラスの実装の残りの部分を活用しながらインターフェイス。

これは、ときに[コンシューマーに返される列を動的に決定](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)します。

## <a name="see-also"></a>関連項目

[単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)