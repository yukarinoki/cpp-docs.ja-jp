---
title: マクロと OLE DB コンシューマー テンプレート用グローバル関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates, macros
- macros, OLE DB consumer template
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 57f61dd54855a2cf0196c0e269eda92295c818b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33114316"
---
# <a name="macros-and-global-functions-for-ole-db-consumer-templates"></a>OLE DB コンシューマー テンプレート用マクロおよびグローバル関数
OLE DB コンシューマー テンプレートには、次のマクロとグローバル関数が含まれます。  
  
### <a name="global-functions"></a>グローバル関数  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](../../data/oledb/atltraceerrorrecords.md)|エラーが返された場合は、ダンプ デバイスに OLE DB エラー レコード情報をダンプします。|  
  
### <a name="accessor-map-macros"></a>アクセサー マップ マクロ  
  
|||  
|-|-|  
|[BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)|アクセサーのエントリの先頭を示します。|  
|[BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)|アクセサー マップ エントリの開始位置を示します。|  
|[END_ACCESSOR](../../data/oledb/end-accessor.md)|アクセサーのエントリの終了を示します。|  
|[END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)|アクセサー マップ エントリの末尾をマークします。|  
  
### <a name="column-map-macros"></a>列マップ マクロ  
  
|||  
|-|-|  
|[BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)|ユーザー レコード クラス内の列マップ エントリの先頭を示します。|  
|[BLOB_ENTRY](../../data/oledb/blob-entry.md)|バイナリ ラージ オブジェクト (BLOB) をバインドするために使用します。|  
|[BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)|BLOB のデータ列の長さを報告します。|  
|[BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)|長さと BLOB のデータ列のステータスを報告します。|  
|[BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)|BLOB のデータ列のステータスを報告します。|  
|[BLOB_NAME](../../data/oledb/blob-name.md)|列名で、バイナリ ラージ オブジェクトをバインドするために使用します。|  
|[BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)|BLOB のデータ列の長さを報告します。|  
|[BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)|長さと BLOB のデータ列のステータスを報告します。|  
|[BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)|BLOB のデータ列のステータスを報告します。|  
|[BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md)|行セットに対してブックマーク エントリを表します。 ブックマークのエントリは、列のエントリの特別な種類です。|  
|[COLUMN_ENTRY](../../data/oledb/column-entry.md)|データベースの特定の列へのバインドを表します。|  
|[COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)|データベースの特定の列へのバインドを表します。 サポート`type`、*長さ*、*精度*、 `scale`、および*ステータス*パラメーター。|  
|[COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)|データベースの特定の列へのバインドを表します。 では、*長さ*変数。|  
|[COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)|データベースの特定の列へのバインドを表します。 サポート*ステータス*と*長さ*パラメーター。|  
|[COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)|データベースの特定の列へのバインドを表します。 サポート*精度*と`scale`パラメーター。|  
|[COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)|データベースの特定の列へのバインドを表します。 サポート、*長さ*変数、*精度*と`scale`パラメーター。|  
|[COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)|データベースの特定の列へのバインドを表します。 サポート*ステータス*と*長さ*変数、*精度*と`scale`パラメーター。|  
|[COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)|データベースの特定の列へのバインドを表します。 サポート、*ステータス*変数、*精度*と`scale`パラメーター。|  
|[COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)|データベースの特定の列へのバインドを表します。 では、*ステータス*変数。|  
|[COLUMN_ENTRY_TYPE](../../data/oledb/column-entry-type.md)|データベースの特定の列へのバインドを表します。 サポート`type`パラメーター。|  
|[COLUMN_ENTRY_TYPE_SIZE](../../data/oledb/column-entry-type-size.md)|データベースの特定の列へのバインドを表します。 サポート`type`と`size`パラメーター。|  
|[COLUMN_NAME](../../data/oledb/column-name.md)|名前で、データベースの特定の列へのバインドを表します。|  
|[COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)|名前で、データベースの特定の列へのバインドを表します。 データ型、サイズ、有効桁数、小数点以下桁数、列の長さ、および列の状態の仕様をサポートします。|  
|[COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)|名前で、データベースの特定の列へのバインドを表します。 列の長さの仕様をサポートします。|  
|[COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)|名前で、データベースの特定の列へのバインドを表します。 列の長さと状態の仕様をサポートします。|  
|[COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)|名前で、データベースの特定の列へのバインドを表します。 有効桁数と小数点以下桁数の指定をサポートします。|  
|[COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)|名前で、データベースの特定の列へのバインドを表します。 有効桁数、小数点以下桁数、および列の長さの仕様をサポートします。|  
|[COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)|名前で、データベースの特定の列へのバインドを表します。 有効桁数、小数点以下桁数、列の長さ、および列の状態の仕様をサポートします。|  
|[COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)|名前で、データベースの特定の列へのバインドを表します。 有効桁数、小数点以下桁数、および列の状態の仕様をサポートします。|  
|[COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)|名前で、データベースの特定の列へのバインドを表します。 列の状態の仕様をサポートします。|  
|[COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)|名前で、データベースの特定の列へのバインドを表します。 データ型の仕様をサポートします。|  
|[COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)|名前で、データベースの特定の列へのバインドを表します。 データ型、有効桁数、および小数点以下桁数の指定をサポートします。|  
|[COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)|名前で、データベースの特定の列へのバインドを表します。 データ型およびサイズの指定をサポートしています。|  
|[COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)|名前で、データベースの特定の列へのバインドを表します。 データ型と列の状態の仕様をサポートします。|  
|[END_COLUMN_MAP](../../data/oledb/end-column-map.md)|列マップ エントリの末尾をマークします。|  
  
### <a name="command-macros"></a>コマンド マクロ  
  
|||  
|-|-|  
|[DEFINE_COMMAND](../../data/oledb/define-command.md)|使用する場合、行セットの作成に使用されるコマンドを指定、 [CCommand](../../data/oledb/ccommand-class.md)クラスです。 指定したアプリケーションの種類 (ANSI または Unicode) に対応する文字列型のみを受け入れます。 使用することをお勧め[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)の代わりに`DEFINE_COMMAND`です。|  
|[DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md)|使用する場合、行セットの作成に使用されるコマンドを指定、 [CCommand](../../data/oledb/ccommand-class.md)クラスです。 ANSI および Unicode のアプリケーションをサポートしています。|  
  
### <a name="parameter-map-macros"></a>パラメーターのマップ マクロ  
  
|||  
|-|-|  
|[BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)|ユーザー レコード クラスのパラメーターのマップ エントリの先頭を示します。|  
|[END_PARAM_MAP](../../data/oledb/end-param-map.md)|パラメーターのマップ エントリの末尾をマークします。|  
|[SET_PARAM_TYPE](../../data/oledb/set-param-type.md)|指定`COLUMN_ENTRY`マクロに続く、`SET_PARAM_TYPE`入力、出力、または入力/出力としてマクロです。|  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)