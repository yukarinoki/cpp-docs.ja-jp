---
title: CComSafeArrayBound クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
dev_langs:
- C++
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 455e71cd0ee323df8cfe43001f87179c649eefe5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364054"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound クラス
このクラスは、用のラッパー、 [SAFEARRAYBOUND](http://msdn.microsoft.com/en-us/303a9bdb-71d6-4f14-8747-84cf84936c6d)構造体。  
  
## <a name="syntax"></a>構文  
  
```
class CComSafeArrayBound : public SAFEARRAYBOUND
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CComSafeArrayBound](#ccomsafearraybound)|コンストラクターです。|  
|[GetCount](#getcount)|このメソッドを呼び出して要素の数を返します。|  
|[GetLowerBound](#getlowerbound)|下限の境界を返すには、このメソッドを呼び出します。|  
|[です](#getupperbound)|上限の境界を返すには、このメソッドを呼び出します。|  
|[SetCount](#setcount)|要素の数を設定するには、このメソッドを呼び出します。|  
|[SetLowerBound](#setlowerbound)|下限の境界を設定するには、このメソッドを呼び出します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[演算子 =](#operator_eq)|セット、`CComSafeArrayBound`に新しい値。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、用のラッパー、 **SAFEARRAYBOUND**によって使用される構造[CComSafeArray](../../atl/reference/ccomsafearray-class.md)です。 クエリを実行するための 1 つのディメンションの上限と下限の境界を設定メソッドを提供する`CComSafeArray`オブジェクトとが含まれている要素の数。 多次元`CComSafeArray`オブジェクトの配列を使用して`CComSafeArrayBound`オブジェクト、ディメンションごとに 1 つです。 したがってなどのメソッドを使用[GetCount](#getcount)、このメソッドは多次元配列の要素の合計数を返されませんことに注意してください。  
  
 **ヘッダー:** atlsafe.h  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsafe.h  
  
##  <a name="ccomsafearraybound"></a>  CComSafeArrayBound::CComSafeArrayBound  
 コンストラクターです。  
  
```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ulCount`  
 配列の要素数。  
  
 `lLowerBound`  
 配列の番号を下限値です。  
  
### <a name="remarks"></a>コメント  
 配列は、Visual C プログラムからアクセスすることの場合は、下限を 0 として定義することをお勧めします。 配列が Visual Basic など他の言語で使用する場合は、別の下限値を使用する方がある可能性があります。  
  
##  <a name="getcount"></a>  CComSafeArrayBound::GetCount  
 このメソッドを呼び出して要素の数を返します。  
  
```
ULONG GetCount() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 要素の数を返します。  
  
### <a name="remarks"></a>コメント  
 場合、関連付けられている`CComSafeArray`オブジェクトは、多次元配列を表す、このメソッドは、右端にあるディメンション内の要素の合計数を返しますのみです。 使用して[CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount)要素の合計数を取得します。  
  
##  <a name="getlowerbound"></a>  CComSafeArrayBound::GetLowerBound  
 下限の境界を返すには、このメソッドを呼び出します。  
  
```
LONG GetLowerBound() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 下限値を返します、`CComSafeArrayBound`オブジェクト。  
  
##  <a name="getupperbound"></a>  CComSafeArrayBound::GetUpperBound  
 上限の境界を返すには、このメソッドを呼び出します。  
  
```
LONG GetUpperBound() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 上限値を返します、`CComSafeArrayBound`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 上限の境界は、要素と下限の境界値の数によって異なります。 たとえば、下限は 0 要素の数は 10、上限の境界が 9 に自動的に設定されます。  
  
##  <a name="operator_eq"></a>  CComSafeArrayBound::operator =  
 セット、`CComSafeArrayBound`に新しい値。  
  
```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `bound`  
 `CComSafeArrayBound` オブジェクト。  
  
 `ulCount`  
 要素の数。  
  
### <a name="return-value"></a>戻り値  
 ポインターを返します、`CComSafeArrayBound`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CComSafeArrayBound`オブジェクトは、既存を使用して割り当てることができる`CComSafeArrayBound`、またはを下限の境界の場合は既定で設定を 0 には、要素の数を指定することによってです。  
  
##  <a name="setcount"></a>  CComSafeArrayBound::SetCount  
 要素の数を設定するには、このメソッドを呼び出します。  
  
```
ULONG SetCount(ULONG ulCount) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `ulCount`  
 要素の数。  
  
### <a name="return-value"></a>戻り値  
 内の要素の数を返します、`CComSafeArrayBound`オブジェクト。  
  
##  <a name="setlowerbound"></a>  CComSafeArrayBound::SetLowerBound  
 下限の境界を設定するには、このメソッドを呼び出します。  
  
```
LONG SetLowerBound(LONG lLowerBound) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lLowerBound`  
 下限値です。  
  
### <a name="return-value"></a>戻り値  
 新しい下限を返します、`CComSafeArrayBound`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 配列は、Visual C プログラムからアクセスすることの場合は、下限を 0 として定義することをお勧めします。 配列が Visual Basic など他の言語で使用する場合は、別の下限値を使用する方がある可能性があります。  
  
 上限の境界は、要素と下限の境界値の数によって異なります。 たとえば、下限は 0 要素の数は 10、上限の境界が 9 に自動的に設定されます。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)
