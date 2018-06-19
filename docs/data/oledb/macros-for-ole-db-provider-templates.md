---
title: OLE DB プロバイダー テンプレート用マクロ |Microsoft ドキュメント
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
- OLE DB provider templates, macros
- macros, OLE DB Provider Templates
- Provider Template macros (OLE DB)
- OLE DB Provider Template macros
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ab7611c49f625a36023b4e31bf6aff47ab16f156
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33111742"
---
# <a name="macros-for-ole-db-provider-templates"></a>OLE DB プロバイダー テンプレート用マクロ
OLE DB プロバイダー テンプレートのマクロは、次のカテゴリで機能を提供します。  
  
### <a name="property-set-map-macros"></a>プロパティ セットのマップに関するマクロ  
  
|||  
|-|-|  
|[BEGIN_PROPERTY_SET](../../data/oledb/begin-property-set.md)|プロパティ セットの先頭をマークします。|  
|[BEGIN_PROPERTY_SET_EX](../../data/oledb/begin-property-set-ex.md)|プロパティ セットの先頭をマークします。|  
|[BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)|セットのプロパティの先頭をマークを非表示またはプロバイダーのスコープ外で定義できます。|  
|[CHAIN_PROPERTY_SET](../../data/oledb/chain-property-set.md)|プロパティのグループを一緒にチェーンします。|  
|[END_PROPERTY_SET](../../data/oledb/end-property-set.md)|プロパティ セットの末尾をマークします。|  
|[END_PROPSET_MAP](../../data/oledb/end-propset-map.md)|プロパティ セットのマップの最後をマークします。|  
|[PROPERTY_INFO_ENTRY](../../data/oledb/property-info-entry.md)|既定値に設定されたプロパティの特定のプロパティを設定します。|  
|[PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md)|指定した値に設定されたプロパティの特定のプロパティを設定します。 フラグとオプションを設定することもできます。|  
|[PROPERTY_INFO_ENTRY_VALUE](../../data/oledb/property-info-entry-value.md)|指定した値に設定されたプロパティの特定のプロパティを設定します。|  
  
### <a name="column-map-macros"></a>列マップ マクロ  
  
|||  
|-|-|  
|[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)|プロバイダーの列マップ エントリの先頭をマークします。|  
|[END_PROVIDER_COLUMN_MAP](../../data/oledb/end-provider-column-map.md)|プロバイダーの列マップ エントリの末尾をマークします。|  
|[PROVIDER_COLUMN_ENTRY](../../data/oledb/provider-column-entry.md)|プロバイダーでサポートされている特定の列を表します。|  
|[PROVIDER_COLUMN_ENTRY_GN](../../data/oledb/provider-column-entry-gn.md)|プロバイダーでサポートされている特定の列を表します。 列のサイズ、データ型、有効桁数、小数点以下桁数、およびスキーマ行セット GUID を指定することができます。|  
|[PROVIDER_COLUMN_ENTRY_FIXED](../../data/oledb/provider-column-entry-fixed.md)|プロバイダーでサポートされている特定の列を表します。 列のデータ型を指定することができます。|  
|[PROVIDER_COLUMN_ENTRY_LENGTH](../../data/oledb/provider-column-entry-length.md)|プロバイダーでサポートされている特定の列を表します。 列のサイズを指定することができます。|  
|[PROVIDER_COLUMN_ENTRY_STR](../../data/oledb/provider-column-entry-str.md)|プロバイダーでサポートされている特定の列を表します。 列の型が文字列と見なします。|  
|[PROVIDER_COLUMN_ENTRY_TYPE_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|プロバイダーでサポートされている特定の列を表します。 PROVIDER_COLUMN_ENTRY_LENGTH、かつ、列のデータ型だけのサイズを指定することもできます。|  
|[PROVIDER_COLUMN_ENTRY_WSTR](../../data/oledb/provider-column-entry-wstr.md)|プロバイダーでサポートされている特定の列を表します。 列のデータ型は Unicode 文字の文字列と見なします。|  
  
### <a name="schema-rowset-macros"></a>スキーマ行セットのマクロ  
  
|||  
|-|-|  
|[BEGIN_SCHEMA_MAP](../../data/oledb/begin-schema-map.md)|スキーマ マップの先頭をマークします。|  
|[SCHEMA_ENTRY](../../data/oledb/schema-entry.md)|GUID をクラスに関連付けます。|  
|[END_SCHEMA_MAP](../../data/oledb/end-schema-map.md)|スキーマ マップの最後をマークします。|  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB プロバイダー テンプレート リファレンス](../../data/oledb/ole-db-provider-templates-reference.md)