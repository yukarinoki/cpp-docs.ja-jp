---
title: ダイナセット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, dynasets
- ODBC cursor library [ODBC], dynasets
- keyset-driven cursors in dynasets
- cursors [ODBC], keyset-driven cursors in dynasets
- cursor library [ODBC], dynaset availability
- recordsets [C++], dynasets
- dynasets
ms.assetid: 2867e6be-208e-4fe7-8bbe-b8697cb1045c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ec71b5b00b26564f9c8dc3c2d98f53f8182b0ca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092319"
---
# <a name="dynaset"></a>ダイナセット
このトピックは、ダイナセットを使う場合を説明し、説明、[可用性](#_core_availability_of_dynasets)です。  
  
> [!NOTE]
>  このトピックの対象を含む、MFC ODBC クラス[CRecordset](../../mfc/reference/crecordset-class.md)です。 ダイナセットを使う場合、DAO クラスの詳細については、次を参照してください。 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)です。 DAO では、ダイナセット タイプのレコード セットを開くことができます。  
  
 ダイナセットは、動的なプロパティを含むレコード セットです。 その有効期間中にダイナセット モード (ダイナセットと通常呼ばれる) のレコード セット オブジェクトでは、次のように、データ ソースとの同期に保たれます。 他のユーザーが編集可能性がありますマルチ ユーザー環境には、ダイナセット内にあるレコードを削除またはまたは、ダイナセットを表すテーブルにレコードを追加します。 アプリケーションを追加したり、削除したレコードのレコードは、ダイナセットに反映されます。 呼び出して、ダイナセットを再構築するまで、他のユーザーがテーブルに追加するレコードをダイナセットに反映されませんが、 **Requery**メンバー関数。 他のユーザーは、レコードを削除、ときに、MFC コードは、レコード セット内の削除をスキップします。 影響を受けるレコードにスクロールするとすぐに、既存のレコードを他のユーザーの編集は、ダイナセットに反映されます。  
  
 同様に、ダイナセットに対して行った編集は、他のユーザーによって使用中でダイナセットを使う場合に反映されます。 追加したレコードは、ダイナセットを使う場合のクエリを再実行するまで、他のユーザーのダイナセットを使う場合に反映されません。 レコードを削除するには、その他のユーザーのレコード セットでは、「削除」設定が使用されます。 同じデータベースに複数の接続がある場合 (複数`CDatabase`オブジェクト)、それらの接続に関連付けられているレコード セットの他のユーザーのレコード セットとして同じステータスになっています。  
  
 ダイナセットを使う場合は、データは、航空券予約システムで、(たとえば) として動的である必要がある場合に最も役に立ちます。  
  
