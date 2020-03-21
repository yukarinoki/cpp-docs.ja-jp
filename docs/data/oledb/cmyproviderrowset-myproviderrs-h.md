---
title: CCustomRowset (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyproviderrowset
- ccustomrowset
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
ms.openlocfilehash: 8e90db287bc7ac8994914766045eb210446dfd48
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079780"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

このウィザードでは、行セットオブジェクトのエントリが生成されます。 この場合、`CCustomRowset`と呼ばれます。 `CCustomRowset` クラスは、行セットオブジェクトに必要なすべてのインターフェイスを実装する `CRowsetImpl`という OLE DB プロバイダークラスから継承されます。 次のコードは、`CRowsetImpl`の継承チェーンを示しています。

```cpp
template <class T, class Storage, class CreatorClass,
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` は、`IAccessor` インターフェイスと `IColumnsInfo` インターフェイスも使用します。 テーブルの出力フィールドには、これらのインターフェイスを使用します。 また、クラスは `IRowsetIdentity`の実装も提供します。これにより、2つの行が同じかどうかをコンシューマーが判断できるようになります。 `IRowsetInfo` インターフェイスは、行セットオブジェクトのプロパティを実装します。 `IConvertType` インターフェイスを使用すると、コンシューマーによって要求されたデータ型とプロバイダーによって使用されるデータ型の違いをプロバイダーが解決できます。

`IRowset` インターフェイスは実際にデータの取得を処理します。 コンシューマーはまず、`GetNextRows` という名前のメソッドを呼び出し、`HROW`と呼ばれる行へのハンドルを返します。 コンシューマーは、その `HROW` で `IRowset::GetData` を呼び出して、要求されたデータを取得します。

`CRowsetImpl` には、いくつかのテンプレートパラメーターも必要です。 これらのパラメーターを使用すると、`CRowsetImpl` クラスがどのようにデータを処理するかを決定できます。 `ArrayType` 引数を使用すると、行データの格納に使用されるストレージメカニズムを決定できます。 *Rowclass*パラメーターは、`HROW`を含むクラスを指定します。

*RowsetInterface*パラメーターを使用すると、`IRowsetLocate` または `IRowsetScroll` インターフェイスを使用することもできます。 `IRowsetLocate` インターフェイスと `IRowsetScroll` インターフェイスはどちらも `IRowset`から継承されます。 したがって、OLE DB プロバイダーテンプレートでは、これらのインターフェイスに特別な処理を行う必要があります。 これらのインターフェイスのいずれかを使用する場合は、このパラメーターを使用する必要があります。

## <a name="see-also"></a>参照

[プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)<br/>
