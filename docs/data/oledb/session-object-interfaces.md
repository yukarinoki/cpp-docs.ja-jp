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
ms.openlocfilehash: 8208a372989fac5fa7c7b0c13b83eb27a4d1444b
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42572871"
---
# <a name="session-object-interfaces"></a>セッション オブジェクト インターフェイス
次の表では、セッション オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。  
  
|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|  
|---------------|---------------|--------------------------------------|  
|[IGetDataSource](/previous-versions/windows/desktop/ms709721\(v=vs.85\))|必須|[はい]|  
|[IOpenRowset](/previous-versions/windows/desktop/ms716946\(v=vs.85\))|必須|[はい]|  
|[ISessionProperties](/previous-versions/windows/desktop/ms713721\(v=vs.85\))|必須|[はい]|  
|[IAlterIndex](/previous-versions/windows/desktop/ms714943\(v=vs.85\))|Optional|いいえ|  
|[IAlterTable](/previous-versions/windows/desktop/ms719764\(v=vs.85\))|Optional|いいえ|  
|[IBindResource](/previous-versions/windows/desktop/ms714936\(v=vs.85\))|Optional|いいえ|  
|[ICreateRow](/previous-versions/windows/desktop/ms716832\(v=vs.85\))|Optional|いいえ|  
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625\(v=vs.85\))|Optional|[はい]|  
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686\(v=vs.85\))|Optional|[はい]|  
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593\(v=vs.85\))|Optional|いいえ|  
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816\(v=vs.85\))|Optional|[はい]|  
|[ITableCreation](/previous-versions/windows/desktop/ms713639\(v=vs.85\))|Optional|いいえ|  
|[ITableDefinition](/previous-versions/windows/desktop/ms714277\(v=vs.85\))|Optional|いいえ|  
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947\(v=vs.85\))|Optional|いいえ|  
|[ITransaction](/previous-versions/windows/desktop/ms723053\(v=vs.85\))|Optional|いいえ|  
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071\(v=vs.85\))|Optional|いいえ|  
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893\(v=vs.85\))|Optional|いいえ|  
|[ITransactionObject](/previous-versions/windows/desktop/ms713659\(v=vs.85\))|Optional|いいえ|  
  
 セッション オブジェクトは、行セット オブジェクトを作成します。 プロバイダーは、コマンドをサポートする場合、セッションもコマンド オブジェクトが作成されます (`CCommand`、OLE DB を実装する`TCommand`)。 コマンド オブジェクトを実装して、`ICommand`インターフェイスと使用、`ICommand::Execute`メソッドを次の図に示すように、行セットに対してコマンドを実行します。  
  
 ![プロバイダー コンセプチュアル ダイアグラム](../../data/oledb/media/vc4u551.gif "vc4u551")  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)