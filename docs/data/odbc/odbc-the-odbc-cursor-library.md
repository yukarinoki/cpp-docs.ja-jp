---
description: '詳細情報: ODBC: odbc カーソルライブラリ'
title: 'ODBC: ODBC カーソル ライブラリ'
ms.date: 11/04/2016
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
ms.openlocfilehash: 1b7c05529f771b281e623502a4b8c4358e17db71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160988"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC カーソル ライブラリ

このトピックでは、ODBC カーソルライブラリについて説明し、その使用方法について説明します。 詳細については、次を参照してください。

- [カーソルライブラリとレベル 1 ODBC ドライバー](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [位置指定更新とタイムスタンプ列](#_core_positioned_updates_and_timestamp_columns)

- [カーソルライブラリの使用](#_core_using_the_cursor_library)

ODBC カーソルライブラリは、ODBC ドライバーマネージャーとドライバーの間に存在するダイナミックリンクライブラリ (DLL) です。 ODBC の用語では、ドライバーは、レコードセット内のその位置を追跡するためのカーソルを保持します。 カーソルは、既にスクロールしているレコードセット内の位置 (現在のレコード) をマークします。

## <a name="cursor-library-and-level-1-odbc-drivers"></a><a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a> カーソルライブラリとレベル 1 ODBC ドライバー

ODBC カーソルライブラリでは、次の新しい機能によってレベル1のドライバーが提供されます。

- 前方および後方スクロール。 レベル2のドライバーは、既にスクロール可能であるため、カーソルライブラリを必要としません。

- スナップショットのサポート。 カーソルライブラリは、スナップショットのレコードを格納しているバッファーを管理します。 このバッファーには、プログラムのレコードの削除と編集が反映されますが、他のユーザーの追加、削除、編集は反映されません。 そのため、スナップショットはカーソルライブラリのバッファーとしての現在のものにすぎません。 また、を呼び出すまで、バッファーには独自の追加が反映されません `Requery` 。 ダイナセットは、カーソルライブラリを使用しません。

カーソルライブラリは、ドライバーで通常サポートされていない場合でも、スナップショット (静的カーソル) を提供します。 ドライバーで既に静的カーソルがサポートされている場合は、スナップショットのサポートを取得するためにカーソルライブラリを読み込む必要はありません。 カーソルライブラリを使用する場合は、スナップショットと順方向専用のレコードセットのみを使用できます。 ドライバーがダイナセット (KEYSET_DRIVEN カーソル) をサポートしていて、それらを使用する場合は、カーソルライブラリを使用しないようにする必要があります。 スナップショットとダイナセットの両方を使用する場合は、ドライバーで両方がサポートさ `CDatabase` れていない限り、2つの異なるオブジェクト (2 つの異なる接続) に基づいて作成する必要があります。

## <a name="positioned-updates-and-timestamp-columns"></a><a name="_core_positioned_updates_and_timestamp_columns"></a> 位置指定更新とタイムスタンプ列

> [!NOTE]
> ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

> [!NOTE]
> ODBC ドライバーでがサポートされている場合、MFC が使用 `SQLSetPos` 可能な場合は、このトピックは適用されません。

ほとんどのレベル1のドライバーは、位置指定更新をサポートしていません。 このようなドライバーは、この点でレベル2のドライバーの機能をエミュレートするために、カーソルライブラリに依存しています。 カーソルライブラリは、変更されていないフィールドに対して検索された更新を実行することで、位置指定更新のサポートをエミュレートします。

場合によっては、レコードセットに、変化しないフィールドの1つとして timestamp 列が含まれていることがあります。 Timestamp 列を含むテーブルで MFC レコードセットを使用すると、2つの問題が発生します。

最初の問題は、timestamp 列を含むテーブルの更新可能なスナップショットに関する問題です。 スナップショットがバインドされているテーブルに timestamp 列が含まれている場合は、およびを呼び出した後にを呼び出す必要があり `Requery` `Edit` `Update` ます。 それ以外の場合は、同じレコードを再び編集することはできません。 およびを呼び出すと `Edit` `Update` 、レコードがデータソースに書き込まれ、タイムスタンプ列が更新されます。 を呼び出さない場合 `Requery` 、スナップショット内のレコードのタイムスタンプ値は、データソースの対応するタイムスタンプと一致しなくなります。 レコードを再度更新しようとすると、データソースが一致しないために更新を許可しないことがあります。

2番目の問題は、関数と共に使用してテーブルとの間で時刻と日付の情報を転送するときに、 [CTime](../../atl-mfc-shared/reference/ctime-class.md) クラスの制限事項を考慮して `RFX_Date` います。 オブジェクトを処理すると、 `CTime` データ転送中に余分な中間処理の形式でオーバーヘッドが発生します。 オブジェクトの日付範囲が、 `CTime` 一部のアプリケーションに対して制限されている場合もあります。 関数の新しいバージョンは、オブジェクトでは `RFX_Date` なく、ODBC *TIMESTAMP_STRUCT* パラメーターを受け取り `CTime` ます。 詳細については、「 `RFX_Date` *MFC リファレンス*」の「[マクロおよびグローバル](../../mfc/reference/mfc-macros-and-globals.md)」の「」を参照してください。

## <a name="using-the-cursor-library"></a><a name="_core_using_the_cursor_library"></a> カーソルライブラリの使用

[Cdatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex)または[Cdatabase:: Open](../../mfc/reference/cdatabase-class.md#open)を呼び出すことによってデータソースに接続すると、データソースのカーソルライブラリを使用するかどうかを指定できます。 そのデータソースでスナップショットを作成する場合は、 `CDatabase::useCursorLib` パラメーターでオプションをに指定する `dwOptions` か、 `OpenEx` *bUseCursorLib* パラメーターに true を指定し `Open` ます (既定値は true です)。 ODBC ドライバーでダイナセットがサポートされており、データソースでダイナセットを開く場合は、カーソルライブラリを使用しないでください (ダイナセットに必要なドライバー機能の一部をマスクします)。 その場合は、でを指定したり、の `CDatabase::useCursorLib` `OpenEx` *BUSECURSORLIB* パラメーターに FALSE を指定したりしないで `Open` ください。

## <a name="see-also"></a>関連項目

[ODBC の基礎](../../data/odbc/odbc-basics.md)
