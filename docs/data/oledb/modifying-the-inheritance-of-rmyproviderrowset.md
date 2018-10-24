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
ms.openlocfilehash: a6f4827ecf0571878bc0eeaef5dce74326488c61
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990284"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset の継承の変更

追加する、`IRowsetLocate`インターフェイスの単純な読み取り専用プロバイダーの例の継承を変更する`RCustomRowset`します。 最初に、`RCustomRowset`継承`CRowsetImpl`します。 継承するように変更する必要がある`CRowsetBaseImpl`します。  
  
これを行うには、新しいクラスを作成`CMyRowsetImpl`の*カスタム*RS.h:  
  
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
  
これに指示する COM インターフェイス マップを作成します`CMyRowsetImpl`を呼び出す`QueryInterface`両方に対して、`IRowset`と`IRowsetLocate`インターフェイス。 その他の行セットの実装のすべてを取得するクラスをマップのリンク、`CMyRowsetImpl`クラスを`CRowsetBaseImpl`OLE DB テンプレートで定義されているクラスは、map の COM マップをスキャンする OLE DB テンプレートに伝える COM_INTERFACE_ENTRY_CHAIN マクロを使用します。`CRowsetBaseImpl`への応答を`QueryInterface`呼び出します。  
  
最後に、リンク`RAgentRowset`に`CMyRowsetBaseImpl`を変更して`RAgentRowset`から継承する`CMyRowsetImpl`、次のようにします。  
  
```cpp  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CCustomCommand>  
```  
  
`RAgentRowset` 使用できるように、`IRowsetLocate`行セット クラスの実装の残りの部分を活用しながらインターフェイス。  
  
これは、ときに[コンシューマーに返される列を動的に決定](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)します。  
  
## <a name="see-also"></a>関連項目  

[単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)