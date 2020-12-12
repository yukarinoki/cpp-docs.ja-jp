---
description: 詳細については、「セッションオブジェクトインターフェイス」を参照してください。
title: Session オブジェクト インターフェイス
ms.date: 11/19/2018
helpviewer_keywords:
- session objects [OLE DB]
- session objects [OLE DB], interfaces
- OLE DB provider templates, object interfaces
- interfaces, session object
- interfaces, list of
ms.assetid: ac01a958-6dde-4bd7-8b63-94459e488335
ms.openlocfilehash: dc4f5644258b0ced4c97a5cda6de1b69abb8c2f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286580"
---
# <a name="session-object-interfaces"></a>Session オブジェクト インターフェイス

次の表は、セッションオブジェクトの OLE DB によって定義される必須および省略可能なインターフェイスを示しています。

|インターフェイス|必須|OLE DB テンプレートによって実装されますか?|
|---------------|---------------|--------------------------------------|
|[IGetDataSource](/previous-versions/windows/desktop/ms709721(v=vs.85))|Mandatory|はい|
|[IOpenRowset](/previous-versions/windows/desktop/ms716946(v=vs.85))|Mandatory|はい|
|[ISessionProperties](/previous-versions/windows/desktop/ms713721(v=vs.85))|Mandatory|はい|
|[IAlterIndex](/previous-versions/windows/desktop/ms714943(v=vs.85))|省略可能|×|
|[IAlterTable](/previous-versions/windows/desktop/ms719764(v=vs.85))|省略可能|×|
|[IBindResource](/previous-versions/windows/desktop/ms714936(v=vs.85))|省略可能|×|
|[ICreateRow](/previous-versions/windows/desktop/ms716832(v=vs.85))|省略可能|×|
|[IDBCreateCommand](/previous-versions/windows/desktop/ms711625(v=vs.85))|Optional|はい|
|[IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85))|Optional|はい|
|[IIndexDefinition](/previous-versions/windows/desktop/ms711593(v=vs.85))|省略可能|×|
|[ISupportErrorInfo](/previous-versions/windows/desktop/ms715816(v=vs.85))|Optional|はい|
|[ITableCreation](/previous-versions/windows/desktop/ms713639(v=vs.85))|省略可能|×|
|[ITableDefinition](/previous-versions/windows/desktop/ms714277(v=vs.85))|省略可能|×|
|[ITableDefinitionWithConstraints](/previous-versions/windows/desktop/ms720947(v=vs.85))|省略可能|×|
|[ITransaction](/previous-versions/windows/desktop/ms723053(v=vs.85))|省略可能|×|
|[ITransactionJoin](/previous-versions/windows/desktop/ms718071(v=vs.85))|省略可能|×|
|[ITransactionLocal](/previous-versions/windows/desktop/ms714893(v=vs.85))|省略可能|×|
|[ITransactionObject](/previous-versions/windows/desktop/ms713659(v=vs.85))|省略可能|×|

セッションオブジェクトは、行セットオブジェクトを作成します。 プロバイダーがコマンドをサポートしている場合は、セッションによってコマンドオブジェクト (OLE DB を実装する) も作成され `CCommand` `TCommand` ます。 Command オブジェクトはインターフェイスを実装 `ICommand` し、メソッドを使用して、次の `ICommand::Execute` 図に示すように、行セットに対してコマンドを実行します。

![プロバイダー コンセプチュアル ダイアグラム](../../data/oledb/media/vc4u551.gif "プロバイダー コンセプチュアル ダイアグラム")

## <a name="see-also"></a>関連項目

[OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
