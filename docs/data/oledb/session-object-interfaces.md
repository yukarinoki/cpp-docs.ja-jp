---
title: セッション オブジェクト インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 01d08fb35a1e954aad07153f63ad3ed34282570d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337847"
---
# <a name="session-object-interfaces"></a>セッション オブジェクト インターフェイス
次の表では、セッション オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](https://msdn.microsoft.com/library/ms709721.aspx)|必須|[はい]|  
|[IOpenRowset](https://msdn.microsoft.com/library/ms716946.aspx)|必須|[はい]|  
|[ISessionProperties](https://msdn.microsoft.com/library/ms713721.aspx)|必須|[はい]|  
|[IAlterIndex](https://msdn.microsoft.com/library/ms714943.aspx)|Optional|いいえ|  
|[IAlterTable](https://msdn.microsoft.com/library/ms719764.aspx)|Optional|いいえ|  
|[IBindResource](https://msdn.microsoft.com/library/ms714936.aspx)|Optional|いいえ|  
|[ICreateRow](https://msdn.microsoft.com/library/ms716832.aspx)|Optional|いいえ|  
|[IDBCreateCommand](https://msdn.microsoft.com/library/ms711625.aspx)|Optional|[はい]|  
|[IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)|Optional|[はい]|  
|[IIndexDefinition](https://msdn.microsoft.com/library/ms711593.aspx)|Optional|いいえ|  
|[ISupportErrorInfo](https://msdn.microsoft.com/library/ms715816.aspx)|Optional|[はい]|  
|[ITableCreation](https://msdn.microsoft.com/library/ms713639.aspx)|Optional|いいえ|  
|[ITableDefinition](https://msdn.microsoft.com/library/ms714277.aspx)|Optional|いいえ|  
|[ITableDefinitionWithConstraints](https://msdn.microsoft.com/library/ms720947.aspx)|Optional|いいえ|  
|[ITransaction](https://msdn.microsoft.com/library/ms723053.aspx)|Optional|いいえ|  
|[ITransactionJoin](https://msdn.microsoft.com/library/ms718071.aspx)|Optional|いいえ|  
|[ITransactionLocal](https://msdn.microsoft.com/library/ms714893.aspx)|Optional|いいえ|  
|[ITransactionObject](https://msdn.microsoft.com/library/ms713659.aspx)|Optional|いいえ|  
  
 セッション オブジェクトは、行セット オブジェクトを作成します。 プロバイダーは、コマンドをサポートする場合、セッションもコマンド オブジェクトが作成されます (`CCommand`、OLE DB を実装する`TCommand`)。 コマンド オブジェクトを実装して、`ICommand`インターフェイスと使用、`ICommand::Execute`メソッドを次の図に示すように、行セットに対してコマンドを実行します。  
  
 ![プロバイダー コンセプチュアル ダイアグラム](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)