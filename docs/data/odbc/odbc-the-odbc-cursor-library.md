---
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
ms.openlocfilehash: 13640dd2a8593057bef708a45dfc8471ba212563
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367181"
---
# <a name="odbc-the-odbc-cursor-library"></a>ODBC: ODBC カーソル ライブラリ

このトピックでは、ODBC カーソル ライブラリについて説明し、その使用方法について説明します。 詳細については、次を参照してください。

- [カーソル ライブラリとレベル 1 ODBC ドライバ](#_core_the_cursor_library_and_level_1_odbc_drivers)

- [位置指定更新とタイムスタンプ列](#_core_positioned_updates_and_timestamp_columns)

- [カーソル ライブラリの使用](#_core_using_the_cursor_library)

ODBC カーソル ライブラリは、ODBC ドライバー マネージャーとドライバーの間に存在するダイナミック リンク ライブラリ (DLL) です。 ODBC 用語では、ドライバーは、レコードセット内の位置を追跡するためにカーソルを保持します。 カーソルは、既にスクロールしたレコードセットの位置(現在のレコード)にマークを付けます。

## <a name="cursor-library-and-level-1-odbc-drivers"></a><a name="_core_the_cursor_library_and_level_1_odbc_drivers"></a>カーソル ライブラリとレベル 1 ODBC ドライバ

ODBC カーソル ライブラリは、レベル 1 のドライバーに次の新しい機能を提供します。

- 前後スクロール。 レベル 2 のドライバーは、既にスクロール可能であるため、カーソル ライブラリは必要ありません。

- スナップショットのサポート。 カーソル ライブラリは、スナップショットのレコードを含むバッファを管理します。 このバッファは、プログラムの削除とレコードへの編集を反映しますが、他のユーザーの追加、削除、編集は反映しません。 したがって、スナップショットはカーソル ライブラリのバッファと同じ現在の状態になります。 また、このバッファは、ユーザーが 呼び出`Requery`すまで、独自の追加を反映しません。 ダイナセットはカーソル ライブラリを使用しません。

カーソル ライブラリは、通常はドライバーでサポートされていない場合でも、スナップショット (静的カーソル) を提供します。 ドライバーが既に静的カーソルをサポートしている場合は、スナップショットのサポートを取得するためにカーソル ライブラリを読み込む必要はありません。 カーソル ライブラリを使用する場合は、スナップショットと転送専用レコードセットのみを使用できます。 ドライバーがダイナセット (KEYSET_DRIVEN カーソル) をサポートしており、それらを使用する場合は、カーソル ライブラリを使用しないでください。 スナップショットとダイナセットの両方を使用する場合は、ドライバーが両方をサポートしていない`CDatabase`限り、2 つの異なるオブジェクト (2 つの異なる接続) に基づいて作成する必要があります。

## <a name="positioned-updates-and-timestamp-columns"></a><a name="_core_positioned_updates_and_timestamp_columns"></a>位置指定更新とタイムスタンプ列

> [!NOTE]
> ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

> [!NOTE]
> ODBC ドライバが`SQLSetPos`をサポートしている場合、MFC が使用する場合は、このトピックはユーザーに適用されません。

ほとんどのレベル 1 ドライバーは、位置指定更新プログラムをサポートしていません。 このようなドライバーは、この点でレベル 2 ドライバーの機能をエミュレートするカーソル ライブラリに依存します。 カーソル ライブラリは、不変のフィールドで検索された更新を実行することにより、位置指定更新サポートをエミュレートします。

場合によっては、レコードセットに、変更されていないフィールドの 1 つとしてタイムスタンプ列が含まれている場合があります。 タイムスタンプ列を含むテーブルで MFC レコードセットを使用する場合は、2 つの問題が発生します。

最初の問題は、タイムスタンプ列を持つテーブルの更新可能なスナップショットに関するものです。 スナップショットのバインド先のテーブルに timestamp 列が含まれている場合は、`Requery`を呼`Edit`び`Update`出した後に呼び出す必要があります。 この設定を行わない場合は、同じレコードを再度編集できない可能性があります。 を呼び`Edit`出すと`Update`、レコードがデータ ソースに書き込まれ、タイムスタンプ列が更新されます。 を呼び出`Requery`さない場合、スナップショットのレコードのタイムスタンプ値がデータ ソースの対応するタイムスタンプと一致しなくなります。 レコードを再度更新しようとすると、データ ソースが不一致のために更新を許可しない場合があります。

2 番目の問題は、時刻と日付の情報を`RFX_Date`テーブルとの間で転送する関数で使用する場合、クラス[CTime](../../atl-mfc-shared/reference/ctime-class.md)の制限に関するものです。 オブジェクトの`CTime`処理は、データ転送中に余分な中間処理の形でいくらかのオーバーヘッドを課します。 オブジェクトの日付範囲`CTime`は、一部のアプリケーションでは制限されすぎる場合もあります。 関数の新しいバージョン`RFX_Date`は、オブジェクトではなく ODBC *TIMESTAMP_STRUCT* `CTime`パラメーターを受け取ります。 詳細については、「MFC`RFX_Date`リファレンス」の[「マクロとグローバル」](../../mfc/reference/mfc-macros-and-globals.md)を*参照してください*。

## <a name="using-the-cursor-library"></a><a name="_core_using_the_cursor_library"></a>カーソル ライブラリの使用

[CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex)または[CDatabase::Open](../../mfc/reference/cdatabase-class.md#open)を呼び出してデータ ソースに接続する場合は、データ ソースにカーソル ライブラリを使用するかどうかを指定できます。 そのデータ ソースでスナップショットを作成する場合`CDatabase::useCursorLib`は、`dwOptions`パラメーターにオプションを`OpenEx`指定するか *、bUseCursorLib*パラメーターに TRUE`Open`を指定します (既定値は TRUE)。 ODBC ドライバがダイナセットをサポートしており、データ ソースでダイナセットを開きたい場合は、カーソル ライブラリを使用しないでください (ダイナセットに必要なドライバ機能の一部をマスクします)。 その場合は、`CDatabase::useCursorLib`で`OpenEx` *bUseCursorLib*パラメーターに FALSE を指定`Open`したり、FALSE を指定したりしないでください。

## <a name="see-also"></a>関連項目

[ODBC の基本](../../data/odbc/odbc-basics.md)
