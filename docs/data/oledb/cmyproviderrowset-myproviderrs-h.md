---
description: 詳細については、CCustomRowset (CustomRS .H) に関するページを参照してください。
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
ms.openlocfilehash: 87025be2a34f8c850bde2be53ab01519968654d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170465"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

このウィザードでは、行セットオブジェクトのエントリが生成されます。 この場合は、と呼ばれ `CCustomRowset` ます。 `CCustomRowset`クラスは `CRowsetImpl` 、行セットオブジェクトに必要なすべてのインターフェイスを実装するという OLE DB プロバイダークラスから継承されます。 次のコードは、の継承チェーンを示してい `CRowsetImpl` ます。

```cpp
template <class T, class Storage, class CreatorClass,
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` また、は `IAccessor` インターフェイスとインターフェイスも使用し `IColumnsInfo` ます。 テーブルの出力フィールドには、これらのインターフェイスを使用します。 クラスは、の実装も提供します `IRowsetIdentity` 。これにより、コンシューマーは2つの行が同じかどうかを判断できます。 インターフェイスは、 `IRowsetInfo` 行セットオブジェクトのプロパティを実装します。 インターフェイスを使用 `IConvertType` すると、プロバイダーによって要求されたデータ型とプロバイダーによって使用されるデータ型の違いを解決できます。

`IRowset`インターフェイスは実際にデータの取得を処理します。 コンシューマーは、まずと呼ばれるメソッドを呼び出し `GetNextRows` て、と呼ばれる行へのハンドルを返し `HROW` ます。 コンシューマーは、そのを使用してを呼び出し、 `IRowset::GetData` `HROW` 要求されたデータを取得します。

`CRowsetImpl` には、いくつかのテンプレートパラメーターもあります。 これらのパラメーターを使用すると、クラスがどのようにデータを処理するかを決定でき `CRowsetImpl` ます。 引数を使用する `ArrayType` と、行データを格納するために使用されるストレージメカニズムを決定できます。 *Rowclass* パラメーターは、を含むクラスを指定し `HROW` ます。

*RowsetInterface* パラメーターを使用すると、 `IRowsetLocate` インターフェイスまたはインターフェイスを使用することもでき `IRowsetScroll` ます。 `IRowsetLocate`インターフェイスと `IRowsetScroll` インターフェイスは、どちらもから継承され `IRowset` ます。 したがって、OLE DB プロバイダーテンプレートでは、これらのインターフェイスに特別な処理を行う必要があります。 これらのインターフェイスのいずれかを使用する場合は、このパラメーターを使用する必要があります。

## <a name="see-also"></a>関連項目

[プロバイダー Wizard-Generated ファイル](../../data/oledb/provider-wizard-generated-files.md)<br/>
