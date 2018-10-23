---
title: CCustomRowset (CustomRS.H) |Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
- ccustomrowset
- customrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4ee7aed5463054256d6903e485b83ce201a685d2
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807914"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

ウィザードでは、行セット オブジェクトのエントリを生成します。 ここでは、`CCustomRowset` という名前になります。 `CCustomRowset`と呼ばれる OLE DB プロバイダー クラスからクラスを継承`CRowsetImpl`、行セット オブジェクトに必要なすべてのインターフェイスを実装します。 次のコードは継承チェーンの`CRowsetImpl`:  
  
```cpp  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T >>  
```  
  
`CRowsetImpl` では、`IAccessor`と`IColumnsInfo`インターフェイス。 出力フィールドをテーブルにこれらのインターフェイスを使用します。 クラスの実装を提供も`IRowsetIdentity`コンシューマーが 2 つの行が同じかどうかを判断することができます。 `IRowsetInfo`インターフェイスは、行セット オブジェクトのプロパティを実装します。 `IConvertType`インターフェイスは、コンシューマーから要求されたデータ型と、プロバイダーによって使用されるものの間の相違点を解決するのには、プロバイダーを使用します。  
  
`IRowset`インターフェイスが実際にデータの取得を処理します。 コンシューマーは、最初に呼び出されるメソッドを呼び出します`GetNextRows`と呼ばれる、行ハンドルを返す、`HROW`します。 コンシューマーを呼び出して`IRowset::GetData`を`HROW`要求されたデータを取得します。  
  
`CRowsetImpl` いくつかのテンプレート パラメーターを受け取ります。 これらのパラメーターでは、決定方法、`CRowsetImpl`クラスはデータを処理します。 `ArrayType`引数では、行データの格納に使用すると、どのような記憶域メカニズム決定できます。 *RowClass*パラメーターは、どのようなクラスが含まれていますを指定します、`HROW`します。  
  
*RowsetInterface*パラメーターを使用すると、使用しても、`IRowsetLocate`または`IRowsetScroll`インターフェイス。 `IRowsetLocate`と`IRowsetScroll`インターフェイスから継承両方`IRowset`します。 したがって、OLE DB プロバイダー テンプレートは、これらのインターフェイスの特別な処理を提供する必要があります。 これらのインターフェイスのいずれかを使用する場合は、このパラメーターを使用する必要があります。  
  
## <a name="see-also"></a>関連項目  

[プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)