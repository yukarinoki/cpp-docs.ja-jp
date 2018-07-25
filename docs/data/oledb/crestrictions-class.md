---
title: CRestrictions クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
- CRestrictions.Open
- ATL::CRestrictions::Open
- ATL.CRestrictions.Open
- CRestrictions::Open
dev_langs:
- C++
helpviewer_keywords:
- CRestrictions class
- Open method
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aa95eb630fac2fe30014e378cc79bdbac285dbdb
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233504"
---
# <a name="crestrictions-class"></a>CRestrictions クラス
ジェネリック クラスには、スキーマ行セットの制限を指定することができます。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, short nRestrictions, const GUID* pguid>  
class CRestrictions : 
        public CSchemaRowset <T, nRestrictions>  
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 アクセサーに使用されるクラス。  
  
 *nRestrictions*  
 スキーマ行セットの制限列の数。  
  
 *pguid*  
 スキーマの GUID へのポインター。  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h 
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[開く](#open)|ユーザーが指定した制限に従って、結果セットを返します。|   

## <a name="open"></a> Crestrictions::open
ユーザーが指定した制限に従って、結果セットを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCTSTR lpszParam 1 = NULL,  
   LPCTSTR lpszParam 2 = NULL,  
   LPCTSTR lpszParam 3 = NULL,  
   LPCTSTR lpszParam 4 = NULL,  
   LPCTSTR lpszParam 5 = NULL,  
   LPCTSTR lpszParam 6 = NULL,  
   LPCTSTR lpszParam 7 = NULL,  
   bool bBind = true);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *セッション*  
 [in]データ ソースに接続するため、既存のセッション オブジェクトを指定します。  
  
 *lpszParam*  
 [in]スキーマ行セットに対して制限を指定します。  
  
 *bBind*  
 [in]列マップを自動的にバインドするかどうかを指定します。 既定値は**true**、これにより、列マップが自動的に連結されます。 設定*bBind*に**false**手動でバインドできるように、列マップの自動に連結します。 (手動バインドは、OLAP ユーザーにとって特に重要ですが) です。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の 1 つ。  
  
### <a name="remarks"></a>Remarks  
 スキーマ行セットでは、7 個の制限の最大数を指定できます。  
  
 参照してください[IDBSchemaRowset](https://msdn.microsoft.com/library/ms713686.aspx)定義されている制限については、各スキーマ行セットにします。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)    
 [スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)