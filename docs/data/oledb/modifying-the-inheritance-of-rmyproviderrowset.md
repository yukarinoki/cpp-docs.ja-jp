---
title: RMyProviderRowset の継承を変更する |Microsoft ドキュメント
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
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75acbc8370c1ea164c72aa6f0c61a95fe287e3d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="modifying-the-inheritance-of-rmyproviderrowset"></a>RMyProviderRowset の継承の変更
追加する、`IRowsetLocate`インターフェイスに単純な読み取り専用プロバイダーの例では、継承を変更する**RMyProviderRowset**です。 最初に、 **RMyProviderRowset**から継承`CRowsetImpl`です。 継承するように変更する必要があります**CRowsetBaseImpl**です。  
  
 これを行うには、新しいクラスを作成する`CMyRowsetImpl`、myproviderrs.h:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>  
{  
...  
};  
```  
  
 ここで、myproviderrs.h に次のように COM インターフェイス マップを編集します。  
  
```  
BEGIN_COM_MAP(CMyRowsetImpl)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 これは、通知する COM インターフェイス マップを作成します。`CMyRowsetImpl`を呼び出す**QueryInterface**両方に対して、`IRowset`と`IRowsetLocate`インターフェイスです。 すべての他の行セットの実装を取得するクラス、マップ リンク、`CMyRowsetImpl`クラスにバックアップ、 **CRowsetBaseImpl**クラスは、OLE DB テンプレートで定義されている以外の場合は、マップでは、これによりは COM_INTERFACE_ENTRY_CHAIN マクロCOM をスキャンする OLE DB テンプレートをマップ**CRowsetBaseImpl**への応答、`QueryInterface`呼び出します。  
  
 最後に、リンク`RAgentRowset`に`CMyRowsetBaseImpl`を変更して`RAgentRowset`から継承する`CMyRowsetImpl`、次のようにします。  
  
```  
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CMyProviderCommand>  
```  
  
 `RAgentRowset` 使用できるように、`IRowsetLocate`行セット クラスの実装の残りの部分の利点を活かしながらインターフェイスです。  
  
 これを行うときに実行できます[コンシューマーに返される列を動的に決定](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)です。  
  
## <a name="see-also"></a>関連項目  
 [単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)