---
title: CMyProviderRowset (MyProviderRS.H) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7bfd7c927342790fee3be2b5a7d48bccba3ea168
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmyproviderrowset-myproviderrsh"></a>CMyProviderRowset (MyProviderRS.H)
ウィザードでは、行セット オブジェクトのエントリを生成します。 ここでは、`CMyProviderRowset` という名前になります。 `CMyProviderRowset`クラスと呼ばれる OLE DB プロバイダー クラスから継承`CRowsetImpl`、行セット オブジェクトに必要なすべてのインターフェイスを実装します。 次のコードは、の継承チェーンを示しています`CRowsetImpl`:。  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage>>  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T >>  
```  
  
 `CRowsetImpl` また、使用、`IAccessor`と`IColumnsInfo`インターフェイスです。 出力フィールドをテーブルにこれらのインターフェイスを使用します。 クラスは、の実装も用意されています。 **IRowsetIdentity**、これにより、コンシューマーを 2 つの行が同じ場合を判断します。 `IRowsetInfo`インターフェイスは、行セット オブジェクトのプロパティを実装します。 **IConvertType**インターフェイスは、コンシューマーから要求されたデータ型と、プロバイダーによって使用されるものの違いを解決するのには、プロバイダーを使用します。  
  
 `IRowset`インターフェイスが実際にデータの取得を処理します。 コンシューマーが最初に呼び出されるメソッドを呼び出す`GetNextRows`と呼ばれる、行へのハンドルを返す、 **HROW**です。 コンシューマーは、呼び出し**irowset::getdata**を**HROW**を要求されたデータを取得します。  
  
 `CRowsetImpl` いくつかのテンプレート パラメーターを受け取ります。 これらのパラメーターを使用するかを判断する方法、`CRowsetImpl`クラスはデータを処理します。 `ArrayType`引数では、行データの格納に使用されるどのようなストレージ機構を決定することができます。 **RowClass**パラメーターは、どのようなクラスに含まれるを指定します、 **HROW**です。  
  
 **RowsetInterface**パラメーターを使用すると、使用しても、`IRowsetLocate`または`IRowsetScroll`インターフェイスです。 `IRowsetLocate`と`IRowsetScroll`インターフェイスから継承両方`IRowset`です。 したがって、OLE DB プロバイダー テンプレートは、これらのインターフェイスの特別な処理を提供する必要があります。 これらのインターフェイスのいずれかを使用する場合は、このパラメーターを使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)