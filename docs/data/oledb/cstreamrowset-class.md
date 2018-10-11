---
title: CStreamRowset クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
- CStreamRowset::CStreamRowset
- CStreamRowset.CStreamRowset
- ATL.CStreamRowset.CStreamRowset
- ATL::CStreamRowset::CStreamRowset
- CStreamRowset
- CStreamRowset<TAccessor>::CStreamRowset
- ATL::CStreamRowset<TAccessor>::CStreamRowset
- CStreamRowset<TAccessor>.Close
- ATL.CStreamRowset<TAccessor>.Close
- CStreamRowset::Close
- CStreamRowset<TAccessor>::Close
- ATL::CStreamRowset::Close
- ATL.CStreamRowset.Close
- ATL::CStreamRowset<TAccessor>::Close
- CStreamRowset.Close
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
- CStreamRowset class, constructor
- Close method
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8a541edb478c29fe04619dda319576717a7b9dc6
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081846"
---
# <a name="cstreamrowset-class"></a>CStreamRowset クラス

使用される、`CCommand`または`CTable`宣言します。  
  
## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
### <a name="parameters"></a>パラメーター  

*TAccessor*<br/>
アクセサー クラス。  

## <a name="requirements"></a>要件  

**ヘッダー:** atldbcli.h  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CStreamRowset](#cstreamrowset)|コンストラクターです。 インスタンスを作成し、初期化、`CStreamRowset`オブジェクト。|  
|[閉じる](#close)|リリース、 [ISequentialStream](/previous-versions/windows/desktop/ms718035)クラスのインターフェイス ポインター。|  
  
## <a name="remarks"></a>Remarks  

使用`CStreamRowset`で、`CCommand`または`CTable`例については、宣言。  
  
[!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
または  
  
[!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
`ICommand::Execute` 返します、`ISequentialStream`ポインターに格納されている`m_spStream`します。 使用して、`Read`の XML 形式 (Unicode 文字列) のデータを取得します。 例えば:  
  
[!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
SQL Server 2000 では、XML 書式設定でを実行し、すべての列と 1 つの XML 文字列として行セットのすべての行が返されます。  
  
> [!NOTE]
>  この機能は、SQL Server 2000 でのみ動作します。  
  
## <a name="cstreamrowset"></a> Cstreamrowset::cstreamrowset

インスタンスを作成し、初期化、`CStreamRowset`オブジェクト。  
  
### <a name="syntax"></a>構文  
  
```cpp
CStreamRowset();  
```  

## <a name="close"></a> Cstreamrowset::close

リリース、 [ISequentialStream](/previous-versions/windows/desktop/ms718035)クラスのインターフェイス ポインター。  
  
### <a name="syntax"></a>構文  
  
```cpp
void Close();   
```  
  
## <a name="see-also"></a>関連項目  

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)