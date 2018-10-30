---
title: セッション オブジェクト インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: cf6f84791e0330c09f61ee612069564781086cc4
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216345"
---
# <a name="session-object-interfaces"></a>セッション オブジェクト インターフェイス

次の表では、セッション オブジェクトの OLE DB で定義されている必須および省略可能なインターフェイスを示します。

|Interface|必須?|OLE DB テンプレートによって実装されるでしょうか。|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721)|必須|はい|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946)|必須|はい|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721)|必須|はい|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943)|Optional|いいえ|
|[IAlterTable](/previous-versions/windows/desktop/ms719764)|Optional|いいえ|
|[IBindResource](/previous-versions/windows/desktop/ms714936)|Optional|いいえ|
|[ICreateRow](/previous-versions/windows/desktop/ms716832)|Optional|いいえ|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625)|Optional|はい|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686)|Optional|はい|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593)|Optional|いいえ|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816)|Optional|はい|
|[ITableCreation](/previous-versions/windows/desktop/ms713639)|Optional|いいえ|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277)|Optional|いいえ|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947)|Optional|いいえ|
|[ITransaction](/previous-versions/windows/desktop/ms723053)|Optional|いいえ|
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071)|Optional|いいえ|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893)|Optional|いいえ|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659)|Optional|いいえ|

セッション オブジェクトは、行セット オブジェクトを作成します。 プロバイダーは、コマンドをサポートする場合、セッションもコマンド オブジェクトが作成されます (`CCommand`、OLE DB を実装する`TCommand`)。 コマンド オブジェクトを実装して、`ICommand`インターフェイスと使用、`ICommand::Execute`メソッドを次の図に示すように、行セットに対してコマンドを実行します。

![プロバイダー コンセプチュアル ダイアグラム](../../data/oledb/media/vc4u551.gif "vc4u551")

## <a name="see-also"></a>関連項目

[OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
