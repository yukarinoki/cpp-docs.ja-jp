---
title: CComCritSecLock クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b6eb7a8e6df16134573b55a7c9666befe4e4a1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358887"
---
# <a name="ccomcritseclock-class"></a>CComCritSecLock クラス
このクラスは、ロックおよびロック解除、クリティカル セクション オブジェクトのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>パラメーター  
 *TLock*  
 ロックおよびロック解除するオブジェクト。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|コンストラクターです。|  
|[CComCritSecLock:: ~ CComCritSecLock](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|クリティカル セクション オブジェクトをロックするには、このメソッドを呼び出します。|  
|[CComCritSecLock::Unlock](#unlock)|クリティカル セクション オブジェクトのロックを解除するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスを使用してロックおよびでより安全な方法でオブジェクトをロック解除、 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)または[CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="ctor"></a>  CComCritSecLock::CComCritSecLock  
 コンストラクターです。  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>パラメーター  
 *cs*  
 クリティカル セクション オブジェクト。  
  
 `bInitialLock`  
 最初のロックの状態: **true**がロックされていることを意味します。  
  
### <a name="remarks"></a>コメント  
 クリティカル セクション オブジェクトを初期化します。  
  
##  <a name="dtor"></a>  CComCritSecLock:: ~ CComCritSecLock  
 デストラクターです。  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>コメント  
 クリティカル セクション オブジェクトのロックを解除します。  
  
##  <a name="lock"></a>  CComCritSecLock::Lock  
 クリティカル セクション オブジェクトをロックするには、このメソッドを呼び出します。  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトは正常にロックされて 場合は S_OK、またはエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトは既にロックされている場合、デバッグ ビルドでアサート エラーが発生します。  
  
##  <a name="unlock"></a>  CComCritSecLock::Unlock  
 クリティカル セクション オブジェクトのロックを解除するには、このメソッドを呼び出します。  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>コメント  
 オブジェクトは、既にロックされているが、デバッグ ビルドでアサート エラーが発生します。  
  
## <a name="see-also"></a>関連項目  
 [CComCriticalSection クラス](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection クラス](../../atl/reference/ccomautocriticalsection-class.md)
