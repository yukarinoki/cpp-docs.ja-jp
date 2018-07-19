---
title: 'レコード フィールド エクス チェンジ: RFX の使い方 |Microsoft ドキュメント'
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
ms.openlocfilehash: 296ae2e4f535e08924a77b8726b93778a6da5026
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091999"
---
# <a name="record-field-exchange-using-rfx"></a>レコード フィールド エクスチェンジ: RFX の使い方
このトピックでは、フレームワークの動作に関連して RFX を使用するには新機能について説明します。  
  
> [!NOTE]
>  このトピックの対象から派生したクラス[CRecordset](../../mfc/reference/crecordset-class.md)バルク行フェッチは実装されていません。 バルク行フェッチを使用している場合は、バルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されます。 バルク rfx 関数は rfx 関数に似ています。 相違点を理解するのを参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)です。  
  
 次のトピックには、関連する情報が含まれて。  
  
-   [レコード フィールド エクス チェンジ: ウィザード コードの使用](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)RFX の主要なコンポーネントを紹介し、コードについて説明する MFC アプリケーション ウィザードと**クラスの追加**(」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) RFX とウィザード コードを変更する方法をサポートするために記述します。  
  
-   [レコード フィールド エクス チェンジ: RFX 関数の使い方](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)で RFX 関数への書き込み呼び出しの説明、`DoFieldExchange`をオーバーライドします。  
  
 次の表は、役割がどのようなフレームワークの役割を関連を示します。  
  
### <a name="using-rfx-you-and-the-framework"></a>RFX の使用: プログラマとフレームワーク  
  
|プログラマの役割|フレームワークの役割|  
|---------|-------------------|  

|ウィザードを使用して、レコード セット クラスを宣言します。 フィールド データ メンバーの名前とデータ型を指定します |。ウィザードの派生、`CRecordset`クラスおよび書き込みを[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)の上書きをなど、RFX 関数の各フィールド データ メンバーの呼び出しです |。  
|(省略可能)クラスに必要なパラメーターのデータ メンバーを手動で追加します。 RFX 関数呼び出しを手動で追加`DoFieldExchange`各パラメーターのデータ メンバーの呼び出しを追加して[つ](../../mfc/reference/cfieldexchange-class.md#setfieldtype)、パラメーターのグループ内のパラメーターの合計数を指定[m_nParams](../../mfc/reference/crecordset-class.md#m_nparams). 参照してください[レコード セット: レコード セット (ODBC) のパラメーター化](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)| |。  
|(省略可能)手動でフィールド データ メンバーに追加の列をバインドします。 手動でインクリメント[m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)です。 参照してください[レコード セット: データ列 (ODBC) を動的に結びつける](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)| |。  

|レコード セット クラスのオブジェクトを構築します。 オブジェクトを使用する前に値を設定、そのパラメーターのデータ メンバーは、存在する場合です |。効率を高めるため、フレームワークは、ODBC を使用して、パラメーターを prebinds です。 パラメーターの値を渡すと、フレームワークはそれらをデータ ソースに渡します。 並べ替えやフィルター文字列を変更しない限り、クエリのパラメーターの値のみが送信されます |。  
|レコード セット オブジェクトを使用して、開く[:open](../../mfc/reference/crecordset-class.md#open)|。レコード セットのクエリを実行する、呼び出しと、レコード セットのフィールド データ メンバーに列をバインドする`DoFieldExchange`を選択した最初のレコードと、レコード セットのフィールド データ メンバーの間でデータを交換します |。  
|使用して、レコード セット内をスクロール[CRecordset::Move](../../mfc/reference/crecordset-class.md#move)またはメニューまたはツールバーのコマンドです |。呼び出し`DoFieldExchange`フィールド データ メンバーを新しい現在のレコードからデータを転送する |。  
|追加、更新、およびレコードを削除します |。呼び出し`DoFieldExchange`データ ソースにデータを転送する |。  
  
## <a name="see-also"></a>関連項目  
 [レコード フィールド エクス (チェンジ RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [レコード フィールド エクス チェンジ: RFX の動作方法](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [レコード セット: 合計およびその他の集計の結果 (ODBC) を取得します。](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)   
 [マクロ、グローバル関数、およびグローバル変数](../../mfc/reference/mfc-macros-and-globals.md)

