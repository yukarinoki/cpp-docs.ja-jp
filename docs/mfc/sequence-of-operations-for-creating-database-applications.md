---
title: データベース アプリケーションの作成操作のシーケンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cbe18e9733388cc6e43f6ca3de520596c713b783
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381330"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>データベース アプリケーションの作成手順
次の表は、データベース アプリケーションの作成で、役割と、フレームワークの役割を示します。  
  
> [!NOTE]
>  Visual C 環境とウィザードは、(ただし、DAO クラスが含まれると、引き続き使用することができます) DAO をサポートしています。 Microsoft では、新しい MFC プロジェクトでは、ODBC を使用することをお勧めします。 DAO は、既存のアプリケーションを保守でのみ使用する必要があります。  
  
### <a name="creating-database-applications"></a>データベース アプリケーションの作成  
  
|タスク|そうですよね|フレームワークを動作します。|  
|----------|------------|------------------------|  
|MFC ODBC と DAO クラスを使用するかどうかを決定します。|新しい MFC プロジェクトでは、ODBC を使用します。 DAO は、既存のアプリケーションを維持するために使用します。 一般情報は、記事を参照してください。[データ アクセス プログラミング](../data/data-access-programming-mfc-atl.md)です。|データベースへのアクセスをサポートするクラスを提供します。|  
|Database オプションと、スケルトン アプリケーションを作成します。|MFC アプリケーション ウィザードを実行します。 データベース サポート ページのオプションを選択します。 レコード ビューを作成するオプションを選択する場合もを指定します。<br /><br /> データ ソースとテーブル名または名前<br />-名前または名前をクエリします。|MFC アプリケーション ウィザードでは、ファイルを作成し、必要なを指定します。 指定するオプションに応じて、ファイルはレコード セット クラスを含めることができます。|  
|データベースのフォームまたはフォームをデザインします。|Visual C ダイアログ エディターを使用してレコード ビュー クラスのダイアログ テンプレート リソースにコントロールを配置します。|MFC アプリケーション ウィザードでは、入力するための空のダイアログ テンプレート リソースを作成します。|  
|必要に応じて、追加のレコード ビューとレコード セット クラスを作成します。|クラス ビューを使用すると、デザイン、ビューのエディター、クラスと、ダイアログ ボックスを作成できます。|クラス ビューでは、新しいクラスの追加のファイルを作成します。|  
|必要に応じて、コードでは、レコード セット オブジェクトを作成します。 レコードを操作するのにには、各レコード セットを使用してください.|レコード セットから派生したクラスに基づく[CRecordset](../mfc/reference/crecordset-class.md)ウィザードを使用します。|ODBC では、レコード フィールド エクス (チェンジ RFX) を使用して、データベースとレコード セットのフィールド データ メンバーの間でデータを交換します。 レコード ビューを使用しているダイアログ データ エクス (チェンジ DDX) は、レコード セットと、レコード ビュー上のコントロールの間でデータを交換します。|  
|.. または、明示的な作成[CDatabase](../mfc/reference/cdatabase-class.md)開きたいデータベースごとに、コードでします。|データベース オブジェクトを基に、レコード セット オブジェクト。|データベース オブジェクトでは、データ ソースへのインターフェイスを提供します。|  
|レコード セットのデータ列を動的にバインドします。|ODBC では、バインドを管理するレコード セットの派生クラスにコードを追加します。 記事を参照して[レコード セット: データ列を動的に結びつける (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)です。||  
  
## <a name="see-also"></a>関連項目  
 [フレームワークでのビルド](../mfc/building-on-the-framework.md)   
 [MFC アプリケーションの作成操作のシーケンス](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE アプリケーションの作成操作のシーケンス](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [ActiveX コントロールの作成手順](../mfc/sequence-of-operations-for-creating-activex-controls.md)
