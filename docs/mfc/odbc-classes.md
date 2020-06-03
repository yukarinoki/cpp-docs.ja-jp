---
title: ODBC クラス
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
ms.openlocfilehash: a4cfa0d7afa197de7b65b6a0bd6b881a09534ef6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447699"
---
# <a name="odbc-classes"></a>ODBC クラス

これらのクラスは、他のアプリケーションフレームワーククラスと連携して、Open Database Connectivity (ODBC) ドライバーが使用可能なさまざまなデータベースに簡単にアクセスできるようにします。

ODBC データベースを使用するプログラムには、少なくとも `CDatabase` オブジェクトと `CRecordset` オブジェクトが必要です。

[CDatabase](../mfc/reference/cdatabase-class.md)<br/>
データソースへの接続をカプセル化します。これにより、データソースを操作できます。

[CRecordset](../mfc/reference/crecordset-class.md)<br/>
データソースから選択された一連のレコードをカプセル化します。 レコードのスクロール、レコードの更新 (レコードの追加、編集、削除)、フィルターによる選択範囲の限定、選択範囲の並べ替え、実行時に取得または計算された情報を使用した選択のパラメーター化を行うことができます。

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
レコードセットオブジェクトに直接接続されたフォームビューを提供します。 ダイアログデータエクスチェンジ (DDX) メカニズムは、レコードセットとレコードビューのコントロールとの間でデータを交換します。 すべてのフォームビューと同様に、レコードビューはダイアログテンプレートリソースに基づいています。 レコードビューでは、レコードビューを閉じるときに、レコードからレコードセットへの移動、レコードの更新、関連付けられたレコードセットの終了もサポートされます。

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
データアクセス処理の失敗に起因する例外。 このクラスは、クラスライブラリの例外処理機構における他の例外クラスと同じ目的を果たします。

[CFieldExchange](../mfc/reference/cfieldexchange-class.md)<br/>
レコードフィールドエクスチェンジ (RFX) をサポートするためのコンテキスト情報を提供します。 RFX は、レコードセットオブジェクトのフィールドデータメンバーとパラメーターデータメンバーと、データソースの対応するテーブル列との間でデータを交換します。 ダイアログデータエクスチェンジ (DDX) と同様に使用される[CDataExchange](../mfc/reference/cdataexchange-class.md)クラスに似ています。

## <a name="related-classes"></a>関連クラス

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
ビットマップなどのバイナリラージオブジェクト (BLOB) のストレージへのハンドルをカプセル化します。 `CLongBinary` オブジェクトは、データベーステーブルに格納されている大規模なデータオブジェクトを管理するために使用されます。

[CDBVariant](../mfc/reference/cdbvariant-class.md)<br/>
値のデータ型を気にせずに値を格納できます。 `CDBVariant` は、共用体に格納されている現在の値のデータ型を追跡します。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
