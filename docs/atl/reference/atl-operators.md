---
title: ATL 演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75c9ffb8c918cce70ad1e150dd80cb07ebdd7b34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360937"
---
# <a name="atl-operators"></a>ATL 演算子
このセクションには、ATL グローバル演算子のリファレンス トピックが含まれています。  
  
|演算子|説明|  
|--------------|-----------------|  
|[operator ==](#operator_eq_eq)|比較する 2 つ`CSid`オブジェクトまたは`SID`構造が等しいかどうか。|  
|[operator !=](#operator_neq)|比較する 2 つ`CSid`オブジェクトまたは`SID`非等値の構造体。|  
|[演算子 <](#operator_lt)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より小さい`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[演算子 >](#operator_gt)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より大きい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[operator <=](#operator_lt__eq)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体は、以下に、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
|[operator > =](#operator_gt__eq)|かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造がより大きいか等しい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsecurity.h です。  
  
##  <a name="operator_eq_eq"></a>  operator ==  
 比較`CSid`オブジェクトまたは`SID`等しいかどうか (セキュリティ識別子) 構造体。  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**オブジェクトが等しい場合は**false**両者が等しくない場合。  
  
##  <a name="operator_neq"></a>  operator! =  
 比較`CSid`オブジェクトまたは`SID`非等値の (セキュリティ識別子) 構造体。  
  
```   
bool operator==(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**オブジェクトが等しくない場合**false**が等しい場合は。  
  
##  <a name="operator_lt"></a>  演算子 <  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より小さい`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合のアドレス、`lhs`オブジェクトがのアドレスより小さい、`rhs`オブジェクト、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリのコレクション クラスとの互換性を提供する実装します。  
  
##  <a name="operator_gt"></a>  operator >  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体より大きい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合のアドレス、`lhs`のアドレスより大きい、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリのコレクション クラスとの互換性を提供する実装します。  
  
##  <a name="operator_lt__eq"></a>  operator <=  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造体は、以下に、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合のアドレス、`lhs`以下のアドレスには、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリのコレクション クラスとの互換性を提供する実装します。  
  
##  <a name="operator_gt__eq"></a>  operator > =  
 かどうか、`CSid`オブジェクトまたは`SID`演算子の左側にある構造がより大きいか等しい、`CSid`オブジェクトまたは`SID`(C++ 標準ライブラリの互換性) の右側にある構造体。  
  
```   
bool operator<(const CSid& lhs, const CSid& rhs) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lhs`  
 最初の`CSid`オブジェクトまたは`SID`に比較します。  
  
 `rhs`  
 2 番目`CSid`オブジェクトまたは`SID`に比較します。  
  
### <a name="return-value"></a>戻り値  
 返します**true**場合のアドレス、`lhs`以上のアドレスには、 `rhs`、 **false**それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 この演算子のアドレスに、`CSid`オブジェクトまたは`SID`構造、および C++ 標準ライブラリのコレクション クラスとの互換性を提供する実装します。



