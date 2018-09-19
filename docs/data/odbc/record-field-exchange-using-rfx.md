---
title: 'レコード フィールド エクス チェンジ: RFX の使い方 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2c3fdededa6e107e15a8c0999d65ba4e0c5cf47f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083042"
---
# <a name="record-field-exchange-using-rfx"></a>レコード フィールド エクスチェンジ: RFX の使い方

このトピックでは、RFX の使い方とは、フレームワークには、何について説明します。  
  
> [!NOTE]
>  このトピックの対象から派生したクラス[CRecordset](../../mfc/reference/crecordset-class.md)バルク行フェッチは実装されていません。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されます。 バルク rfx 関数は、rfx 関数に似ています。 相違点を理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
次のトピックでは、関連情報を含めます。  
  
- [レコード フィールド エクス チェンジ: ウィザード コードの使用](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)RFX の主要なコンポーネントを紹介し、コードについて説明する MFC アプリケーション ウィザードと**クラスの追加**(」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) と、ウィザードのコードを変更する方法をサポートするために記述します。  
  
- [レコード フィールド エクス チェンジ: RFX 関数の使い方](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)で RFX 関数への書き込み呼び出しについて説明します、`DoFieldExchange`をオーバーライドします。  
  
次の表では、関連するは、フレームワーク、ロールを示します。  
  
### <a name="using-rfx-you-and-the-framework"></a>RFX の使い方と、フレームワーク  
  
|プログラマの役割|フレームワークの役割|  
|---------|-------------------|  

|ウィザードを使用して、レコード セット クラスを宣言します。 フィールド データ メンバーの名前とデータ型を指定します |。ウィザードの派生を`CRecordset`クラスと書き込みを[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)をオーバーライドするなど、RFX 関数の各フィールド データ メンバーの呼び出し |。  
|(省略可能)クラスに必要なパラメーターのデータ メンバーを手動で追加します。 RFX 関数の呼び出しを手動で追加`DoFieldExchange`、各パラメーターのデータ メンバーへの呼び出しを追加[つ](../../mfc/reference/cfieldexchange-class.md#setfieldtype)、パラメーターのグループのパラメーターの合計数を指定し、 [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams). 参照してください[レコード セット: レコード セット (ODBC) をパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)| |。  
|(省略可能)手動で追加の列をフィールド データ メンバーにバインドします。 手動でインクリメント[m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)します。 参照してください[レコード セット: データ列 (ODBC) を動的に結びつける](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)| |。  

|レコード セット クラスのオブジェクトを構築します。 オブジェクトを使用する前に値を設定、そのパラメーターのデータ メンバーは、存在する場合 |。効率を高めるため、フレームワークは、ODBC を使用して、パラメーターを prebinds します。 パラメーターの値を渡すと、フレームワークはそれらをデータ ソースに渡します。 並べ替えやフィルター文字列を変更しない限り、クエリのパラメーターの値のみが送信されます |。  
|使用してレコード セット オブジェクトを開く[:open](../../mfc/reference/crecordset-class.md#open)|。レコード セットのクエリを実行する、レコード セットと呼び出しのフィールド データ メンバーへの列をバインド`DoFieldExchange`を選択した最初のレコードとレコード セットのフィールド データ メンバーの間でデータを交換します |。  
|使用して、レコード セット内をスクロール[CRecordset::Move](../../mfc/reference/crecordset-class.md#move)またはメニューまたはツールバーのコマンドです |。呼び出し`DoFieldExchange`フィールド データ メンバーを新しい現在のレコードからデータを転送します |。  
|追加、更新、およびレコードを削除します |。呼び出し`DoFieldExchange`データ ソースにデータを転送する |。  
  
## <a name="see-also"></a>関連項目  

[レコード フィールド エクスチェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[レコードセット: 集計値の計算 (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[CRecordset クラス](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)<br/>
[マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)

