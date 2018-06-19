---
title: クラスの持つ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: facf4abc01ed55ec7c6d84755530a776c68e166d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362739"
---
# <a name="cfiletimespan-class"></a>持つクラス
このクラスは、相対的な日付と時刻の値がファイルへの関連付けを管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CFileTimeSpan
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|期間を取得するには、このメソッドを呼び出して、`CFileTimeSpan`オブジェクト。|  
|[CFileTimeSpan::SetTimeSpan](#settimespan)|時間の範囲を設定するには、このメソッドを呼び出して、`CFileTimeSpan`オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CFileTimeSpan::operator-](#operator_-)|減算を実行、`CFileTimeSpan`オブジェクト。|  
|[CFileTimeSpan::operator! =](#operator_neq)|2 つの `CFileTimeSpan` オブジェクトが等しくないかどうかを比較します。|  
|[CFileTimeSpan::operator +](#operator_add)|加算を実行する、`CFileTimeSpan`オブジェクト。|  
|[CFileTimeSpan::operator + =](#operator_add_eq)|加算を実行する、`CFileTimeSpan`オブジェクトし、現在のオブジェクトに、結果を代入します。|  
|[CFileTimeSpan::operator &lt;](#operator_lt)|比較する 2 つ`CFileTimeSpan`小さい方を決定するオブジェクト。|  
|[CFileTimeSpan::operator &lt;=](#operator_lt_eq)|比較する 2 つ`CFileTimeSpan`オブジェクトが等しいかどうか、または小さい方を決定します。|  
|[CFileTimeSpan::operator =](#operator_eq)|代入演算子です。|  
|[CFileTimeSpan::operator =](#operator_-_eq)|減算を実行、`CFileTimeSpan`オブジェクトし、現在のオブジェクトに、結果を代入します。|  
|[CFileTimeSpan::operator = =](#operator_eq_eq)|2 つの `CFileTimeSpan` オブジェクトが等しいかどうかを比較します。|  
|[CFileTimeSpan::operator &gt;](#operator_gt)|比較する 2 つ`CFileTimeSpan`大きい方を決定するオブジェクト。|  
|[CFileTimeSpan::operator &gt;=](#operator_gt_eq)|比較する 2 つ`CFileTimeSpan`オブジェクトが等しいかどうか、または大きい方を決定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、相対的な期間を管理するためのメソッドを提供時に関する操作を実行するときに多くの場合、発生時のファイルが作成された、最後にアクセスまたは最後に変更されました。 このクラスのメソッドはと共に頻繁に使用される[加算クラス](../../atl-mfc-shared/reference/cfiletime-class.md)オブジェクト。  
  
## <a name="example"></a>例  
 例を参照して[CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltime.h  
  
##  <a name="cfiletimespan"></a>  CFileTimeSpan::CFileTimeSpan  
 コンストラクターです。  
  
```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 既存の `CFileTimeSpan` オブジェクト。  
  
 `nSpan`  
 ミリ秒単位の時間の期間。  
  
### <a name="remarks"></a>コメント  
 `CFileTimeSpan`既存を使用してオブジェクトを作成できる`CFileTimeSpan`オブジェクト、または 64 ビット値として表されます。 既定のコンス トラクターは、時間間隔を 0 に設定します。  
  
##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan  
 期間を取得するには、このメソッドを呼び出して、`CFileTimeSpan`オブジェクト。  
  
```
LONGLONG GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 時間間隔をミリ秒単位で返します。  
  
##  <a name="operator_-"></a>  CFileTimeSpan::operator-  
 減算を実行、**持つ**オブジェクト。  
  
```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します、 `CFileTimeSpan` 2 つの期間の違いの結果を表すオブジェクト。  
  
##  <a name="operator_neq"></a>  CFileTimeSpan::operator! =  
 2 つの `CFileTimeSpan` オブジェクトが等しくないかどうかを比較します。  
  
```
bool operator!=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**比較対象のアイテムと等しくない場合、`CFileTimeSpan`オブジェクト。 それ以外の場合**false**です。  
  
##  <a name="operator_add"></a>  CFileTimeSpan::operator +  
 加算を実行する、`CFileTimeSpan`オブジェクト。  
  
```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します、`CFileTimeSpan`にまたがるの合計を 2 つの時刻を含むオブジェクトします。  
  
##  <a name="operator_add_eq"></a>  CFileTimeSpan::operator + =  
 加算を実行する、`CFileTimeSpan`オブジェクトし、結果、現在のオブジェクトに代入します。  
  
```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CFileTimeSpan`にまたがるの合計を 2 つの時刻を含むオブジェクトします。  
  
##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;  
 比較する 2 つ`CFileTimeSpan`小さい方を決定するオブジェクト。  
  
```
bool operator<(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**最初のオブジェクトが小さい場合 (つまりより短い期間を表します)、2 番目よりそれ以外の場合**false**です。  
  
##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=  
 比較する 2 つ`CFileTimeSpan`オブジェクトが等しいかどうか、または小さい方を決定します。  
  
```
bool operator<=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**最初のオブジェクトより小さい場合 (つまりより短い期間を表す) か、またはそれ以外の場合、2 番目に等しい**false**です。  
  
##  <a name="operator_eq"></a>  CFileTimeSpan::operator =  
 代入演算子です。  
  
```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CFileTimeSpan`オブジェクト。  
  
##  <a name="operator_-_eq"></a>  CFileTimeSpan::operator =  
 減算を実行、`CFileTimeSpan`オブジェクトし、結果、現在のオブジェクトに代入します。  
  
```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 更新されたを返します`CFileTimeSpan`オブジェクト。  
  
##  <a name="operator_eq_eq"></a>  CFileTimeSpan::operator = =  
 2 つの `CFileTimeSpan` オブジェクトが等しいかどうかを比較します。  
  
```
bool operator==(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true** 、オブジェクトが等しい場合、それ以外の場合**false**です。  
  
##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;  
 比較する 2 つ`CFileTimeSpan`大きい方を決定するオブジェクト。  
  
```
bool operator>(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**最初のオブジェクトがより大きい場合 (つまりより長い期間を表します)、2 番目よりそれ以外の場合**false**です。  
  
##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=  
 比較する 2 つ`CFileTimeSpan`オブジェクトが等しいかどうか、または大きい方を決定します。  
  
```
bool operator>=(CFileTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `span`  
 比較される `CFileTimeSpan` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 返します**true**最初のオブジェクトがより大きい場合 (つまりより長い期間を表す) か、またはそれ以外の場合、2 番目に等しい**false**です。  
  
##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan  
 時間の範囲を設定するには、このメソッドを呼び出して、`CFileTimeSpan`オブジェクト。  
  
```
void SetTimeSpan(LONGLONG nSpan) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nSpan`  
 ミリ秒単位の時間の長さの新しい値。  
  
## <a name="see-also"></a>関連項目  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [加算クラス](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)