> [!NOTE]
>  ダイナセットを使用するのには、ダイナセットをサポートするデータ ソースの ODBC ドライバーが必要し、ODBC カーソル ライブラリを読み込むことができません必要があります。 詳細については、次を参照してください。[ダイナセット](#_core_availability_of_dynasets)です。  
  
 レコード セットには、ダイナセットを指定するには、渡す**crecordset::dynaset**最初のパラメーターとして、**開く**レコード セット オブジェクトのメンバー関数。  
  
> [!NOTE]
>  ODBC ドライバーの更新可能なダイナセットを使う場合、位置指定の update ステートメントのいずれかをサポートする必要がありますまたは **:: SQLSetPos** ODBC API 関数。 MFC を使用して、両方がサポートされている場合 **:: SQLSetPos**効率を上げるのためです。  
  
##  <a name="_core_availability_of_dynasets"></a> ダイナセットの可用性  
 MFC データベース クラスは、ダイナセットをサポートして、次の要件が満たされた場合。  
  
-   ODBC カーソル ライブラリ DLL はこのデータ ソースの使用ではなければなりません。  
  
     カーソル ライブラリを使用する場合は、ダイナセットのサポートに必要な基になる ODBC ドライバーの一部の機能をマスクします。 ダイナセットを使う場合に使用する (このセクションの残りの部分の説明に従って、ODBC ドライバーは、ダイナセットを使う場合に必要な効果を持ちます) 場合、MFC を作成するときに、カーソル ライブラリを読み込むにはない可能性があります、`CDatabase`オブジェクト。 詳細については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)と[OpenEx](../../mfc/reference/cdatabase-class.md#openex)または[開く](../../mfc/reference/cdatabase-class.md#open)クラスのメンバー関数`CDatabase`です。  
  
     ODBC 用語では、ダイナセットを使う場合とスナップショットと呼ばれるカーソル。 カーソルは、レコード セット内での位置を追跡するために使用されるメカニズムです。  
  
-   データ ソースの ODBC ドライバーでは、キーセット ドリブン カーソルをサポートする必要があります。  
  
     キーセット ドリブン カーソルでは、取得して、一連のキーを格納すること、テーブルからデータを管理します。 キーは、ユーザーが特定のレコードにスクロールすると、現在のデータをテーブルから取得に使用されます。 ドライバーが、このサポートを提供するかどうかを判断するのには、呼び出し、 **:: SQLGetInfo** ODBC API 関数を**SQL_SCROLL_OPTIONS**パラメーター。  
  
     キーセットのサポートのないダイナセットを開こうとすると、表示、`CDBException`リターン コード値を持つ**AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED**です。  
  
-   データ ソースの ODBC ドライバーでは、拡張フェッチをサポートする必要があります。  
  
     拡張フェッチは、SQL クエリの結果のレコードを逆方向にスクロール機能です。 ドライバーがこの機能をサポートしているかどうかを確認するのには、呼び出し、 **:: SQLGetFunctions** ODBC API 関数を**SQL_API_SQLEXTENDEDFETCH**パラメーター。  
  
 更新可能なダイナセットを使う場合 (またはそのさらに言えば、スナップショット) する場合、ODBC ドライバー必要がありますもサポートするか、 **:: SQLSetPos** ODBC API 関数または位置指定更新します。 **:: SQLSetPos**関数により、MFC を SQL ステートメントを送信せずに、データ ソースを更新します。 このサポートが利用可能な場合は、MFC は、SQL を使用して更新を行う方が優先的に使用します。 ドライバーをサポートしているかどうかを判断する **:: SQLSetPos**、呼び出す **:: SQLGetInfo**で、 **SQL_POS_OPERATIONS**パラメーター。  
  
 位置指定更新は、SQL 構文を使用して (フォームの**WHERE CURRENT OF** \<カーソル名 >) をデータ ソースのテーブルの特定の行を識別します。 ドライバーが位置指定更新をサポートしているかどうかを確認するのには、呼び出す **:: SQLGetInfo**で、 **SQL_POSITIONED_STATEMENTS**パラメーター。  
  
 一般に、MFC ダイナセットを使う場合 (ただし、前方スクロール専用レコード セット) には、レベル 2 の API への準拠の ODBC ドライバーが必要です。 データ ソースのドライバーは、レベル 1 の API セットに従ってが、更新可能なと読み取り専用のスナップショットと順方向専用レコード セットでは、ダイナセットは引き続き使用できます。 ただし、レベル 1 のドライバーでは、ダイナセット拡張フェッチをサポートしている場合、キーセット ドリブン カーソルをサポートできます。 ODBC 準拠のレベルの詳細については、次を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)です。  
  
> [!NOTE]
>  スナップショットとダイナセットを使う場合の両方を使用する場合は、する必要があります基づかせる 2 つの異なる`CDatabase`オブジェクト (2 つの異なる接続)。  
  
 ODBC カーソル ライブラリによって維持中級者向けの記憶域を使用するスナップショットとは異なりダイナセットを使う場合、レコードのフェッチ、データ ソースから直接にスクロールするとすぐにします。 これにより、データ ソースと同期されているダイナセットで選択されたレコードが保持されます。  
  
 このバージョンの Visual C に含まれている ODBC ドライバーの一覧、および追加のドライバーを取得する方法についてを参照してください。 [ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)