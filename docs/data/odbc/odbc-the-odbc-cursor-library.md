---
title: 'ODBC: ODBC カーソル ライブラリ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cursor library [ODBC]
- snapshots, support in ODBC
- timestamps, ODBC timestamp columns
- ODBC cursor library [ODBC]
- static cursors
- ODBC drivers, Level 1
- ODBC drivers, cursor support
- positioned updates
- cursors, ODBC cursor library
- Level 1 ODBC drivers
- cursor library [ODBC], snapshots
- ODBC, timestamp
- positioning cursors
ms.assetid: 6608db92-82b1-4164-bb08-78153c227be3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e57251263738d534b7e7e22ff287607fbc5159a5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092595"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC カーソル ライブラリ
このトピックでは、ODBC カーソル ライブラリについて説明し、その使用方法について説明します。 詳細については次を参照してください:  
  
-   [カーソル ライブラリ、レベル 1 の ODBC ドライバー](#_core_the_cursor_library_and_level_1_odbc_drivers)  
  
-   [位置指定更新とタイムスタンプ列](#_core_positioned_updates_and_timestamp_columns)  
  
-   [カーソル ライブラリを使用します。](#_core_using_the_cursor_library)  
  
 ODBC カーソル ライブラリは、ODBC ドライバー マネージャーとドライバーの間にあるダイナミック リンク ライブラリ (DLL) です。 Odbc では、ドライバーは、レコード セットの位置を追跡するためのカーソルを保持します。 カーソルがスクロール既にレコード セット内の位置をマーク: 現在のレコードです。  
  
##  <a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> カーソル ライブラリ、レベル 1 の ODBC ドライバー  
 ODBC カーソル ライブラリは、次の新機能をレベル 1 のドライバーには。  
  
-   前方と後方スクロールします。 レベル 2 のドライバーでは、スクロール可能なそれらが存在するので、カーソル ライブラリは必要ありません。  
  
-   スナップショットのサポート。 カーソル ライブラリでは、スナップショットのレコードを格納するバッファーを管理します。 このバッファーには、プログラムの削除や変更レコードがない、追加、削除、または他のユーザーの編集が反映されます。 したがって、スナップショットは、カーソル ライブラリのバッファーで最新でのみです。 バッファーもが反映されない独自の追加機能が呼び出されるまで**Requery**です。 ダイナセットを使う場合は、カーソル ライブラリを使用できません。  
  
 カーソル ライブラリを使用するスナップショット (静的カーソル)、ドライバーによって通常どおりサポートされていない場合でもです。 ドライバーは、既に静的カーソルをサポートする場合は、スナップショットのサポートを受けるカーソル ライブラリを読み込む必要はありません。 カーソル ライブラリを使用する場合は、スナップショットおよび前方スクロール専用レコードのみを使用できます。 場合は、ドライバーは、ダイナセットを使う場合 (KEYSET_DRIVEN カーソル) をサポートし、それらを使用する場合、カーソル ライブラリを使用しないでください。 スナップショットとダイナセットを使う場合の両方を使用する場合は、する必要があります基づかせる 2 つの異なる`CDatabase`オブジェクト (2 つの異なる接続) をドライバーは、両方をサポートしない限り、します。  
  
##  <a name="_core_positioned_updates_and_timestamp_columns"></a> 位置指定更新とタイムスタンプ列  
  
> [!NOTE]
>  ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。  
  
> [!NOTE]
>  ODBC ドライバーがサポートする場合は**SQLSetPos**、使用可能な場合、どの MFC が使用して、このトピックは、するには適用されません。  
  
 レベル 1 のほとんどのドライバーは、位置指定更新をサポートしていません。 このようなドライバーは、この点でレベル 2 のドライバーの機能をエミュレートするために、カーソル ライブラリに依存します。 カーソル ライブラリは、変化しないフィールドの検索の更新の手順を実行して、位置指定更新のサポートをエミュレートします。  
  
 場合によっては、レコード セットは変化しないフィールドの 1 つとして、timestamp 列を含む可能性があります。 Timestamp 列を含むテーブルを持つ MFC レコード セットでは、2 つの問題が発生します。  
  
 最初の問題では、タイムスタンプ列を持つテーブルで更新可能なスナップショットに関するものです。 呼び出す必要がありますが、スナップショットがバインドされているテーブルに timestamp 列が含まれている場合**Requery**を呼び出した後**編集**と**更新**です。 ない場合は、もう一度同じレコードを編集することができません。 呼び出すと**編集**し**更新**レコードがデータ ソースに書き込まれ、タイムスタンプ列が更新される、します。 呼び出さない場合**Requery**スナップショット内のレコードのタイムスタンプ値と一致していませんデータ ソースに対応するタイムスタンプ。 レコードを再度更新しようとすると、データ ソースは不一致のため、更新プログラムを禁止可能性があります。  
  
 2 つ目の問題は、クラスの制限事項[CTime](../../atl-mfc-shared/reference/ctime-class.md)と共に使用すると、`RFX_Date`にまたはテーブルから、日付と時刻の情報を転送する関数。 処理、`CTime`オブジェクトのオーバーヘッドはいくつかのデータ転送中に余分な中間処理の形式でします。 日付の範囲`CTime`オブジェクト可能性がありますも小さすぎる一部のアプリケーションです。 新しいバージョンの`RFX_Date`関数には、ODBC **TIMESTAMP_STRUCT**パラメーターの代わりに、`CTime`オブジェクト。 詳細については、次を参照してください。`RFX_Date`で[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)で、 *『 MFC リファレンス*です。  

  
##  <a name="_core_using_the_cursor_library"></a> カーソル ライブラリを使用します。  
 データ ソースに接続する場合: を呼び出して[cdatabase::openex](../../mfc/reference/cdatabase-class.md#openex)または[cdatabase::open](../../mfc/reference/cdatabase-class.md#open) — データ ソースで、カーソル ライブラリを使用するかどうかを指定できます。 そのデータ ソースでのスナップショットを作成する場合は、指定、**読み込む**オプション、`dwOptions`パラメーターを`OpenEx`指定または**TRUE**の**データ**パラメーターを**開く**(既定値は**TRUE**)。 ODBC ドライバーは、ダイナセットをサポートしている場合を開くには、データ ソースでダイナセットを使う場合は、(ダイナセットを使う場合に必要ないくつかのドライバーの機能を使用)、カーソル ライブラリを使わないでください。 その場合は、指定しない**読み込む**で`OpenEx`かを指定**FALSE**の**データ**パラメーター **を開く**.  
  
## <a name="see-also"></a>関連項目  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)