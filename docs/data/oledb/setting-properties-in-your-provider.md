---
title: プロバイダーでプロパティの設定 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5d43e452d0fffcb4dc6eddcae722f8056dbd39dd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="setting-properties-in-your-provider"></a>プロバイダーでのプロパティの設定
目的のプロパティのプロパティ グループとプロパティ ID が見つかりません。 詳細については、次を参照してください。 [OLE DB プロパティ](https://msdn.microsoft.com/en-us/library/ms722734.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 ウィザードによって生成されたプロバイダーのコードでは、プロパティ グループに対応するプロパティのマップを検索します。 プロパティ グループの名前は、通常、オブジェクトの名前に対応します。 コマンドまたは行セットのコマンドや行セットのプロパティが見つかりませんデータ ソースと初期化プロパティは、データ ソース オブジェクトに含まれています。  
  
 プロパティ マップを追加、 [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)マクロです。 PROPERTY_INFO_ENTRY_EX は 4 つのパラメーターを受け取ります。  
  
-   プロパティに対応するプロパティ ID。 プロパティ名の先頭から最初の 7 文字 (「dbprop _」) を削除する必要があります。 たとえば、追加する**DBPROP_MAXROWS**、渡す`MAXROWS`最初の要素として。 カスタム プロパティの場合は、GUID のフル_ネームを渡す (たとえば、 `DBMYPROP_MYPROPERTY`)。  
  
-   プロパティのバリアント型 (で[OLE DB プロパティ](https://msdn.microsoft.com/en-us/library/ms722734.aspx)で、 *OLE DB プログラマーズ リファレンス*)。 入力、 **vt _ を付けます**型 (など`VT_BOOL`または`VT_I2`) データ型に対応します。  
  
-   プロパティの読み取りと書き込みのありそれが属するグループを示すフラグ。 たとえば、次のコードは、行セットのグループに属している、読み取り/書き込みプロパティを示します。  
  
    ```  
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE  
    ```  
  
-   プロパティのベース値。 これは、場合があります**VARIANT_FALSE**ブール値を入力するか、たとえば、整数型では、0 です。 プロパティが変更されない限り、この値を持ちます。  
  
    > [!NOTE]
    >  一部のプロパティは接続されているか、ブックマークや更新などその他のプロパティにチェーンします。 コンシューマーが 1 つのプロパティを true に設定すると、ときに別のプロパティも設定できます。 OLE DB プロバイダー テンプレートでは、これをサポート メソッドを介して[cutlprops::onpropertychanged](../../data/oledb/cutlprops-onpropertychanged.md)です。  
  
## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Microsoft OLE DB プロバイダーでは無視されますプロパティ  
 Microsoft OLE DB プロバイダーは、次の OLE DB プロパティを無視します。  
  
-   **DBPROP_MAXROWS**読み取り専用プロバイダーに対してのみ機能 (つまり、DBPROP_IRowsetChange および DBPROP_IRowsetUpdate がいる場合は false) です。 それ以外の場合このプロパティがサポートされていません。  
  
-   **DBPROP_MAXPENDINGROWS**は無視されます。 プロバイダーは独自の制限を指定します。  
  
-   **DBPROP_MAXOPENROWS**は無視されます。 プロバイダーは独自の制限を指定します。  
  
-   **DBPROP_CANHOLDROWS**は無視されます。 プロバイダーは独自の制限を指定します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)