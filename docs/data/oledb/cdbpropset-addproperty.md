---
title: Cdbpropset::addproperty |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
dev_langs:
- C++
helpviewer_keywords:
- AddProperty method
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 454d86b7c5b654ac1af5b628abc5db7d3678d2f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cdbpropsetaddproperty"></a>CDBPropSet::AddProperty
プロパティ セットに、プロパティを追加します。  
  
## <a name="syntax"></a>構文  
  
```
bool AddProperty(DWORD dwPropertyID,   
   constVARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   LPCSTR szValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   LPCWSTR szValue,DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   bool bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   BYTE bValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   short nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   long nValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   float fltValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED);bool AddProperty(DWORD dwPropertyID,  
   double dblValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();bool AddProperty(DWORD dwPropertyID,  
   CY cyValue,  DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 *dwPropertyID*  
 [in]追加するプロパティの ID。 初期化するために使用される、 **dwPropertyID**の`DBPROP`構造、プロパティ セットに追加します。  
  
 `var`  
 [in]バリアント型のプロパティの値を初期化するために使用される、`DBPROP`構造、プロパティ セットに追加します。  
  
 `szValue`  
 [in]プロパティの値を初期化するために使用する文字列、`DBPROP`構造、プロパティ セットに追加します。  
  
 `bValue`  
 [in]A**バイト**またはのプロパティの値を初期化するために使用されるブール値、`DBPROP`構造、プロパティ セットに追加します。  
  
 `nValue`  
 [in]プロパティの値を初期化するために使用される整数値、`DBPROP`構造、プロパティ セットに追加します。  
  
 *fltValue*  
 [in]浮動小数点値のプロパティの値を初期化するために使用される、`DBPROP`構造、プロパティ セットに追加します。  
  
 `dblValue`  
 [in]倍精度浮動小数点値のプロパティの値を初期化するために使用される、`DBPROP`構造、プロパティ セットに追加します。  
  
 `cyValue`  
 [in]プロパティの値を初期化するために使用される CY 通貨値、`DBPROP`構造、プロパティ セットに追加します。  
  
## <a name="return-value"></a>戻り値  
 **true**場合は、プロパティが正常に追加します。 それ以外の場合、 **false**です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDBPropSet クラス](../../data/oledb/cdbpropset-class.md)   
 [DBPROP 構造体](https://msdn.microsoft.com/en-us/library/ms717970.aspx)