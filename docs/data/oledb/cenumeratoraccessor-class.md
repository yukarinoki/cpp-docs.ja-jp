---
title: CEnumeratorAccessor クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
- CEnumeratorAccessor.m_bIsParent
- ATL::CEnumeratorAccessor::m_bIsParent
- m_bIsParent
- ATL.CEnumeratorAccessor.m_bIsParent
- CEnumeratorAccessor::m_bIsParent
- ATL::CEnumeratorAccessor::m_nType
- CEnumeratorAccessor.m_nType
- CEnumeratorAccessor::m_nType
- ATL.CEnumeratorAccessor.m_nType
- m_nType
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
- m_szName
- ATL::CEnumeratorAccessor::m_szName
- CEnumeratorAccessor.m_szName
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d6275b07cd06c82d2b9531c3b206b81eedef10db
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233426"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor クラス
使用される[CEnumerator](../../data/oledb/cenumerator-class.md)列挙子の行セットからデータにアクセスします。  
  
## <a name="syntax"></a>構文

```cpp
class CEnumeratorAccessor  
```  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="members"></a>メンバー  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_bIsParent](#bisparent)|行が列挙子の場合、列挙子は親の列挙子をかどうかを示す変数。|  
|[m_nType](#ntype)|行がデータ ソースまたは列挙子について説明するかどうかを示す変数。|  
|[m_szDescription](#szdescription)|データ ソースまたは列挙子の説明です。|  
|[m_szName](#szname)|データ ソースまたは列挙子の名前。|  
|[m_szParseName](#szparsename)|渡す文字列[ため](http://msdn.microsoft.com/library/windows/desktop/ms680604)をデータ ソースまたは列挙子のモニカーを取得します。|  
  
## <a name="remarks"></a>Remarks  
 この行セットは、データ ソースと現在の列挙子から見えるの列挙子で構成されます。  
  
## <a name="bisparent"></a> Cenumeratoraccessor::m_bisparent
行が列挙子の場合、列挙子は親の列挙子をかどうかを示す変数。  
  
### <a name="syntax"></a>構文  
  
```cpp
VARIANT_BOOL m_bIsParent;  
  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[isourcesrowset::getsourcesrowset](https://msdn.microsoft.com/library/ms711200.aspx)で、 *OLE DB プログラマーズ リファレンス*詳細についてはします。 

## <a name="ntype"></a> Cenumeratoraccessor::m_ntype
行がデータ ソースまたは列挙子について説明するかどうかを示す変数。  
  
### <a name="syntax"></a>構文  
  
```cpp
USHORT m_nType;  
  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[isourcesrowset::getsourcesrowset](https://msdn.microsoft.com/library/ms711200.aspx)で、 *OLE DB プログラマーズ リファレンス*詳細についてはします。

## <a name="szdescription"></a> Cenumeratoraccessor::m_szdescription
データ ソースまたは列挙子の説明です。  
  
### <a name="syntax"></a>構文  
  
```cpp
WCHAR m_szDescription[129];  
  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[isourcesrowset::getsourcesrowset](https://msdn.microsoft.com/library/ms711200.aspx)で、 *OLE DB プログラマーズ リファレンス*詳細についてはします。

## <a name="szname"></a> Cenumeratoraccessor::m_szname
データ ソースまたは列挙子の名前。  
  
### <a name="syntax"></a>構文  
  
```cpp
WCHAR m_szName[129];  
  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[isourcesrowset::getsourcesrowset](https://msdn.microsoft.com/library/ms711200.aspx)で、 *OLE DB プログラマーズ リファレンス*詳細についてはします。  

## <a name="szparsename"></a> Cenumeratoraccessor::m_szparsename
渡す文字列[ため](http://msdn.microsoft.com/library/windows/desktop/ms680604)をデータ ソースまたは列挙子のモニカーを取得します。  
  
### <a name="syntax"></a>構文  
  
```cpp
WCHAR m_szParseName[129];  
  
```  
  
### <a name="remarks"></a>Remarks  
 参照してください[isourcesrowset::getsourcesrowset](https://msdn.microsoft.com/library/ms711200.aspx)で、 *OLE DB プログラマーズ リファレンス*詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)